# E-Commerce Backend Setup Instructions

This guide will walk you through setting up the NestJS E-Commerce backend project from scratch.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher)
- **PNPM** (v8 or higher)
- **Database** (PostgreSQL recommended)
- **Git** (for version control)

## Step 1: Clone the Repository

```bash
# Clone the repository
git clone <your-repository-url>

# Navigate to project directory
cd nestJS_ecommerce
```

## Step 2: Install Dependencies

```bash
# Install all dependencies
pnpm install
```

## Step 3: Database Setup

1. **Install PostgreSQL** if you haven't already.

2. **Create a new database** for the project:
   ```sql
   CREATE DATABASE nestjs_ecommerce;
   ```

3. **Setup Prisma**:
   ```bash
   # Initialize Prisma
   pnpm prisma init
   ```

4. **Configure Database Connection**:
   
   Update your `.env` file with your database connection string:
   ```
   DATABASE_URL="postgresql://username:password@localhost:5432/nestjs_ecommerce?schema=public"
   ```

## Step 4: Environment Configuration

Create a `.env` file in the root directory with the following variables:

```
# Application
PORT=3000
NODE_ENV=development

# Database
DATABASE_URL="postgresql://username:password@localhost:5432/nestjs_ecommerce?schema=public"

# JWT Authentication
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRATION=1d

# Google OAuth (if using)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:3000/auth/google/callback
```

## Step 5: Prisma Schema Setup

1. **Update the Prisma schema** in `prisma/schema.prisma` with your data models:

```prisma
model User {
  id          String   @id @default(uuid())
  email       String   @unique
  password    String
  name        String?
  role        Role     @default(USER)
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
  
  // Relations
  orders      Order[]
  cart        Cart?
  // ... other relations
}

model Product {
  id          String   @id @default(uuid())
  name        String
  description String?
  price       Float
  stock       Int
  // ... other fields
  
  // Relations
  category    Category @relation(fields: [categoryId], references: [id])
  categoryId  String
  // ... other relations
}

// Add other models based on the schema design in your documentation
```

2. **Generate Prisma Client**:
```bash
pnpm prisma generate
```

3. **Run Migration**:
```bash
pnpm prisma migrate dev --name init
```

## Step 6: GraphQL Setup

The GraphQL setup should be already configured in the app.module.ts file. Verify that you have the following configuration:

```typescript
// In app.module.ts
GraphQLModule.forRoot<ApolloDriverConfig>({
  driver: ApolloDriver,
  autoSchemaFile: join(process.cwd(), 'src/schema.gql'),
  sortSchema: true,
  playground: true,
}),
```

## Step 7: Start the Development Server

```bash
# Run in development mode with hot-reload
pnpm run start:dev
```

The server will start on `http://localhost:3000` (or the port you specified in the .env file).
GraphQL playground will be available at `http://localhost:3000/graphql`.

## Step 8: Test the API

You can test your GraphQL API using the GraphQL Playground at `http://localhost:3000/graphql`. 

Try the hello query to verify everything is working:

```graphql
query {
  hello {
    message
  }
}
```

## Troubleshooting

### Common Issues:

1. **Database Connection Error**: 
   - Verify that your PostgreSQL service is running
   - Check that the connection string in `.env` is correct

2. **Prisma Migration Errors**:
   - If you encounter issues with migrations, try resetting the database:
     ```bash
     pnpm prisma migrate reset
     ```

3. **Port Conflicts**:
   - If port 3000 is already in use, change the PORT in your .env file

## Next Steps

Now that your environment is set up, you can start implementing the features outlined in the [e-commerce-backend-plan.md](./e-commerce-backend-plan.md) document, starting with:

1. User authentication
2. Product management
3. Shopping cart functionality
4. Order processing

Happy coding! 
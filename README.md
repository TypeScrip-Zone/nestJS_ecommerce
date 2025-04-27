# NestJS E-Commerce Backend

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg" alt="Donate us"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow" alt="Follow us on Twitter"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description

A modern e-commerce backend API built with NestJS, GraphQL, Apollo Server, and Prisma. This project provides a complete solution for building and managing an e-commerce platform with features including user authentication, product management, shopping cart, order processing, and more.

## Features

- **User Management** - Registration, authentication, profile management
- **Product Catalog** - Categories, products, variants, search and filtering
- **Shopping Experience** - Cart management, wishlist functionality 
- **Order Processing** - Checkout flow, payment integration, order management
- **GraphQL API** - Modern API with Apollo Server

## Documentation

- [E-Commerce Backend Plan](./Docs/e-commerce-backend-plan.md) - Detailed project roadmap
- [Setup Instructions](./Docs/setup-instructions.md) - Step-by-step setup guide

## Project Setup

For detailed setup instructions, please refer to our [Setup Guide](./Docs/setup-instructions.md).

Quick start:

```bash
# Install dependencies
$ pnpm install

# Start development server
$ pnpm run start:dev
```

## Technology Stack

- **NestJS** - Progressive Node.js framework
- **GraphQL with Apollo** - API query language and runtime
- **Prisma** - Next-generation ORM
- **TypeScript** - Typed JavaScript
- **JWT & Passport** - Authentication
- **Jest** - Testing framework

## Development Scripts

```bash
# development
$ pnpm run start

# watch mode
$ pnpm run start:dev

# production mode
$ pnpm run start:prod

# unit tests
$ pnpm run test

# e2e tests
$ pnpm run test:e2e

# test coverage
$ pnpm run test:cov
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Deployment

When you're ready to deploy your NestJS application to production, there are some key steps you can take to ensure it runs as efficiently as possible. Check out the [deployment documentation](https://docs.nestjs.com/deployment) for more information.

## Resources

Check out a few resources that may come in handy when working with NestJS:

- Visit the [NestJS Documentation](https://docs.nestjs.com) to learn more about the framework.
- For questions and support, please visit the [Discord channel](https://discord.gg/G7Qnnhy).

## License

This project is [MIT licensed](LICENSE).

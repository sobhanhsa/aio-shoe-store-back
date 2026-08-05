# AIO Shoe Store — Backend API

![TypeScript](https://img.shields.io/badge/TypeScript-%233178C6.svg?logo=typescript&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E.svg?logo=nestjs&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D.svg?logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248.svg?logo=mongodb&logoColor=white)

Main goal of building this project and related [front project](https://github.com/sobhanhsa/](https://github.com/sobhanhsa/aio-shoe-store) was for attending to AIO cup.
A production-oriented backend API for an e-commerce shoe store built with NestJS and MongoDB — focused on clean architecture, secure authentication, and developer ergonomics.

---

## Key features

- Designed for fast onboarding: well-structured NestJS modules (controllers, services, schemas) that are easy to read and extend.
- Secure authentication: JWT + Passport strategies for stateless, production-ready auth flows.
- Robust data modeling: Mongoose schemas with validation to keep product and user data consistent.
- Developer-focused DX: TypeScript-first codebase, linting, formatting, and test scripts to keep quality high.
- Testable and automatable: Jest + Supertest-powered test configuration and clear npm scripts for CI use.

## Tech stack

- Languages: TypeScript (primary), JavaScript
- Frameworks & libs: NestJS, Mongoose, Passport, Passport-JWT, RxJS
- Testing: Jest, Supertest
- Tooling: ESLint, Prettier, ts-node, ts-jest
- Runtime: Node.js
- Database: MongoDB

## Architecture / How it works (high-level)

- The application follows NestJS opinionated architecture: feature modules contain controllers (HTTP layer), services (business logic), and Mongoose schemas (persistence).
- Authentication is handled via Passport strategies: local (where used) and JWT for issuing and validating tokens.
- Configuration values (database URI, secrets, ports) are provided through environment variables and loaded via @nestjs/config.
- Requests are validated at the DTO layer and persisted through Mongoose models; services are thin and focused for easier unit testing.

## Installation & setup

Requirements

- Node.js (18+) and npm
- MongoDB instance (local, cloud atlas, or Docker)

Quick start

1. Clone the repo

```bash
git clone https://github.com/sobhanhsa/aio-shoe-store-back.git
cd aio-shoe-store-back
```

2. Install dependencies

```bash
npm install
```

3. Create a `.env` file in the project root with the minimum required values:

```env
MONGO_URI=mongodb://localhost:27017/aio-shoe-store
JWT_SECRET=your_jwt_secret_here
PORT=3000
```

4. Run in development mode (auto-reloads on change)

```bash
npm run start:dev
```

5. Build & run production

```bash
npm run build
npm run start:prod
```

6. Run tests

```bash
# Unit / integration tests
npm test

# End-to-end tests (if available)
npm run test:e2e
```

Notes

- If you use MongoDB Atlas, set `MONGO_URI` to the connection string and ensure IP/network access is permitted.
- Adjust `JWT_SECRET` to a strong, unique value and store it securely in CI or a secrets manager in production.

## What I learned / challenges solved

- Built a production-oriented NestJS backend with clear module separation and TypeScript-first development.
- Implemented stateless authentication using Passport + JWT and handled token lifecycle and validation securely.
- Modeled application data using Mongoose schemas and learned how to balance schema validation with application-level checks.
- Improved developer experience through scripts, linting, and test configuration — reduced cognitive load for future contributors.
- Dealt with async flows and error propagation in NestJS, improving reliability and logging points for easier debugging.

These experiences demonstrate practical knowledge in building backend systems you can operate and iterate on in real-world projects.

## Future improvements

- Add a Dockerfile and docker-compose for local development and reproducible environments.
- Add CI pipeline (GitHub Actions) that runs linting, tests, and builds on each PR.
- Implement role-based access control and finer-grained permissions for admin/customer flows.
- Add caching (Redis) and request rate-limiting to improve performance and resiliency.
- Expand test coverage with targeted unit tests and contract tests for the API surface.
- Provide OpenAPI (Swagger) documentation for easier API exploration.

## Contact / Links

- GitHub: https://github.com/sobhanhsa
- LinkedIn: https://www.linkedin.com/in/sobhangss
- Email: sobhanhsa1@gmail.com

---

If you'd like, I can also add a CONTRIBUTING.md, Docker setup, or a CI workflow to make this repository production-ready for hiring demos and technical interviews.

---
layout: single
title: "AdonisJS"
categories: [backend]
tags: [AdonisJS, Node.js, Backend-Framework, REST-API, ORM, Typescript]
search: true
---

## Introduction to AdonisJS

AdonisJS is a fully-featured and comprehensive Node.js framework that simplifies backend development by providing a well-structured and consistent ecosystem. It is designed to make building web applications and APIs seamless, with a strong emphasis on developer productivity, maintainability, and performance.

### Why AdonisJS?

1. **TypeScript First**: AdonisJS is built with TypeScript by default, providing type safety and reducing runtime errors.
2. **MVC Architecture**: It follows the Model-View-Controller (MVC) architecture, making it easier to organize and manage code.
3. **Integrated Ecosystem**: AdonisJS includes everything needed for backend development, such as routing, middleware, database management, authentication, and more.
4. **Lucid ORM**: An expressive and powerful Object-Relational Mapper (ORM) that simplifies database interactions.
5. **First-Class CLI Tools**: Includes powerful CLI tools for scaffolding, migrations, seeding, and testing.
6. **Extensibility**: Highly modular and supports custom packages, making it easy to extend the framework to suit your needs.

### Key Reatures and Details

1. **Lucid ORM in Depth**: Explain Lucid ORM's features (relations, query builder, hooks, transactions) with example code.
2. **Middleware**: Describe the role of middleware, built-in options, and how to create custom middleware.
3. **Validation**: Demonstrate how AdonisJS handles data validation and how to use the Validator.
4. **Authentication & Authorization**: Cover the basics of authentication and authorization, with examples like API token authentication.
5. **Task Scheduling**: Explain how to schedule periodic tasks in AdonisJS.
6. **Testing**: Provide steps to set up a testing environment and use AdonisJS's testing tools.

### Overview of Each Framework

- **AdonisJS**  
  A full-stack backend framework with a strong focus on developer productivity, type safety, and consistency. Built-in features like ORM, authentication, and validation make it ideal for structured projects.

- **Express.js**  
  A minimalist and flexible Node.js framework. Known for its unopinionated approach, it requires external libraries to build features like authentication or ORM.

- **NestJS**  
  A progressive framework built with TypeScript. Based on modular architecture, it’s inspired by Angular and focuses on scalability, maintainability, and dependency injection.

#### Feature Comparison

| Feature            | AdonisJS                               | Express.js                                    | NestJS                                  |
| ------------------ | -------------------------------------- | --------------------------------------------- | --------------------------------------- |
| **TypeScript**     | Built-in, first-class support          | Optional                                      | Built-in, mandatory                     |
| **Architecture**   | MVC (Model-View-Controller)            | Unstructured                                  | Modular, based on Dependency Injection  |
| **Built-in ORM**   | Lucid ORM (built-in)                   | Requires external libraries (e.g., Sequelize) | Prisma, TypeORM (configurable)          |
| **CLI Tools**      | Strong scaffolding and migration tools | Minimal                                       | Comprehensive CLI for project structure |
| **Middleware**     | Built-in                               | Requires manual setup                         | Integrated                              |
| **Community Size** | Growing                                | Large                                         | Large and rapidly growing               |

#### AdonisJS Strengths

1. **Integrated Ecosystem**: AdonisJS provides all essential tools (ORM, migrations, validations, etc.) out of the box, reducing the need to configure third-party libraries.
2. **TypeScript by Default**: AdonisJS is fully TypeScript-driven, offering better type safety compared to Express.js.
3. **Simpler Learning Curve**: The built-in features and MVC structure make it easier to adopt for beginners compared to Express.js or NestJS.
4. **Developer Productivity**: Powerful CLI tools help with scaffolding, migrations, and API generation, speeding up development.

#### Suitable Project Types

- **AdonisJS**:  
  Best for projects where you want a cohesive backend system with minimal configuration. Examples include REST APIs, small-to-medium web applications, and projects needing fast development cycles.

- **Express.js**:  
  Ideal for lightweight applications, microservices, or projects requiring complete flexibility in the stack. Examples include custom server logic or small API services.

- **NestJS**:  
  Excellent for enterprise-level applications, large-scale projects, and teams accustomed to modular architecture. Examples include multi-layered applications, real-time apps, or systems requiring complex dependency injection.

#### Choosing the Right Framework

| Criteria                 | AdonisJS                | Express.js              | NestJS              |
| ------------------------ | ----------------------- | ----------------------- | ------------------- |
| **Speed of Development** | Fast (integrated tools) | Moderate (manual setup) | Moderate            |
| **Scalability**          | Medium                  | High (with effort)      | High                |
| **Type Safety**          | Strong (default TS)     | Weak (needs setup)      | Strong (default TS) |
| **Flexibility**          | Medium                  | High                    | Medium              |
| **Project Complexity**   | Small to medium         | Simple to complex       | Medium to large     |

---

### Setting Up AdonisJS

Follow these steps to set up an AdonisJS project with the **"api" starter kit**.
<br>

1. **Install the AdonisJS CLI**

- Use the `npm init adonis-ts-app@latest` command to scaffold a new AdonisJS project:

```bash
npm init adonis-ts-app@latest <my-project-name>
```

When prompted, choose the "Web API" or "Fullstack" boilerplate based on your project needs.
<br>

2. **Navigate to the Project Directory**

Move into the newly created project directory:

```bash
cd my-project
```

<br>

3. **Install Dependencies**

- Install the required dependencies using npm:

```bash
npm install

# OR

yarn
```

<br>

4. **Configure the Environment**

- Copy the` .env.example` file to `.env`:

```bash
cp .env.example .env
```

Update the .env file with your database credentials and other necessary environment variables.
<br>

5. **Run the Development Server**

- Start the AdonisJS development server:

```bash
npm run dev
```

The application will be available at http://127.0.0.1:3333 by default.
<br>

6. **Example Project Structure**

- Here’s a brief overview of the project structure when using the api starter kit:

```bash
my-project/
├── app/               # Application logic (controllers, models, middleware)
├── config/            # Configuration files (e.g., database, app settings)
├── database/          # Migrations, seeds, and factories
├── start/             # Application bootstrap files
├── .env               # Environment variables
├── package.json       # Project dependencies and scripts
└── server.ts          # Application entry point
```

<br>

7. **Test the Setup**

- Navigate to the default route in your browser or use a tool like Postman to test the API. By default, the "api" starter kit does not include frontend code, making it ideal for building RESTful APIs or backends for mobile applications.

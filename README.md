# Web Server Kit Kit

A repo forked from Web Server Kit and removed Mobile module.

Visit [apollokit.org] to learn about Web Server Kit. You can also test a [demo application] deployed on
Heroku.

## Description

![](Technologies.png)

Web Server Kit Kit is an SEO-friendly, fully configured, modular starter project for developing [Universal
JavaScript] applications. You can use this kit to create your applications in JavaScript or TypeScript for all major
platforms &ndash; mobile, web, and server.

Web Server Kit Kit is built with [Apollo], [GraphQL], [React], [Knex.js],
and [Express] with support for relational databases such as PostgreSQL, MySQL, and SQLite.

[TypeScript] is our language of choice and we use it across the entire project. However, you can freely mix vanilla
JavaScript (the ES6 and ES7 syntax) and TypeScript when creating your modules.

The starter kit also integrates [Twitter Bootstrap], [Ant Design],
to provide great possibilities for styling for your web applications.

## Table of Contents

- [Overview](#overview)
  - [Why Use Web Server Kit](#why-use-web-server-kit)
  - [Concept](#concept)
  - [Architecture and Implemented Modules](#architecture-and-implemented-modules)
- [Demo](#demo)
- [Branches](#branches)
- [First Run of Web Server Kit](#first-run-of-web-server-kit)
- [Project Structure](#project-structure)
- [Web Server Kit Documentation](#web-server-kit-documentation)
- [License Info](#license)

## Overview

### Why Use Web Server Kit

#### I am a Developer

- Great productivity thanks to live reload and (partial) hot code reload
- Fractal modular architecture that's easy to support and extend
- The possibility to create modules in TypeScript _and_ JavaScript at the same time
- No need to develop [typical features](#architecture-and-implemented-modules) for your applications

#### I am a Project Manager

- Your application will work faster thanks to GraphQL
- Your team will be able to reuse the code for all the platforms
- Your team can create client, server, and mobile JavaScript applications
- Your application will be easier to support and evolve thanks to the fractal modular architecture
- Your application will be based on a widely-used JavaScript ecosystem (it's easy to find JS developers)
- Your team can develop new features straightaway instead of creating the basic features
- Your application will be integrated with Stripe, one of the top payment processors

### Architecture and Implemented Modules

Among all the approaches to building the application architecture, we opt for the _disposable fractal-based modular
architecture_. Thanks to it, it's possible to remove any built-in module from Web Server Kit without
breaking the application. We recommend that you develop your custom modules with the same idea in mind when using our
starter kit.

Web Server Kit comes with the following modules:

- **Authentication**. Authentication via social networks (Facebook, GitHub, LinkedIn, and Google using OAuth) and
  password-based authentication; refreshing a forgotten password
- **Authorization**. Permission-based authorization with various user roles
- **Internationalization**. A complete internationalization solution for the client and server
- **Pagination**. Navigation between pages and presentation of entities
- **State Management**. The application state stored in the database and on the client using different approaches
- **404 Not Found Page**. A minimalistic module for handling 404 requests

If you don't want to use the pre-built modules in your project, you can remove them using a [dedicated CLI]. For module
names, see the names of directories under `modules`.

## First Run of Web Server Kit

Verify if you use Node.js 6.x or higher (Node.js ^10 is recommended) before running the starter kit.

1. Clone Web Server Kit.

```
git clone https://github.com/sateesh2020/web-server-kit.git
cd web-server-kit
```

**NOTE**: The master branch is not recommended for development. Use it at your own risk.

**NOTE**: If you're going to use Windows to develop with Web Server Kit, you need to additionally enable
symlinks _before_ you run the project.

For Windows 10:

- Press `Win` + `I` to open **Settings**
- Click **Update & Security**
- Click the **For Developers** tab
- In the **Use developer features** window, switch to **Developer Mode**

**NOTE**: You can remove the unnecessary stacks from Web Server Kit by using the CLI. Consult a
[respective CLI section]. Alternatively, you can use the capabilities of your operating system. For example, by running
the command below, you can remove all Scala server files:

```bash
find . -name server-scala | xargs rm -rf
```

If you don't need the ready-made modules, you can also remove them using the [custom CLI].

2. Install the dependencies. Make sure that you use Yarn 1.0.0 or higher.

```
yarn
```

You can use NPM instead of Yarn to handle the starter kit dependencies and to run scripts. Throughout the Apollo
Universal Starter Kit documentation, we'll always use Yarn.

3. Seed sample data to the database. The command below will create new tables with sample data in SQLite:

```
yarn seed
```

SQLite is a typical default relational database installed in most Linux distributions including Mac OS X; otherwise,
consult [SQLite installation guide].

4. Run the starter kit in development mode:

```
yarn watch
```

The server application will be running on [http://localhost:3000], while the client application will be running on
[http://localhost:8080]. The terminal will tell your the exact ports.

For more information about running this starter kit for mobile development or Docker, consult the [Getting Started]
guide.

## Project Structure

The project structure presents generally accepted guidelines and patterns for building scalable web and mobile
applications.

The structure is _fractal_ meaning the available functionality is grouped primarily by feature rather than by file type.
But the current structure isn't prescriptive, and you can change it however you like.

```
web-server-kit
├── config                      # Various application configurations
├── docs                        # Documentation
├── node_modules                # Global Node.js modules
├── modules                     # All the prebuilt project modules
├── packages                    # Available packages
│   ├── client                  # React client
│   ├── common                  # Common code
│   ├── server                  # Node.js and Express server
└── tools                       # All build and CLI-related files
```

Inside `modules`, you'll find all the prebuilt modules that Web Server Kit comes with. Each module under
`modules` contains sub-directories with module implementations for different technologies. For example, if you look up
the module `modules/core`, you'll see the following sub-modules:

```
web-server-kit
├── modules                       # Available packages
│   ├── core                      # The core module
│       ├── client-react          # Core functionality for React app
│       ├── common                # React Native mobile client
│       └── server-ts             # Core functionality for Express server
└── tools                         # All build and CLI-related files
```

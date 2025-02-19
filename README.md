# Hacker News API

This is the backend service for the Hacker News application. It provides a custom GraphQL server that aggregates and serves data from Hacker News. The API supports queries for top stories, story details, and nested comments with pagination support.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## Overview

The Hacker News API is designed to power a client-side Hacker News application. It uses GraphQL to offer flexible data retrieval methods and supports efficient pagination strategies:

- **Cursor-based pagination** for top stories (infinite scrolling).
- **Offset-based pagination** for fetching nested comments on individual stories.

## Features

- **GraphQL API:** Provides a robust and flexible interface for fetching data.
- **Custom Data Aggregation:** Integrates with the official Hacker News API to gather and transform data.
- **Pagination Support:** Implements cursor-based and offset-based pagination for an optimal data-fetching experience.
- **Performance Optimizations:** Designed with caching and efficient data retrieval in mind.
- **Easy Integration:** Works seamlessly with the Hacker News Client application.

## Tech Stack

- **Backend Framework:** Node.js, Express
- **GraphQL Server:** Apollo Server
- **Data Fetching:** Axios
- **Environment Management:** dotenv

## Demo

You can view a live demo of the project here: [Live Demo](https://news-hn.site/graphql)

# Environment Setup

This project fetches data from a custom Hacker News API using GraphQL. Set up your environment variable by creating a .env file in the root directory with the following content:

```bash
  BASE_URL=https://hacker-news.firebaseio.com/v0
  PORT=4000
```

This ensures your server application uses the correct Hacker New API endpoint.

## Installation

To set up the project locally, follow these steps:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/dnguyen316/hacker-news-api.git
   ```

2. **Navigate to the project directory:**

   ```bash
    cd hacker-news-api
   ```

3. **Install dependencies:**

   ```bash
    npm install
   ```

4. **Start the development server:**

   ```bash
   npm run dev
   ```

   The application should now be running at http://localhost:4000/graphql.

# Usage

- Browse Stories: On the home page, you'll see a list of Hacker News top stories loaded via an infinite scroll mechanism.
- View Details: Click on a story title to see detailed information, including the story's URL and nested comments.
- Navigation: Use the intuitive navigation to move between different sections of the app.

# Project Structure

The project follows a straightforward structure. Here’s an overview:

## Project Structure

The backend is structured to ensure **modularity, scalability, and maintainability**, following best practices for a GraphQL API built with **Node.js, Apollo Server, and TypeScript**.

```graphql
HACKER-NEWS-API/
├── dist/                  # Compiled JavaScript output after build
├── node_modules/          # Installed dependencies (ignored in Git)
├── src/                   # Source code
│   ├── app/               # Application entry and server setup
│   │   ├── app.ts         # Main application logic
│   │   ├── server.ts      # Server initialization
│   ├── configs/           # Configuration files
│   │   ├── constants.ts   # Application-wide constants
│   ├── graphql/           # GraphQL schema and resolvers
│   │   ├── apollo-server.ts # Apollo GraphQL Server setup
│   │   ├── resolvers.ts   # GraphQL resolvers to handle queries
│   │   ├── schema.ts      # GraphQL schema definitions
│   ├── ingestion/         # Data ingestion and external API handling
│   ├── modules/           # Business logic modules
│   ├── shared/            # Shared utilities and reusable components
│   │   ├── components/    # Shared UI components (if applicable)
│   │   ├── core/          # Core logic and utilities
│   │   ├── middlewares/   # Express/Apollo middlewares for handling requests
│   │   ├── utils/         # Helper functions and utilities
│   ├── types/             # TypeScript type definitions
├── .env                   # Environment variables configuration (ignored in Git)
├── .gitignore             # Specifies ignored files/folders
├── DockerFile             # Docker configuration for containerization
├── drizzle.config.ts      # Database configuration using Drizzle ORM
├── package-lock.json      # Ensures consistent dependency versions
├── package.json           # Project metadata, scripts, and dependencies
├── Procfile               # Deployment instructions for platforms like Heroku
├── README.md              # Project documentation
└── tsconfig.json        # TypeScript configuration
```

# API Documentation

- Top Stories: Retrieve a list of top stories using cursor-based pagination.
- Story Details: Retrieve detailed information about a specific story, including nested comments via offset-based pagination.

  ```graphql
  query {
    topStories(cursor: "cursorValue", limit: 20) {
      id
      title
      url
      score
      time
      author
    }
  }
  ```

  After starting the server, you can explore and test these queries using the Apollo GraphQL Playground at http://localhost:4000/graphql.

# Contributing

Contributions are welcome! If you'd like to improve the project, please follow these steps:

1. Fork the repository.
2. Create a new branch (git checkout -b feature/your-feature).
3. Commit your changes (git commit -m 'Add some feature').
4. Push to the branch (git push origin feature/your-feature).
5. Open a pull request describing your changes.
6. Please ensure your code adheres to the existing style and includes relevant tests if applicable.

# License

This project is licensed under the MIT License. See the LICENSE file for details.

```pgsql
  Feel free to update or adjust any sections as needed to better fit your project's specifics.
```

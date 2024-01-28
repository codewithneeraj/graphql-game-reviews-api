# GraphQL Game Reviews API

This project implements a GraphQL API for managing game information and reviews. It includes a basic schema for games, reviews, and authors, with CRUD operations for games and relationships between entities.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [GraphQL Schema](#graphql-schema)
  - [Types](#types)
  - [Queries](#queries)
  - [Mutations](#mutations)
- [Data Structure](#data-structure)
- [Resolvers](#resolvers)

## Getting Started

### Prerequisites

- Node.js (version 14 or higher)
- npm (Node Package Manager)

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/codewithneeraj/graphql-game-reviews-api.git
   cd graphql-game-reviews
   
2. **Install dependencies:**
   ```bash
   npm install

3. **Running the Server:**
   ```bash
   npm start

# GraphQL Schema

## Types

### Game

- **id**: ID!
- **title**: String!
- **platform**: [String!]!
- **reviews**: [Review!]

### Review

- **id**: ID!
- **rating**: Int!
- **content**: String!
- **author**: Author!
- **game**: Game!

### Author

- **id**: ID!
- **name**: String!
- **verified**: Boolean!
- **reviews**: [Review!]

## Queries

- **games**: Retrieve a list of all games.
- **game(id: ID!)**: Retrieve details for a specific game.
- **authors**: Retrieve a list of all authors.
- **author(id: ID!)**: Retrieve details for a specific author.
- **reviews**: Retrieve a list of all reviews.
- **review(id: ID!)**: Retrieve details for a specific review.

## Mutations

- **addGame(game: AddGameInput!)**: Game: Add a new game to the database.
- **deleteGame(id: ID!)**: [Game]: Delete a game by ID.
- **updateGame(id: ID!, edits: EditGameInput)**: Game: Update game details by ID.

## Data Structure

The data structure is managed in-memory and includes arrays for games, reviews, and authors. Relationships between entities are established through IDs.

## Resolvers

Resolvers define the functions that execute GraphQL queries and mutations. They interact with the data stored in the database (in-memory array) and provide the necessary data for each field in the schema.

# User Organisation App Integration Documentation

## Table of Contents

- Overview
- Databse design
- Folder Structure
- Dependencies
- Getting Started
- Contribution Guide
- Setup Instructions
- Database Design
- Scripts
- Additional Resources
- API Endpoints
- API Reference
- Versioning

## Overview

The User Organisation App is designed to manage user data and organisational hierarchies efficiently. It leverages Node.js and TypeScript to provide a robust and scalable backend service.

## Database Design (ERD)

![database](./public/hng_erd.jpg)


# Database Design Overview

This document outlines the database design for the User Organisation App, focusing on the `User` and `Organisation` entities.

## Entities and Relationships

### 1. User

- **Table Name:** `users`
- **Description:** Stores user information.
- **Fields:**
  - `id` (Primary Key, UUID): Unique identifier for each user.
  - `username` (String): Unique username for the user.
  - `email` (String): Unique email address for the user.
  - `password` (String): Hashed password for authentication.
  - `first_name` (String): User's first name.
  - `last_name` (String): User's last name.
  - `organisation_id` (Foreign Key, UUID): References the organisation to which the user belongs.
  - `role` (String): Role of the user within the organisation (e.g., admin, member).
  - `created_at` (Timestamp): Timestamp when the user was created.
  - `updated_at` (Timestamp): Timestamp when the user was last updated.

### 2. Organisation

- **Table Name:** `organisations`
- **Description:** Stores organisation information.
- **Fields:**
  - `id` (Primary Key, UUID): Unique identifier for each organisation.
  - `name` (String): Name of the organisation.
  - `address` (String): Address of the organisation.
  - `phone` (String): Contact phone number for the organisation.
  - `email` (String): Contact email address for the organisation.
  - `created_at` (Timestamp): Timestamp when the organisation was created.
  - `updated_at` (Timestamp): Timestamp when the organisation was last updated.

## Relationships

- **One-to-Many Relationship:** 
  - An organisation can have multiple users. This is represented by the foreign key `organisation_id` in the `users` table.


## Folder Structure

This is a folder structure

```
|--- src
|    |--- controllers
|    |--- database
|    |--- interfaces
|    |--- middlewares
|    |--- routes
|    |--- services
|    |--- utils
|    |--- server.ts
|--- .env
|--- app.ts
|--- .gitignore
|--- package.json
|--- tsconfig.json
```

## Dependencies (Dev)

- Node.js
- TypeScript
- Express
- ts-node-dev
- [Other dependencies]

## Getting Started

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (v14 or later)
- [npm](https://www.npmjs.com/) (Node Package Manager, included with Node.js)
- [Git](https://git-scm.com/)

## Contribution Guide


## Getting Started

#### If you don't have git on your machine, [install it](https://docs.github.com/en/get-started/quickstart/set-up-git).

## Fork this repository

Fork this repository by clicking on the fork button on the top of this page.
This will create a copy of this repository in your account.

## Clone the repository

<img align="right" width="300" src="https://firstcontributions.github.io/assets/Readme/clone.png" alt="clone this repository" />

Now clone the forked repository to your machine. Go to your GitHub account, open the forked repository, click on the code button and then click the _copy to clipboard_ icon.

Open a terminal and run the following git command:

```bash
git clone "url you just copied"
```

where "url you just copied" (without the quotation marks) is the url to this repository (your fork of this project). See the previous steps to obtain the url.

<img align="right" width="300" src="https://firstcontributions.github.io/assets/Readme/copy-to-clipboard.png" alt="copy URL to clipboard" />

For example:

```bash
git clone git@github.com:this-is-you/first-contributions.git
```

where `this-is-you` is your GitHub username. Here you're copying the contents of the first-contributions repository on GitHub to your computer.

## Create a branch

Change to the repository directory on your computer (if you are not already there):

```bash
cd first-contributions
```

Now create a branch using the `git switch` command:

```bash
git switch -c your-new-branch-name
```

For example:

```bash
git switch -c add-alonzo-church
```

### Make Changes

Make your changes to the codebase. Ensure your code follows the project's coding standards and guidelines.

### Run Tests

Run the existing tests to ensure your changes do not break anything. If you added new functionality, write corresponding tests.

```sh
npm run test
```

## Commit those changes

Now open `Contributors.md` file in a text editor, add your name to it. Don't add it at the beginning or end of the file. Put it anywhere in between. Now, save the file.

<img align="right" width="450" src="https://firstcontributions.github.io/assets/Readme/git-status.png" alt="git status" />

If you go to the project directory and execute the command `git status`, you'll see there are changes.

Add those changes to the branch you just created using the `git add` command:

## Push changes to GitHub

Push your changes using the command `git push`:

```bash
git push -u origin your-branch-name
```

replacing `your-branch-name` with the name of the branch you created earlier.

<details>
<summary> <strong>If you get any errors while pushing, click here:</strong> </summary>

- ### Authentication Error
     <pre>remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
  remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
  fatal: Authentication failed for 'https://github.com/<your-username>/first-contributions.git/'</pre>
  Go to [GitHub's tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) on generating and configuring an SSH key to your account.

</details>
Soon your changes will be merged into the staging branch of this project. You will get a notification email once the changes have been merged.

## Setup Instructions

### 1. Clone the Repository

First, clone the repository to your local machine using Git.

```sh
git clone https://github.com/StarmannReassy/hng_boilerplate_node_web.git
cd hng_boilerplate_node_web.git
```

### 2. Install Dependencies

Navigate to the project directory and install the required dependencies.

```sh
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory of the project and add your environment-specific variables. You can use the provided `.env.example` file as a reference.

```sh
cp .env.example .env
```

Edit the `.env` file to match your environment configuration.

### 4. Compile TypeScript

Compile the TypeScript code to JavaScript.

```sh
npm run build
```

### 5. Run the Development Server

Start the development server with the following command. This will also watch for any changes in your code and automatically restart the server.

```sh
npm run start:dev
```

### 6. Run the Production Server

To run the application in a production environment, use the following command:

```sh
npm run start
```

### 7. Verify the Setup

Open your browser and navigate to `http://localhost:3000/api/v1/` to verify that the application is running correctly.

## Folder Structure

Here's an overview of the project's folder structure:

```
|--- src
|    |--- controllers
          |--- v1
|    |--- database
|    |--- interfaces
|    |--- middlewares
|    |--- routes
|         |--- v1
|    |--- services
|    |--- utils
|    |--- server.ts
|--- .env
|--- app.ts
|--- .gitignore
|--- package.json
|--- tsconfig.json
```

## Scripts

Here are some useful npm scripts that you can use during development and production:

- `npm run build`: Compiles the TypeScript code to JavaScript.
- `npm run start:dev`: Starts the development server with live reloading.
- `npm run start`: Starts the production server.
- `npm run test`: Runs the test suite (if available).
- `npm run lint`: Runs the linter to check for code style issues.

## Additional Resources

- [Node.js Documentation](https://nodejs.org/en/docs/)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Express Documentation](https://expressjs.com/)

By following these steps, you should have your Node.js and TypeScript application up and running. If you encounter any issues, please refer to the documentation of the respective tools or seek help from the community.

## API Endpoints
- Example to how the endpoints looks like..
- **GET /api/v1/users**: Retrieves a list of all users.
  - Parameters: None
  - Response: An array of user objects.

- **POST /api/v1/users**: Creates a new user.
  - Parameters: User data (name, email, etc.)
  - Response: The newly created user object.

### API Reference
All API endpoints can be referenced in the [API Reference](https://app.swaggerhub.com/apis/BLARD/TechDevs/1.0.0) document.


## Database Schema

Our application uses a Postgres database with the following Tables:

- **Users**: Stores user information (name, email, etc.)
- **Organizations**: Represents organizational hierarchies.
- ...

Here's a simplified [ER diagram:](https://app.eraser.io/workspace/8Av0Vdm6JOpMtc3uxQCO?origin=share&elements=qIHB3yk1wrfaHVQKGvjOwQ)


## Versioning

This project is versioned to ensure backward compatibility and easy maintenance. The current version is 1.0.0.
```
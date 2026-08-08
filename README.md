# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Features

- Interactive terminal quiz experience
- Multiple quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Randomized question order
- Progress indicator during quizzes
- Instant feedback with explanations
- Final score summary and review of incorrect answers
- Built with modern ES modules and native Node.js APIs

## Requirements

- Node.js 18 or later

## Getting Started

### Install dependencies

This project uses only built-in Node.js modules, so there are no external dependencies to install.

### Run the quiz

```bash
npm start
```

Or run directly:

```bash
node index.js
```

## Available Scripts

- `npm start` - Start the quiz application
- `npm test` - Run the test suite

## How It Works

The application loads quiz questions from `data/questions.json`, then uses a simple terminal interface to:

1. Choose a category
2. Choose the number of questions
3. Answer each question in sequence
4. View results and review missed answers

## Project Structure

```text
.
├── index.js
├── package.json
├── data/questions.json
└── src
    ├── colors.js
    ├── input.js
    └── quiz.js
```

## Core Concepts Demonstrated

- ES Modules
- Async/await
- File system operations
- Readline-based user input
- Classes and OOP
- Array methods
- Destructuring
- Error handling

## License

MIT

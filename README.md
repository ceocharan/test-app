# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Project Overview

**Quiz CLI** is a Node.js terminal application that loads quiz questions from a JSON file, lets the user choose a category and question count, and then runs an interactive multiple-choice quiz in the terminal.

### Tech Stack

- **Node.js** (required: `>=18.0.0`)
- **ES Modules**
- Built-in Node APIs:
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`

### High-Level Functionality

- Displays a styled welcome banner in the terminal
- Lets the user select a quiz category
- Lets the user choose how many questions to answer
- Shuffles questions before starting the quiz
- Tracks score and progress
- Shows explanations for each question
- Displays a final results summary and review of incorrect answers
- Offers the option to play again

## Key Features

- Interactive multiple-choice quiz in the terminal
- Category selection from JSON-backed content
- Question count selection
- Randomized question order
- Progress bar and per-question progress display
- Immediate feedback for correct/incorrect answers
- Final score summary with performance message
- Review section for missed questions
- ANSI color styling without external dependencies

## Setup Instructions

### Prerequisites

- Node.js **18 or newer**

### Installation

Clone the repository and install dependencies:

```bash
npm install
```

> The project does not declare external runtime dependencies in `package.json`, but running `npm install` will still prepare the project in the standard Node.js workflow.

### Configuration

No environment variables or configuration files are required.  
Quiz content is stored in:

```text
data/questions.json
```

## How to Run the Project

Start the quiz application with:

```bash
npm start
```

Or run it directly with:

```bash
node index.js
```

## Usage Examples

When the app starts, it:

1. Shows a welcome banner
2. Prompts you to choose a category:
   - JavaScript Basics
   - Node.js Fundamentals
   - General Programming
3. Prompts you to choose how many questions to answer
4. Presents each question as a numbered multiple-choice list
5. Shows whether your answer was correct
6. Displays the correct answer and explanation when needed
7. Shows your final score and offers to play again

### Example Flow

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions
```

Then for each question:

```text
Question 1 of 5

What keyword is used to declare a constant in JavaScript?

  1. var
  2. let
  3. const
  4. define
```

## File Structure

```text
.
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Roles

- **`index.js`** – Application entry point; loads questions, handles the main game loop, and coordinates user interaction
- **`src/input.js`** – Reusable terminal input helpers built on Node’s `readline` module
- **`src/quiz.js`** – Quiz logic, scoring, question rendering, progress display, and results summary
- **`src/colors.js`** – ANSI color utilities for styled terminal output
- **`data/questions.json`** – Quiz content organized by category
- **`package.json`** – Project metadata and npm scripts

## Additional Insights

### Scripts

The repository defines these npm scripts:

```json
{
  "start": "node index.js",
  "test": "node --test"
}
```

### Architecture Notes

- The project uses **ES module syntax** (`import` / `export`)
- Quiz questions are loaded from a local JSON file at runtime
- The quiz logic is encapsulated in a `Quiz` class
- Input handling is separated from quiz logic, which keeps responsibilities clear
- The question order is randomized with a Fisher–Yates shuffle implementation
- Terminal styling is handled without third-party packages

### Data Format

Each question in `data/questions.json` includes:

- `question`
- `options`
- `answer`
- `explanation`

Each category includes:

- `name`
- `questions`

### Testing

A test script is available via `npm test`, which runs Node’s built-in test runner:

```bash
node --test
```

No separate test files are present in the repository tree shown here.

## License

This project is licensed under the **MIT** license.

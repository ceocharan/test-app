# Quiz CLI

## Project Overview

**Quiz CLI** is an interactive command-line quiz game built with Node.js. It lets users choose a quiz category, answer multiple-choice questions, review results, and replay the game.

The application uses:

- **Node.js ES Modules**
- Built-in **`fs/promises`**, **`path`**, **`url`**, and **`readline`**
- A small internal module structure for input handling, quiz logic, and terminal colors
- JSON-based question data stored in `data/questions.json`

The repository description in `package.json` identifies it as:

> "An interactive command-line quiz game for learning JavaScript"

## Key Features

- Interactive terminal UI with colored output
- Category selection:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Question count selection:
  - All questions
  - 3 questions
  - 5 questions
- Randomized question order using a shuffle function
- Score tracking and completion percentage
- Final results summary with performance feedback
- Review section for incorrect answers
- Replay option after each quiz round

## Setup Instructions

### Prerequisites

- **Node.js 18 or later**

This requirement is defined in `package.json`:

```json
"engines": {
  "node": ">=18.0.0"
}
```

### Installation

This project does not declare any external npm dependencies.  
If you want to work with the project locally:

1. Clone the repository
2. Make sure you are using Node.js 18+
3. Run the app with the commands below

### Configuration

No environment variables or separate configuration files are required.  
All quiz content is stored in:

- `data/questions.json`

## How to Run the Project

### Start the quiz

```bash
npm start
```

This runs:

```bash
node index.js
```

### Run tests

```bash
npm test
```

This runs:

```bash
node --test
```

## Usage Examples

When the app starts, it:

1. Clears the terminal
2. Displays a welcome banner
3. Prompts you to choose a quiz category
4. Prompts you to choose how many questions to answer
5. Shows each question with numbered answer choices
6. Displays whether your answer was correct
7. Shows explanations where available
8. Presents a final score summary
9. Offers to play again

### Example flow

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions

Your choice (enter number):
```

During the quiz, answers are selected by entering the number of the option shown.

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

### Major files

- **`index.js`** — Application entry point; loads questions, handles the main loop, and coordinates gameplay
- **`data/questions.json`** — Quiz content grouped by category
- **`src/quiz.js`** — Quiz class and game logic, including scoring, progress, and results display
- **`src/input.js`** — Readline-based terminal input helpers
- **`src/colors.js`** — ANSI color formatting utilities for terminal output
- **`package.json`** — Project metadata and npm scripts

## Additional Insights

- The app is written as an **ES module** project (`"type": "module"` in `package.json`)
- It uses **only built-in Node.js modules**; no third-party packages are declared
- Questions are defined as objects with:
  - `question`
  - `options`
  - `answer`
  - optional `explanation`
- The quiz logic shuffles questions using the **Fisher-Yates algorithm**
- Incorrect answers are reviewed at the end of the quiz for learning reinforcement
- The app includes a formatted progress bar and performance-based result message

## License

This project is licensed under the **MIT License** according to `package.json`.
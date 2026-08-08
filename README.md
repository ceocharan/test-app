# quiz-cli

An interactive command-line quiz game for learning JavaScript and general programming concepts.

## Project Overview

`quiz-cli` is a Node.js terminal application that runs an interactive multiple-choice quiz in the console. It loads questions from `data/questions.json`, lets the user choose a category and question count, then presents questions one by one with colorized output, progress tracking, and a final score summary.

### Tech Stack

- **Node.js** (requires **v18.0.0 or newer**)
- **ES Modules** (`"type": "module"`)
- Built-in Node APIs:
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- No third-party runtime dependencies

### Key Features

- Interactive terminal quiz experience
- Category selection
- Question count selection
- Randomized question order
- Progress bar during the quiz
- Immediate feedback for correct/incorrect answers
- Explanations shown after each question when available
- Final results screen with performance-based message
- Review of missed questions at the end
- “Play again” loop
- ANSI colorized output for a more readable CLI experience

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

### What each file does

- **`index.js`** – Main entry point; loads questions, handles the game loop, and coordinates user interaction.
- **`data/questions.json`** – Quiz content organized into categories.
- **`src/quiz.js`** – Quiz logic, scoring, progress display, and results rendering.
- **`src/input.js`** – Readline-based input helpers for prompts, selection, confirmation, and pause handling.
- **`src/colors.js`** – ANSI terminal color utilities used throughout the app.
- **`package.json`** – Project metadata and npm scripts.

## Setup Instructions

### Prerequisites

- Node.js **18.0.0+**
- npm (bundled with Node.js)

### Installation

Clone the repository and install dependencies:

```bash
npm install
```

There are no external dependencies listed in `package.json`, so this step mainly prepares the local project environment and lockfile state if needed.

### Configuration

No environment variables or external configuration files are required. The quiz content is loaded directly from:

```text
data/questions.json
```

## How to Run the Project

Start the quiz from the project root:

```bash
npm start
```

This runs:

```bash
node index.js
```

### Available npm Scripts

From `package.json`:

- **`npm start`** – Runs the quiz app
- **`npm test`** – Runs Node’s built-in test runner with `node --test`

> Note: The repository snapshot does not include dedicated test files, but the test script is defined in `package.json`.

## Usage Examples

When you run the app, it will:

1. Display a welcome banner
2. Ask you to choose a category
3. Ask how many questions you want to answer
4. Show each question with numbered answer choices
5. Display whether your answer was correct
6. Show explanations where provided
7. Present your final score and a review of missed questions
8. Ask whether you want to play again

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

### Answering questions

You respond by entering the number of the answer choice:

```text
What keyword is used to declare a constant in JavaScript?

  1. var
  2. let
  3. const
  4. define

Your choice (enter number):
```

## Additional Insights

### Question Data

The quiz content currently includes these categories:

- **JavaScript Basics**
- **Node.js Fundamentals**
- **General Programming**

Each question can include:

- `question`
- `options`
- `answer`
- `explanation`

### Architecture Notes

- The app is organized into small modules:
  - `input.js` handles user interaction
  - `quiz.js` handles game state and scoring
  - `colors.js` handles terminal styling
  - `index.js` orchestrates the overall flow
- Questions are shuffled using the Fisher-Yates algorithm before the quiz begins.
- The app uses `async/await` throughout for a simple sequential CLI flow.
- The codebase relies entirely on Node’s built-in modules, so it stays lightweight and easy to run.

### Terminal Behavior

The app clears the console before showing the banner and uses colored output to distinguish:

- success messages
- errors
- warnings
- informational prompts
- highlighted headings

## License

This project is licensed under the **MIT** license, as declared in `package.json`.
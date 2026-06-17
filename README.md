# Quiz CLI

An interactive command-line quiz game built with Node.js ES modules. It lets users choose a quiz category, pick how many questions to answer, and receive immediate feedback with a final score summary.

## Project Overview

Quiz CLI is a lightweight terminal-based learning app focused on JavaScript and general programming concepts. It demonstrates:

- ES module syntax (`import` / `export`)
- Async/await with Promises
- Node.js built-in `readline` for terminal interaction
- File-based quiz data loaded from JSON
- Object-oriented quiz flow with a `Quiz` class
- ANSI terminal colors for a better CLI experience

### Features

- Multiple quiz categories
- Configurable question count per session
- Randomized question order
- Instant correct/incorrect feedback
- Explanations shown after each question
- Final score summary with performance message
- Review of missed questions

## Setup Instructions

### Prerequisites

- Node.js **18 or newer**
- npm (bundled with Node.js)

### Install

Clone the repository and move into the project directory:

```bash
git clone <your-repo-url>
cd test
```

Install dependencies:

```bash
npm install
```

> This project currently has no external dependencies, so `npm install` is optional unless you want npm to create or manage a lockfile.

### Important note about the current file layout

The application entry point in `index.js` currently imports from `./src/input.js`, `./src/quiz.js`, and `./src/colors.js`, and it loads quiz data from `./data/questions.json`.

However, in the repository as currently structured, those files are located in the repository root:

- `input.js`
- `quiz.js`
- `colors.js`
- `questions.json`

If you run the app without adjusting paths, Node.js will fail to resolve those imports. To make the app run, either:

1. update the import/data paths in `index.js` to match the root-level files, or
2. move the files into the expected `src/` and `data/` directories.

## Usage Examples

### Start the quiz

```bash
npm start
```

Or run directly:

```bash
node index.js
```

### Typical gameplay flow

1. Launch the app
2. Choose a category
3. Choose how many questions to answer
4. Select answers by entering the option number
5. Review your score and missed questions
6. Choose whether to play again

### Example session

```text
Choose a category:
1. JavaScript Basics
2. Node.js Fundamentals
3. General Programming

How many questions?
1. All questions
2. 3 questions
3. 5 questions

Question 1 of 3
What keyword is used to declare a constant in JavaScript?
1. var
2. let
3. const
4. define

Your choice (enter number): 3
```

## Questions Data Format

Quiz questions are stored in `questions.json` under a `categories` object.

Each category contains:

- `name`: Display name shown in the menu
- `questions`: Array of question objects

Each question object contains:

- `question`: The prompt text
- `options`: Array of answer choices
- `answer`: Zero-based index of the correct answer
- `explanation`: Short explanation shown after answering

## File Structure

```text
.
├── README.md
├── colors.js
├── index.js
├── input.js
├── package.json
├── questions.json
└── quiz.js
```

### File descriptions

- **`index.js`** — Application entry point; loads data, handles category selection, and runs the quiz loop
- **`quiz.js`** — Quiz engine; shuffles questions, tracks score, and prints results
- **`input.js`** — Readline helpers for prompting, selecting, confirming, and pausing
- **`colors.js`** — ANSI color helper functions for terminal styling
- **`questions.json`** — Quiz categories and question data
- **`package.json`** — Project metadata, scripts, and Node.js engine requirement

## Scripts

- `npm start` — Run the quiz application
- `npm test` — Run Node's built-in test runner

## Troubleshooting

### "Cannot find module" errors

This usually means the file paths in `index.js` do not match the actual folder structure. Update the import paths or move the files into the expected directories.

### Terminal colors look wrong

If your terminal does not support ANSI escape codes, color output may not display correctly.

### Node version issues

Make sure you are using Node.js 18 or later, as required by `package.json`.

## License

MIT

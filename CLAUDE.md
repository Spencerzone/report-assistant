# Report Assistant

## Project Overview

A client-side web tool that helps teachers write student assessment report comments. No build process, server, or dependencies required — just open `index.html` in a browser.

## Running the Project

Open `index.html` directly in any modern browser, or serve it locally:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Project Structure

```
index.html   # Main UI — form, checkboxes, output, embedded AI prompt
script.js    # All logic — comment generation, modifier system, undo, clipboard
style.css    # Dark theme, responsive grid layout (breakpoint: 768px)
favicon.png  # App icon
```

## Key Functionality

- **Comment generation**: Assembles a structured assessment comment from selected checkboxes (adjectives, academic engagement, behaviour, collaboration, assessment, improvements)
- **Pronoun handling**: Supports he/him, she/her, they/them — affects generated text
- **Assessment marks**: A–E grades affect tone/language in the output
- **Modifier system**: Clicking highlighted words in the output opens a dropdown to swap modifiers (frequency, degree, academic level, noun strength)
- **Undo**: Single-level undo restores previous checkbox state and output
- **AI prompt**: Embedded in a `<details>` element — gives teachers a ready-made prompt to expand the raw comment into a full 900–1000 character school report using a generative AI model

## No Build, No Tests, No CI

This is a zero-dependency static web app. There is no:
- Package manager (no `npm install` needed)
- Build step
- Test suite
- Linting config
- CI/CD pipeline

## Code Conventions

- Vanilla JS (ES6+), no frameworks or libraries
- All state is managed in-memory (no localStorage, no backend)
- Australian English spelling in all user-facing text
- Formal, third-person tone in generated comments
- Generated comments target 900–1000 characters when expanded via AI

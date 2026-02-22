# C Coding Guidelines

My personal coding guidelines for C/C++ projects.

## Adding Coding Guidelines to Other Projects

To add these coding guidelines to other projects as a submodule, use the following command:

```bash
git submodule add https://github.com/ChrGri/c-coding-guidelines.git shared/Guidelines
```

## Executing Coding Guidelines Check with an AI Agent

To check your code against these guidelines using an AI agent, follow these steps:

1.  Open the project you want to check in your editor (e.g., VS Code).
2.  Paste the following prompt into your AI agent's prompt window:

    ```
    Please review the C code in this project. Strictly evaluate it against the rules defined in the `CODING_GUIDELINES.md` file.

    1. First, list all the violations you found (pay special attention to variable suffixes, Allman style formatting, and the use of 'double').
    2. Afterwards, refactor the entire code so that it is 100% compliant with the guidelines.
    ```

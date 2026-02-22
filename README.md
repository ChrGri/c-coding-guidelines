# C Coding Guidelines

My personal coding guidelines for C/C++ projects.

## Adding Coding Guidelines to Other Projects

To add these coding guidelines to other projects as a submodule, use the following command:

```bash
git submodule add https://github.com/ChrGri/c-coding-guidelines.git shared/Guidelines
```

## Setup and Usage

Ensure you have the following installed:

*   [Visual Studio Code](https://code.visualstudio.com/)
*   [Gemini Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=GoogleCloudTools.gemini-code-assist)

## Checking your code

You can use the following prompt in the Gemini chat:

```
@workspace /ask Please review the C code in this project. Strictly evaluate it against the rules defined in the `CODING_GUIDELINES.md` file.

1. First, list all the violations you found (pay special attention to variable suffixes, Allman style formatting, and the use of 'double').
2. Afterwards, refactor the entire code so that it is 100% compliant with the guidelines.
```


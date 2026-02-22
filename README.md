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
Please review the C code in this project against /shared/Guidelines/CODING_GUIDELINES.md. First, list all violations you found, then fully refactor the code to be 100% compliant.
```


# Roo Code & VSCode Extension

## What is Roo Code?

**Roo code** is a domain-specific configuration and rules format used by the [Roo VSCode extension](https://marketplace.visualstudio.com/items?itemName=your-roo-extension-link) to automate, standardize, and accelerate rapid prototyping of web applications. Roo code files (typically found under `.roo/`) define agent prompts, coding standards, and workflow rules that guide AI-powered agents in generating, validating, and testing full-stack applications directly within Visual Studio Code.

The Roo extension interprets these files to:
- Provide AI-driven code generation and prototyping workflows.
- Enforce project structure, coding conventions, and automation scripts.
- Ensure reproducible, error-free builds and automated testing.
- Personalize and document generated projects based on user input.

## About This Repository

This project contains a `.roo/rules/rules.md` file, which defines the rapid prototyping agent's behavior and requirements for generated apps.

### Summary of `.roo/rules/rules.md`

- **General Requirements:**  
  - All generated apps must be full-stack (Python backend, Streamlit frontend).
  - Enforces clear file structure, linted code, and inclusion of a detailed `README.md`.
  - Assumptions and user personalization are documented.

- **Backend:**  
  - Always Python (FastAPI if API needed).
  - SQLite for persistence.
  - Input validation and API mocking if needed.

- **Frontend:**  
  - Always Streamlit, with modern UI and version-aware code.
  - Enforces Streamlit ≥1.30 and best practices.
  - UI must be visually appealing and user-friendly.

- **Shell Script & Setup:**  
  - Every project includes a `start.sh` script to set up virtual environments, install dependencies, and launch backend/frontend on fixed ports (8000/8501).
  - Script cleans up old processes and checks for successful startup.

- **Automated Testing:**  
  - Every project includes a `test.sh` script to exercise all user-facing features via HTTP requests and log scanning for errors.
  - Tests must pass and logs must be error-free before presenting output.

- **Verification:**  
  - The agent must fully build and verify the app before presenting code or documentation.
  - Only verified, working output is shown to the user.

- **Instructions:**  
  - Focus on requested features only.
  - Fix all build/dependency issues before output.
  - Output only after successful verification.

## How to Use Roo Code in VSCode

1. Install the Roo extension in VSCode.
2. Place your rules and prompts in `.roo/rules/rules.md`.
3. Use the extension's commands to generate, test, and validate full-stack apps according to your rules.
4. Review the generated `README.md` for build/run/test instructions and assumptions.

## License

See the extension or repository for license details.

# README.md

This repository contains scripts and utilities.

## Scripts

*   `generate_readme.py`:
    *   **Usage:** `python generate_readme.py`
    *   **What it does:** This script uses the Gemini API to automatically update the README.md file. It gathers context from other scripts and files in the repository and uses this information to generate a comprehensive and informative README. It preserves existing content while adding details about scripts, their usage, and functionality. Requires `GEMINI_API_KEY` environment variable.

*   `.github/workflows/update-readme.yml`:
    *   **Usage:** This is a GitHub Actions workflow file, triggered on pushes to the `main` or `develop` branches. It's also set up as a reusable workflow.
    *   **What it does:** This workflow automates the process of updating the README.md file using the `generate_readme.py` script. It checks out the repository, sets up Python, installs the necessary dependencies (google-generativeai), executes the script (providing the Gemini API key as an environment variable), and then commits and pushes the updated README.md file back to the repository. It handles cases where there are no changes to commit gracefully. This workflow requires the `GEMINI_API_KEY` secret to be configured in the repository settings.
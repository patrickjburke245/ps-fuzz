# Contributing to PS_Fuzz

Thank you for your interest in contributing to PS_Fuzz! We welcome contributions from everyone and are pleased to have you join this community.
This document provides guidelines and instructions for contributing to this project.

## Code of Conduct

The PS_Fuzz project adheres to a code of conduct that you can read at [Code of Conduct](LINK_TO_CODE_OF_CONDUCT).
By participating in this project, you agree to abide by its terms.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.7 or later
- Git

### Setting Up Your Development Environment

1. **Fork the Repository**: Start by forking the repository on GitHub.

2. **Clone Your Fork**:
```bash
git clone https://github.com/yourusername/ps_fuzz.git
cd ps_fuzz
```

### Set up a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Unix or macOS
venv\Scripts\activate     # On Windows
```

### Install dependencies

Install the project dependencies in editable mode (with the '-e' argument).
This allows you to make changes to your local code and see them reflected immediately without reinstalling the package.

```bash
pip install -e .[dev]
```

### Run tests

```bash
pytest
```

### Running the Tool

To run the ps_fuzz tool from your development environment, you can use the command-line interface set up in the project.
Since the package is installed in editable mode, you can run the tool directly from the source code without needing a separate installation step for testing changes.

To execute the tool, use the following command:
```bash
ps_fuzz --help
```

or alternatively:
```bash
python -m ps_fuzz --help

```

## Making Changes

1. Always create a new side-branch for your work.
```bash
git checkout -b your-branch-name
```

2. Make your changes to the code and add or modify unit tests as necessary.

3. Run tests again

Ensure all tests pass after your changes.
```bash
pytest
```

4. Commit Your Changes

Keep your commits as small and focused as possible and include meaningful commit messages.
```bash
git add .
git commit -m "Add a brief description of your change"
```

5. Push the changes you did to GitHub
```bash
git push origin your-branch-name
```

## Submitting a pull request

1. Update your branch

Fetch any new changes from the base branch and rebase your branch.
```bash
git fetch origin
git rebase origin/main
```

2. Submit a Pull Request

Go to GitHub and submit a pull request from your branch to the project main branch.


3. Request Reviews

Request reviews from other contributors listed as maintainers. If you receive a feedback - make any necessary changes and push them.

4. Merge

Once your pull request is approved, it will be merged into the main branch.

## Additional Resources

Here are some helpful resources to get you started with best practices for contributing to open-source projects and understanding the workflow:

- [GitHub Flow](https://guides.github.com/introduction/flow/) - An introduction to the GitHub workflow, which explains branches, pull requests, and more.
- [Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/) - A guide on how to write clear and concise commit messages, which are crucial for following the changes in a project.
- [Python Coding Style](https://pep8.org/) - Guidelines for writing clean and understandable Python code.


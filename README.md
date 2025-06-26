# Node.js GitHub Actions Workflow Demo

This project demonstrates how to create a basic **GitHub Actions workflow** that sets up a **Node.js environment** and logs a custom message to the workflow logs.

---

## 📌 Project Objective

To configure a **CI workflow using GitHub Actions** that:
- Sets up a Node.js environment.
- Logs a message: `Hello from @<your_github_username>` when a commit is pushed or the workflow is manually triggered.

---

## 📦 Tech Stack

- **GitHub Actions**
- **Node.js** (v20)
- **YAML** for workflow configuration

---

## 📂 Project Structure

```

node-github-actions-demo/
├── .github/
│   └── workflows/
│       └── nodejs-greeting.yml
└── README.md

````

---

## 🚀 Workflow Details

- **Trigger:** On push to `main` branch and via manual dispatch.
- **Job:** 
  - Runs on `ubuntu-latest`.
  - Checks out the repository code.
  - Sets up **Node.js v20** using `actions/setup-node`.
  - Logs a custom greeting message.

---

## 📜 Workflow Code

```yaml
name: Node.js Greeting Workflow

on:
  push:
    branches: [ main ]
  workflow_dispatch:

jobs:
  greet:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Log greeting message
        run: echo "Hello from @004Saichaithanya"
````

---

## 📖 How to Use

1. Clone or download this repository.
2. Ensure your project has a `.github/workflows/` directory.
3. Add the workflow YAML file inside.
4. Push the code to the `main` branch.
5. Go to your repository’s **Actions tab** and check the workflow run logs.

---

## ✅ Pros

* Automates environment setup and logging tasks.
* Demonstrates basic **CI workflow setup** using GitHub Actions.
* Can be extended for testing, deployments, and automation pipelines.

---

## 📌 Challenges Faced

* Adapting Linux/macOS commands like `mkdir -p` and `touch` for **Windows CMD compatibility**.
* Understanding YAML indentation and structure (which is strict in GitHub Actions).

---

## 📬 Author

**Sai Chaithanya Poloju**

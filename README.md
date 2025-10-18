# DevOps-CI-Demo
This project demonstrates how to create a GitHub repository, add a simple project, work with branches, open a Pull Request (PR), and set up a continuous integration (CI) workflow using GitHub Actions.
---
## Step 1: Create a New Repository
1. Go to GitHub.
2. Click on **New Repository**.
3. Name the repository `DevOps-CI-Demo`.
4. Add a description if you like.
5. Choose to initialize with a **README.md** file.
6. Click **Create Repository**.
---

## Step 2: Add a Simple Project

1. Clone the repository to your local machine:

2. Create a simple Python file, `app.py`, with the following content:
print("Hello CI - main branch!")

3. Commit and push the file to GitHub:
git add app.py
git commit -m "Add base Python app"
git push origin main
---
## Step 3: Create a New Branch and Modify the Code
1. Create and checkout a new branch named `feature-update`:
git checkout -b feature-update

text

2. Modify `app.py` to update the message:

print("Hello CI - feature branch update!")

text

3. Commit and push the changes:

git add app.py
git commit -m "Update app message in feature branch"
git push origin feature-update

text

---

## Step 4: Open a Pull Request (PR)

1. Navigate to your GitHub repository page.
2. You will see a **Compare & pull request** button for your `feature-update` branch — click it.
3. Add a PR title (e.g., "Feature update for CI").
4. Click **Create Pull Request**.

*(Take screenshot 1: Pull Request creation screen)*

---

## Step 5: Set Up GitHub Actions CI Workflow

1. Create directories and the workflow file `.github/workflows/ci.yml` in your repo:

mkdir -p .github/workflows
touch .github/workflows/ci.yml

text

2. Add the following YAML content to `.github/workflows/ci.yml`:

name: Hello CI

on:
pull_request:
branches: [ main ]
push:
branches: [ main ]

jobs:
run-ci:
runs-on: ubuntu-latest

text
   steps:
     - name: Checkout repository
       uses: actions/checkout@v4

     - name: Set up Python
       uses: actions/setup-python@v5
       with:
         python-version: '3.x'

     - name: Run test
       run: python app.py
text

3. Commit and push the workflow:

git add .github/workflows/ci.yml
git commit -m "Add GitHub Actions CI workflow"
git push origin feature-update

text

The workflow will automatically run for your pull request.

*(Take screenshot 2: CI pipeline running)*

---

## Step 6: Merge the Pull Request

1. Once the CI pipeline shows success (green checkmark), click **Merge pull request**.
2. Confirm the merge.






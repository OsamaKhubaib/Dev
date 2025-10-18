# DevOps-CI-Demo

Minimal demo repository to show GitHub Actions CI running tests and a simple feature branch workflow.

Steps to reproduce:

1. Initialize git and commit

   git init
   git add .
   git commit -m "chore: initial commit"

2. Create feature branch and modify

   git checkout -b feature-update
   # make changes, commit

3. Push branches and open PR

   # create repo on GitHub named DevOps-CI-Demo, then:
   git remote add origin https://github.com/YOUR_USERNAME/DevOps-CI-Demo.git
   git push -u origin main
   git push -u origin feature-update

Open a Pull Request from `feature-update` to `main` on GitHub. The CI workflow runs on PR creation.

Screenshots to capture:

- Pull request creation screen
- CI pipeline running
- Successful merge and passing checks

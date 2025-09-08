# CI/CD With GitHub Actions (CI) and Vercel (CD)

This is a simple Node.js web application built with Express, demonstrating a CI/CD pipeline using GitHub Actions. The app displays "Hello, CI/CD!" when visited. The pipeline automatically tests the code and deploys it to Vercel whenever changes are pushed to the `main` branch.

## Prerequisites
- [Node.js](https://nodejs.org) (version 20 or higher)
- [Git](https://git-scm.com)
- A [GitHub](https://github.com) account
- A [Vercel](https://vercel.com) account for deployment

## Setup Instructions
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/my-first-cicd.git
   cd my-first-cicd
   ```
   Replace `your-username` with your GitHub username.

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the app locally**:
   ```bash
   npm start
   ```
   Open your browser and visit `http://localhost:3000`. You should see "Hello, CI/CD!".

4. **Run tests**:
   ```bash
   npm test
   ```
   This runs the Jest test suite to verify the code.

## Project Structure
- `index.js`: The main Express application.
- `index.test.js`: Jest tests for the application.
- `package.json`: Project metadata and dependencies.
- `.github/workflows/ci.yml`: GitHub Actions workflow for Continuous Integration (runs tests).
- `.github/workflows/cd.yml`: GitHub Actions workflow for Continuous Delivery (deploys to Vercel).

## CI/CD Pipeline
The project uses GitHub Actions for CI/CD:
- **Continuous Integration (CI)**: On every push or pull request to the `main` branch, GitHub Actions:
  - Checks out the code.
  - Sets up Node.js (version 20).
  - Installs dependencies (`npm install`).
  - Runs tests (`npm test`).
- **Continuous Delivery (CD)**: On pushes to the `main` branch, GitHub Actions deploys the app to Vercel using the `amondnet/vercel-action`.

### GitHub Secrets
For deployment to work, add the following secret in your GitHub repository (Settings > Secrets and variables > Actions):
- `VERCEL_TOKEN`: Your Vercel API token (from Vercel’s Account Settings).

### Vercel Configuration
- **Org ID** and **Project ID**: Replace placeholders in `.github/workflows/cd.yml` with your Vercel project’s Org ID and Project ID (found in Vercel’s project settings).
- The app is deployed to a Vercel URL (e.g., `my-first-cicd.vercel.app`).

## How to Contribute
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Make changes and commit: `git commit -m "Add feature"`.
4. Push to your branch: `git push origin feature-name`.
5. Create a pull request on GitHub.

## Troubleshooting
- **CI fails**: Check the Actions tab in GitHub for logs. Look for test failures or setup errors.
- **CD fails**: Ensure `VERCEL_TOKEN`, `vercel-org-id`, and `vercel-project-id` are correct.
- Contact the repository owner or check GitHub Actions/Vercel documentation for help.

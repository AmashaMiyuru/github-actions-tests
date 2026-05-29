# GitHub Actions CI/CD Test Repository

A test repository to validate GitHub Actions CI/CD workflows with Node.js.

## Project Structure

```
.
├── .github/workflows/     # GitHub Actions workflows
│   ├── ci.yml            # Build & Test pipeline
│   └── cd.yml            # Deployment pipeline
├── src/                  # Source code
│   ├── index.js         # Main application
│   └── index.test.js    # Unit tests
├── package.json         # Dependencies and scripts
└── .eslintrc.json       # Linting configuration
```

## Setup

1. **Initialize git repository:**
   ```bash
   cd github-actions-test
   git init
   git add .
   git commit -m "Initial commit: GitHub Actions test project"
   ```

2. **Create GitHub repository:**
   - Go to [github.com/new](https://github.com/new)
   - Create a new repository named `github-actions-test`
   - Do NOT initialize with README/gitignore/license

3. **Push to GitHub:**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/github-actions-test.git
   git branch -M main
   git push -u origin main
   ```

4. **Install dependencies (local testing):**
   ```bash
   npm install
   ```

## Available Scripts

- `npm start` - Run the application
- `npm test` - Run unit tests
- `npm run lint` - Run ESLint
- `npm run build` - Build the project

## Workflows

### CI Workflow (`.github/workflows/ci.yml`)
Triggered on: Push to `main`/`develop` or Pull Requests
- ✅ Installs dependencies
- ✅ Runs linter
- ✅ Runs tests
- ✅ Builds project
- ✅ Uploads artifacts

Runs on Node.js versions: 16.x, 18.x, 20.x

### CD Workflow (`.github/workflows/cd.yml`)
Triggered on: Push to `main` or tag creation
- ✅ Builds application
- ✅ Creates deployment package
- ✅ Simulates staging deployment
- ✅ Creates releases for tags

## Testing the Workflows

1. **Test CI workflow:**
   - Create a feature branch: `git checkout -b feature/test`
   - Make a change to any file
   - Commit and push: `git push origin feature/test`
   - Open a Pull Request to `main`
   - Watch CI workflow run in the PR

2. **Test CD workflow:**
   - Push directly to `main`: `git push origin main`
   - Navigate to **Actions** tab in GitHub
   - Watch CD workflow run

3. **Test with tags:**
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```
   - CD workflow will run and create a release

## GitHub Actions Dashboard

Monitor workflow execution at: `https://github.com/YOUR_USERNAME/github-actions-test/actions`

## Artifacts

- **CI artifacts:** Build outputs stored for 5 days
- **CD artifacts:** Deployment packages stored for 30 days

View at: **Actions** → Select workflow → Artifacts section

## Troubleshooting

- **Workflows not running?** Check branch protection rules and workflow permissions in Settings → Actions → General
- **Build failures?** Check Node.js version compatibility
- **Artifacts missing?** Ensure deployment directories exist (`dist/`, `deployment/`)

## Next Steps

Once CI/CD is working, you can:
1. Add real deployment steps (Docker, AWS, Vercel, etc.)
2. Add coverage reports
3. Add security scanning
4. Add performance monitoring
5. Integrate with status checks and auto-merge

---

Happy testing! 🚀

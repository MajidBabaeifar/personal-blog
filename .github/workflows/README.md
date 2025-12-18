# GitHub Actions CI/CD Workflows

This directory contains GitHub Actions workflows that automatically run on every push and pull request to ensure code quality, performance, and security.

## Workflows Overview

### 1. CI Pipeline (`ci.yml`)
**Triggers:** Push and PR to `master`/`main`

**What it does:**
- ✅ Tests on multiple Node.js versions (18.x, 20.x)
- ✅ Runs TypeScript type checking
- ✅ Builds the project to ensure no build errors
- ✅ Uploads build artifacts for inspection

**Why it's useful:** Catches build errors and TypeScript issues before they reach production.

---

### 2. Code Quality (`code-quality.yml`)
**Triggers:** Push and PR to `master`/`main`

**What it does:**
- 🎨 Checks code formatting with Prettier
- 🔍 Runs TypeScript type checking
- 🔒 Performs security audit on dependencies
- 📦 Reviews dependencies for known vulnerabilities (PRs only)

**Why it's useful:** Maintains code quality standards and catches security vulnerabilities early.

---

### 3. Lighthouse CI (`lighthouse.yml`)
**Triggers:** Push and PR to `master`/`main`

**What it does:**
- 🚀 Runs Google Lighthouse performance audits
- 📊 Tests Performance, Accessibility, Best Practices, and SEO
- 📈 Requires minimum 90% score in all categories
- 🔗 Uploads reports for review

**Why it's useful:** Ensures your blog maintains excellent performance and SEO scores.

---

### 4. PR Checks (`pr-checks.yml`)
**Triggers:** Pull requests (opened, updated)

**What it does:**
- 💬 Comments on PR with build information
- 📏 Reports build size
- ✍️ Validates blog post frontmatter (title, description, pubDate)
- 🔍 Checks for new blog posts

**Why it's useful:** Provides immediate feedback on PRs and ensures blog posts have all required metadata.

---

## Workflow Status

You can see the status of all workflows in the **Actions** tab of your GitHub repository.

### Status Badges

Add these to your README.md to show build status:

```markdown
![CI](https://github.com/YOUR_USERNAME/YOUR_REPO/actions/workflows/ci.yml/badge.svg)
![Code Quality](https://github.com/YOUR_USERNAME/YOUR_REPO/actions/workflows/code-quality.yml/badge.svg)
```

---

## Configuration Files

### `.lighthouserc.json`
Configures Lighthouse CI thresholds:
- Performance: 90%
- Accessibility: 90%
- Best Practices: 90%
- SEO: 90%

You can adjust these thresholds if needed.

---

## How It Works

1. **On every push:**
   - All workflows run automatically
   - You get immediate feedback if something breaks
   - Vercel deploys automatically (separate from GitHub Actions)

2. **On pull requests:**
   - All checks must pass before merging
   - PR gets commented with build info
   - Dependency security is reviewed
   - Blog post frontmatter is validated

3. **Artifacts:**
   - Build artifacts are saved for 7 days
   - Lighthouse reports are uploaded and shareable

---

## Common Issues & Solutions

### Issue: Prettier check fails
**Solution:** Run locally to fix formatting:
```bash
npx prettier --write "src/**/*.{astro,ts,js,json,css,md}"
```

### Issue: TypeScript errors
**Solution:** Run type check locally:
```bash
npx astro check
```

### Issue: Lighthouse fails
**Solution:**
- Check the Lighthouse report in the workflow artifacts
- Common issues: large images, missing meta tags, slow performance

### Issue: Security audit fails
**Solution:** Update dependencies:
```bash
npm audit fix
```

---

## Customization

### Add More Checks

To add ESLint or other linters, edit `code-quality.yml`:

```yaml
- name: Run ESLint
  run: npx eslint "src/**/*.{ts,js,astro}"
```

### Change Node.js Versions

Edit `ci.yml` matrix:

```yaml
strategy:
  matrix:
    node-version: [18.x, 20.x, 22.x]  # Add more versions
```

### Adjust Lighthouse Thresholds

Edit `.lighthouserc.json`:

```json
"minScore": 0.95  // Increase to 95%
```

---

## Performance Optimization

These workflows run in parallel to save time:
- CI builds on multiple Node versions simultaneously
- Code quality checks run independently
- Lighthouse runs separately

Total runtime: ~2-3 minutes for all checks

---

## Cost

All these workflows run on GitHub's free tier:
- ✅ Unlimited for public repositories
- ✅ 2,000 minutes/month for private repositories

Your blog workflows use ~3 minutes per push, so you can make hundreds of updates per month on the free tier.

---

## Monitoring

### View Workflow Runs
1. Go to your repository on GitHub
2. Click the **Actions** tab
3. See all workflow runs, their status, and logs

### Get Notifications
GitHub automatically sends notifications for:
- ❌ Failed workflows
- ✅ Fixed workflows (after a failure)

Configure in: GitHub Settings → Notifications

---

## Best Practices

1. **Don't skip CI:** Always let checks complete before merging
2. **Fix failures quickly:** Failed checks indicate real issues
3. **Review Lighthouse reports:** Even if passing, check for improvement areas
4. **Update dependencies regularly:** Run `npm update` monthly
5. **Monitor workflow duration:** If workflows get slow, optimize them

---

## Questions?

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Lighthouse CI Docs](https://github.com/GoogleChrome/lighthouse-ci)
- [Astro Check Docs](https://docs.astro.build/en/reference/cli-reference/#astro-check)

---

**Happy coding!** 🚀 These workflows help maintain high code quality automatically.

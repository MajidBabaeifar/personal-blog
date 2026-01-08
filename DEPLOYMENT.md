# Deployment Guide

This guide will help you deploy your personal blog to Vercel for free.

## Prerequisites

- GitHub account
- Vercel account (sign up at [vercel.com](https://vercel.com) - it's free!)
- Git installed on your computer

## Step 1: Push to GitHub

1. Create a new repository on GitHub:
   - Go to [github.com/new](https://github.com/new)
   - Name it something like `personal-blog` or `my-blog`
   - Make it public or private (both work with Vercel)
   - Don't initialize with README (we already have one)

2. Push your code to GitHub:

```bash
# If you haven't initialized git yet
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Personal blog with Astro"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git push -u origin master
```

## Step 2: Deploy to Vercel

### Option A: Using Vercel Dashboard (Easiest)

1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "New Project"
3. Import your GitHub repository
4. Vercel will auto-detect Astro settings:
   - **Framework Preset**: Astro
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`
5. Click "Deploy"
6. Wait 1-2 minutes for deployment to complete
7. You'll get a URL like `your-blog.vercel.app`

### Option B: Using Vercel CLI

1. Install Vercel CLI:

```bash
npm install -g vercel
```

2. Login to Vercel:

```bash
vercel login
```

3. Deploy:

```bash
vercel
```

4. Follow the prompts:
   - Link to existing project? No
   - What's your project's name? `my-personal-blog`
   - In which directory is your code located? `./`
   - Want to override the settings? No

5. For production deployment:

```bash
vercel --prod
```

## Step 3: Configure Custom Domain (Optional)

If you have a custom domain:

1. In Vercel Dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your domain (e.g., `majidbabaeifar.com`)
4. Follow the DNS configuration instructions
5. Update `astro.config.mjs`:
   ```javascript
   export default defineConfig({
     site: 'https://yourdomain.com',
     // ... rest of config
   });
   ```
6. Update `public/robots.txt` with your domain
7. Commit and push changes - Vercel will auto-deploy

## Step 4: Post-Deployment Checklist

After deployment, update these files:

### 1. Update astro.config.mjs

```javascript
export default defineConfig({
  site: 'https://your-actual-domain.vercel.app', // or your custom domain
  // ...
});
```

### 2. Update public/robots.txt

```txt
Sitemap: https://your-actual-domain.vercel.app/sitemap-index.xml
```

### 3. Verify SEO

- Visit `your-domain.vercel.app/sitemap-index.xml` - should show sitemap
- Visit `your-domain.vercel.app/rss.xml` - should show RSS feed
- Check meta tags with browser dev tools
- Test on [Google's Rich Results Test](https://search.google.com/test/rich-results)

### 4. Submit to Search Engines

- [Google Search Console](https://search.google.com/search-console)
- [Bing Webmaster Tools](https://www.bing.com/webmasters)

## Continuous Deployment

Vercel automatically deploys when you push to your main branch:

1. Make changes to your blog
2. Commit and push:

```bash
git add .
git commit -m "Add new blog post"
git push
```

3. Vercel automatically builds and deploys
4. Check deployment status at [vercel.com/dashboard](https://vercel.com/dashboard)

## Adding New Blog Posts

To add a new post after deployment:

1. Create a new markdown file in `src/content/blog/`:

```bash
# Example: src/content/blog/my-new-post.md
```

2. Add frontmatter and content:

```markdown
---
title: 'My New Post Title'
description: 'Brief description'
pubDate: 2024-12-18
tags: ['web-dev', 'javascript']
---

Your content here...
```

3. Commit and push:

```bash
git add .
git commit -m "Add new blog post: My New Post Title"
git push
```

4. Vercel will automatically deploy in ~1-2 minutes

## Troubleshooting

### Build Fails

- Check build logs in Vercel dashboard
- Test build locally: `npm run build`
- Ensure all dependencies are in `package.json`

### 404 Errors

- Ensure `dist` folder is set as output directory
- Check that routes match your file structure

### Styles Not Loading

- Clear Vercel cache and redeploy
- Check Tailwind CSS is properly configured

## Performance Optimization

Your blog is already optimized, but you can:

1. **Add Images**: Place in `public/` folder
2. **Enable Analytics**: Add Vercel Analytics
3. **Monitor Performance**: Use Vercel's built-in analytics

## Environment Variables

If you need environment variables:

1. In Vercel Dashboard → Settings → Environment Variables
2. Add variables (e.g., API keys)
3. Reference in code with `import.meta.env.YOUR_VAR`

## Support

- [Astro Docs](https://docs.astro.build)
- [Vercel Docs](https://vercel.com/docs)
- [Vercel Community](https://github.com/vercel/vercel/discussions)

## Cost

Vercel's Hobby (free) plan includes:

- Unlimited deployments
- Automatic HTTPS
- 100GB bandwidth/month
- Serverless functions
- Analytics (limited)

This is more than enough for a personal blog!

---

**Congratulations!** Your blog is now live and will automatically deploy whenever you push changes to GitHub.

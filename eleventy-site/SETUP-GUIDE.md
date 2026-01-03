# Seventh Day Studios Website - Setup Guide

This guide will walk you through deploying your new website with Eleventy + Decap CMS. After setup, you'll be able to publish blog posts and edit pages from a dashboard at `seventhdaystudios.com/admin`.

---

## What's Included

- **Eleventy (11ty)** - Static site generator that builds your pages
- **Decap CMS** - Dashboard for editing content without coding
- **Your exact design** - All your styling preserved
- **Blog system** - Write posts in a visual editor, newest first
- **Draft mode** - Save posts without publishing
- **Preview deploys** - Review changes before going live

---

## Step-by-Step Setup

### Step 1: Replace Your Repository Files

1. Open your website folder on your computer (the `seventhdaystudios-website` folder)
2. **Delete everything inside it** EXCEPT the `.git` folder (this keeps your GitHub connection)
   - If you can't see `.git`, it's hidden. That's fine, just delete everything you can see.
3. Unzip the `seventhdaystudios-eleventy.zip` file I gave you
4. Copy ALL the contents of the unzipped folder INTO your `seventhdaystudios-website` folder

Your folder should now contain:
```
seventhdaystudios-website/
├── .eleventy.js
├── .gitignore
├── netlify.toml
├── package.json
├── src/
│   ├── _includes/
│   ├── admin/
│   ├── blog/
│   ├── images/
│   ├── index.njk
│   ├── about.njk
│   ├── blog.njk
│   ├── games.njk
│   ├── community.njk
│   ├── contact.njk
│   ├── favicon.ico
│   ├── (other static files)
```

---

### Step 2: Push to GitHub

1. Open **GitHub Desktop**
2. You should see all the new files listed as changes
3. At the bottom, type a commit message like: `Convert to Eleventy + Decap CMS`
4. Click **Commit to main**
5. Click **Push origin**

---

### Step 3: Wait for Netlify to Build

1. Go to **[app.netlify.com](https://app.netlify.com)**
2. Click on your site
3. Go to **Deploys** in the sidebar
4. You should see a new deploy in progress
5. Wait for it to say **Published** (this may take 1-2 minutes the first time)

If the build fails, check the deploy log for errors. Common issues:
- Missing files
- Typos in file names

---

### Step 4: Enable Netlify Identity

This lets you log into the CMS dashboard.

1. In Netlify, go to **Site configuration** (left sidebar)
2. Click **Identity** in the left menu
3. Click **Enable Identity**

---

### Step 5: Enable Git Gateway

This connects the CMS to your GitHub repo.

1. Still in Netlify, go to **Site configuration** → **Identity**
2. Scroll down to **Services**
3. Click **Enable Git Gateway**

---

### Step 6: Invite Yourself as a User

1. Go to **Identity** tab (top of page)
2. Click **Invite users**
3. Enter YOUR email address
4. Click **Send**
5. Check your email for the invite
6. Click the link in the email to set your password

---

### Step 7: Test the CMS

1. Go to `https://seventhdaystudios.com/admin`
2. Click **Login with Netlify Identity**
3. Enter your email and password
4. You should see the Decap CMS dashboard!

---

## How to Use the CMS

### Writing a Blog Post

1. Go to `seventhdaystudios.com/admin`
2. Click **Blog Posts** in the sidebar
3. Click **New Blog Posts**
4. Fill in the fields:
   - **Title** - Your post title
   - **Publish Date** - When to publish
   - **Description** - Short preview text
   - **Category** - Development, Announcement, etc.
   - **Body** - Write your post using the visual editor
5. Click **Save** (creates a draft)
6. When ready, change status from "Draft" to "Ready" 
7. Click **Publish**

### The Editorial Workflow

Posts go through stages:
- **Drafts** - Work in progress, not published
- **In Review** - Ready to review
- **Ready** - Approved and ready to publish

You can move posts between stages using the workflow board.

---

## Preview Before Publishing

Netlify automatically creates **preview deploys** for drafts:

1. When you save a draft, Netlify builds a preview
2. Go to **Deploys** in Netlify
3. Find the deploy preview link
4. Review your changes at the preview URL
5. If it looks good, publish the post

---

## Folder Structure

```
src/
├── _includes/layouts/    # Page templates
├── admin/                # CMS dashboard files
├── blog/                 # Blog posts (Markdown files)
├── images/uploads/       # Images uploaded via CMS
├── index.njk             # Homepage
├── about.njk             # About page
├── blog.njk              # Blog listing page
├── games.njk             # Games page
├── community.njk         # Community page
├── contact.njk           # Contact page
```

---

## Making Changes via Code (Optional)

You can still edit files in VS Code if you prefer:

1. Edit files in the `src/` folder
2. Save your changes
3. Commit and push to GitHub
4. Netlify auto-deploys in ~30 seconds

---

## Troubleshooting

**"Unable to access identity settings"**
→ Make sure Identity is enabled in Netlify (Step 4)

**"Git Gateway not found"**
→ Enable Git Gateway in Netlify settings (Step 5)

**Can't log in to CMS**
→ Make sure you accepted the email invite and set a password (Step 6)

**Build failed**
→ Check the deploy log in Netlify for specific errors

**Blog posts not showing**
→ Make sure the post has a date and the file is in the `src/blog/` folder

---

## Need Help?

If you run into any issues, just ask! I can help troubleshoot any problems with the setup.

---

## Quick Reference

| Task | How |
|------|-----|
| Write a blog post | Go to `/admin` → Blog Posts → New |
| Edit a page | Go to `/admin` → Pages → Select page |
| Preview changes | Check deploy previews in Netlify |
| Publish | Change status to Ready → Publish |
| Upload images | Use the image widget in the CMS |

---

You're all set! 🎉

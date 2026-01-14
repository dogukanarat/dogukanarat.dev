# Dogukan Arat - Personal Website

Personal blog built with [Hugo](https://gohugo.io/) using the [Hugo Blog Awesome](https://github.com/hugo-sid/hugo-blog-awesome) theme.

## Quick Start

```bash
# Run local development server
hugo server -D

# Build for production
hugo --minify
```

## Creating a New Post

### Option 1: Using Hugo CLI (Recommended)

```bash
hugo new posts/your-post-title.md
```

This creates a new post with pre-filled front matter in `content/en/posts/`.

### Option 2: Manual Creation

1. Create a new `.md` file in `content/en/posts/`
2. Add the front matter at the top of the file

### Front Matter Template

```toml
+++
date = '2025-01-14T12:00:00+03:00'
draft = false
title = 'Your Post Title'
description = 'A brief description for SEO and previews'
tags = ['tag1', 'tag2']
keywords = ['keyword1', 'keyword2']
+++
```

### Front Matter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `date` | Yes | Publication date in ISO 8601 format |
| `draft` | Yes | Set to `true` to hide from production |
| `title` | Yes | Post title displayed on the page |
| `description` | No | SEO description and post preview |
| `tags` | No | Tags for categorization |
| `keywords` | No | SEO keywords for this post |
| `toc` | No | Override global table of contents setting |

### Writing Content

- Use standard Markdown syntax
- Code blocks with syntax highlighting: ` ```language `
- Images: place in `static/images/` and reference as `/images/filename.png`

## Creating a New Page

Pages (like About) go in `content/en/pages/`:

```bash
hugo new pages/page-name.md
```

## Project Structure

```
.
├── content/en/
│   ├── posts/          # Blog posts
│   └── pages/          # Static pages (about, etc.)
├── static/             # Static files (images, robots.txt)
├── layouts/partials/   # Custom template overrides
├── assets/             # Avatar and other assets
└── hugo.toml           # Site configuration
```

## Configuration

Main configuration is in `hugo.toml`:

- **Google Analytics**: Update `services.googleAnalytics.ID` with your GA4 ID
- **Site info**: Modify `[Languages.en-gb.params]` section
- **Navigation**: Edit `[Languages.en-gb.menu]` section

## Deployment

The site auto-deploys to GitHub Pages on push to `main` branch via GitHub Actions.

## Useful Commands

```bash
# Preview with drafts
hugo server -D

# Build production site
hugo --minify

# Create new post
hugo new posts/my-new-post.md

# Check for issues
hugo --gc --minify
```

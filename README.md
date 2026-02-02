# Personal Website

A minimalist static website built with Jekyll for GitHub Pages.

## Quick Start

### 1. Setup Repository

1. Create a new repository on GitHub named `username.github.io` (replace `username` with your GitHub username)
2. Clone this repository locally
3. Push the contents to your GitHub repository

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/username.github.io.git
git branch -M main
git push -u origin main
```

### 2. Configure Your Custom Domain

1. Open `CNAME` file and replace `yourdomain.com` with your actual domain
2. In your domain registrar's DNS settings, add these records:
   - Type: `A`, Name: `@`, Value: `185.199.108.153`
   - Type: `A`, Name: `@`, Value: `185.199.109.153`
   - Type: `A`, Name: `@`, Value: `185.199.110.153`
   - Type: `A`, Name: `@`, Value: `185.199.111.153`
   - Type: `CNAME`, Name: `www`, Value: `username.github.io`
3. In your GitHub repository settings, go to Pages and enter your custom domain

If you don't want a custom domain, simply delete the `CNAME` file and your site will be available at `https://username.github.io`.

### 3. Personalize Your Site

Edit `_config.yml` to update:
- `title`: Your name
- `email`: Your email address
- `description`: Brief description
- `url`: Your custom domain (or leave as is for username.github.io)

### 4. Add Your Content

Replace placeholder content in:
- `index.md` - Home page with your bio and social links
- `publications.md` - Your publications
- `projects.md` - Your projects
- `blog.md` - Blog index (manually add links to posts here)

## Writing Blog Posts

### Creating a New Post

1. Create a new file in the `_posts` folder
2. Name it: `YYYY-MM-DD-post-title.md` (e.g., `2026-01-30-my-first-post.md`)
3. Add front matter at the top:

```yaml
---
layout: post
title: "Your Post Title"
date: 2026-01-30
---
```

4. Write your content using markdown
5. Manually add a link to the post in `blog.md`:

```html
<li>
  <div class="post-title"><a href="{{ '/blog/post-title/' | relative_url }}">Your Post Title</a></div>
  <div class="post-date">January 30, 2026</div>
  <div class="post-excerpt">
    Brief description of your post.
  </div>
</li>
```

### Markdown Syntax

- `# Heading 1`, `## Heading 2`, `### Heading 3`
- `**bold**`, `*italic*`
- `[Link text](URL)`
- `` `inline code` ``
- Lists: `- item` or `1. item`
- Code blocks: triple backticks with language

## Local Development

### Option 1: Using Docker (Recommended)

The easiest way to run the site locally without installing Ruby/Jekyll:

```bash
docker-compose up
```

Visit `http://localhost:4000` in your browser. See `DOCKER.md` for detailed instructions.

### Option 2: Native Installation

To preview your site locally:

1. Install Jekyll:
```bash
gem install bundler jekyll
```

2. Install dependencies:
```bash
bundle install
```

3. Run the local server:
```bash
bundle exec jekyll serve
```

4. Visit `http://localhost:4000` in your browser

## File Structure

```
.
├── _config.yml           # Site configuration
├── _layouts/             # HTML templates
│   ├── default.html      # Main layout
│   └── post.html         # Blog post layout
├── _posts/               # Blog posts (YYYY-MM-DD-title.md)
│   └── 2026-01-30-example-post.md
├── assets/
│   └── css/
│       └── main.css      # Stylesheet
├── index.md              # Home page
├── publications.md       # Publications page
├── projects.md           # Projects page
├── blog.md               # Blog index
├── CNAME                 # Custom domain configuration
└── README.md             # This file
```

## Customization

### Colors

Edit `assets/css/main.css` to customize the color scheme. The current palette uses:
- Black (`#000`) for headings
- Dark gray (`#333`) for body text
- Light gray (`#666`, `#999`) for secondary text
- Very light gray (`#e0e0e0`, `#f0f0f0`) for borders

### Layout

Modify `_layouts/default.html` to change the overall page structure or add new navigation items.

### Styling

All styles are in `assets/css/main.css`. The design is intentionally minimal and easy to customize.

## Publishing Changes

After making changes, commit and push to GitHub:

```bash
git add .
git commit -m "Update content"
git push
```

GitHub Pages will automatically rebuild your site within a few minutes.

## Support

For Jekyll documentation: https://jekyllrb.com/docs/
For GitHub Pages: https://docs.github.com/en/pages

## License

Feel free to use this template for your personal website.

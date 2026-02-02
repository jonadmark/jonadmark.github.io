# Quick Start Guide

## Immediate Next Steps

1. **Replace Placeholder Content**
   - Edit `_config.yml`: Update title, email, description, and custom domain
   - Edit `CNAME`: Replace with your actual domain (e.g., `yourname.com`)
   - Edit `index.md`: Add your bio, research interests, and social links
   - Edit `publications.md`: Add your actual publications
   - Edit `projects.md`: Add your actual projects

2. **Set Up GitHub Repository**
   ```bash
   # Create a repo named: username.github.io
   # Then push this code:
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/username/username.github.io.git
   git branch -M main
   git push -u origin main
   ```

3. **Configure Custom Domain** (Optional)
   - In your DNS settings, add A records pointing to GitHub's IPs
   - In GitHub repo Settings → Pages, add your custom domain
   - See README.md for detailed DNS setup

4. **Wait 2-5 Minutes**
   - GitHub Pages will build your site automatically
   - Visit your site at `https://username.github.io` or your custom domain

## Adding Your First Blog Post

1. Create: `_posts/2026-01-30-my-first-post.md`
2. Add front matter:
   ```yaml
   ---
   layout: post
   title: "My First Post"
   date: 2026-01-30
   ---
   ```
3. Write content in markdown
4. Manually add link in `blog.md`
5. Commit and push to GitHub

## Need Help?

- Full instructions in `README.md`
- Jekyll docs: https://jekyllrb.com
- GitHub Pages: https://docs.github.com/en/pages

# Lijun Zhu's Personal Website

A fast, modern personal website and blog built with [Zola](https://www.getzola.org/) static site generator and hosted on GitHub Pages.

🌐 **Live Site**: [https://lijunzhu.info](https://lijunzhu.info)

## Tech Stack

- **Static Site Generator**: [Zola](https://www.getzola.org/) (Rust-based)
- **Theme**: [PaperMod](https://github.com/cydave/zola-theme-papermod) (customized)
- **Hosting**: GitHub Pages
- **Domain**: Custom domain with SSL/TLS
- **CI/CD**: GitHub Actions (automatic deployment)

## Features

- ✅ Fast, lightweight static site
- ✅ Responsive design with dark/light theme toggle
- ✅ Blog with RSS/Atom feeds
- ✅ Full-text search functionality
- ✅ Custom domain with HTTPS
- ✅ SEO optimized
- ✅ Tag and category system

## Project Structure

```
website/
├── config.toml              # Main configuration
├── content/                 # All content files
│   ├── _index.md           # Homepage content
│   ├── about.md            # About page
│   ├── search.md           # Search page
│   └── posts/              # Blog posts
│       ├── _index.md
│       └── *.md            # Individual blog posts
├── static/                 # Static assets
│   ├── css/
│   ├── images/
│   └── CNAME               # Custom domain configuration
├── templates/              # Custom templates (override theme)
│   └── section.html        # Custom RSS/Atom feed labels
└── themes/papermod/        # Theme files
```

## Getting Started

### Prerequisites

- [Zola](https://www.getzola.org/documentation/getting-started/installation/) installed
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/lijunzh/website.git
   cd website
   ```

2. **Install Zola** (if not already installed)
   ```bash
   # macOS
   brew install zola
   
   # Or download from https://github.com/getzola/zola/releases
   ```

3. **Serve locally**
   ```bash
   zola serve
   ```
   
   Visit `http://127.0.0.1:1111` to view the site locally.

4. **Build for production**
   ```bash
   zola build
   ```

## Content Management

### Creating a New Blog Post

1. Create a new markdown file in `content/posts/`:
   ```bash
   touch content/posts/my-new-post.md
   ```

2. Add frontmatter and content:
   ```markdown
   +++
   title = "My New Blog Post"
   date = 2025-09-21
   [taxonomies]
   tags = ["tag1", "tag2"]
   categories = ["category"]
   +++
   
   Your blog post content here...
   ```

3. The post will automatically appear in:
   - Homepage recent posts
   - `/posts/` page
   - RSS/Atom feeds
   - Search index

### Editing Static Pages

- **About page**: Edit `content/about.md`
- **Homepage**: Edit `content/_index.md` and `config.toml` (home_content section)

## Configuration

Key configuration options in `config.toml`:

```toml
# Site basics
base_url = "https://lijunzhu.info"
title = "Lijun Zhu"

# Features
build_search_index = true
generate_feeds = true
feed_filenames = ["rss.xml", "atom.xml"]

# Theme customization
[extra.papermod]
show_theme_toggle = true
show_reading_time = true
# ... more options
```

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to the `main` branch.

### Custom Domain Setup

1. **DNS Configuration**: Point your domain to GitHub Pages
   - A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - CNAME (www): `lijunzhu.info`

2. **GitHub Pages Settings**:
   - Repository Settings → Pages
   - Custom domain: `lijunzhu.info`
   - Enforce HTTPS: ✅

3. **CNAME File**: Already included in `static/CNAME`

## Customization

### Theme Overrides

Custom templates in `/templates/` override the theme defaults:
- `section.html` - Custom RSS/Atom feed icons with proper labels

### Styling

- Custom CSS: `static/css/override.css`
- Theme CSS: Inherited from PaperMod theme

### Adding Features

The site supports:
- Custom shortcodes in `templates/shortcodes/`
- Additional static assets in `static/`
- Theme customization via `config.toml`

## Feeds

The site generates multiple feed formats:
- **RSS**: `https://lijunzhu.info/rss.xml`
- **Atom**: `https://lijunzhu.info/atom.xml`

Feeds include only blog posts (static pages are excluded via `in_feed = false`).

## Search

Full-text search is available at `/search/` using:
- Elasticlunr.js for client-side search
- Search index automatically generated from all content

## Contributing

This is a personal website, but if you spot issues or have suggestions:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is open source. The content is personal, but the code and configuration can be used as reference for other Zola sites.

## Acknowledgments

- [Zola](https://www.getzola.org/) - Fast static site generator
- [PaperMod Theme](https://github.com/cydave/zola-theme-papermod) - Clean, responsive theme
- [GitHub Pages](https://pages.github.com/) - Free hosting
- [Let's Encrypt](https://letsencrypt.org/) - Free SSL certificates

---

Built with ❤️ using Rust and Zola
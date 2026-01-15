# Personal Academic Website

A Quarto-based academic website for researchers. Built with [Quarto](https://quarto.org) and deployed via GitHub Pages.

## Quick Start

### Prerequisites

1. Install [Quarto](https://quarto.org/docs/get-started/)
2. Install R (optional, for R code execution)

### Local Development

```bash
# Clone your repository
git clone https://github.com/yourusername/yourusername.github.io.git
cd yourusername.github.io

# Preview locally
quarto preview

# Build the site
quarto render
```

### Customization

1. **Edit `_quarto.yml`** — Update site title, URL, navigation, and theme
2. **Edit `index.qmd`** — Your homepage and profile
3. **Add your photo** — Place `profile.jpg` in `images/`
4. **Update pages** — Edit `research.qmd`, `publications.qmd`, `teaching.qmd`, `cv.qmd`
5. **Add publications** — Update `references.bib` with your BibTeX entries

### Deployment

The site automatically deploys via GitHub Actions when you push to `main`.

**First-time setup:**
1. Go to repository **Settings** → **Pages**
2. Under "Build and deployment", select **GitHub Actions**

### Project Structure

```
.
├── _quarto.yml          # Site configuration
├── index.qmd            # Homepage
├── research.qmd         # Research page
├── publications.qmd     # Publications page
├── teaching.qmd         # Teaching page
├── cv.qmd               # CV page
├── styles.css           # Custom styles
├── references.bib       # BibTeX references
├── images/              # Images (add profile.jpg here)
│   └── profile.jpg
├── papers/              # PDF papers (optional)
├── slides/              # Presentation slides (optional)
├── cv/                  # CV PDF (optional)
│   └── cv-full.pdf
└── .github/workflows/   # GitHub Actions
    └── publish.yml
```

### Adding Content

**New blog posts (optional):**
Create a `posts/` directory and add to `_quarto.yml`:

```yaml
website:
  navbar:
    left:
      - href: posts.qmd
        text: Blog
```

**R code execution:**
Add executable R code blocks to any `.qmd` file:

````markdown
```{r}
library(ggplot2)
ggplot(mtcars, aes(mpg, hp)) + geom_point()
```
````

### Resources

- [Quarto Documentation](https://quarto.org/docs/websites/)
- [Quarto Gallery](https://quarto.org/docs/gallery/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

## License

Content © Your Name. Code MIT licensed.

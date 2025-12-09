# Ajit Kumar Sorout - Personal Academic Website

A Quarto-based academic website with blog, research pages, and photo gallery.

## Quick Start

### 1. Install Quarto

Download and install Quarto from [quarto.org/docs/get-started](https://quarto.org/docs/get-started/).

**macOS (Homebrew):**
```bash
brew install quarto
```

**Linux (Ubuntu/Debian):**
```bash
# Download the latest .deb from quarto.org
sudo dpkg -i quarto-*.deb
```

**Windows:**
Download the .msi installer from the Quarto website.

Verify installation:
```bash
quarto --version
```

### 2. Preview Locally

Navigate to the website folder and run:
```bash
cd website
quarto preview
```

This opens a live preview at `http://localhost:4000`. Changes to `.qmd` files automatically refresh.

### 3. Build the Site

To generate the static HTML site:
```bash
quarto render
```

Output goes to the `_site/` folder.

---

## Deploying to GitHub Pages

### Option A: Using `quarto publish` (Recommended)

1. **Create a GitHub repository** named `yourusername.github.io` (for a user site) or any name (for a project site).

2. **Initialize git and push:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/yourusername.github.io.git
   git push -u origin main
   ```

3. **Publish with Quarto:**
   ```bash
   quarto publish gh-pages
   ```
   
   This creates a `gh-pages` branch with the rendered site and pushes it. Your site will be live at `https://yourusername.github.io`.

### Option B: Manual Setup

1. Go to your repo's **Settings → Pages**
2. Under "Source", select the `gh-pages` branch
3. Save, and GitHub will deploy your site

---

## Site Structure

```
website/
├── _quarto.yml          # Main configuration
├── _metadata.yml        # Default metadata
├── index.qmd            # Home page
├── research.qmd         # Research overview
├── about.qmd            # CV and bio
├── photos.qmd           # Photo gallery
├── blog/
│   ├── index.qmd        # Blog listing page
│   └── *.qmd            # Individual posts
├── topics/
│   └── *.qmd            # Topic landing pages
├── images/              # Images and figures
├── assets/
│   └── cv.pdf           # Your CV
├── styles.scss          # Custom styling
└── styles.css           # Additional CSS
```

---

## Common Tasks

### Adding a New Blog Post

1. Create a new file in `blog/` with the naming convention:
   ```
   blog/YYYY-MM-DD-short-title.qmd
   ```

2. Add YAML front matter:
   ```yaml
   ---
   title: "Your Post Title"
   description: "A brief description for listings"
   date: 2025-01-20
   categories: [string-theory, condensed-matter]
   image: images/thumbnail.png   # Optional
   draft: false                  # Set to true to hide
   ---
   ```

3. Write your content in Markdown. Use LaTeX for math:
   - Inline: `$E = mc^2$`
   - Display: `$$\int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}$$`

4. Preview and publish:
   ```bash
   quarto preview
   quarto publish gh-pages
   ```

### Adding an Image

1. Place the image in `images/`:
   ```
   images/my-figure.png
   ```

2. Reference in your `.qmd` file:
   ```markdown
   ![Caption text](images/my-figure.png){width=80%}
   ```

3. For figures with captions and numbering:
   ```markdown
   ::: {#fig-myplot}
   ![](images/my-figure.png)
   
   This is the figure caption.
   :::
   
   See @fig-myplot for details.
   ```

### Adding a Code Block

**Python:**
````markdown
```python
import numpy as np
x = np.linspace(0, 2*np.pi, 100)
y = np.sin(x)
```
````

**Julia:**
````markdown
```julia
using LinearAlgebra
A = rand(3, 3)
eigvals(A)
```
````

Code blocks support:
- Syntax highlighting
- Line numbers: `{.python .numberLines}`
- Folding: Set `code-fold: true` in YAML
- Copy button: Automatic

### Adding a New Research Project

1. Open `research.qmd`
2. Add a new collapsible callout:
   ```markdown
   ::: {.callout-note collapse="true"}
   #### Project Title
   
   Project description...
   
   **Key techniques:** list here
   :::
   ```

### Creating a New Topic Page

1. Create `topics/new-topic.qmd`:
   ```yaml
   ---
   title: "New Topic"
   subtitle: "Description"
   listing:
     contents: ../blog/*.qmd
     type: default
     sort: "date desc"
     include:
       categories: "{new-topic}"
   toc: false
   ---
   
   Introductory text...
   ```

2. Add to navigation in `_quarto.yml` under `sidebar`.

### Updating Navigation

Edit `_quarto.yml`:

```yaml
navbar:
  left:
    - href: index.qmd
      text: Home
    - href: new-page.qmd    # Add new page
      text: New Page
```

---

## Customization

### Changing Colors/Theme

Edit `styles.scss`:

```scss
// Change primary color
$primary: #your-hex-color;

// Change fonts
$headings-font-family: 'Your Font', serif;
```

After changes:
```bash
quarto render
```

### Changing the Base Theme

In `_quarto.yml`, change the theme:

```yaml
format:
  html:
    theme:
      light: cosmo    # Try: cosmo, flatly, journal, lumen, etc.
      dark: darkly
```

Available themes: [quarto.org/docs/output-formats/html-themes.html](https://quarto.org/docs/output-formats/html-themes.html)

### Adding Social Links

In `_quarto.yml`, under `navbar.right`:

```yaml
right:
  - icon: twitter
    href: https://twitter.com/yourhandle
  - icon: linkedin
    href: https://linkedin.com/in/yourprofile
```

---

## Placeholder Replacements

Before publishing, replace these placeholders:

| Placeholder | Replace with |
|------------|--------------|
| `YOUR_GITHUB_USERNAME` | Your GitHub username |
| `YOUR_EMAIL@umass.edu` | Your email address |
| `YOUR_ID` (Google Scholar) | Your Scholar ID |
| `assets/cv.pdf` | Upload your actual CV |
| `images/profile.jpg` | Your profile photo |
| `XXXX.XXXXX` (arXiv) | Actual arXiv IDs |

---

## Useful Commands

| Command | Description |
|---------|-------------|
| `quarto preview` | Live preview with hot reload |
| `quarto render` | Build site to `_site/` |
| `quarto publish gh-pages` | Deploy to GitHub Pages |
| `quarto check` | Verify Quarto installation |
| `quarto render file.qmd` | Render single file |

---

## Troubleshooting

**Math not rendering?**
- Ensure your browser allows JavaScript
- Try clearing browser cache

**Styles not applying?**
- Check SCSS syntax with `quarto check`
- Clear the `_site/` folder and re-render

**GitHub Pages not updating?**
- Check the Actions tab for build errors
- Ensure `gh-pages` branch exists
- Verify Pages settings point to correct branch

**Images not showing?**
- Check file paths (case-sensitive!)
- Ensure images are committed to git

---

## Resources

- [Quarto Documentation](https://quarto.org/docs/guide/)
- [Quarto Blog Guide](https://quarto.org/docs/websites/website-blog.html)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [MathJax Documentation](https://www.mathjax.org/)

---

## License

Content © Ajit Kumar Sorout. Code examples MIT licensed.

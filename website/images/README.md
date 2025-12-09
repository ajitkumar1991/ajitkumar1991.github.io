# Images Folder

Place your images here. Suggested organization:

```
images/
├── profile.jpg              # Your profile photo (square, ~400x400px recommended)
├── logo.png                 # Optional site logo for navbar
├── brane-tiling-thumb.png   # Blog post thumbnails
├── worm-thumb.png
├── tensor-network-thumb.png
├── diffusion-thumb.png
├── conference-*.jpg         # Conference photos
├── whiteboard-*.jpg         # Whiteboard photos
├── plot-*.png               # Research figures
└── travel-*.jpg             # Personal photos
```

## Image Guidelines

- **Profile photo**: Square aspect ratio, minimum 400x400px
- **Blog thumbnails**: 16:9 or 4:3 aspect ratio, ~800px wide
- **Research figures**: PNG for plots, JPG for photos
- **Compress images** before adding (use tools like ImageOptim or TinyPNG)

## Referencing Images

In your `.qmd` files:

```markdown
![Alt text](images/filename.png)
```

With sizing:
```markdown
![Alt text](images/filename.png){width=50%}
```

With figure environment:
```markdown
::: {#fig-label}
![](images/filename.png){width=80%}

Caption text here.
:::
```

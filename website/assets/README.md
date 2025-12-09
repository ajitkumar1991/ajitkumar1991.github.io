# Assets Folder

Place downloadable files here:

```
assets/
├── cv.pdf                   # Your CV (required)
└── other-documents.pdf      # Any other downloadable documents
```

## Adding Your CV

1. Export your CV as PDF
2. Name it `cv.pdf` 
3. Place it in this folder
4. The navbar and About page will automatically link to it

## Linking to Assets

In your `.qmd` files:

```markdown
[Download my CV](assets/cv.pdf)
```

Or with a button:
```markdown
[{{< fa file-pdf >}} Download CV](assets/cv.pdf){.btn .btn-primary}
```

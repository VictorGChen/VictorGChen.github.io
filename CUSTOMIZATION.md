# Customization Guide

This guide explains how to customize your GitHub Pages portfolio site. Follow the sections below to update different parts of your site.

---

## Table of Contents

1. [Basic Site Information](#basic-site-information)
2. [Social Media Links](#social-media-links)
3. [Navigation Tabs](#navigation-tabs)
4. [About Page](#about-page)
5. [CV/Resume](#cvresume)
6. [Projects](#projects)
7. [Adding Images](#adding-images)
8. [Colors and Styling](#colors-and-styling)

---

## Basic Site Information

**File:** `_config.yml`

Update your site's basic information:

```yaml
title: "Your Name"
description: "Your professional tagline"
url: "https://yourusername.github.io"
```

---

## Social Media Links

**File:** `_config.yml`

Add your social media usernames and links:

```yaml
# Social media usernames (remove the ones you don't want to use)
github_username: your-github-username
linkedin_username: your-linkedin-username
email: your.email@example.com
cv_url: /assets/cv.pdf  # Path to your CV PDF
itch_username: your-itch-username
```

The social icons will automatically appear in the footer of every page and on your About page.

### Supported Social Platforms

The social icons currently support:
- GitHub
- LinkedIn
- Email
- CV/Resume PDF download
- itch.io

**To add more platforms:** Edit `_includes/social.html` and follow the pattern for existing icons using Font Awesome 6 icons.

---

## Navigation Tabs

**Files:** `_pages/*.md`

Navigation tabs are controlled by the front matter in each page file.

### Changing Tab Order

Edit the `nav_order` field in each page's front matter:

```yaml
---
layout: page
title: Projects      # This appears in the navigation
permalink: /projects/
nav: true           # Set to false to hide from navigation
nav_order: 1        # Lower numbers appear first (left to right)
---
```

### Current Navigation Structure

1. **Projects** (`_pages/projects.md`) - nav_order: 1
2. **Dissertation** (`_pages/dissertation.md`) - nav_order: 2
3. **CV** (`_pages/cv.md`) - nav_order: 3
4. **About** (`_pages/about.md`) - nav_order: 4

### Adding a New Tab

1. Create a new file in `_pages/` (e.g., `_pages/publications.md`)
2. Add the front matter:

```yaml
---
layout: page
title: Publications
permalink: /publications/
nav: true
nav_order: 5  # Choose position in navigation
---

# Publications

Your content here...
```

---

## About Page

**File:** `_pages/about.md`

### Profile Photo

Add a profile photo by:

1. Upload your image to `assets/img/profile.jpg`
2. Update the front matter:

```yaml
profile:
  align: right          # or 'left'
  image: /assets/img/profile.jpg
  image_circular: false # true for circular crop
  more_info: >
    <p>Your Office</p>
    <p>Your Address</p>
    <p>City, State ZIP</p>
```

### Editing Biography

Edit the markdown content below the front matter:

```markdown
---
layout: about
# ... front matter ...
---

Hi, my name is [Your Name], a [your profession] interested in...

[Your bio content here]

## Hobbies

- **Hobby 1**: Description
- **Hobby 2**: Description
```

### Social Buttons

Control social button display with:

```yaml
social: true  # Show social buttons on About page
```

---

## CV/Resume

**File:** `_data/cv.yml`

The CV page pulls data from a structured YAML file.

### CV Structure

```yaml
- title: Section Name
  type: time_table    # or 'map' or 'list'
  contents:
    - title: Position/Degree
      institution: Organization Name, Location
      year: 2020 - Present  # Leave blank to hide dates
      description:
        - Bullet point 1
        - Bullet point 2
```

### Section Types

**1. Time Table** (for Experience, Education, Projects):
```yaml
- title: Experience
  type: time_table
  contents:
    - title: Job Title
      institution: Company Name, City, State
      year: 2021 - Present
      description:
        - Achievement 1
        - Achievement 2
```

**2. Map** (for General Information):
```yaml
- title: General Information
  type: map
  contents:
    - name: Full Name
      value: Your Name
    - name: Email
      value: your.email@example.com
```

**3. List** (for Skills):
```yaml
- title: Skills
  type: list
  contents:
    - "Skill category 1: List of skills"
    - "Skill category 2: List of skills"
```

### HTML Formatting

You can use HTML tags for formatting:
- **Bold**: `<strong>text</strong>`
- **Exponents**: `2<sup>14</sup>` renders as 2¹⁴
- **Line breaks**: Use HTML for complex layouts

### Adding Your CV PDF

1. Place your PDF in `assets/cv.pdf`
2. It will automatically appear as a download button on the CV page
3. The PDF is tracked in git (not ignored) so it will be publicly accessible

---

## Projects

Projects are managed through individual markdown files in the `_projects/` directory.

### Creating a New Project

1. Create a file: `_projects/your-project.md`
2. Add front matter and content:

```yaml
---
layout: page
title: Your Project Title
description: Brief description of your project
img: /assets/img/project-thumbnail.jpg  # Optional
importance: 1           # Lower numbers appear first
category: featured      # or 'all'
github: https://github.com/username/repo  # Optional
itch_io: https://username.itch.io/game    # Optional
---

## Project Overview

Your project description in markdown...

## Features

- Feature 1
- Feature 2

## Technologies Used

- Technology 1
- Technology 2
```

### Project Categories

**Featured Projects**: Set `category: featured`
- Appears in both "Featured" and "All" sections
- Use for your best/most important work

**All Projects**: Set `category: all`
- Appears only in "All" section
- Use for other projects

### Project Fields

- **title**: Project name (required)
- **description**: Short description shown on card (required)
- **img**: Path to thumbnail image (optional)
- **importance**: Sort order - lower numbers first (required)
- **category**: `featured` or `all` (required)
- **github**: GitHub repository URL (optional)
- **itch_io**: itch.io game page URL (optional)

### Project Categories Display

**File:** `_pages/projects.md`

```yaml
display_categories: [featured, all]
horizontal: false  # true for horizontal layout
```

---

## Adding Images

### Where to Put Images

Store images in:
- `assets/img/` for general images
- `assets/img/projects/` for project images (create this folder)

### Image Formats

Supported formats: JPG, PNG, GIF, SVG

### Using Images

**In Markdown:**
```markdown
![Alt text](/assets/img/your-image.jpg)
```

**In Project Front Matter:**
```yaml
img: /assets/img/projects/project-name.jpg
```

**In Profile:**
```yaml
profile:
  image: /assets/img/profile.jpg
```

### Image Size Recommendations

- **Profile photo**: 400x400px (square)
- **Project thumbnails**: 800x600px (4:3 ratio)
- **Optimize images** for web (< 500KB each)

---

## Colors and Styling

**File:** `assets/css/custom.css`

### Main Colors

```css
/* Dark theme colors */
body {
  background: #0f1115;      /* Main background */
  color: #f1f1f1;           /* Main text */
}

a {
  color: #61dafb;           /* Links */
}

.site-header {
  background: #161920;      /* Header background */
  border-bottom: 1px solid #252a34;
}
```

### Changing Colors

Find and replace these hex color codes:

- **Primary accent**: `#61dafb` (light blue)
- **Dark background**: `#0f1115`
- **Card background**: `#171a22`
- **Border color**: `#252a34`
- **Text colors**:
  - Main: `#f1f1f1`
  - Secondary: `#bbbbbb`
  - Muted: `#aaaaaa`

### Changing Fonts

```css
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}
```

Replace with your preferred font stack or add Google Fonts.

---

## Testing Locally

### Requirements

- Ruby (version 2.5+)
- Bundler

### Setup

1. Install dependencies:
```bash
bundle install
```

2. Run local server:
```bash
bundle exec jekyll serve
```

3. View at: `http://localhost:4000`

### Live Reload

The server automatically reloads when you save changes to files.

---

## Deployment

### GitHub Pages Deployment

1. Commit your changes:
```bash
git add .
git commit -m "Update site content"
```

2. Push to GitHub:
```bash
git push
```

3. Site rebuilds automatically in 1-2 minutes
4. View at: `https://yourusername.github.io`

### Build Errors

If your site doesn't update:
1. Check GitHub Actions tab in your repository
2. Look for build errors
3. Common issues:
   - Invalid YAML syntax (use a YAML validator)
   - Missing required fields in front matter
   - Incorrect file paths

---

## Quick Reference

### File Structure

```
├── _config.yml           # Site configuration
├── _data/
│   └── cv.yml           # CV/Resume data
├── _includes/
│   ├── header.liquid    # Navigation bar
│   └── social.html      # Social media icons
├── _layouts/
│   ├── default.html     # Base layout
│   ├── about.html       # About page layout
│   ├── projects.html    # Projects listing layout
│   └── cv.html          # CV page layout
├── _pages/
│   ├── projects.md      # Projects page (homepage)
│   ├── dissertation.md  # Dissertation page
│   ├── cv.md            # CV page
│   └── about.md         # About page
├── _projects/
│   ├── 01-project.md    # Individual project files
│   ├── 02-project.md
│   └── ...
├── assets/
│   ├── css/
│   │   └── custom.css   # Styling
│   ├── img/             # Images
│   └── cv.pdf           # Your CV PDF
└── README.md
```

### Common Tasks Checklist

- [ ] Update name and description in `_config.yml`
- [ ] Add social media links in `_config.yml`
- [ ] Add profile photo to `assets/img/`
- [ ] Update About page bio in `_pages/about.md`
- [ ] Fill in CV data in `_data/cv.yml`
- [ ] Add CV PDF to `assets/cv.pdf`
- [ ] Create project files in `_projects/`
- [ ] Add project images to `assets/img/`
- [ ] Test locally with `bundle exec jekyll serve`
- [ ] Push to GitHub and verify deployment

---

## Getting Help

### Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Liquid Template Language](https://shopify.github.io/liquid/)
- [Font Awesome Icons](https://fontawesome.com/icons)

### Troubleshooting

**Problem: Changes not showing**
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- Wait 2-3 minutes for GitHub Pages rebuild
- Check GitHub Actions for errors

**Problem: YAML errors**
- Validate YAML at [yamllint.com](http://www.yamllint.com/)
- Check indentation (use spaces, not tabs)
- Ensure quotes around special characters

**Problem: Images not loading**
- Check file path (case-sensitive)
- Ensure image is in `assets/img/`
- Verify image is committed to git

---

## Advanced Customization

### Adding New Layouts

1. Create file in `_layouts/your-layout.html`
2. Extend default layout:

```html
---
layout: default
---

<div class="your-custom-class">
  {{ content }}
</div>
```

### Custom CSS

Add to `assets/css/custom.css`:

```css
/* Your custom styles */
.your-custom-class {
  /* styles here */
}
```

### Adding JavaScript

Add before `</body>` in `_layouts/default.html`:

```html
<script>
  // Your JavaScript here
</script>
```

---

**Last Updated:** December 2025
**Questions?** Check the Resources section above or open an issue in your repository.

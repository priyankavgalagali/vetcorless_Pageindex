# Quick Start: Add Visitor Badge (No Backend Required!)

If you want to add a visitor counter **immediately** without setting up a backend API, use this simple badge solution.

## Option 1: Visitor Badge (Recommended for Quick Start)

Add this to your `index.md` file right after the title:

```markdown
---
layout: default
title: OpenRAG Docs
---

![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fpriyankavgalagali.github.io%2Fvetcorless_Pageindex&label=Visitors&countColor=%23263759&style=flat)

# OpenRAG Docs

Welcome to the documentation.
```

**Replace the URL** with your actual GitHub Pages URL:
- Format: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME`
- URL encode it (replace `/` with `%2F`, `:` with `%3A`)

## Option 2: Shields.io Badge

Add this to `index.md`:

```markdown
![GitHub visitors](https://img.shields.io/badge/dynamic/json?color=informational&label=visitor%20count&query=value&url=https%3A%2F%2Fapi.countapi.xyz%2Fhit%2Fpriyankavgalagali.github.io.vetcorless_Pageindex%2Freadme)
```

## Option 3: Simple Hit Counter

Add this HTML to your `index.md`:

```html
<img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fpriyankavgalagali.github.io%2Fvetcorless_Pageindex&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=visitors&edge_flat=false"/>
```

## Customization

### Change Badge Style

For visitorbadge.io, add these parameters:
- `&style=flat` - Flat style (default)
- `&style=plastic` - Plastic style
- `&style=flat-square` - Flat square style
- `&labelColor=%23555555` - Change label background color
- `&countColor=%2379C83D` - Change count background color

### Change Badge Position

Add CSS to your `_layouts/default.html`:

```html
<style>
  .visitor-badge {
    position: fixed;
    bottom: 20px;
    right: 20px;
    z-index: 1000;
  }
</style>
```

Then wrap your badge in `index.md`:

```html
<div class="visitor-badge">
  <img src="https://api.visitorbadge.io/api/visitors?path=YOUR-URL" alt="Visitors">
</div>
```

## Which Option to Choose?

| Feature | Visitor Badge | Shields.io | Hit Counter |
|---------|--------------|------------|-------------|
| Setup Time | 1 minute | 1 minute | 1 minute |
| Unique Visitors | ✅ Yes | ❌ No (total hits) | ❌ No (total hits) |
| Customizable | ✅ Yes | ✅ Yes | ⚠️ Limited |
| Free | ✅ Yes | ✅ Yes | ✅ Yes |
| Privacy-friendly | ✅ Yes | ✅ Yes | ⚠️ Moderate |

**Recommendation**: Use **Visitor Badge** (Option 1) for the best balance of features and ease of use.

## Next Steps

After adding the badge:
1. Commit and push to GitHub
2. Wait 1-2 minutes for GitHub Pages to rebuild
3. Visit your site to see the counter
4. The count will increment with each unique visitor

## Upgrade Later

Once you're ready for more advanced analytics:
- Follow the full `GA_SETUP.md` guide to integrate Google Analytics API
- This will give you real-time data from your existing GA tracking
- You can keep the badge or replace it with the custom counter
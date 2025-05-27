# 🎨 GitHub Pages Custom Styling Guide
## Adding Inter Font and Custom Styling

## Method 1: CSS Override File (Recommended)

### Step 1: Create Custom CSS File

Create a file called `assets/css/style.scss` in your repository:

```scss
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

@import "{{ site.theme }}";

/* Apply Inter font globally */
body, html {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif !important;
  font-feature-settings: 'cv02', 'cv03', 'cv04', 'cv11';
}

/* Headings with Inter */
h1, h2, h3, h4, h5, h6 {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif !important;
  font-weight: 600;
  letter-spacing: -0.025em;
}

/* Code blocks keep monospace */
code, pre {
  font-family: 'SF Mono', Monaco, 'Cascadia Code', 'Roboto Mono', Consolas, 'Courier New', monospace !important;
}

/* Improve readability */
body {
  line-height: 1.6;
  font-size: 16px;
}

/* Better spacing for content */
.markdown-body {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem;
}

/* Style improvements */
.markdown-body h1 {
  border-bottom: 2px solid #e1e4e8;
  padding-bottom: 0.5rem;
  margin-bottom: 1.5rem;
}

.markdown-body h2 {
  border-bottom: 1px solid #e1e4e8;
  padding-bottom: 0.3rem;
  margin-top: 2rem;
  margin-bottom: 1rem;
}

/* Better table styling */
.markdown-body table {
  font-size: 14px;
}

.markdown-body table th {
  font-weight: 600;
  background-color: #f6f8fa;
}
```

### Step 2: Repository Structure

Your repository should look like this:
```
your-repo/
├── README.md
├── images/
├── assets/
│   └── css/
│       └── style.scss
└── _config.yml
```

### Step 3: Configure _config.yml

Create or update `_config.yml`:

```yaml
title: Gapteq DLC Management Platform - User Onboarding Guide
description: Complete user setup and training program for the DLC platform
theme: minima

# Enable custom CSS
plugins:
  - jekyll-feed

# Custom settings
markdown: kramdown
highlighter: rouge

# SEO and metadata
author: Gapteq Team
lang: en-US
```

---

## Method 2: Custom HTML Layout (Advanced)

### Step 1: Create Custom Layout

Create `_layouts/default.html`:

```html
<!DOCTYPE html>
<html lang="{{ site.lang | default: "en-US" }}">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <!-- Inter Font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <title>{{ page.title | default: site.title }}</title>
    <meta name="description" content="{{ page.description | default: site.description }}">
    
    <style>
      body {
        font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        font-feature-settings: 'cv02', 'cv03', 'cv04', 'cv11';
        line-height: 1.6;
        color: #24292e;
        background-color: #ffffff;
        margin: 0;
        padding: 0;
      }
      
      .container {
        max-width: 900px;
        margin: 0 auto;
        padding: 2rem;
      }
      
      h1, h2, h3, h4, h5, h6 {
        font-family: 'Inter', sans-serif;
        font-weight: 600;
        letter-spacing: -0.025em;
        margin-top: 2rem;
        margin-bottom: 1rem;
      }
      
      h1 {
        font-size: 2.5rem;
        border-bottom: 2px solid #e1e4e8;
        padding-bottom: 0.5rem;
      }
      
      h2 {
        font-size: 2rem;
        border-bottom: 1px solid #e1e4e8;
        padding-bottom: 0.3rem;
      }
      
      code {
        font-family: 'SF Mono', Monaco, 'Cascadia Code', 'Roboto Mono', Consolas, monospace;
        background-color: #f6f8fa;
        padding: 0.2em 0.4em;
        border-radius: 3px;
        font-size: 0.9em;
      }
      
      pre {
        background-color: #f6f8fa;
        padding: 1rem;
        border-radius: 6px;
        overflow-x: auto;
      }
      
      img {
        max-width: 100%;
        height: auto;
        border-radius: 6px;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        margin: 1rem 0;
      }
      
      table {
        border-collapse: collapse;
        width: 100%;
        margin: 1rem 0;
      }
      
      table th,
      table td {
        border: 1px solid #d0d7de;
        padding: 0.75rem;
        text-align: left;
      }
      
      table th {
        background-color: #f6f8fa;
        font-weight: 600;
      }
      
      blockquote {
        border-left: 4px solid #d0d7de;
        padding-left: 1rem;
        margin-left: 0;
        color: #656d76;
      }
      
      .highlight {
        background-color: #fff3cd;
        padding: 0.1em 0.3em;
        border-radius: 3px;
      }
    </style>
  </head>
  
  <body>
    <div class="container">
      {{ content }}
    </div>
  </body>
</html>
```

---

## Method 3: Quick CSS Injection (Simplest)

Add this to the top of your `README.md`:

```html
<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

body, .markdown-body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif !important;
  font-feature-settings: 'cv02', 'cv03', 'cv04', 'cv11';
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Inter', sans-serif !important;
  font-weight: 600;
  letter-spacing: -0.025em;
}
</style>
```

---

## Method 4: Using GitHub Pages Themes with Custom CSS

### Popular themes that work well with Inter:

1. **Minimal theme** with custom CSS
2. **Cayman theme** with overrides
3. **Architect theme** with Inter font

Update your `_config.yml`:

```yaml
title: Gapteq DLC Management Platform - User Onboarding Guide
description: Complete user setup and training program
theme: minima  # or cayman, architect, etc.

# Custom CSS will override theme styles
```

---

## 🎯 **Recommended Approach:**

**Use Method 1 (CSS Override File)** because:
- ✅ Clean separation of content and styling
- ✅ Easy to maintain and update
- ✅ Works with any GitHub Pages theme
- ✅ Professional appearance
- ✅ Doesn't clutter your markdown content

## 🚀 **Quick Implementation:**

1. **Create the folder structure:**
   ```
   mkdir -p assets/css
   ```

2. **Create `assets/css/style.scss`** with the CSS code above

3. **Create `_config.yml`** with theme configuration

4. **Commit and push** - your site will rebuild with Inter font!

Your documentation will now have a modern, professional look with the Inter font family. The font will load quickly and provide excellent readability across all devices. 
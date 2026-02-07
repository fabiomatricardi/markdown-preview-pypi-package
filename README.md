# 🌟 md-preview v1.1.0

[![PyPI Version](https://img.shields.io/pypi/v/md-preview.svg)](https://pypi.org/project/md-preview/)
[![Python Versions](https://img.shields.io/pypi/pyversions/md-preview.svg)](https://pypi.org/project/md-preview/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

**TRUE BOOTSTRAP RENDERING** - Headers, tables, lists, blockquotes, and code blocks all styled with authentic Bootstrap aesthetics. No more "GitHub CSS + random code theme" mismatch!

![Bootstrap Preview](https://blog.ronin.cloud/content/images/size/w2000/2022/02/markdown.png)  
*Left: Flatly theme • Right: Darkly theme (full UI consistency)*

## ✨ What Changed in v1.1.0?
| Feature | v1.0 | v1.1.0 |
|---------|------|------|
| **Headers** | GitHub style | ✅ Bootstrap typography |
| **Tables** | Basic borders | ✅ `.table-striped` + hover effects |
| **Blockquotes** | Plain italics | ✅ Bootstrap alerts with icons |
| **Lists** | Default bullets | ✅ Bootstrap spacing & semantics |
| **Code Blocks** | Only syntax colored | ✅ Full Bootstrap card styling + copy buttons |
| **Theme Scope** | Code blocks only | ✅ **ENTIRE PAGE** (true UI kit) |
| **Responsiveness** | Limited | ✅ Mobile-first Bootstrap grid |

## 🎨 Available Bootstrap Themes
| Theme | CLI Flag | Type | Best For |
|-------|----------|------|----------|
| **Cosmo** | `default` | Light | Friendly documentation |
| **Flatly** | `flatly` | Light | Modern clean interfaces |
| **Litera** | `litera` | Light | Readable long-form content |
| **Darkly** | `darkly` | Dark | Dark mode lovers (vibrant) |
| **Cyborg** | `cyborg` | Dark | Futuristic/terminal aesthetic |
| **Superhero** | `superhero` | Dark | Bold presentations |

> 💡 **All themes include**:  
> - Responsive tables with hover effects  
> - Blockquotes styled as Bootstrap alerts  
> - Consistent spacing & typography  
> - Mobile-optimized layout  
> - Syntax highlighting that matches theme mode

## 🚀 Usage
```bash
# Install updated package
pip install --upgrade .

# Preview with default Bootstrap theme (Cosmo)
md-preview README.md

# Use popular Flatly theme (clean light design)
md-preview report.md --style flatly

# Dark mode workflow
md-preview notes.md --style darkly

# See ALL elements styled consistently:
echo '# Header\n\n- List item\n\n| Table | Header |\n|-------|--------|\n| Cell  | Data   |\n\n> Blockquote\n\n```python\nprint("Code")\n```' > test.md
md-preview test.md --style cyborg
```

---

# 🌟 md-preview

Render Markdown files with beautiful, modern themes directly in your browser. Zero configuration, instant preview.

<img src='https://user-images.githubusercontent.com/11283502/116907735-a58d7280-ac4a-11eb-8dbd-b905648593f8.png'>  
*Left: GitHub Light • Right: Dracula Dark (auto-switches with OS theme)*

## ✨ Features
- 🎨 **5 gorgeous themes**: GitHub (default), Dracula, Catppuccin, Solarized, Atom
- 🌓 **Automatic dark mode** (respects OS preference)
- 💡 **Syntax highlighting** with copy buttons on code blocks
- 📱 **Fully responsive** design (mobile/desktop)
- 🔒 **No network required after first load** (CDN assets cached by browser)
- 🚀 **Blazing fast** - pure Python, no heavy dependencies
- 🌐 **Works everywhere**: Windows, macOS, Linux


> what if you have some more features to add?


### Tables rendering

#### 🌓 Recommended highlight.js Themes (via `--style` flag):
| Style Arg | Theme | Vibe |
|-----------|-------|------|
| `github` (default) | `github.min.css` | Familiar, professional |
| `dracula` | `dracula.min.css` | Dark, vibrant, developer favorite |
| `catppuccin` | `catppuccin-macchiato.min.css` | Modern pastel dark theme |
| `solarized` | `solarized-dark.min.css` | Classic low-contrast |
| `atom` | `atom-one-dark.min.css` | Smooth dark UI |

> 💡 **Pro Insight**: `github-markdown-css` **already includes dark mode** via system preference detection. Pair with a dark `highlight.js` theme (e.g., `dracula`) for full dark-mode harmony.

## 📦 Installation

### Option 1: Install as package (recommended)
```bash
pip install .
```

### Example of rendered Python code

```python
#!/usr/bin/env python3
"""
md-preview: Render Markdown files with beautiful themes in your browser
"""
import argparse
import html
import pathlib
import sys
import tempfile
import webbrowser

try:
    import markdown
except ImportError:
    print("❌ 'markdown' library not found. Install with: pip install markdown", file=sys.stderr)
    sys.exit(1)

# CORRECTED THEME MAPPINGS (verified CDN paths)
THEME_MAP = {
    "github": "github.min",
    "dracula": "dracula.min",
    "catppuccin": "catppuccin.min",  # FIXED: was catppuccin-macchiato (invalid CDN path)
    "solarized": "solarized-dark.min",
    "atom": "atom-one-dark.min",
}
DEFAULT_THEME = "github"
HIGHLIGHT_VERSION = "11.9.0"  # For cache-busting
```

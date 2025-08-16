# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Portfolio Analysis Report

### Issues Found

#### 1. **Missing Images (Critical)**
- **6 deleted portfolio images** referenced in HTML but missing from assets:
  - `assets/img/portfolio/1-6.jpg` (deleted from git)
  - These images are still referenced in portfolio modals (index.html:287, 322, 357, 392, 427, 462) and portfolio pages
  - Broken image references in both robotics.html and mechanical.html

#### 2. **Incomplete Content**
- **Lorem ipsum placeholder text** throughout:
  - About section timeline (index.html:117-157)
  - Portfolio modal descriptions (index.html:286-462)
  - Meta descriptions are empty or generic
- **Generic branding**: Still using "Agency - Start Bootstrap Theme" title
- **Placeholder copyright**: "Your Website 2023"

#### 3. **Non-functional Contact Form**
- Form requires API token (index.html:207): `data-sb-form-api-token="API_TOKEN"`
- Submit button is disabled by default
- No backend implementation

#### 4. **Path Inconsistencies**
- Mechanical.html uses inconsistent image paths:
  - Line 68: `/assets/img/Mechanical_Portfolio/` (absolute path)
  - Line 78: `assets/img/Mechanical_Portfolio/` (relative path)

#### 5. **Accessibility Issues**
- Empty alt texts: `alt="..."` throughout
- Missing aria-labels on interactive elements
- No skip navigation links
- Poor contrast on some text elements

### Functionality

#### Working Features
- **Navigation**: Responsive navbar with scroll effects
- **ScrollSpy**: Active section highlighting
- **Mobile responsive**: Bootstrap 5.2.3 responsive grid
- **Live server**: Development server via npm scripts

#### JavaScript Components
- **Navbar shrink on scroll** (js/scripts.js:13-24)
- **Bootstrap ScrollSpy** (js/scripts.js:35-39)
- **Responsive nav collapse** (js/scripts.js:42-52)
- **Bootstrap modals** for portfolio items

### Visibility Status
- **Public facing**: Ready for basic viewing
- **SEO**: Poor - missing meta descriptions, generic titles
- **Performance**: Loads external CDNs (Font Awesome, Google Fonts, Bootstrap)
- **Cross-browser**: Should work on modern browsers

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (port 3000)
npm start
# or
npm run dev

# The site will open at http://localhost:3000
```

## Architecture Overview

### File Structure
- **index.html**: Main landing page with skills, about, and contact sections
- **mechanical.html**: Mechanical engineering portfolio page
- **robotics.html**: Robotics engineering portfolio page
- **css/styles.css**: Bootstrap-based custom styles (Start Bootstrap Agency theme)
- **js/scripts.js**: Navigation and scroll behavior handlers
- **assets/**: Images, logos, and SVG assets

### Technology Stack
- **Frontend Framework**: Bootstrap 5.2.3
- **Icons**: Font Awesome 6.3.0
- **Fonts**: Google Fonts (Montserrat, Roboto Slab)
- **Dev Server**: live-server (for local development)
- **Forms**: SB Forms (requires configuration)

### Key Integration Points
1. **Navigation**: All pages share the same navbar structure - changes should be replicated across all HTML files
2. **Modals**: Portfolio modals are defined inline in index.html (lines 276-484)
3. **Contact Form**: Requires SB Forms API token configuration
4. **Image Assets**: Portfolio images should be in `assets/img/portfolio/` or respective subdirectories

## Priority Fixes

1. **Restore or replace missing portfolio images**
2. **Update all placeholder content with real information**
3. **Fix contact form or implement alternative**
4. **Standardize image paths in mechanical.html**
5. **Add proper alt texts and ARIA labels**
6. **Update page titles and meta descriptions**
7. **Replace logo placeholder (navbar-logo.svg)**
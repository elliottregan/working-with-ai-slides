# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Slidev presentation project titled "Working with AI Agents in Code" - a practical guide for developers learning AI-assisted development. The presentation is built using Slidev (https://sli.dev), a markdown-based slide deck framework powered by Vue.

## Common Commands

### Development
```bash
npm run dev
```
Starts the Slidev development server with hot reload for editing slides. Open the provided URL in a browser to view and navigate the presentation.

### Build
```bash
npm run build
```
Builds the presentation for production deployment. Creates static files in the `dist` directory that can be hosted anywhere.

### Export to PDF
```bash
npm run export
```
Exports the presentation to a PDF file using Playwright Chromium. The PDF will be generated in the root directory as `slides-export.pdf`.

## Architecture

### Slide Content
All presentation content is in `slides.md` at the root. This single markdown file contains:
- YAML frontmatter with configuration (theme, title, transitions, etc.)
- Slide content separated by `---` dividers
- Layout specifications per slide (e.g., `layout: center`, `layout: two-cols`)
- Mermaid diagrams for visualizations
- Markdown content with speaker notes in HTML comments (`<!-- notes -->`)

### Slidev Configuration
The presentation uses:
- **Theme**: `default` theme from `@slidev/theme-default`
- **MDC**: Markdown Components enabled (`mdc: true`)
- **Transitions**: Disabled (`transition: none`)
- **Drawings**: Not persisted between slides (`persist: false`)

### Key Slide Layouts Used
- `center`: Centered content for emphasis
- `two-cols`: Two-column layout with `::right::` separator
- Default layout: Standard slide with title and content

### Dependencies
- `@slidev/cli`: Core Slidev framework
- `@slidev/theme-default`: Default presentation theme
- `playwright-chromium`: For PDF export functionality

## Working with Slides

### Adding New Slides
Add slides by inserting content between `---` dividers in `slides.md`. Each slide can specify a layout:
```markdown
---
layout: center
---

# Your Slide Title
Content here
```

### Using Two-Column Layout
```markdown
---
layout: two-cols
---

# Left Column Content

::right::

# Right Column Content
```

### Adding Speaker Notes
Use HTML comments for speaker notes:
```markdown
# Slide Title

Content visible to audience

<!--
These are speaker notes, only visible in presenter mode
-->
```

### Styling and Components
- Use standard markdown for content formatting
- HTML/Vue components can be embedded directly
- Tailwind CSS classes are available for styling (e.g., `class="mt-8 p-4 bg-blue-100"`)
- Mermaid diagrams are supported for flowcharts and visualizations

## Development Workflow

1. **Edit slides**: Modify `slides.md` - changes will hot reload in the browser
2. **View presenter mode**: Press 'p' in the browser during development
3. **Test export**: Run `npm run export` before committing to ensure PDF generation works
4. **Build for deployment**: Run `npm run build` to create production assets in `dist/`

## Git Workflow

This project uses a standard git workflow with `main` as the primary branch. The repository includes built slide assets for deployment.

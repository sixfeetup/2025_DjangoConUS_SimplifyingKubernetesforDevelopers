# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Reveal.js presentation repository for "Simplifying Kubernetes for Developers" - a 5-minute lightning talk for DjangoCon US 2025 by Calvin Hendryx-Parker. The talk targets a technical audience who are skeptical of Kubernetes and commonly complain that "Kubernetes is too complicated." The presentation showcases Six Feet Up's Scaf tool as a complete solution that combines project bootstrapping with Tilt for streamlined Kubernetes development.

### Talk Context
- **Duration**: 5 minutes (lightning talk format)
- **Audience**: Technical developers skeptical of Kubernetes complexity
- **Key Message**: Kubernetes isn't too complicated - it just needs better bootstrapping and developer tooling
- **Solution Focus**: Six Feet Up's Scaf tool + Tilt integration for "zero to full-stack Kubernetes in minutes"

### Six Feet Up Scaf Integration
The presentation highlights Scaf as Six Feet Up's open-source project template management tool that:
- Bootstraps complete Django + Kubernetes projects with `scaf myproject`
- Includes pre-configured Tilt integration for instant development workflows
- Provides production-ready templates with monitoring, CI/CD, and multi-environment support
- Eliminates both setup complexity and development friction

The project builds HTML presentations from Markdown source files using Pandoc and includes custom themes.

## Common Commands

### Development Setup
```bash
# Install LTS version of Node.js
nvm install --lts

# Build and start the presentation server
make start
```

### Build Commands
```bash
# Build presentation HTML
make index.html

# Start development server (builds first)
make start

# Watch for changes and rebuild automatically
make watch

# Clean up generated files
make clean

# Show all available make targets
make help
```

### Dependencies
- nvm (Node Version Manager)
- pandoc (for Markdown to HTML conversion)
- bsdtar (part of libarchive-tools package on Ubuntu)
- watchdog (Python package for file watching)

## Project Structure

### Core Files
- `slides.md` - Main presentation content in Pandoc Markdown format
- `Makefile` - Build system with targets for building, watching, and serving
- `tricks.yaml` - Watchdog configuration for auto-rebuilding on file changes

### Content Organization
- `images/` - Presentation assets (background images, logos)
- `themes/` - Custom Reveal.js SCSS theme files
- `research.md` - Draft content and speaker notes (not part of the presentation)

### Build Process
1. Pandoc converts `slides.md` to `index.html` using Reveal.js
2. Custom themes from `themes/` are compiled to CSS
3. Reveal.js framework is downloaded and configured automatically
4. GitHub Actions deploys the presentation to GitHub Pages

### Theme System
- Default theme: `wildclouds` (configurable in Makefile)
- Custom themes in `themes/` directory as SCSS files
- Themes are compiled during build process

## Development Workflow

The typical workflow involves:
1. Edit `slides.md` for presentation content
2. Use `make watch` for live reloading during development  
3. Use `make start` to build and serve locally
4. Push to main branch triggers automatic GitHub Pages deployment

The presentation uses Pandoc's reveal.js output format with custom configuration for optimal presentation display.
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Comedy Prague is a Jekyll-based static website listing English stand-up comedy shows in Prague. It is hosted on GitHub Pages:
https://comedyprague.cz

### Standalone Pages

Invividual comedy shows can have their own standalone pages
indepependent on the main page (TODO except optional header strip
on the top, if specific layout is used)

For example, the `/tykavo/` directory contains a standalone page (`layout: null`) with its own complete HTML, Tailwind config, and JavaScript. It has its own images in `tykavo/img/`.


## Commands

```bash
# Install dependencies
bundle

# Run local development server
bundle exec jekyll serve
```

The site builds to `_site/` directory.

## Architecture

### Data-Driven Shows Listing

The main page (`index.html`) displays comedy shows grouped by day of the week. Show data is stored in `_data/shows.yml` as a YAML array with fields:
- `name`, `day`, `time`, `frequency`
- `venueName`, `venueAddress`, `venueUrl`
- `type` (open mic, showcase)
- `cost`, `ticketsUrl`
- `url` (optional link to show's own page)

### Layout Structure

- `_layouts/default.html` - Base HTML structure with Tailwind CSS (via CDN)
- `_layouts/page.html` - Extends default, adds optional page title
- `_includes/navigation.html` - Site navigation
- `_includes/head.html` - HTML head with meta tags

### Styling

- Main site uses Tailwind CSS via CDN
- Custom styles in `style.css`
- Tykavo page uses dark mode Tailwind with inline configuration

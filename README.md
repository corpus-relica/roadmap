see it live at [https://corpus-relica.github.io/roadmap/](https://corpus-relica.github.io/roadmap/)

# CRG Roadmap

A clean, visually appealing web-based project roadmap that displays development milestones and planned features for the Corpus Relica Group projects.

## Overview

This project is a single-page HTML application that presents a timeline-style roadmap showing completed, in-progress, and planned features across multiple quarters. It serves as a living document for stakeholders, team members, and users to understand the project's development trajectory.

## Features

- **Dense Ledger Layout**: Compact status-glyph rows instead of cards — the full timeline fits in roughly one desktop screen
- **Status Indicators**: ✓ shipped (green), ◆ in progress (amber), ○ planned (cyan), with a legend in the masthead
- **RELICA Design Language**: Matches relica.io — dark terminal palette (#0A0E12 / #00D9FF), STIX Two Text headings, Inter body, Martian Mono meta, Departure Mono micro-labels, scanline overlay
- **Single Readable Column**: Quarters stack in one ~860px column for a calm chronological read
- **YAML-Driven**: Roadmap content lives in `roadmap.yaml`; `index.html` renders it client-side via js-yaml

## Technology Stack

- HTML5 / CSS3 (single self-contained page)
- js-yaml (CDN) for parsing `roadmap.yaml`
- Git for version control

## Usage

Serve the directory over HTTP (the YAML is fetched at runtime, so `file://` won't work):

```
python3 -m http.server 8000
```

## Project Structure

```
roadmap/
├── index.html                     # Roadmap page (markup, styles, renderer)
├── roadmap.yaml                   # Roadmap content — edit this
├── DepartureMono-Regular.woff2    # Self-hosted micro-label font
└── README.md                      # This file
```

## Maintenance

To update the roadmap, edit `roadmap.yaml`. Each quarter has a `name`, optional `date`, and `items` with optional `title`, `description`, and `status` (`done` / `in-progress` / `planned`).

## Note

This roadmap is subject to change based on priorities, resources, and feedback. It represents current plans and aspirations rather than firm commitments.

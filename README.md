---
layout: 'page'
uri: '/'
position: 1
slug: 'home'
navTitle: 'Quick start'
title: 'Documan.ai'
description: 'A tool that spins up a web documentation site from your project''s Markdown files, installed and launched via a single command — includes a live MCP server for Claude Code CLI, Cursor IDE, and more.'
---

# Documan.ai

## Quick Start

### 1. Installation

**Download from GitHub Releases:** https://github.com/documan-ai/documan/releases and copy the downloaded binary
to the root of your project.

### 2. Configuration

**Locally:** Create or edit a `.env` file in your project:

```bash
DOCUMAN_PROJECT_NAME=Documan.ai
DOCUMAN_DOCS_FILES=docs/**/*.md,README.md
DOCUMAN_DB_PATH=.documan/db/docs.db
DOCUMAN_HTTP_PORT=3000
```

### 3. Fix Frontmatter

```bash
./documan fix
```

This command automatically scans all documentation files, reorders existing frontmatter fields to the standard order, and generates missing fields (`slug`, `uri`, `title`, `navTitle`, `layout`) based on the file path and content. This ensures all your Markdown files have the required metadata in a consistent format.

### 4. Lint Documentation

```bash
./documan lint
```

Validates all markdown files without modifying anything. Checks for required frontmatter fields, duplicate slugs/URIs, circular parent references, and broken internal links. Useful for CI/CD pipelines.

### 5. Import Documentation

```bash
./documan import
```

This imports your documentation into the database for indexing and search.

### 6. Start Server

```bash
./documan serve
```

- Web server: `http://localhost:3000`
- MCP server: `http://localhost:3000/mcp` (HTTP + Streamable HTTP)

### 7. And that's it!

You can now view your documentation in the browser at `http://localhost:3000`, or register the MCP server (not implemented yet) to your AI coding tools to enable semantic search directly from Claude Code, Cursor, or other MCP-compatible tools.

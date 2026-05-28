# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for blitherocher.com — a Jekyll static site hosted on GitHub Pages.

## Commands

- **Serve locally:** `bundle exec jekyll serve` (site available at http://localhost:4000)
- **Build:** `bundle exec jekyll build` (outputs to `_site/`)
- **Install dependencies:** `bundle install`
- **Create a new blog post:** `rake post title="My Post Title"` (optionally `date="YYYY-MM-DD"`)

## Architecture

- **Jekyll 4.4** with Ruby 3.1.1; only plugin is `jekyll-feed`
- Two layouts in `_layouts/`: `default.html` (full page shell with header/nav/footer) and `post.html` (identical structure, used for blog posts). Both layouts contain the complete HTML document including `<head>`, Google Analytics, header with navigation, and footer — they do not nest into each other despite their front matter suggesting otherwise.
- Pages: `index.html` (about/bio), `blog.html` (post listing via Liquid loop), `resume.html`
- Blog posts live in `_posts/` as HTML files (not Markdown) with `layout: post` front matter
- Static assets served from `stylesheets/`, `javascripts/`, and `images/`; some images hosted externally on S3
- `static.json` configures clean URLs and HTTPS with `_site/` as root
- `CNAME` points to blitherocher.com

## Deployment

Pushes to `master` deploy automatically via GitHub Pages.

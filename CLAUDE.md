# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page personal "About" site for Mohammed Muzammil Bhurani (MMB). The whole site is one self-contained file, `index.html`, with inline CSS and JS. There is no build step, package manager, linter, or test suite. To preview, open `index.html` in a browser (or serve the folder with any static server). Deployment is static hosting from `main`; a CNAME file was added and later deleted in git history, so don't assume a custom domain is configured.

## Structure of `index.html`

- **Theming:** colors are CSS variables on `:root`, overridden in a `prefers-color-scheme: dark` block. The accent differs per scheme (orange in light, golden in dark), so change both blocks when adjusting the palette.
- **Sections:** a single `.card` containing intro, "What I do" (an `.info-card` plus the video grid), and Contact links.
- **Video grid:** `#videos` is empty in the HTML and populated by the inline script from the `shorts` array of `[youtubeVideoId, label]` pairs. To add an episode, prepend an entry to that array (newest first). Thumbnails come from `i.ytimg.com/.../frame0.jpg`, falling back to `hqdefault.jpg` on error.
- **Placeholders:** the Instagram contact link still points to `https://instagram.com/your-handle`. Replace it when the real handle is known.
- The footer year is set at runtime from `new Date().getFullYear()`.

## Working Rules

1. Always check for API key leakage in the frontend.
2. Make changes in small steps.
3. After every change, ask the user whether to commit.
4. Review code thoroughly while writing it; the website must not crash.
5. After every change, first check your own work for errors, and report any you find to the user.

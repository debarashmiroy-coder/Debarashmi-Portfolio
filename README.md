# Debarashmi Roy — Portfolio

Static site, ready to deploy as-is to any static host (Netlify, Vercel, GitHub Pages, S3/CloudFront, etc).

## Structure

```
index.html                        Home page
ai-interviews.html                Case study
ai-assessment-creation.html       Case study
access-management-system.html     Case study
trainer-management-system.html    Case study
live-chat-experience.html         Case study
resume.html                       Resume
support.js                        Shared runtime (loads React/ReactDOM/Babel from unpkg at runtime)
assets/                           Images used across all pages
```

## How it's built

Each page is a single self-contained HTML file — styling is inline (no separate .css files by design), and per-page interactivity is embedded in a `<script type="text/x-dc">` block compiled at load time by `support.js`. `support.js` pulls React, ReactDOM, and Babel Standalone from unpkg over HTTPS the first time a page loads, so an internet connection is required at runtime (no build step, no bundler, no server needed).

## Deploying

Upload this whole folder as-is to any static host, with `index.html` as the site root. No build command needed — just point the host at this directory.

## Editing

Colors/spacing/layout are inline styles inside each HTML file. Content copy is in the same files, plus a few `const ARRAY = [...]` blocks near the bottom of each file (inside the `<script type="text/x-dc">` tag) that drive repeated content like FAQ accordions and stat lists.

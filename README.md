# Lab Pages

A public collection of small, static, browser-based utilities and experiments.

This repo is published with GitHub Pages at:

https://jaballadares.github.io/lab-pages/

## Purpose

`lab-pages` is a lightweight home for useful one-page tools, prototypes, and experiments that are easier to run in a browser than as local scripts or full applications.

The guiding idea: if a tiny HTML page is useful enough to reuse across machines, it belongs here.

Good candidates include:

- clipboard/paste utilities
- data formatting and transformation helpers
- LLM workflow helpers
- visual debugging tools
- small browser experiments
- self-contained demos or games

This is intentionally not a polished product repo. It is a practical collection of browser-native lab tools.

## Current Pages

| Page | URL | Purpose |
|---|---|---|
| Lab Pages Home | https://jaballadares.github.io/lab-pages/ | Landing page for all tools |
| Hex Color Notepad | https://jaballadares.github.io/lab-pages/hexcolor-notepad/ | Paste text containing hex colors and preview detected colors |
| Data Playground | https://jaballadares.github.io/lab-pages/data-playground/ | Paste JSON/CSV/text, then transform it with JavaScript |
| OpenAPI LLM Formatter | https://jaballadares.github.io/lab-pages/openapi-llm-formatter/ | Convert OpenAPI YAML/JSON into compact LLM-ready text |
| Cosmic Cannonball | https://jaballadares.github.io/lab-pages/cosmic-cannonball/ | Canvas gravity slingshot game / experiment |

## Repo Structure

Each tool lives in its own directory and should expose an `index.html` file:

```txt
lab-pages/
  index.html
  README.md
  hexcolor-notepad/
    index.html
  data-playground/
    index.html
  openapi-llm-formatter/
    index.html
  cosmic-cannonball/
    index.html
```

## Adding a New Page

1. Create a new folder using a URL-friendly name:

   ```bash
   mkdir my-new-tool
   ```

2. Add an `index.html` inside it:

   ```txt
   my-new-tool/index.html
   ```

3. Add a link to the root `index.html` landing page.

4. Commit and push:

   ```bash
   git add .
   git commit -m "Add my new tool"
   git push
   ```

GitHub Pages will rebuild automatically.

## Design Notes

- Prefer self-contained static pages.
- CDN dependencies are acceptable for quick tools, but avoid unnecessary build steps.
- Keep page routes stable once referenced by external shortcuts, Raycast commands, bookmarks, etc.
- If a tool accepts injected text via URL hash, prefer this pattern:

  ```txt
  /tool-name/#text=<url-encoded-text>
  ```

- For personal workflow integrations, keep the integration script outside this repo unless it is broadly reusable.

## Related Local Integration

The Hex Color Notepad is currently used by a Raycast Script Command that reads clipboard text and opens:

```txt
https://jaballadares.github.io/lab-pages/hexcolor-notepad/#text=<encoded clipboard>
```

Local Raycast script path:

```txt
/Users/johnb/Library/Mobile Documents/com~apple~CloudDocs/raycast-script-commands/open-hex-notepad-from-clipboard.sh
```

## Deployment

This repo uses GitHub Pages from the `main` branch root.

Repository:

https://github.com/Jaballadares/lab-pages

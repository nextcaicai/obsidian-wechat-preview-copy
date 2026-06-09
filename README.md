# WeChat Preview Copy

An Obsidian plugin that opens a right-sidebar preview for the active Markdown note and copies rich HTML for WeChat Official Account.

## Features

- Preview the currently active Markdown note in a right sidebar view.
- Keep the preview synchronized with the active file and editor changes.
- Copy rendered HTML to the clipboard with inline styles.
- Apply a target-platform copy profile. The first profile is tuned for WeChat Official Account article layout.
- Embed local vault images as `data:` URLs so the clipboard does not depend on Obsidian local resource paths.
- Also writes a Markdown/plain-text fallback to the clipboard.

## Copy profiles

The copy pipeline renders Markdown with Obsidian first, then applies a target-platform profile before writing HTML to the clipboard. A profile owns the platform-specific inline styles and DOM cleanup rules for headings, paragraphs, lists, tables, code blocks, images, callouts, and links.

Current profile:

- `wechat`: WeChat Official Account article layout.

Future platforms can be added by extending `PLATFORM_PROFILES` in `src/main.ts`.

## Development

```bash
npm install
npm run dev
```

For manual installation, copy `manifest.json`, `main.js`, and `styles.css` into:

```text
<Vault>/.obsidian/plugins/wechat-preview-copy/
```

Reload Obsidian and enable the plugin from Community plugins.

## Notes

WeChat Official Account paste behavior is controlled by the WeChat editor. This plugin prepares self-contained HTML with embedded local images and inline styles, which is the most portable clipboard format Obsidian can provide without uploading assets to a remote image host.

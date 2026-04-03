# Harness Apps Shared

Shared frontend assets for apps built on [a-simple-llm-harness](https://github.com/chuckfinca/a-simple-llm-harness).

## Files

- **`chat-ui.js`** — Markdown rendering, citation superscripts, Gradio API helper, source list rendering
- **`chat-ui.css`** — Chat UI styles with CSS custom property fallbacks

## Usage

Apps fetch these at Docker build time:

```dockerfile
RUN curl -sL https://raw.githubusercontent.com/chuckfinca/harness-apps-shared/main/chat-ui.js -o /app/static/chat-ui.js
RUN curl -sL https://raw.githubusercontent.com/chuckfinca/harness-apps-shared/main/chat-ui.css -o /app/static/chat-ui.css
```

Then include in HTML:

```html
<link rel="stylesheet" href="/static/chat-ui.css" />
<script src="/static/chat-ui.js"></script>
```

CSS custom properties use fallback values, so the file works standalone or with a design system that defines `--neutral-200`, `--primary`, etc.

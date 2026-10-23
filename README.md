<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://ai.google.dev/static/site-assets/images/share-ais-513315318.png" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/8308df34-98f1-4e64-b61a-2125bb3be278

## Run Locally

**Prerequisites:**  Node.js


1. Install dependencies:
   `npm install`
2. Set the `GEMINI_API_KEY` in [.env.local](.env.local) to your Gemini API key
3. Run the app:
   `npm run dev`

## Engineering-fidelity regression checks

The candidate repair package adds a regression-test entry point. After installing dependencies and installing Bun, run:

```bash
bun install
bun run lint
bun run build
bun run test:fidelity
```

`test:fidelity` checks flowchart classification, formula-parser regressions, response-spectrum parameter completeness, and DOCX export smoke tests. The attachment-based script uses representative Markdown for DOCX generation; it does **not** run OCR or translation end-to-end. These checks do not replace visual acceptance in Microsoft Word desktop, especially for complex flowchart topology and equations.

See `CHANGELOG_FIDELITY_FIXES.md` and `TEST_STATUS.md` for the changes and current verification boundaries.

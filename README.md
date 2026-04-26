# Chrome Store Screenshots

An AI skill for generating production-ready Chrome Web Store screenshots. Built for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Cursor, Windsurf, and other AI-powered coding agents.

Based on [ParthJadhav/app-store-screenshots](https://github.com/ParthJadhav/app-store-screenshots), adapted for browser extensions.

![License](https://img.shields.io/badge/license-MIT-blue)

## What it does

- Asks about your extension's brand, features, and style
- Scaffolds a minimal Next.js project
- Designs each screenshot as a **marketing ad**, not a UI showcase
- Writes copy using proven store listing patterns
- Renders at exact Chrome Web Store dimensions
- Exports PNGs ready to upload

## Why this exists

App Store screenshot tools assume mobile: vertical layouts, phone frames, portrait orientation. Chrome Web Store needs **1280x800 horizontal banners** with no device frame. This skill fills that gap.

## Export sizes

| Target | Resolution |
|---|---|
| Chrome Web Store (screenshot) | 1280 x 800 |
| Chrome Web Store (small promo tile) | 440 x 280 |
| Chrome Web Store (marquee promo tile) | 1400 x 560 |

## Install

### Using npx skills (recommended)

```bash
npx skills add jrbayguade/chrome-store-screenshots
```

Works with Claude Code, Cursor, Windsurf, OpenCode, Codex, and [40+ other agents](https://github.com/vercel-labs/skills#available-agents).

Install globally (available across all projects):

```bash
npx skills add jrbayguade/chrome-store-screenshots -g
```

Install for a specific agent:

```bash
npx skills add jrbayguade/chrome-store-screenshots -a claude-code
```

### Manual (git clone)

```bash
git clone https://github.com/jrbayguade/chrome-store-screenshots ~/.claude/skills/chrome-store-screenshots
```

## Usage

Once installed, the skill triggers automatically when you ask your agent to:

- Build Chrome Web Store screenshots
- Generate marketing screenshots for a browser extension
- Create store listing graphics for my Chrome extension

Or just tell it what you need:

```
> Build Chrome Web Store screenshots for my extension
```

The agent will ask about your extension's features, brand colors, target audience, and style before building anything.

### Good starting prompts

These give the agent enough context while leaving room for the skill to guide design:

```
Build Chrome Web Store screenshots for my Gmail productivity extension.
It tracks email follow-ups and reminds you when to nudge.
I want 5 slides, clean style, warm neutrals, and a professional feel.
```

```
Generate store screenshots for my tab manager extension.
Key features: group tabs by project, search across all tabs, keyboard shortcuts.
Dark mode aesthetic, 5 slides, developer audience.
```

## What gets scaffolded

```
project/
├── public/
│   ├── screenshots/       # Your extension UI PNGs
│   └── exports/           # Final exported PNGs
├── src/app/
│   ├── layout.tsx         # Font setup
│   └── page.tsx           # Screenshot generator (single file)
├── package.json
└── ...
```

The entire generator is a **single `page.tsx` file**. Run the dev server, open the browser, click any screenshot to export it as a PNG.

## Slide archetypes

The skill uses 5 default archetypes. You can override any of them.

| Slide | Purpose | Background |
|---|---|---|
| 1. Hero | Brand intro, logo, main value prop | Warm / light |
| 2. Trigger | How to activate (zero friction) | Dark |
| 3. Value delivery | The "wow" moment, output shown | Light / neutral |
| 4. Power features | Dashboard, analytics, PRO tier | Dark accent |
| 5. Trust | Privacy, security, social proof | Split / white |

## Design principles

- **Screenshots are ads, not docs.** Each slide sells one idea.
- **Thumbnail-first.** All text readable at 640x400 (Chrome Web Store preview size).
- **No device frames.** Browser extensions are not mobile apps. The UI floats directly on the background.
- **Layout variety.** No two adjacent slides share the same composition.
- **Real UI only.** Product mockups use your actual extension screenshots, not generic components.

## Tech stack

| Dependency | Purpose |
|---|---|
| Next.js | Dev server + static image serving |
| TypeScript | Type safety |
| Tailwind CSS | Styling |
| html-to-image | PNG export at exact resolutions |
| React | Component composition |

## Requirements

- Node.js 18+
- One of: bun, pnpm, yarn, or npm (detected automatically)

## Credits

Adapted from [ParthJadhav/app-store-screenshots](https://github.com/ParthJadhav/app-store-screenshots). The original skill generates iOS App Store and Google Play screenshots. This fork adapts the concept for Chrome Web Store's horizontal format.

## License

MIT


Example:
<img alt="01_hero" src="https://github.com/user-attachments/assets/ed1b94a5-9771-46c8-8df7-c5e14c808a10" />

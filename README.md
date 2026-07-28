# Padel — Vessel Theme

Shopify theme development for the **Vessel** theme (v3.5.1), customized for the Padel store.

**Dev store:** [padeldev.myshopify.com](https://padeldev.myshopify.com/)

## Prerequisites

- **Node.js** 18.12+ (20+ recommended for newer Shopify CLI versions)
- **Git**
- Access to the padeldev store via Shopify Partners or staff account

## Setup

### 1. Install dependencies

```bash
npm install
```

This installs Shopify CLI locally (no global install required).

### 2. Log in to Shopify

Run the dev server in your terminal — the CLI will open a browser window to authenticate:

```bash
npm run theme:dev
```

On first run you'll be prompted to log in with your Shopify Partners or store account. Credentials are saved locally in `~/.config/shopify/`.

The dev store is already configured in `shopify.theme.toml`:

```toml
[environments.default]
store = "padeldev.myshopify.com"
```

## Common commands

| Command | Description |
|---------|-------------|
| `npm run theme:dev` | Start live preview — changes sync to a development theme in real time |
| `npm run theme:push` | Push local theme files to padeldev |
| `npm run theme:push:unpublished` | Push as a new unpublished theme in your theme library |
| `npm run theme:pull` | Pull remote theme files down to your local project |
| `npm run theme:list` | List all themes on padeldev |
| `npm run theme:check` | Run Theme Check linter on your theme |

## Workflow

1. **Develop locally** — `npm run theme:dev` uploads your theme as a dev theme and hot-reloads changes
2. **Commit to Git** — push changes to this repo (GitHub + Shopify app integration can sync to padeldev)
3. **Deploy** — `npm run theme:push:unpublished` to create a reviewable theme, or `npm run theme:push -- --theme THEME_ID` to update an existing one

## Project structure

Standard Shopify Online Store 2.0 theme layout:

```
assets/      CSS, JS, images
blocks/      Theme blocks
config/      settings_schema.json, settings_data.json
layout/      theme.liquid, password.liquid
locales/     Translation files
sections/    Theme sections
snippets/    Reusable Liquid snippets
templates/   JSON page templates
```

## Upgrading Node.js (optional)

Shopify CLI 4.x requires Node 22+. This project pins CLI 3.60.0 which works on Node 18. To upgrade:

```bash
# Using nvm (recommended)
nvm install 22
nvm use 22
npm install @shopify/cli@latest --save-dev
```

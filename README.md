# fuck_translate

A browser extension that strips the `?tl=` query parameter from Reddit URLs, preventing unwanted auto-translation that Reddit applies for regional or logged-out users.

## How it works

Uses the Manifest V3 `declarativeNetRequest` API to declaratively remove the `tl` query parameter from Reddit requests. No background scripts, no content scripts, no JavaScript -- just JSON configuration.

The rule fires only on `reddit.com` (including all subdomains like `old.reddit.com`, `www.reddit.com`, etc.) and only for page navigations. When no `tl` parameter is present, the rule is a no-op.

## Install

### Chrome

1. Run `task build` (see Build section below)
2. Open `chrome://extensions`
3. Enable "Developer mode"
4. Click "Load unpacked" and select the `dist/chrome/` directory

### Firefox

1. Run `task build`
2. Open `about:debugging#/runtime/this-firefox`
3. Click "Load Temporary Add-on..."
4. Select `dist/firefox/manifest.json`

## Build

Requires [Task](https://taskfile.dev/) and `zip`.

```sh
task build
```

This produces:
- `dist/fuck_translate-chrome.zip`
- `dist/fuck_translate-firefox.zip`

Other commands:
- `task clean` -- remove the `dist/` directory
- `task build:chrome` -- build Chrome zip only
- `task build:firefox` -- build Firefox zip only

## Permissions

- `declarativeNetRequest` -- required to register URL rewrite rules
- `*://*.reddit.com/*` -- host permission scoped to Reddit only; the extension does not access any other sites

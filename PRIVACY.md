# Privacy Policy -- f_translate

**Last updated:** 2026-03-16

## Data Collection

f_translate does not collect, store, transmit, or process any user data. No personal information, browsing history, cookies, or analytics are gathered.

## How It Works

The extension uses the browser's built-in `declarativeNetRequest` API to remove the `tl` query parameter from Reddit URLs. This happens entirely within the browser before the page loads. No network requests are made by the extension, and no data leaves your device.

## Permissions

- **declarativeNetRequest** -- Used to register a URL rewrite rule that strips the `tl` parameter. No data is read or stored.
- **Host permission (reddit.com)** -- Scoped to Reddit only. Required so the rewrite rule can match Reddit URLs. No page content is accessed.

## Remote Code

The extension does not execute any JavaScript. It contains no background scripts, content scripts, or remote code. All logic is defined declaratively in static JSON configuration files.

## Third Parties

No data is shared with third parties. The extension does not communicate with any external servers.

## Changes

If this policy changes, the update will be published in this repository.

## Contact

For questions about this policy, open an issue in the repository.

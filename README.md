# FF Icon Extractor

A lightweight, frontend-only utility for scanning, previewing and downloading Free Fire icon assets using sequential asset IDs.

## What it does

- Selects **Advance** or **Live** server
- Selects an OB version
- Selects an asset category
- Generates category-aware asset IDs
- Scans sequential IDs until the configured stopping condition
- Displays discovered assets in a grid
- Copies asset IDs
- Downloads individual assets through browser-side Blob handling

## Workflow

```text
Server + OB + Category
        ↓
ID generation
        ↓
Sequential asset requests
        ↓
Available assets
        ↓
Preview → Copy ID / Download
```

## Tech stack

- HTML
- CSS
- Vanilla JavaScript
- No framework or build step

## Running locally

Clone the repository and open the HTML entry point in a modern browser, or serve the directory through a static HTTP server.

For the most reliable browser behavior, use HTTPS/static hosting rather than relying on `file://` URLs.

## Important limitations

This is a frontend application. CDN requests are visible to the browser and can be inspected through developer tools. The application therefore **does not and cannot hide the underlying asset URLs**.

Browser download behavior also varies between mobile and desktop browsers.

The current project does not provide ZIP export or screenshot generation.

## Security clarification

Blob-based downloads prevent the application from intentionally navigating the user to an asset URL, but they are **not a mechanism for hiding the CDN URL**. True URL mediation would require a backend/proxy architecture.

## Asset ownership

Free Fire names, icons and other game assets belong to their respective rights holders, including Garena. This repository is for the source code and educational/reference use; it does not claim ownership of third-party game assets.

## Status

The frontend implementation is intentionally feature-focused. Further changes should be driven by concrete bugs or a backend architecture rather than adding cosmetic features.

## License

See the repository license for source-code licensing terms.

## Author

**Mohith Krishnaa** — [@mohith-krishnaa](https://github.com/mohith-krishnaa)

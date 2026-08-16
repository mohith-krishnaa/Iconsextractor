# FF Icon Extractor

A browser-based utility for scanning known Free Fire asset-ID patterns and previewing matching PNG icons.

**Live Demo:** https://mohith-krishnaa.github.io/Iconsextractor/

> **Status:** Unofficial research utility. Asset IDs and CDN behavior can change at any time.

## Features

- Advance / Live server selection
- OB version selection (currently OB 40–60 in the UI)
- Category-based asset-ID generation
- Sequential asset probing
- Automatic stop after consecutive misses
- Live found-count and scan status
- Progress indicator
- Manual scan stop
- Clear results
- Responsive icon preview grid

## How scanning works

```text
Server + OB + Category
          ↓
Generate candidate asset ID
          ↓
Request PNG
          ↓
Found → display in grid
Missing → increase miss counter
          ↓
40 consecutive misses → move to next pattern / finish
```

## Running locally

No build system or framework is required.

1. Clone the repository.
2. Open `index.html` in a modern browser, or serve the directory with a local static server.
3. Select the server, OB version and category.
4. Click **Scan**.

## Technical notes

The application uses browser `Image` loading to probe candidate PNG URLs. Requests are made directly from the user's browser to the configured asset host.

The current implementation does not provide a backend proxy, ZIP exporter, screenshot exporter, or asset-ID clipboard button.

## Limitations

- This is not an official Garena tool.
- Asset availability depends on third-party game infrastructure.
- Large scans can create many network requests and may be slow or rate-limited.
- CDN URLs are visible to the browser and can be inspected with developer tools.
- Hard-coded ID patterns require updates when asset conventions change.

## Asset ownership

Free Fire and related game assets belong to their respective rights holders, including Garena. This repository is for the source code and educational/reference purposes and does not claim ownership of third-party assets.

## License

See the repository's license for source-code licensing terms.

## Author

**Mohith Krishnaa** — [@mohith-krishnaa](https://github.com/mohith-krishnaa)

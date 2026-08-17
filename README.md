# FF Icon Extractor

A browser-based research utility for scanning configured Free Fire asset-ID patterns and previewing matching PNG icons.

**Live Demo:** https://mohith-krishnaa.github.io/Iconsextractor/

> **Unofficial tool:** This project is independent of Garena. Asset IDs, CDN behavior and game-version patterns can change without notice.

## Features

- Advance / Live server selection
- OB version selection (currently OB 40–60 in the UI)
- Category-based asset-ID generation
- Sequential candidate scanning
- Automatic stop after consecutive misses
- Live found-count and scan status
- Progress indicator
- Manual scan cancellation
- Responsive preview grid

## Scan flow

```text
Server + OB + Category
          ↓
Generate candidate ID
          ↓
Probe configured asset URL
      ↙           ↘
   Found         Missing
     ↓              ↓
  Preview       Miss counter
                    ↓
             Stop / next pattern
```

## Run locally

No build system or framework is required.

```bash
git clone https://github.com/mohith-krishnaa/Iconsextractor.git
cd Iconsextractor
```

Open `index.html` in a modern browser, or serve the directory with a local static server.

## Technical notes

The application uses browser image loading to probe candidate PNG URLs. Requests are made directly from the user's browser to the configured third-party asset host.

That means the browser can inspect the requested CDN URLs. **A frontend-only application cannot secretly proxy or hide those URLs.** A backend would be required for that architecture.

The current implementation intentionally does not claim to provide ZIP export, screenshot export, or server-side URL protection.

## Limitations

- This is not an official Garena tool.
- Large scans can generate many network requests and may be slow or rate-limited.
- CDN availability can change independently of this repository.
- Hard-coded asset patterns require maintenance when conventions change.
- A successful request does not establish ownership or licensing rights for the returned asset.

## Asset ownership

Free Fire and related game assets belong to their respective rights holders, including Garena. This repository provides source code for a research/educational browser utility and does not claim ownership of third-party assets.

## License

See `LICENSE` for the source-code licensing terms.

## Author

**Mohith Krishnaa** — [@mohith-krishnaa](https://github.com/mohith-krishnaa)

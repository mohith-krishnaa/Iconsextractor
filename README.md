# FF Icon Extractor

A lightweight browser-based utility for scanning known Free Fire asset-ID patterns and previewing matching PNG icons.

> **Status:** Experimental / unofficial research utility. Asset IDs and CDN behavior can change at any time.

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

## Current asset categories

The current implementation contains patterns for categories including:

- Bundle
- Tops / Bottoms / Shoes
- Head Mask / Face Paint
- Weapons / Collab Frame / Skywing
- Avatar / Banner / Profile Pin / Battle Card
- Emotes / Super Emote / Final Shot
- Vehicle / Surfboard / Parachute / Arrival Animation
- Lobby Music / Backpack
- Token / Exchange Token
- Pet / Pet Skill / Pet Skin / Pet Emote
- Characters
- Loot Box / Choice Crate / Loot Crate
- Hyper Book / Look Changer / Skill Skin

The patterns live directly in `index.html` and may require maintenance when asset conventions change.

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

The current scanner uses **40 consecutive misses** as its stopping threshold.

## Running locally

No build system or framework is required.

1. Clone the repository.
2. Open `index.html` in a modern browser, or serve the directory with a local static server.
3. Select the server, OB version and category.
4. Click **Scan**.

A local HTTP/HTTPS server is generally more reliable than opening the file directly with `file://`.

## Technical notes

The application uses browser `Image` loading to probe candidate PNG URLs. This means requests are made directly from the user's browser to the configured asset host.

The current implementation **does not provide a backend proxy, ZIP exporter, screenshot exporter, or asset-ID clipboard button**. Those would require additional implementation and should not be assumed from the UI/documentation.

## Limitations

- This is not an official Garena tool.
- Asset availability depends on third-party game infrastructure.
- A missing asset response does not prove that an ID is permanently invalid.
- Large scans can create many network requests and may be slow or rate-limited.
- CDN URLs are visible to the browser and can be inspected with developer tools.
- Browser security policies and network conditions can affect image loading.
- The hard-coded ID patterns require updates when the game's asset conventions change.

## Privacy

The project has no application backend, account system, or project database. Asset requests are performed by the browser.

## Asset ownership

Free Fire and related game assets belong to their respective rights holders, including Garena. This repository is for the source code and educational/reference purposes and does not claim ownership of third-party assets.

## License

See the repository's license for source-code licensing terms.

## Author

**Mohith Krishnaa** — [@mohith-krishnaa](https://github.com/mohith-krishnaa)

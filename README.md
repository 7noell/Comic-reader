# Comic Reader (React Native / Expo)

Dark, cinematic comic reader for people who already own CBZ / CBR / PDF files.

## Run it
1. Install Node.js (LTS) and the **Expo Go** app on your phone.
2. In this folder: `npm install` then `npm start`
3. Scan the QR code with Expo Go. Tap **+ Add** and pick a `.cbz` file.

Windows PowerShell blocking npm? Run: `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`, or use Command Prompt.

## What works now (phase 1)
- Import CBZ/ZIP (and `.cbr` files that are secretly zips, detected by content)
- Library: covers, continue reading, shelves (Reading / To read / Finished), long-press menu
- Reader: Page mode (swipe, pinch, double-tap zoom, tap zones), Scroll/webtoon mode, Guided panel-by-panel mode
- Left-to-right and right-to-left, remembered per comic
- Progress saved automatically; scrubber to jump to a page
- Settings: default direction and mode, reduce motion, keep screen on, haptics

## Not yet (needs native modules, so a development build instead of Expo Go)
- PDF pages, true RAR `.cbr` files (workaround: re-save as CBZ), EPUB, auto-crop, scan enhancement

## Known limits
- The whole archive is read into memory when opened; very large files can be slow or crash on low-RAM phones.
- Panel detection (`src/lib/panels.ts`) is a gutter-finding heuristic; irregular pages fall back to the full page.

## Structure
- `src/lib/` archive reading, panel detection, storage
- `src/components/` Zoomable, PagedView, WebtoonView, GuidedView
- `src/screens/` Library, Reader, Settings

# Suno Playlist Downloader

A small browser-console script that downloads every song **you created** in a Suno playlist, in the formats you choose.

## Features

- Pick any combination of formats: **MP3**, **WAV** (lossless), **MP4 video**, **cover image**, **lyrics (.txt)** and **metadata (.json)**
- Skips songs in the playlist that were made by other users
- Skips songs that are still generating or failed
- Optional numbering so files stay in playlist order, e.g. `03 - Song Title [ab12cd34].mp3`
- Live log in a small on-page panel

## Usage

1. Log in to [suno.com](https://suno.com) and open the playlist (`https://suno.com/playlist/<id>`).
2. Open the developer console:
   - Windows/Linux: `F12` or `Ctrl+Shift+J`
   - Mac: `Cmd+Option+J`
3. Paste the contents of [`suno-playlist-downloader.js`](suno-playlist-downloader.js) and press Enter.
   Chrome may ask you to type `allow pasting` first.
4. In the panel that appears top-right, tick the formats you want and click **Download**.
5. When the browser asks whether suno.com may download multiple files, allow it.

## Notes

- **WAV** files are rendered by Suno on request, so each takes a few seconds. They require a plan that includes WAV downloads; if Suno refuses, WAV is skipped for that song and other formats still download.
- The script uses Suno's internal web API, which is undocumented and may change. If something breaks, the panel log shows which step failed.
- Only download content you own or have rights to. Use at your own risk and in line with Suno's terms of service.

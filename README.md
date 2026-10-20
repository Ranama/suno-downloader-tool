# Suno Playlist Downloader

A browser-console script that downloads every song **you created** in a Suno playlist, in the formats you choose,
with a panel you can pause, minimise and close.

## Features

- Formats: **MP3**, **WAV** (lossless), **MP4 video**, **cover image**, **lyrics (.txt)** and **metadata (.json)**
- **Start, Pause/Resume, Stop** and **Retry failed** (also per song)
- Progress: songs done, current file with its own bar, time left, and counters for saved, skipped, failed and
  Suno downloads left
- **Minimise** the panel to a small progress pill; drag the panel or pill anywhere
- Chrome and Edge can save into **a folder you pick** (a subfolder named after the playlist, no "allow multiple
  downloads" prompt); other browsers save to Downloads
- **Resume:** paste it again after closing or reloading and it skips the songs it already saved
- Skips songs made by other users and songs that are still generating or failed
- Optional numbering so files stay in playlist order, e.g. `03 - Song Title [ab12cd34].mp3`
- Retries with back-off when Suno is busy; pauses (instead of failing every song) when your plan has no downloads left

## Usage

1. On a computer, log in to [suno.com](https://suno.com) and open the playlist (`https://suno.com/playlist/<id>`).
2. Open the developer console:
   - Windows/Linux: `Ctrl+Shift+J` (Chrome, Edge) or `Ctrl+Shift+K` (Firefox)
   - Mac: `Cmd+Option+J` (Chrome, Edge) or `Cmd+Option+K` (Firefox)
3. Paste the contents of [`suno-playlist-downloader.js`](suno-playlist-downloader.js) and press Enter.
   The first time, the browser may ask you to type `allow pasting`.
4. In the panel, keep MP3 ticked, choose where to save, and click **Start**.
5. If you save to Downloads, allow multiple downloads when the browser asks.

The same script and a step-by-step guide are built into [TwinSpin](https://ranama.github.io/twinspin/) (the Suno
button in the header).

## Notes

- Since late August 2026 Suno blocks most direct MP3 links. The script then uses Suno's own Download (if you allow
  it in the panel), which counts once per song toward your plan's downloads. WAV always goes through Suno's Download
  and needs a plan that includes WAV.
- It talks only to Suno's own addresses, stores no token or cookie, and never opens tabs.
- The script uses Suno's internal web API, which is undocumented and may change. Suno's terms do not allow bots or
  scraping: use it at your own risk, and only for songs you made.

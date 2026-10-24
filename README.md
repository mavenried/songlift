# songlift

A terminal UI for downloading tracks, albums, and playlists from Apple Music, Spotify, and YouTube Music as MP3s with embedded ID3 metadata.

Paste a supported music URL, fetch its track information, then download each track through `yt-dlp` and tag it (title, artist, album, artwork, and more). Search results are taken from YouTube Music.

## Requirements

- [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) available on your `PATH`
- `ffmpeg` (used by `yt-dlp` for audio extraction)

## Usage

```sh
cargo run --release
```

| Key                   | Action                            |
| --------------------- | --------------------------------- |
| `Enter`               | Queue the pasted URL              |
| `F5`                  | Fetch track lists for queued URLs |
| `F6`                  | Download all pending tracks       |
| `Ctrl+D`              | Same as `F6`                      |
| `Ctrl+L`              | Clear URLs, tracks, and log       |
| Mouse wheel           | Scroll the track table            |
| `PageUp` / `PageDown` | Scroll the log                    |
| `Ctrl+C` / `q`        | Quit                              |

Supported URL types: Apple Music album, track, and playlist links; Spotify track links; and YouTube Music track, album, and playlist links. Spotify support uses Spotify's public embed metadata, so Spotify albums and playlists may resolve only to the single item exposed by that metadata.

Downloaded files are saved to `songlift/` inside your system's Downloads folder (e.g. `~/Downloads/songlift`) at 320 kbps by default.

## Disclaimer

This tool is intended for personal, non-commercial use with content you have the right to access (e.g. previews, royalty-free or licensed material). It is not intended to facilitate piracy or copyright infringement. You are responsible for ensuring your use complies with applicable laws and the terms of service of any platforms involved.

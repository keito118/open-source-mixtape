# Contributing

English | [日本語](./CONTRIBUTING.ja.md)

Thanks for adding to the mixtape! 🎶

## Pull request checklist

- [ ] One line per song, added at the **end** of `playlists/open-source-mixtape.txt`.
- [ ] Each line has a note: `# Artist - Title`.
- [ ] Up to 3 songs in this pull request.
- [ ] The song isn't already in the playlist.

Accepted link forms: `https://open.spotify.com/track/<id>` (with or without `?si=…`), `spotify:track:<id>`, or the bare 22-character ID.

## What happens next

1. The **Validate playlists** check runs on your pull request. If it fails, open **Details** to see which line has the problem. If you're a first-time contributor, the check starts after a maintainer approves it.
2. The maintainer listens and either merges, comments, or closes the pull request.
3. After merging, the **Sync to Spotify** workflow updates the playlist.

## Please don't

- Edit lines other than your own, or reorder the playlist.
- Change files outside `playlists/` in a song pull request. Ideas for the tool itself are welcome at [spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code).

Be kind in reviews and comments. Music taste is personal.

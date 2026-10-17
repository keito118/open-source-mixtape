<h1 align="center">🎧 Open Source Mixtape</h1>

<p align="center">
  <b>A Spotify playlist built by pull requests.</b><br />
  Anyone, anywhere can add a song. Merge it, and it's on Spotify a minute later.
</p>

<p align="center">
  <a href="https://open.spotify.com/playlist/6RrEtS1qX6csamOV6ET74Q"><img src="https://img.shields.io/badge/Listen%20on-Spotify-1DB954?logo=spotify&logoColor=white" alt="Listen on Spotify" /></a>
  <a href="https://github.com/keito118/open-source-mixtape/actions/workflows/validate.yml"><img src="https://github.com/keito118/open-source-mixtape/actions/workflows/validate.yml/badge.svg?branch=main" alt="Validate playlists" /></a>
  <a href="./CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome" /></a>
  <a href="https://github.com/keito118/spotify-playlist-as-code"><img src="https://img.shields.io/badge/built%20with-spotify--playlist--as--code-black?logo=github" alt="Built with spotify-playlist-as-code" /></a>
</p>

<p align="center">English | <a href="./README.ja.md">日本語</a></p>

---

## What is this?

Open Source Mixtape is a shared playlist that lives in this repository. The whole playlist is one text file, [`playlists/open-source-mixtape.txt`](./playlists/open-source-mixtape.txt), with one song per line. You suggest a song by editing that file in a pull request. Each pull request gets a listen, and when it's merged, GitHub Actions updates the real playlist on Spotify.

The result is a playlist with a full history: every song has a commit, an author, and a reason it was added.

**▶️ [Listen on Spotify](https://open.spotify.com/playlist/6RrEtS1qX6csamOV6ET74Q)**

## Add a song

You only need a GitHub account. Everything happens in the browser.

1. **Copy the song link.** In Spotify, open the song and choose **Share → Copy Song Link**.
2. **Edit the playlist file.** Open [`playlists/open-source-mixtape.txt`](./playlists/open-source-mixtape.txt) and click the ✏️ pencil icon. GitHub makes your own copy (a fork) automatically.
3. **Add one line at the end:** the link, then `# Artist - Title`.

   ```text
   https://open.spotify.com/track/4uLU6hMCjMI75M1A2tKUQC  # Rick Astley - Never Gonna Give You Up
   ```

4. **Open the pull request.** Click **Commit changes → Propose changes → Create pull request**, then fill in the short template: which song, why, and (if you like) where you're listening from.

<details>
<summary>Prefer the command line?</summary>

```bash
gh repo fork keito118/open-source-mixtape --clone
cd open-source-mixtape
git switch -c add-my-song
echo 'https://open.spotify.com/track/<id>  # Artist - Title' >> playlists/open-source-mixtape.txt
python -m pac validate          # optional local check (Python 3.10+)
git commit -am "Add Artist - Title"
git push -u origin add-my-song
gh pr create --fill
```

</details>

## What happens after you open a pull request

1. **A bot checks it.** The *Validate playlists* check confirms the link is a real Spotify track and isn't already in the playlist, and lists what changed. If this is your first pull request here, the check starts once the maintainer approves it.
2. **Someone listens.** The maintainer plays the song and merges, comments, or politely passes.
3. **It goes live.** On merge, the *Sync to Spotify* workflow makes the Spotify playlist match the file, in the same order.

## Guidelines

- **Up to 3 songs per pull request**, so each one gets a real listen.
- **Add to the end** of the file, and don't edit or reorder other people's lines.
- **Any genre, any language, any decade.** Bonus points for songs most people haven't heard yet.
- **Be kind.** Music taste is personal. Not every song will make it, and that's okay.

Details are in [CONTRIBUTING.md](./CONTRIBUTING.md).

## FAQ

<details>
<summary>Do I need Spotify Premium?</summary>

No. You only need a song link. Free accounts can copy links and listen to the playlist.

</details>

<details>
<summary>My check says "waiting for approval". Did I do something wrong?</summary>

No. Checks for first-time contributors wait until the maintainer approves them. This keeps unknown code from running automatically.

</details>

<details>
<summary>The check failed. What now?</summary>

Click **Details** next to the failed check. The summary points to the exact line. The usual causes are a link that isn't a track (an album or playlist link) or a song that's already in the playlist.

</details>

<details>
<summary>Can I ask for a song to be removed?</summary>

Yes. Open an issue or a pull request that deletes the line, and say why.

</details>

## Start your own playlist like this

This repository is a working example of **[spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code)**, a template that turns any Spotify playlist into a GitHub repository.

- Validation on every pull request (bad links, duplicates, track names)
- Automatic sync to Spotify on merge
- Python standard library only, no servers to run

Use it for a team playlist, a party queue, or a playlist with friends. Click **Use this template** on [spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code) and follow the setup steps there.

## License

[MIT](./LICENSE). The code is MIT licensed; the songs belong to their artists.

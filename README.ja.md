<h1 align="center">🎧 Open Source Mixtape</h1>

<p align="center">
  <b>プルリクでつくる Spotify プレイリスト。</b><br />
  世界中の誰でも曲を追加できます。マージされると、1分ほどで Spotify に反映されます。
</p>

<p align="center">
  <a href="https://open.spotify.com/playlist/6RrEtS1qX6csamOV6ET74Q"><img src="https://img.shields.io/badge/Listen%20on-Spotify-1DB954?logo=spotify&logoColor=white" alt="Spotify で聴く" /></a>
  <a href="https://github.com/keito118/open-source-mixtape/actions/workflows/validate.yml"><img src="https://github.com/keito118/open-source-mixtape/actions/workflows/validate.yml/badge.svg?branch=main" alt="Validate playlists" /></a>
  <a href="./CONTRIBUTING.ja.md"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome" /></a>
  <a href="https://github.com/keito118/spotify-playlist-as-code"><img src="https://img.shields.io/badge/built%20with-spotify--playlist--as--code-black?logo=github" alt="Built with spotify-playlist-as-code" /></a>
</p>

<p align="center"><a href="./README.md">English</a> | 日本語</p>

---

## これは何？

Open Source Mixtape は、このリポジトリで管理している共同プレイリストです。プレイリスト全体が [`playlists/open-source-mixtape.txt`](./playlists/open-source-mixtape.txt) という1つのテキストファイルで、1行が1曲です。曲の提案は、このファイルを編集するプルリクで行います。プルリクは実際に聴いてレビューされ、マージされると GitHub Actions が Spotify のプレイリストを更新します。

すべての曲に、コミットと追加した人と追加した理由が残る、履歴つきのプレイリストです。

**▶️ [Spotify で聴く](https://open.spotify.com/playlist/6RrEtS1qX6csamOV6ET74Q)**

## いま入っている曲

[![Songs on the playlist right now](https://raw.githubusercontent.com/keito118/open-source-mixtape/tracklist/open-source-mixtape.svg)](https://open.spotify.com/playlist/6RrEtS1qX6csamOV6ET74Q)

曲がマージされるたびに自動で更新されます。

## 曲の追加方法

必要なのは GitHub アカウントと曲のリンクだけです。

1. **曲のリンクをコピー。** Spotify で曲を開き、**共有 → 曲のリンクをコピー** を選びます。
2. **[「🎵 Add a song」の Issue を作る](https://github.com/keito118/open-source-mixtape/issues/new?template=add-song.yml)** を開いてリンクを貼ります。よければ選んだ理由も書いてください。
3. **これで完了。** bot が曲を調べてプレイリストのファイルに追加し、プルリクを代わりに作ります。Issue にプルリクのリンクが返ってきます。

曲ではないリンクや、すでに入っている曲の場合は、bot が Issue でそう伝えます。

<details>
<summary>ファイルを自分で編集する場合</summary>

1. [`playlists/open-source-mixtape.txt`](./playlists/open-source-mixtape.txt) を開いて ✏️ のアイコンを押します。自分用のコピー（フォーク）は GitHub が自動で作ります。
2. ファイルの**最後**に1行追加します。リンクのあとに `# アーティスト - 曲名` を書きます。

   ```text
   https://open.spotify.com/track/4uLU6hMCjMI75M1A2tKUQC  # Rick Astley - Never Gonna Give You Up
   ```

3. **Commit changes → Propose changes → Create pull request** を押し、テンプレートを埋めます。

</details>

<details>
<summary>コマンドラインでやる場合</summary>

```bash
gh repo fork keito118/open-source-mixtape --clone
cd open-source-mixtape
git switch -c add-my-song
echo 'https://open.spotify.com/track/<id>  # Artist - Title' >> playlists/open-source-mixtape.txt
git commit -am "Add Artist - Title"
git push -u origin add-my-song
gh pr create --fill
```

</details>

## このあとの流れ

1. **bot がチェック。** プルリクで *Validate playlists* が、リンクが Spotify の曲か、すでにプレイリストに入っていないかを確認し、変更内容を一覧にします。自分でプルリクを出した場合、このリポジトリで初めてなら管理者が承認してからチェックが始まります。
2. **誰かが聴く。** 管理者が曲を聴いて、マージ・コメント・見送りのどれかをします。
3. **反映。** マージされると *Sync to Spotify* が、Spotify のプレイリストをファイルと同じ内容・同じ順番にそろえます。

## ルール

- **1つのプルリクで3曲まで。** 1曲ずつちゃんと聴くためです。
- **ファイルの最後に追加**してください。ほかの人の行の編集や並べ替えはしないでください。
- **ジャンル・言語・年代は自由。** まだあまり知られていない曲は大歓迎です。
- **やさしく。** 音楽の好みは人それぞれです。すべての曲が採用されるわけではありませんが、それで大丈夫です。

詳しくは [CONTRIBUTING.ja.md](./CONTRIBUTING.ja.md) を見てください。

## よくある質問

<details>
<summary>Spotify Premium は必要？</summary>

いりません。必要なのは曲のリンクだけです。無料アカウントでもリンクのコピーとプレイリストの再生ができます。

</details>

<details>
<summary>チェックが「承認待ち」のまま。何か間違えた？</summary>

間違えていません。初めての人のプルリクは、管理者が承認するまでチェックが止まる設定にしています。知らないコードが自動で動かないようにするためです。

</details>

<details>
<summary>チェックが失敗した。どうすればいい？</summary>

失敗したチェックの **Details** を開くと、問題のある行が表示されます。よくある原因は、曲ではないリンク（アルバムやプレイリストのリンク）か、すでに入っている曲です。

</details>

<details>
<summary>曲を消してほしいときは？</summary>

その行を消すプルリクか Issue を、理由を書いて出してください。

</details>

## 同じようなプレイリストを自分でつくる

このリポジトリは **[spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code)** の実際の運用例です。spotify-playlist-as-code は、Spotify のプレイリストを GitHub のリポジトリで管理できるようにするテンプレートです。

- プルリクごとの自動チェック（不正なリンク、重複、曲名の表示）
- マージすると Spotify に自動で同期
- Python の標準ライブラリだけで動き、サーバーは不要

チームのプレイリスト、パーティーの選曲、友だちとの共同プレイリストなどに使えます。[spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code) で **Use this template** を押して、セットアップの手順に沿って進めてください。

## ライセンス

[MIT](./LICENSE)。MIT ライセンスはコードに対するもので、曲の権利はそれぞれのアーティストにあります。

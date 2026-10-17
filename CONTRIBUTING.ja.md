# コントリビュートの方法

[English](./CONTRIBUTING.md) | 日本語

Mixtape に曲を追加してくれてありがとうございます！🎶

いちばん簡単なのは、[「🎵 Add a song」の Issue](https://github.com/keito118/open-source-mixtape/issues/new?template=add-song.yml) に Spotify のリンクを貼る方法です。bot がプルリクを代わりに作ります。下のチェックリストは、自分でプルリクを出す場合のものです。

## プルリクのチェックリスト

- [ ] 1曲1行で、`playlists/open-source-mixtape.txt` の**最後**に追加した
- [ ] 各行に `# アーティスト - 曲名` のメモを付けた
- [ ] このプルリクの曲は3曲まで
- [ ] すでにプレイリストに入っている曲ではない

書ける形式：`https://open.spotify.com/track/<id>`（`?si=…` 付きでも可）、`spotify:track:<id>`、22文字の ID そのもの。

## このあとの流れ

1. プルリクで **Validate playlists** のチェックが動きます。失敗したら **Details** を開くと、どの行が問題かわかります。初めての人は、管理者が承認してからチェックが始まります。
2. 管理者が曲を聴いて、マージ・コメント・クローズのどれかをします。
3. マージ後、**Sync to Spotify** がプレイリストを更新します。

## しないでほしいこと

- 自分の行以外の編集や、プレイリストの並べ替え
- 曲のプルリクで `playlists/` 以外のファイルを変えること。ツール自体へのアイデアは [spotify-playlist-as-code](https://github.com/keito118/spotify-playlist-as-code) で歓迎しています。

レビューやコメントはやさしく。音楽の好みは人それぞれです。

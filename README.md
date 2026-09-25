# LF2 Twitch Lite

Panasonic TH-43LF2Y向けの軽量Twitchランチャーです。

## 目的

通常のTwitchサイト全体を開かず、`player.twitch.tv` を直接開くことで、テレビ内蔵Chromium上で軽快に視聴します。

## 特徴

- お気に入りストリーマーの追加・削除
- Twitch URL / チャンネル名から直接再生
- 最近見たチャンネルを最大10件保存
- お気に入り・履歴をテレビ側 `localStorage` に保存
- 設定のJSON書き出し・読み込み
- PCによる動画中継なし
- TH-43LF2Yのリモコンで扱いやすい大きめUI

## GitHub Pages

このリポジトリの `main` ブランチ / root をGitHub PagesのSourceに設定してください。

公開後はテレビのブックマークからPages URLを開くだけで利用できます。

## Twitch再生

配信を選ぶと以下の形式でTwitch公式プレイヤーを直接開きます。

`https://player.twitch.tv/?channel=<channel>&parent=twitch.tv&player=popout&autoplay=true&muted=false`

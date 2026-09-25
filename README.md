# LF2 Twitch Lite

Panasonic TH-43LF2Y向けの軽量Twitchランチャーです。

## v0.4

当面の完成ラインです。機能を増やしすぎず、テレビ上での軽さを優先しています。

### 実装済み

- お気に入りストリーマーの追加・削除
- お気に入りの LIVE / OFFLINE 表示
- LIVE中の配信者を先頭へ並べ替え
- 起動時・約5分ごとのLIVE状態更新
- 手動の「LIVE更新」
- Twitch URL / チャンネル名から直接再生
- 最近見たチャンネルを最大10件保存
- お気に入り・履歴をテレビ側 localStorage に保存
- 設定のJSON書き出し・読み込み
- PCによる動画中継なし
- TH-43LF2Yのリモコンで扱いやすい大きめUI

## LIVE判定

v0.4では軽量性を優先し、DecAPI の Twitch uptime エンドポイントを使って LIVE / OFFLINE のみ判定しています。

- Twitch Client ID / OAuth設定は不要
- APIキーや秘密情報をPublicリポジトリに置かない
- お気に入り一覧そのものはGitHubには保存しない
- LIVE状態はDecAPI側で最大約5分キャッシュされるため、切り替わり直後は表示に遅延する場合があります
- DecAPIが利用できない場合は状態を「不明」として扱い、視聴機能自体はそのまま使えます

## GitHub Pages

https://nuju.github.io/lf2-twitch/

## Twitch再生

配信を選ぶと、Twitch公式サイト全体ではなく以下の軽量プレイヤーを直接開きます。

https://player.twitch.tv/?channel=<channel>&parent=twitch.tv&player=popout&autoplay=true&muted=false

## 方針

v0.4以降は一旦機能追加を止めます。
実機で使って物足りないと感じた機能だけ、保留案から追加します。

保留案:
- 配信サムネイル
- 配信タイトル
- ゲームカテゴリ
- 配信開始時刻
- スマホからのお気に入り編集
- Twitch公式APIを使った高度な連携

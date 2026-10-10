# LF2 Twitch Lite

Panasonic TH-43LF2Y向けの軽量Twitchランチャーです。

## 通常版

公開トップページの `index.html` は v0.5 のまま維持します。画面、操作、再生先は変更しません。

- https://nuju.github.io/lf2-twitch/

配信を選ぶと、これまで通り Twitch の軽量プレイヤーを直接開きます。

## チャット付き視聴（透過版）

通常版とは別に、チャット付き視聴専用の入口を用意しています。

- https://nuju.github.io/lf2-twitch/chat.html

`chat.html` では、通常版で保存したお気に入りと履歴をそのまま共有します。配信を選ぶと動画を画面全幅で表示し、その右端にTwitch公式チャットを半透明で重ねます。

- 通常版の画面・再生動作は維持し、右上に「チャット版へ」リンクだけ追加
- お気に入り・履歴は通常版と共有
- お気に入りと最近見たチャンネルに LIVE / OFFLINE / 不明 を表示
- 起動時・約5分ごと・手動の「LIVE更新」で状態を確認
- LIVE中のチャンネルを一覧の先頭へ表示
- 動画は100%幅のまま縮めない
- チャットは右端350px（1600px以上では400px）
- チャットiframe全体を透明度70%で表示
- チャット操作は無効にして読む用途に限定
- 全画面表示に対応し、戻る操作はテレビ／ブラウザの「戻る」を使用
- PCによる動画中継、独自サーバー、独自認証は追加しない

旧 `overlay.html` と `watch.html` は、既存リンクを壊さないため `chat.html` へ転送します。互換性用の `overlay-watch.html` も同じ70%透過表示です。

**TH-43LF2Y実機での表示、全画面表示、リモコンの戻る操作は引き続き実機で確認します。**

## LIVE判定

通常版とチャット版は、軽量性を優先し、DecAPI の Twitch uptime エンドポイントを使って LIVE / OFFLINE のみ判定しています。

- Twitch Client ID / OAuth設定は不要
- APIキーや秘密情報をPublicリポジトリに置かない
- お気に入り一覧そのものはGitHubには保存しない
- LIVE状態はDecAPI側で最大約5分キャッシュされるため、切り替わり直後は表示に遅延する場合があります
- DecAPIが利用できない場合は状態を「不明」として扱い、視聴機能自体はそのまま使えます

## Twitch再生

通常版:

https://player.twitch.tv/?channel=<channel>&parent=twitch.tv&player=popout&autoplay=true&muted=false

チャット版の入口から配信を選ぶと、同じ `chat.html` 内で動画を全幅表示し、公式チャットを右端へ70%の透明度で重ねます。埋め込み元を指定する `parent` はページの実際のホスト名を使用します。

公式仕様:
- [Embedding Chat](https://dev.twitch.tv/docs/embed/chat/)
- [Embedding Video and Clips](https://dev.twitch.tv/docs/embed/video-and-clips/)
- [Embedding Twitch](https://dev.twitch.tv/docs/embed/)

## 方針

通常版は現在の軽さと操作感を維持します。追加機能は通常版へ混ぜず、必要に応じて別ルートで試します。

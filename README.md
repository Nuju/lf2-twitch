# LF2 Twitch Lite

Panasonic TH-43LF2Y向けの軽量Twitchランチャーです。

## 通常版

公開トップページの `index.html` は v0.5 のまま維持します。画面、操作、再生先は変更しません。

- https://nuju.github.io/lf2-twitch/

配信を選ぶと、これまで通り Twitch の軽量プレイヤーを直接開きます。

## チャット付き視聴（別ルート・試験表示）

通常版とは別に、チャット付き視聴専用の入口を追加します。

- https://nuju.github.io/lf2-twitch/chat.html

`chat.html` では、通常版で保存したお気に入りと履歴をそのまま共有します。ここから配信者を選んだ場合だけ `watch.html` を開き、左に映像、右に公式Twitchチャットを表示します。

- 通常版の `index.html` は変更しない
- お気に入り・履歴は通常版と共有
- 「全体を全画面」で映像とチャットをまとめて全画面表示
- 「チャットを隠す」でチャットの読み込みを終了し、映像領域を広げる
- 「映像のみで開く」で従来の軽量プレイヤーへ移動
- PCによる動画中継、独自サーバー、独自認証は追加しない

**TH-43LF2Y実機での映像・チャットの同時表示、チャット更新、リモコン操作は未確認です。** Twitch側の埋め込みチャットがテレビのChromium 83で安定して動作するかは実機で確認します。

## LIVE判定

通常版 v0.5 は軽量性を優先し、DecAPI の Twitch uptime エンドポイントを使って LIVE / OFFLINE のみ判定しています。

- Twitch Client ID / OAuth設定は不要
- APIキーや秘密情報をPublicリポジトリに置かない
- お気に入り一覧そのものはGitHubには保存しない
- LIVE状態はDecAPI側で最大約5分キャッシュされるため、切り替わり直後は表示に遅延する場合があります
- DecAPIが利用できない場合は状態を「不明」として扱い、視聴機能自体はそのまま使えます

## Twitch再生

通常版:

https://player.twitch.tv/?channel=<channel>&parent=twitch.tv&player=popout&autoplay=true&muted=false

チャット付き表示では `watch.html?channel=<channel>` から、公式の映像とチャットを別々のiframeとして読み込みます。埋め込み元を指定する `parent` はページの実際のホスト名を使用します。

公式仕様:
- [Embedding Chat](https://dev.twitch.tv/docs/embed/chat/)
- [Embedding Video and Clips](https://dev.twitch.tv/docs/embed/video-and-clips/)
- [Embedding Twitch](https://dev.twitch.tv/docs/embed/)

## 方針

通常版は現在の軽さと操作感を維持します。追加機能は通常版へ混ぜず、必要に応じて別ルートで試します。

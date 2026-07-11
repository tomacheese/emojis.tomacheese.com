# GitHub Copilot Instructions

Tomachi Emojis Discord サーバーの招待リンク一覧を表示する静的サイト (HTML + Vue.js 3 + Vuetify 3、いずれも CDN 読み込み) のコードレビュー用インストラクション。以下はレビュー時に重点確認すべき点をまとめたもの。

## レビュー時の重点確認事項

- **`servers.json`**: 有効な JSON であり、各要素が `name` / `inviteUrl` / `image` / `disabled` の構造を保っているか。`image` は `/images/<番号>.png` 形式で、参照先ファイルが `images/` に実在するか。
- **招待 URL**: `inviteUrl` が `https://discord.gg/` 形式か。無効化する場合は URL を空にせず `disabled: true` を使っているか。
- **機密情報**: API キー・パスワード・トークン等がコードや `servers.json` に混入していないか。
- **CDN 維持**: ライブラリは CDN 経由の読み込みを維持しているか (npm 等パッケージ管理の新規導入は方針外)。

## コーディング規約

- コミットメッセージ・PR タイトルは [Conventional Commits](https://www.conventionalcommits.org/) に従う。description は日本語。
- 日本語と英数字の間には半角スペースを入れる。
- コメントは日本語、エラーメッセージは英語。

## フラグ不要な既知パターン (誤検知しないこと)

- `index.html` が CDN からライブラリを読み込み、`package.json` やビルド設定を持たないのは意図的な構成 (静的サイト)。ビルドツール・バンドラーの導入を促さない。
- `<meta name="robots" content="noindex,nofollow,noarchive">` は意図的な設定。
- 自動テストが存在しないのは既知 (ブラウザでの目視確認が前提)。テストフレームワーク導入を必須指摘としない。

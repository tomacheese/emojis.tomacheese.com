# GitHub Copilot Instructions

リポジトリの概要、規約、言語ルールは [AGENTS.md](../AGENTS.md) を参照してください。

## レビュー時の重点確認事項

- **`servers.json`**: 有効な JSON であり、各要素が `name` / `inviteUrl` / `image` / `disabled` の構造を保っているか。`image` の参照先が `images/` に実在するか。
- **招待 URL**: `inviteUrl` が `https://discord.gg/` 形式か。無効化する場合は URL を空にせず `disabled: true` を使っているか。
- **機密情報**: API キー・パスワード・トークン等が混入していないか。
- **CDN 維持**: ライブラリは CDN 経由の読み込みを維持しているか。

## 指摘不要な既知パターン

- `package.json` やビルド設定がないのは意図的な構成 (静的サイト)。ビルドツールの導入を促さない。
- `<meta name="robots" content="noindex,nofollow,noarchive">` は意図的な設定。
- 自動テストがないのは既知 (ブラウザでの目視確認が前提)。

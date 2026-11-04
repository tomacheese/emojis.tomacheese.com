# AGENTS.md

## 言語ルール

このリポジトリの言語は日本語です。

- コミットメッセージの description、PR / Issue のタイトルと本文、コードコメント、ドキュメントは日本語で書く
- 日本語と英数字の間には半角スペースを入れる
- エラーメッセージは英語
- 例外: サイトに表示される UI 文言やデータ (`servers.json` の値)、引用、技術的な識別子
- コミットは [Conventional Commits](https://www.conventionalcommits.org/)、ブランチ名は [Conventional Branch](https://conventional-branch.github.io) に従う

## 概要

Tomachi Emojis Discord サーバーへの招待リンクを一覧表示する静的サイト ([emojis.tomacheese.com](https://emojis.tomacheese.com)) です。GitHub Pages で配信しています (`CNAME` 参照)。`index.html` が `servers.json` を読み込み、Vuetify でサーバーアイコンを並べて表示します。

## 開発コマンド

ビルドやテストはありません。ローカルでは静的サーバーを起動してブラウザで確認します。

```bash
python -m http.server 8080
# http://localhost:8080 にアクセスする
```

## 構成

- `index.html`: エントリーポイント。Vue 3 (Composition API) と Vuetify 3 のロジックを含む
- `servers.json`: データソース。各要素は `name` / `inviteUrl` / `image` / `disabled` を持つ
- `images/`: サーバーアイコン画像 (`servers.json` の `image` から `/images/<番号>.png` で参照)
- `CNAME`: GitHub Pages のカスタムドメイン

## 守るべきルール

- Vue、Vuetify、axios などのライブラリは CDN 経由での読み込みを維持する。npm などのパッケージ管理やビルドツールは導入しない
- `servers.json` の JSON 構文とデータ構造を壊さない。`image` の参照先が `images/` に実在することを確認する
- 招待を無効にするときは `inviteUrl` を空にせず `disabled: true` にする (`index.html` は `disabled` でリンクを外し、画像を半透明にする)
- API キーやパスワードなどの機密情報をコードや `servers.json` に含めない
- 機能を変更したときは `README.md` を更新する。サーバーを追加するときは `servers.json` を更新する
- `<meta name="robots" content="noindex,nofollow,noarchive">` は意図的な設定

## テスト

自動テストはありません。変更後はローカルサーバーで表示崩れがないかを目視で確認します。

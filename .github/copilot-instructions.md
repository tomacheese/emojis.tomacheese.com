# GitHub Copilot Instructions

## プロジェクト概要
- 目的: Tomachi Emojis Discord サーバーへの招待リンクを一覧表示する
- 主な機能: サーバー情報のリスト表示、招待リンクへの遷移
- 対象ユーザー: Tomachi Emojis への参加希望者

## 共通ルール
- 会話は日本語で行う。
- PR タイトルとコミットメッセージは Conventional Commits に従う。
- 日本語と英数字の間には半角スペースを入れる。

## 技術スタック
- 言語: HTML, JavaScript
- フレームワーク: Vue.js 3 (CDN), Vuetify 3 (CDN)
- パッケージマネージャー: なし (静的サイト)

## 開発コマンド
```bash
# ローカルサーバー起動
python -m http.server 8080
```

## サーバー情報の編集
- `servers.json` にサーバー情報を定義する
- 画像は `images/` ディレクトリに配置する

## リポジトリ固有
- `index.html` 内で CDN 経由でライブラリを読み込んでいる

# GEMINI.md

## 目的
Gemini CLI を使用して `emojis.tomacheese.com` の開発支援を行う際のコンテキストとルールです。

## 出力スタイル
- 言語: 日本語
- トーン: 簡潔かつ丁寧
- 形式: Markdown

## 共通ルール
- 会話は日本語で行う。
- コミットメッセージは Conventional Commits に従う (`<type>(<scope>): <description>` 形式。scope は任意)。
- 日本語と英数字の間には半角スペースを入れる。

## プロジェクト概要
- Tomachi Emojis Discord サーバーの招待リンク一覧サイト
- HTML + Vue.js 3 (CDN) + Vuetify 3 (CDN)

## コーディング規約
- HTML/JS のフォーマットは既存コードのスタイルに合わせる。
- コメントは日本語で記述する。

## 開発コマンド
```bash
# ローカルサーバー起動
python -m http.server 8080
```

## 注意事項
- 認証情報を含めないこと。
- `servers.json` のデータ構造を破壊しないこと。
- ライブラリは CDN 利用を維持すること（npm 導入などは行わない）。

## リポジトリ固有
- ビルド不要の静的サイト構成。

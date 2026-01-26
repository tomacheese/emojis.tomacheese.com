# CLAUDE.md

## 目的
このドキュメントは、Claude Code を使用して `emojis.tomacheese.com` の開発を行う際の方針とルールを定めたものです。

## 判断記録のルール
- 判断内容の要約
- 検討した代替案
- 採用しなかった案とその理由
- 前提条件・仮定・不確実性
- 他エージェントによるレビュー可否

## プロジェクト概要
- 目的: Tomachi Emojis Discord サーバーへの招待リンク一覧表示
- 主な機能: `servers.json` からデータを読み込み、Vuetify でカード表示する

## 重要ルール
- **会話言語**: 日本語
- **コミット規約**: [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) (`<type>(<scope>): <description>` - descriptionは日本語)
- **コメント言語**: 日本語
- **エラーメッセージ**: 英語
- **スペース**: 日本語と英数字の間に半角スペースを挿入

## 環境のルール
- **ブランチ命名**: [Conventional Branch](https://conventional-branch.github.io) (`feat/`, `fix/` 等)
- **Git Worktree**: 使用する場合、`.bare/<branch>` 構成に従う (必須ではない)

## コード改修時のルール
- エラーメッセージの先頭に絵文字がある場合、全体で統一する
- `index.html` 内の Vue/Vuetify ロジックはわかりやすく記述する
- `servers.json` の JSON 構文エラーに注意する

## 相談ルール
- 実装レビュー、局所設計は Codex CLI に相談可能
- 外部仕様、最新情報は Gemini CLI に確認可能
- 指摘された事項は黙殺せず対応する

## 開発コマンド
```bash
# ローカルサーバー起動 (Python)
python -m http.server 8080
```
※ ブラウザで http://localhost:8080 にアクセスして確認

## アーキテクチャと主要ファイル
- `index.html`: アプリケーションのエントリーポイント (Vue/Vuetify ロジック含む)
- `servers.json`: データソース
- `images/`: 画像リソース

## 実装パターン
- Vue 3 Composition API (CDN版での記述) を使用
- Vuetify コンポーネントを活用して UI を構築

## テスト
- 自動テスト環境なし。ブラウザでの目視確認を行う。

## ドキュメント更新ルール
- 機能変更時は `README.md` を更新する
- サーバー追加時は `servers.json` を更新する

## 作業チェックリスト

### 新規改修時
1. `README.md` と `index.html` を読み、構造を理解する
2. 最新の `main` ブランチから作業ブランチを作成する (`feat/...` or `fix/...`)

### コミット・プッシュ前
1. コミットメッセージが Conventional Commits に従っているか確認
2. `servers.json` のフォーマットが正しいか確認
3. ローカルサーバーで表示崩れがないか確認

### PR 作成前
1. ユーザーから PR 作成の依頼があるか確認
2. 変更内容が要件を満たしているか確認

### PR 作成後
1. PR 本文に「何を変更したか」「なぜ変更したか」を日本語で明確に記載
2. GitHub Actions (もしあれば) の結果を確認

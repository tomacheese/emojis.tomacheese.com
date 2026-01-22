# emojis.tomacheese.com

[emojis.tomacheese.com](https://emojis.tomacheese.com) のソースコードです。

## 概要

Tomachi Emojis Discord サーバーへの招待リンクを一覧表示するウェブサイトです。

## 技術スタック

- HTML
- [Vue.js 3](https://vuejs.org/)
- [Vuetify 3](https://vuetifyjs.com/)

## ファイル構成

| ファイル | 説明 |
|---------|------|
| `index.html` | メインページ |
| `servers.json` | Discord サーバー情報（名前、招待 URL、画像） |
| `images/` | サーバーアイコン画像 |
| `CNAME` | GitHub Pages カスタムドメイン設定 |

## サーバー情報の編集

`servers.json` を編集してサーバー情報を更新できます。各配列要素が 1 件の Discord サーバーを表します。

```json
[
  {
    "name": "サーバー名",
    "inviteUrl": "Discord 招待 URL",
    "image": "/images/番号.png",
    "disabled": false
  }
]
```

`disabled` を `true` にすると、招待リンクが無効化されます（画像は半透明で表示）。

## ローカルでの実行

```bash
# リポジトリのクローン
git clone https://github.com/tomacheese/emojis.tomacheese.com.git
cd emojis.tomacheese.com

# ローカルサーバーで実行（例: Python）
python -m http.server 8080

# ブラウザで http://localhost:8080 にアクセス
```

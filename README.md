# 調整くん

Google Calendar の `free/busy` を使って、複数人の空き時間を提案する日程調整アプリです。

## 開発

```powershell
npm install
npm run dev
```

Open:

```text
http://127.0.0.1:4173
```

Check:

```powershell
npm run check
```

## 初期設定

1. `config.js` に Google OAuth Client ID を設定
2. 見本は `config.example.js` を参照
3. `npm run dev` でローカル起動

## 構成

- `index.html` UI
- `styles.css` スタイル
- `app.js` 日程調整ロジック、Google OAuth、ルーム同期
- `server.mjs` ローカルサーバーとローカル room API
- `netlify/functions/room.mjs` Netlify 用 room API
- `config.js` 実運用向けの公開設定
- `config.example.js` 設定サンプル
- `DEPLOY.md` デプロイ手順

## Runtime config

```js
window.SLOTWISE_CONFIG = {
  googleClientId: "xxxxx.apps.googleusercontent.com"
};
```

OAuth Client ID は `config.js` からアプリ側に読み込ませます。招待URLには含めません。`client secret` はこのリポジトリに入れません。

## 現在の機能

- 30分刻みで候補を提案
- 2カ月先まで検索
- 参加者ごとの Google Calendar free/busy を取り込み
- 招待URLを共有
- 主催者画面へ参加者の空き状況を自動集約
- Google Calendar 予定を作成して参加者へ招待送信
- 日別、参加者別の空き状況を可視化

## GitHub 運用

- GitHub repository: `chousei-kun/chousei-kun`
- デフォルトブランチ: `main`
- このリポジトリを開発の本線として使う
- Netlify は GitHub 連携デプロイ前提

## 公開URL

- Production: `https://chousei-kun.netlify.app`

## デプロイ

`DEPLOY.md` を参照してください。

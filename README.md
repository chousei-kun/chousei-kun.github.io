# 調整くん

Google Calendar の `free/busy` を使って、複数人の空き時間を提案する日程調整アプリです。

## Local development

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

## First setup

1. `config.js` に Google OAuth Client ID を設定
2. `config.example.js` を見本として使う
3. `npm run dev` でローカル起動

## Project structure

- `index.html` application shell
- `styles.css` interface styles
- `app.js` scheduling logic, Google OAuth, and room sync
- `server.mjs` local server and local room API
- `netlify/functions/room.mjs` Netlify room sync API
- `config.js` local runtime config
- `config.example.js` example runtime config
- `DEPLOY.md` deployment notes

## Runtime config

`config.js` に Google OAuth Client ID を設定します。

```js
window.SLOTWISE_CONFIG = {
  googleClientId: "xxxxx.apps.googleusercontent.com"
};
```

OAuth Client ID は公開識別子です。client secret はこのリポジトリに入れません。

## Current features

- 30分刻みで候補を提案
- 2カ月先まで検索
- 参加者ごとの Google Calendar free/busy を取り込み
- 招待URLを共有
- 主催者画面へ参加者の空き状況を自動集約
- Google Calendar 予定を作成して参加者へ招待送信
- 日別、参加者別の空き状況を可視化

## Deployment

`DEPLOY.md` を参照してください。

## GitHub readiness

- repository initialized on `main`
- local-only files such as `.data/`, logs, zips, `outputs/`, and `work/` are ignored
- Netlify Functions live under `netlify/functions`

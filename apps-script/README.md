# Apps Script room API

Use the code in `Code.gs` as a Google Apps Script Web App for shared room storage and free/busy aggregation.

## Setup

1. Open your Google Apps Script project.
2. Replace the existing `Code.gs` contents with `apps-script/Code.gs`.
3. Deploy as `Web app`.
5. Set:
   - `Execute as`: Me
   - `Who has access`: Anyone

4. Copy the Web App URL.

## App config

After the Web App is deployed, put the URL into `config.js` like this:

```js
window.SLOTWISE_CONFIG = {
  googleClientId: "xxxxx.apps.googleusercontent.com",
  roomStore: "remote",
  roomApiUrl: "https://script.google.com/macros/s/your-web-app-id/exec",
  preferredGoogleAccount: "your-account@gmail.com"
};
```

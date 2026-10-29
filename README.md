# Coral Island Checklist
A shared checklist for Coral Island: Lake Temple offerings and museum donations, with fish, insect and sea critter spawn info, dish recipes and artifact drop chances. Ticks sync live between everyone who opens the same invite link. No Claude account is needed.

Data comes from [coral.guide](https://coral.guide/) (game version v1.3). Place and time info for 11 fish comes from the [Coral Island wiki](https://coralisland.wiki/wiki/Fish).

## Setup (about 10 minutes, once)
You need a GitHub account and a Google account. Your friend needs nothing.

### 1. Create the database (Firebase, free)
1. Go to <https://console.firebase.google.com> and click **Create a project**. Any name works, for example `coral-checklist`. You can turn off Google Analytics.
2. In the left menu open **Build → Realtime Database** and click **Create Database**.
   - Location: **Belgium (europe-west1)** is closest to Poland.
   - Security rules: choose **Start in locked mode**.
3. Open the **Rules** tab, replace everything with the contents of `database.rules.json`, and click **Publish**.

### 2. Copy the Firebase settings
1. Click the gear icon next to **Project Overview → Project settings**.
2. Under **Your apps**, click the web icon `</>`. Give it any nickname and click **Register app**. Skip Firebase Hosting.
3. Firebase shows a `firebaseConfig` block. Copy its values into `firebase-config.js` (`apiKey`, `authDomain`, `databaseURL`, `projectId`, `appId`).
   - If `databaseURL` is missing, copy it from the top of the **Realtime Database** page. It looks like `https://coral-checklist-default-rtdb.europe-west1.firebasedatabase.app`.

### 3. Put the site on GitHub Pages
1. On GitHub, click **New repository**. Name it, for example `coral-checklist`, make it **Public**, and create it.
2. Click **uploading an existing file** and upload `index.html`, `firebase-config.js`, `database.rules.json` and this `README.md`. Click **Commit changes**.
3. Open **Settings → Pages**. Under **Build and deployment**, set **Source: Deploy from a branch**, **Branch: main**, folder **/(root)**, and click **Save**.
4. After a minute the page shows your site address, like `https://YOUR-NAME.github.io/coral-checklist/`.

### 4. Play together
1. Open your site. It creates a private room and adds `?room=...` to the address.
2. Type your name, click **Copy invite link**, and send the link to your friend.
3. Everyone who opens that exact link sees and ticks the same checklist live. Opening the site without the `?room=` part starts a new, empty room, so bookmark your invite link.

## Good to know
- Anyone who has your invite link can tick and untick. Share it only with people you play with.
- The free Firebase plan (Spark) is far more than enough for this.
- To change something on the site, edit the file on GitHub. Pages updates within a minute or two.

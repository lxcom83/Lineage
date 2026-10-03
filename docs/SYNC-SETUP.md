# Setting up Google Drive sync

Sync lets people use Lineage Tracker on several devices with the same records, through
their own Google Drive. Google requires every web app that signs people in to
have its own **client ID**. Whoever hosts Lineage Tracker (for example on GitHub Pages)
creates one once, about 15 minutes. Everyone who uses that site then shares it,
and each person's records still go only to their own Drive.

Google renames menus from time to time, so labels below may differ slightly.

## 1. Create a Google Cloud project

1. Go to <https://console.cloud.google.com> and sign in.
2. Create a new project, for example **Lineage Tracker**. Billing is not needed.

## 2. Turn on the Google Drive API

**APIs & Services > Library**, search for **Google Drive API**, open it and
choose **Enable**.

## 3. Set up the sign-in screen

Open **Google Auth Platform** (older consoles call it **OAuth consent screen**).

1. **Branding:** app name `Lineage Tracker`, your email as the support and developer
   contact.
2. **Audience:** choose **External**.
3. **Data access:** add the scope
   `https://www.googleapis.com/auth/drive.file`.
   This is the only permission Lineage Tracker asks for: it can see and change only
   the files Lineage Tracker itself created, never the rest of anyone's Drive.
4. While the app is in **Testing**, only the Google accounts you add under
   **Test users** can connect (up to 100). Add your own account now.
5. When you want anyone using your site to be able to connect, choose
   **Publish app**. Because `drive.file` is one of Google's least sensitive Drive
   permissions, a full security review is not normally required, but Google
   may ask you to verify the app's name and branding. Until then people may see
   an "unverified app" notice they can click through.

## 4. Create the client ID

1. **Clients** (or **Credentials > Create credentials > OAuth client ID**).
2. Application type: **Web application**. Name: `Lineage Tracker web`.
3. **Authorised JavaScript origins:** add your site's address with no path and
   no trailing slash, for example `https://lxcom83.github.io`.
4. No redirect URIs are needed. Save.
5. Copy the **Client ID**. It ends in `.apps.googleusercontent.com`. It is not
   a secret, so it is fine for it to sit in a public repository.

## 5. Add it to your Lineage Tracker site

In your GitHub repository, add a file named `config.json` next to
`index.html`:

```json
{
  "googleClientId": "1234567890-abc.apps.googleusercontent.com"
}
```

`config.example.json` shows the format. Lineage Tracker updates only ship the example
file, so uploading a new version never overwrites your `config.json`.

## 6. Connect each device

Open your Lineage Tracker address, go to **Settings > Sync across devices** and tap
**Connect Google Drive**. Approve the Google window. Repeat on each phone,
tablet or computer. The first sync on a device that already has records merges
them with what's in Drive.

Your Drive gets a folder called **Lineage Tracker sync** containing
`lineage-records.json`, a `photos` folder and a `weekly snapshots` folder with
the last eight weekly copies of your records.

## Troubleshooting

- **Nothing happens when tapping Connect:** allow pop-ups for the site.
- **"Access blocked" or "not a test user":** add the account under Test users,
  or publish the app (step 3).
- **"Origin not allowed" or a mismatch error:** the JavaScript origin in step 4
  must exactly match the address in your browser, such as
  `https://lxcom83.github.io`.
- **The cloud button turns red after a while:** Google sign-ins last about an
  hour. Tap the cloud button to sign in again; usually no typing is needed.
- **Sync isn't offered at all:** it only works from the web address, not when
  `index.html` is opened as a file.

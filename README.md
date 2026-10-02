# Lineage

A breeding journal for plants and animals that runs entirely on your own device.
Keep a seed and stock library, tag individual plants and animals, record crosses
and pairings, choose what each project measures (harvests, storage trials,
weigh-ins, litters, your own fields), compare candidates side by side, follow
lineage across generations, and keep a dated log of notes and photos.

No account, no server, no subscription. Records and photos stay on the device.

## Put it online with GitHub Pages (free)

The address only serves the app. Your records never leave your device.

1. Sign in at github.com and create a new repository named `lineage`.
   Make it **Public** (free Pages sites need a public repository).
2. On the empty repository page, choose **uploading an existing file** and drag
   in everything from this folder: `index.html`, `sw.js`,
   `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `README.md`.
   Commit the files.
3. Go to **Settings > Pages**. Under Branch choose `main` and `/ (root)`, then
   Save.
4. After a minute or two the site is live at
   `https://YOUR-USERNAME.github.io/lineage/`.
5. Open that address in Chrome on your phone, tap the menu, then
   **Install app** (or **Add to Home screen**).

Never upload backup files or your starter file to the repository. Everything in
a public repository can be seen by anyone.

**Updating later:** upload the new `index.html` (and `sw.js` if it changed)
over the old ones. The installed app picks up the new version the next time
it opens with internet. Your records are not affected.

Keep using the same address. Each address has its own separate storage, so if
you ever move Lineage, back up first and restore at the new address.

## On a computer, without the internet

Double-click `index.html`. Chrome, Edge and Firefox all work. Records saved this
way are separate from the phone's; use a backup to move them across.

## Backups

Everything lives in the browser's storage on one device, so keep copies
elsewhere.

- **Full backup** (Home or Settings, **Back up now**): one zip file with every
  record and photo. Inside are your photos as normal image files and spreadsheet
  (CSV) copies of every record, so your data is readable even without Lineage.
  Lineage restores straight from the zip; there's no need to unzip it.
- **Quick backup** (on phones): records only, small enough to send to Google
  Drive or email after every session.
- Copy full backups to a USB stick, SD card, computer or cloud drive. Lineage
  reminds you when changes pile up.
- **Restoring** (Settings, **Restore or import a file**) adds what's missing
  and only overwrites a record when the backup's copy is newer. **Undo last
  restore** puts things back if you restore the wrong file.
- **Recycle bin:** deleted records stay for 30 days before they're removed for
  good.

## What each project tracks

Each breeding project can add record types:

- Suggested for plants: Fruit harvest, Storage check (logged against each
  fruit, and shows how many days it keeps), Plant check.
- Suggested for animals: Weigh-in, Litter or clutch, Egg count, Health event.
- Or build your own with number, score, choice, text, date, yes/no and
  calculated fields.

Lines share their parent project's record types. The project page compares every
tagged member on scores and measurements, and can log one storage check for
every stored fruit at once.

## Smart features (optional, off by default)

Settings has two ways to have Claude read packets and labels or answer questions
about your records: copy and paste with your existing Claude or ChatGPT app
(free), or a Claude API key (automatic, billed per use by Anthropic).

## Files

- `index.html`: the whole app
- `sw.js`, `manifest.webmanifest`, `icon-*.png`: let it install and work offline

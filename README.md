# Grouped Thesaurus (Word add-in)

Synonyms grouped by meaning, each with a short definition. Click a synonym to
replace the selected word; click ↗ to look that synonym up instead.

## 1. Host the files (free, GitHub Pages)

Word loads add-ins from a web address, so these files need to be online.

1. Sign in to github.com and create a **public** repository named `grouped-thesaurus`.
2. Click **Add file → Upload files** and upload everything in this folder
   (`taskpane.html`, `commands.html`, `index.html`, `manifest.xml`, `README.md`
   and the `assets` folder). Commit.
3. Go to **Settings → Pages**. Under "Build and deployment", pick
   **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute, open `https://YOUR-USERNAME.github.io/grouped-thesaurus/`
   (with your GitHub username). You should see a short welcome page.

## 2. Point the manifest at your copy

Open `manifest.xml` in a text editor and use find-and-replace to change
`YOUR-USERNAME` to your GitHub username (it appears several times). Save it.
This edited copy is the one you load into Word.

## 3. Load it into Word

**Word on the web (office.com):** open a document → **Home → Add-ins → More Add-ins**
(or **Insert → Add-ins**) → **My Add-ins** → **Upload My Add-in** → choose `manifest.xml`.

**Word for Mac:** in Finder, press Cmd+Shift+G and go to
`~/Library/Containers/com.microsoft.Word/Data/Documents/`. Create a folder named
`wef` there (if it isn't already there) and copy `manifest.xml` into it.
Restart Word, then **Home → Add-ins** (or **Insert → My Add-ins**) and pick
Grouped Thesaurus under Developer Add-ins.

**Word for Windows:** create a folder (e.g. `C:\WordAddins`), right-click it →
**Properties → Sharing → Share**, and note its network path (e.g. `\\YOURPC\WordAddins`).
Copy `manifest.xml` into it. In Word: **File → Options → Trust Center →
Trust Center Settings → Trusted Add-in Catalogs**, paste the network path into
"Catalog Url", click **Add catalog**, tick **Show in Menu**, OK, and restart Word.
Then **Home → Add-ins → More Add-ins → Shared Folder** and add Grouped Thesaurus.

A **Grouped Thesaurus** button then appears on the Home tab.

## 4. (Recommended) Merriam-Webster key

Without a key the add-in uses free dictionaryapi.dev data, which has fewer
synonyms. For much better results, register (free, non-commercial) at
https://dictionaryapi.com/register/index, request **Merriam-Webster's Collegiate
Thesaurus**, and paste the key into the add-in's ⚙ settings.

## Privacy

Looked-up words are sent to Merriam-Webster (if you added a key) or to
dictionaryapi.dev. Nothing else from your document leaves Word.

## Updating

Upload changed files to the same GitHub repository; Word picks them up the next
time the panel opens. You only need to reload the manifest if `manifest.xml` changes.

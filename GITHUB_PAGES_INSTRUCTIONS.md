# Clearframe V14 — GitHub Pages PWA

**Source:** The live Clearframe Site's published version **32** (source commit `073f27aa38a07915c274ab67deadd1a3a6d1d892`), repackaged as **V14** for GitHub Pages installation testing on November 10, 2026.

This is a complete static app: no npm, build process, database, server, or secret keys required. All paths are relative so the app can run from a GitHub Pages project repository such as `https://USERNAME.github.io/clearframe-v14/`.

## Upload to GitHub

1. On GitHub, create a new repository, such as `clearframe-v14`. For simple public GitHub Pages hosting, choose a **public** repository.
2. Download and extract `V14.zip` on your computer.
3. In the repository, choose **Add file → Upload files**. Select and upload **all files inside the extracted folder**, including `index.html`, `manifest.webmanifest`, `sw.js`, the JavaScript and CSS files, and the app icons. **Do not upload just the ZIP**, and **do not put everything inside a second folder**. `index.html` must be at the repository root.
4. Commit the files to `main`.
5. Go to **Settings → Pages**. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/(root)`, then save.
6. Wait for GitHub Pages to show the deployed URL, generally `https://USERNAME.github.io/REPOSITORY/`, and open it in your browser.
7. To install the PWA, use the browser's **Install app** menu option when available; on iPhone/iPad, use Safari's **Add to Home Screen**. A PWA installs from the live HTTPS site, not directly from the ZIP.

## Test checklist

- [ ] The app title and installed app name identify **Clearframe V14**.
- [ ] **Process an emotion** begins with **What's weighing on you?** Enter a situation, then press **Untangle this**.
- [ ] Step **2 · Matching subroutines** opens automatically. Matches of at least 1% are grouped by control routine, and each row has **+ Add** or **− Remove**.
- [ ] The **Recently Picked Subroutine** footer shows the subroutine name, Expectation Trigger, Protective Response, navigation arrows and selection status.
- [ ] The bottom observation area reserves a consistent height, whether choices are shown or hidden. Navigating between subroutines must **not move the footer controls up and down**.
- [ ] Red and green observation choices remain contained within their fixed-height boxes. Text does not overflow when first shown or after selection, and text size does not jump when an option is selected.
- [ ] Choosing a red or green observation updates the reflection; selecting **Swap Shoes** changes perspective text without changing the underlying selected observation.
- [ ] Preferences, saved moments, and export/import continue to work after a reload.
- [ ] After a **full online visit**, disconnect from the internet and reopen the installed app. Its cached interface should still launch offline.

## Data, privacy, and updates

- The GitHub Pages copy and the ChatGPT-hosted version have **separate browser storage**. Existing saved moments will **not** automatically transfer. Use Clearframe's export and import features if you want to move saved information.
- Do not clear site data or uninstall without exporting anything you want to keep; browser removal can also remove locally stored data.
- Installing from a **new repository path** can create a separately scoped PWA. Replacing files in the same repository updates the existing installation when its service worker refreshes. For later revisions, refresh the asset query values in `index.html` and the cache name/files in `sw.js`.
- GitHub Pages serves the PWA over HTTPS. Opening `index.html` directly as a `file://` page will not register its service worker or make it installable.
- This app is an educational tool for reflection, **not** a diagnosis, validated clinical instrument, or emergency safety assessment.

The included `book1-v10-source-ledger.json` preserves the project's source mapping and editorial notes for review.

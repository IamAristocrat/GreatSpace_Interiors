# GreatSpace Interiors Studio — website deployment

This package contains the website published on 18 November 2026, including 50 articles, gallery, site photographs, walkthrough video and five-stage process. This is a static HTML/CSS/JavaScript website; it needs no Node.js build or database.

## Run locally

From this folder run `python3 -m http.server 8000` and open `http://localhost:8000`. Open the folder in a terminal first. Running a local server lets all links and scripts resolve correctly.

## Deploy to Hostinger through GitHub

1. Extract this ZIP and create a GitHub repository. Upload the **contents** of this folder to the repository root, so `index.html`, `assets/` and `.github/` are at the top level. Ensure hidden files are included when uploading. Keep the repository private if preferred.
2. In Hostinger hPanel, locate the FTP account details for the intended website and determine the correct remote directory (often `/public_html/`, but this depends on the domain and account). Do not assume a directory for an addon domain. Back up any existing site before replacing files.
3. In GitHub, open the repository's Settings → Secrets and variables → Actions → New repository secret. Add `FTP_SERVER`, `FTP_USERNAME`, `FTP_PASSWORD`, and `FTP_SERVER_DIR`. Use the FTP host, username, password and destination folder supplied by Hostinger. The directory must start and end with `/`.
4. Open Actions → Deploy to Hostinger → Run workflow. This is a manual deployment. Later edits can be pushed to the repository and deployed by running the workflow again.
5. Open the website and test the homepage, gallery, journal, images, video, language selector, phone and WhatsApp links on desktop and mobile. Verify the correct domain and TLS certificate in Hostinger.

The workflow uses FTPS (explicit TLS). Confirm the hosting account supports FTPS and that the credentials have access to the intended directory. It uploads changed files and does not deliberately delete existing remote files, so remove obsolete files only after reviewing a backup. The first deployment may take time because of images and video.

The language dropdown uses Google Translate and requires an internet connection; translated output depends on Google. The site's imagery includes original site photographs and earlier archive inspiration images; preserve their existing captions. The previous 99,000-word target has not been completed.

This package does not configure DNS, create a GitHub repository, provision Hostinger, or change a live domain. Source corresponds to site commit `5d639bd719ff31b6aee7426092b02a56ec8bf763`.

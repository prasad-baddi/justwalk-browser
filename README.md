# JustWalk Browser Edition

`index.html` is the complete browser-only tracker. No Python, paid server,
account or server database is required. Interface libraries load from CDNs,
so internet access is required when opening it.

## Use on associate and manager laptops

1. Open the same published website address in a normal Chrome or Edge window.
2. In Associate View, import your original CSV/XLSX and confirm its preview.
3. For continued jobs, choose the reporting date and subtract previously counted
   minutes in the preview before confirming.
4. Choose **Download backup / Share data**. Send that JSON file to your manager
   using your approved file-sharing channel.
5. The manager chooses **Import backup**, reviews the merge notice, and confirms.
6. Switch to Manager View to filter by associate/date/week, inspect jobs and
   export a date, week or month Excel summary.

Each browser saves its own copy in IndexedDB. No tracker data is uploaded to
GitHub or a server by this app. Loading the page requests interface libraries
from external CDNs. The app does not automatically synchronize devices.
Manager View is a view selector, not a security boundary or account login.
Anyone with access to the browser profile can use its records.

Backups contain all original uploads and their minute/date adjustments from
that browser, including all associates present there. Keep them private.
Import merges new upload IDs and skips IDs already present. New imports replace
matching date/associate/job records, even if the imported file is older; review
the selected file. Deletions do not propagate between laptops. Each browser
keeps its own Changes history rather than importing another laptop's history.
Deleting an upload restores earlier surviving versions of matching jobs.

Use the same website address and browser profile consistently. Changing the
address, switching profiles or using another laptop gives a separate workspace.
Clearing browser/site data can erase the workspace. Download backups regularly;
browser storage is not guaranteed permanent storage. Avoid private browsing.
Importing a backup into an empty browser restores its retained uploads.

## Publish on GitHub Pages

For free Pages hosting, create a **public repository containing only this browser
edition**, upload `index.html` to its root, then select **Settings → Pages →
Deploy from a branch → main → /(root) → Save**. GitHub displays the live URL when
deployment finishes. Do not upload CSVs, JSON backups, databases or Excel reports.

This repository contains the browser edition only. The Python server edition
remains in the separate private `justwalk-tracker` repository.

You can also download this HTML and open it directly for a local demonstration.
File-URL storage behavior varies by browser; use a published HTTPS URL for
regular work and transfer a downloaded backup when moving to that URL.

## Verification

Checked with an IndexedDB test implementation: CSV/XLSX parsing, all statuses,
strict date validation, carry-over adjustments, upsert, deletion replay,
original-file download, Excel export, backup restoration and duplicate-import
skipping. React JSX compilation passed. A real-browser visual check and public
GitHub Pages deployment still need verification.

# MedX PDFs

PDF library for the MedX app (notes, MIST workbooks, exam archives), served from a CDN.

- CDN base: `https://cyberromeo.github.io/pdf` (GitHub Pages)
- A file at `notes/workbooks/ENT/x.pdf` is served at `https://cyberromeo.github.io/pdf/notes/workbooks/ENT/x.pdf`
- The app builds URLs from `NEXT_PUBLIC_CDN_BASE` + the paths in `src/lib/notes-data.json` / `exam-archives` data.

## Adding a PDF
1. Commit it under `notes/` or `exam-archives/` here (keep the folder layout).
2. In the app repo, run `node generate_notes_json.js` or `node generate_exams_json.js` with this repo cloned next to it (`../pdf`) or `PDF_REPO_DIR=/path/to/pdf`.

Files over 20 MB are fine here (GitHub Pages serves up to 100 MB per file); jsDelivr is not used because it refuses files over 20 MB.

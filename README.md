# Al-Hayat — Ilm-us-Sarf

An Urdu, RTL learning platform based on the subjects and examples of the supplied **Ilm Us Sarf** (57 pages) and **Ilm Us Sarf Aakhireen** (105 pages), attributed in the supplied scans to مولانا مشتاق احمد چرتھاولی / مکتبۃ البشریٰ. Explanations and exercises are newly written teaching material rather than a transcription.

## Start

Extract the ZIP and open `index.html`. No installation, build, API key, account or internet connection is required. Keep the folders together. Progress is stored in the current browser; use the export/import buttons for a backup. Browser policies for local-file storage may differ; static hosting is recommended for regular classroom use.

## Curriculum and features

- 62 connected lessons in 10 stages, with smaller topics retained as subsections. The count follows the curriculum rather than a target of 100.
- Foundations, pronouns, active/passive verbs, moods, commands/prohibitions, emphatic nun, verbal nouns, derivatives, simple/augmented/quadriliteral patterns and ilhaq, semantic properties, seven morphological classes and weak-letter changes.
- 872 lesson MCQs with feedback, 485 short-answer items, and 812 conjugation-row questions: 1,684 available MCQs in total.
- 14 curated verb models, 37 pattern reference cards, noun tables, hidden-form recall, revision cards, stage quizzes, mistake review, search and progress tracking.
- Separate Arabic Amiri and Urdu Jameel Noori Nastaleeq fonts bundled locally. Different lesson palettes, Arabic emphasis, light/dark appearance and text-size controls. No print button.

The paradigm tool covers the displayed models and modes; it is not an unrestricted Arabic conjugation engine. Some paradigms intentionally omit modes where a curated table has not been provided.

## Deploy

This is a plain static site. For GitHub Pages, publish the folder containing `index.html`. For Cloudflare Pages direct upload, upload the contents of this folder. For a Git integration, use no build command and set the output directory to the folder containing `index.html` (or `/` if these files are at repository root). No server functions are needed. Hash routes work without rewrite rules. Do not upload source PDFs, temporary scans or development dependency folders.

## Edit and check

`content.json` contains lessons, sections, stages and pattern cards. `conjugations.json` contains the curated paradigms. After edits:

```sh
python3 scripts/build_data.py
node tests/smoke.cjs
```

The build script regenerates `data.js`, `conjugations.js` and `coverage.json`. The app loads these scripts directly so it does not depend on fetching JSON from a local file URL. `app.js` handles navigation and practice; `styles.css` controls presentation.

The automated smoke check exercises all 248 lesson views, major routes, table modes, question structure, scoring, mistake retry, stage sampling and selected Arabic-form fixtures. It uses a simulated DOM. A real-browser visual and device check was not available in the build environment and remains pending. Before public classroom rollout, an Arabic morphology teacher should review the teaching text and infrequent forms. The coverage map audits the authored curriculum; it does not certify a line-by-line scholarly collation of all 162 scanned pages.

## Fonts and source scans

Font files are included for the requested appearance. Amiri is an open font; see https://github.com/aliftype/amiri for its OFL terms and attribution. Jameel Noori Nastaleeq is included as supplied in the working project; verify applicable redistribution permissions before further redistribution. Original book PDFs and scan images are not bundled.

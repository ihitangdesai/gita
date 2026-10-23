# Scripture sources and editorial record

## English translation

Annie Besant, *The Bhagavad-Gita, or The Lord’s Song*, fourth edition. G. A. Natesan & Co., Madras, October 1922.

Text source: https://en.wikisource.org/wiki/Bhagavad-Gita_(Besant_4th)

All 18 discourse pages were downloaded and processed. Each verse has its chapter source URL. `data/source-manifest.json` records SHA-256 hashes of the downloaded source pages. The import retains the original English verse wording, normalises whitespace, removes page numbers and footnote markers, and places available translator’s notes in a separate field. The chapter-number conventions and names are retained consistently with this edition.

The work’s source page identifies the translation as public domain in the United States because of its publication date. Annie Besant died in 1933; the page gives additional author-life-term jurisdiction details. This is a historical translation, not a modern copyrighted translation copied from another app. Credit Wikisource contributors for the transcription; any applicable contributor material is available under the source’s Creative Commons Attribution-ShareAlike terms (https://creativecommons.org/licenses/by-sa/4.0/). Consult the source page for its full rights statement; do not assume a blanket worldwide copyright conclusion.

## Sanskrit and romanisation

The ancient Sanskrit and romanisation fields are from `gita/gita`, `data/verse.json`:

- Repository: https://github.com/gita/gita
- File: https://github.com/gita/gita/blob/main/data/verse.json
- Licence: Unlicense, https://github.com/gita/gita/blob/main/LICENSE

No modern English translation or word-meaning field from that repository is used. The raw downloaded file’s SHA-256 is in the source manifest. The transliteration is the source’s phonetic romanisation, not a claim of strict IAST. Ancient Sanskrit has no modern author copyright; transcription conventions can differ. The site does not claim to be a critical edition or a new scholarly translation.

## Verse numbering

The corpus has 701 sequential numbered verses:
47, 72, 43, 42, 29, 47, 30, 28, 34, 42, 55, 20, **35**, 27, 20, 24, 28, 78.

Chapter 13 includes Arjuna’s opening question as 13.1. Editions that omit that question generally count 700 verses and number the remaining Chapter 13 verses one lower. No verse is silently removed or renumbered. The English and Sanskrit use the same 701-verse convention.

## Documented presentation corrections

The following source-transcription numbering issues are corrected by the importer. English wording is preserved.

- 3.42: terminal marker lacks its closing parenthesis.
- 10.31: the marker is absent in visible text, but recorded as `(31)` in Wikisource’s tooltip annotation.
- 17.19: English marker says `(20)`; preceding Sanskrit and verse sequence identify 19.
- 18.14: English marker says `(15)`; preceding Sanskrit and verse sequence identify 14.
- 18.32: terminal marker lacks its opening parenthesis.

The importer fails if the expected complete sequence cannot be assembled. It does not synthesise missing scripture.

## Contemporary study guides

`lib/study-guides.ts` contains original AI-assisted chapter-level introductions, examples, takeaways, and reflection prompts. They are labelled as **chapter context**, not paraphrases of each individual verse. `data/editorial-notes.json` contains the original three verse-specific notes for 18.46–48. These are editorial interpretations, not direct scripture, traditional commentaries, or a scholarly endorsement.

## Reproducing the import

Install Python and `beautifulsoup4`, download the above 18 Wikisource discourse pages to `work/source/besant-1.html` through `besant-18.html`, and download the Sanskrit JSON to `work/source/sanskrit.json`. Run:

```sh
python scripts/import-scripture.py
node scripts/check-content.mjs
node scripts/generate-seed.mjs
```

The generated data is committed, so deployment requires no source downloads, scraping, Python, external scripture API, or API key.

## Display punctuation

The reader displays em dashes as commas. Canonical imported data retains its source punctuation; this display adjustment does not rewrite the translation.

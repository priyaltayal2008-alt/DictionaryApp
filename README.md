# शब्दालय (Shabdalaya) — The Royal Manuscript Dictionary

An Indian-heritage-inspired, responsive Hindi–English dictionary, built in plain HTML, CSS and JavaScript for Track 3.

## Run locally

1. Download or clone this repository.
2. In VS Code, open the project folder.
3. For basic browsing, open `index.html` in Chrome. **For offline PWA features**, serve through localhost instead:
   - VS Code: use the **Live Server** extension and click **Go Live**, or
   - Terminal: run `python3 -m http.server 8000` and open `http://localhost:8000`.
4. Search for Hindi (`धर्म`), Romanised (`dharma`, `dharm`), or English meanings (`peace`).
5. For an offline test: open on localhost, refresh once, disconnect, then refresh. App assets are cached after a successful visit.

## Features and decisions

- **60 complete entries**, including all ten starter words, with headword, IAST transliteration, romanised variants, part of speech, meanings and an original Hindi example.
- **Live search** supports Devanagari and Latin spelling, including common romanisations, simplified diacritics, partial words, basic transliteration fallback, and typo tolerance for Latin queries.
- **Word details** include all required fields; click cards or use keyboard Enter.
- **Responsive design** optimised for phone, tablet, and desktop.
- **Bookmarks and recents** stored on the device in localStorage, without user accounts.
- **Offline support** through a service worker; core app runs without a network after initial caching. Web fonts may fall back to local fonts offline.
- **Optional pronunciation** uses browser speech synthesis where a Hindi voice exists.
- **No results state** suggests retrying different spellings.

## Roman spelling trade-offs

Most users will type in Roman script. The data includes common variants, but search does not rely on that list alone: it also normalises IAST diacritics, creates approximate roman representations from Devanagari and compares simplified alternatives. A lightweight Levenshtein check handles small typos (typically one or two edits). This is deliberately heuristic, not a formal transliteration engine: highly irregular spelling variations and all possible Hindi keyboard mistakes are not guaranteed. English meanings also work as a useful extra way to explore.

## Data quality

All entries are locally bundled and editable in `data.js`. The ten required starter entries are kept, and fifty further common Hindi terms have been added. Verify spellings and nuances with an authoritative dictionary or Hindi speaker before a public competition submission. Examples and meanings can depend on context.

## What I'd build with two more weeks

1. Linguist-reviewed expanded dataset with synonyms, inflections, and multiple senses.
2. A standards-based transliteration engine and better ranking for ambiguous Roman spellings.
3. Hindi audio recordings and example translations.
4. Automated tests, accessible keyboard suggestion list, and improved Hindi speech quality.
5. Optional online API for third-party integrations, with privacy controls.

## Suggested demo (2–3 minutes)

- Show homepage and its mobile layout.
- Search `धर्म`, `dharma`, and `dharm`, proving they resolve to the same entry.
- Try `shiksha`, `siksha`, `shaanti`, and a typo such as `shantii`.
- Open a card and show all fields.
- Try a nonexistent word to show the empty state.
- Bookmark a word, view Saved and Recent.
- Turn off network and demonstrate an already loaded/cached page still works.

## Git history / publishing

Commit your actual progress in stages (data, search, UI, details, offline, documentation) as you work. Deploy to GitHub Pages, Netlify, or Vercel. Service workers work on HTTPS and localhost; GitHub Pages supports HTTPS.

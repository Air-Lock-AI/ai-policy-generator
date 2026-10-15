# Changelog

## 1.4.0 — 2026-10-15
- Template moved to airlock Brand 2.0: noir cover with the blue-to-lilac orb and grain, chalk pages, slate ink, the pill mark in place of the orb, Instrument Serif roman headings (italic only for the airlock wordmark)
- Prohibitions use the semantic stop red; Flare is kept for status
- "Built with airlock" credit on the cover
- Page renumbering after a split now works in every language pack, not only English
- Fixed a stray space before the comma in clause 10 (nl, fr)
- Content pages print on white so no white frame shows around a chalk sheet
- SKILL.md: when run from airlock, load template and language packs as skill attachments
- Runtime files moved under `assets/` (`assets/template.html`, `assets/i18n/`, `assets/examples/`) so airlock's GitHub skill sync imports them

## 1.3.1 — 2026-06-22
- Added a canonical-text reference in `SKILL.md` so the chat draft mirrors the HTML output word for word, no more freelanced clauses
- Operating principle now explicitly forbids rephrasing or expanding fixed clause text

## 1.3.0 — 2026-06-22
- Split the AI tools question into three (chat clients, embedded AI, customer-facing AI)
- Added scope question (whole company / one department / specific cohort)
- Added enforcement / detection question (becomes a sentence in clause 9)
- Annex III addendum now requires enumeration of which uses apply
- Regulated-sector DPO informer note added when DPO is `[ to appoint ]`

## 1.2.0 — 2026-06-22
- New "people and internals" question step ensures the chat draft has zero placeholders
- The eight required fields (CEO, AI Officer, DPO, channel, access path, register URL, disciplinary code) are now asked upfront

## 1.1.1 — 2026-06-22
- Sector addendum is now a clause inside an existing band, never a new band, so it doesn't land alone on a sparse page

## 1.1.0 — 2026-06-22
- Don't assume airlock is the AI governance layer, ask explicitly
- Don't assume Claude is the AI client, ask which tools are in use
- Draft the full policy in chat for the user to read and explicitly approve before any file is generated

## 1.0.0 — 2026-06-17
- Initial release
- Three-page A4 layout (cover, the rules, the duties)
- 12-clause structure aligned to EU AI Act Articles 4, 5, 50
- Languages: English, Dutch, French, German
- Print-ready HTML with JS splitter for long content

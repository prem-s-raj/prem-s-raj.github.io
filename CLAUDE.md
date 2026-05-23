# CLAUDE.md — Personal Academic Website

This file guides Claude Code when working on this personal academic website.
Read it fully before making any changes.

---

## What this site is

A personal academic website for a researcher working at the intersection of
computational neuroscience, AI agents, and brain modeling. The site serves as
a home for: bio and affiliation, research papers and preprints, software
projects, blog posts/notes, and contact information.

The intended audience is other researchers, potential collaborators, and
anyone curious about the work. It should feel like it belongs in academia —
not in a startup or design portfolio.

---

## Aesthetic reference

The primary reference is **Dan Goodman's Neural Reckoning site**:
http://neural-reckoning.org and http://neural-reckoning.org/dan_goodman.html

Study it before making design decisions. Key properties to observe:
- Information is presented plainly, without visual decoration
- Papers are listed with authors, venue, and year — nothing more
- Navigation is flat and text-only
- The site does not try to impress; it tries to inform
- Typography does the heavy lifting

This site follows the same philosophy. It is a personal site, not a group
site, so it is slightly warmer and more first-person in tone.

---

## Design rules — never violate these

**Typography**
- Body font: EB Garamond (serif). This is non-negotiable. Do not switch to
  sans-serif for body text under any circumstance.
- Mono font: JetBrains Mono. Used for nav links, labels, dates, tags, and
  metadata only — never for body copy.
- Font sizes are deliberately set. Do not increase heading sizes to make
  things feel "more impressive". Do not go below 0.68rem for any visible text.

**Color**
- Palette is near-monochrome: off-white background (#faf9f6), dark text
  (#1a1a18), muted gray for secondary text, faint gray for metadata.
- The only accent colors are a muted navy for links (#2a4a8a) and a muted
  terracotta (#8a3a2a) reserved for rare highlights if needed.
- Do not introduce new colors. Do not add colored backgrounds to sections.
  Do not use bright or saturated colors anywhere.

**Layout**
- Maximum content width: 680px, centered.
- Single column. No sidebars. No multi-column layouts.
- Section separation is done with horizontal rules and whitespace, not
  background colors or cards.

**No animations**
- Zero animations. Zero transitions (except the most subtle link color
  change on hover, which is already in the CSS).
- No scroll effects, no fade-ins, no sticky elements beyond standard browser
  behavior.

**No decorative elements**
- No icons, emoji, badges, hero images, or illustration.
- No gradients, shadows, or rounded cards.
- Horizontal rules (`border-bottom: 1px solid var(--rule)`) are the only
  visual dividers.

---

## Site structure

All content lives in a single `index.html` file unless the site grows to need
separate pages. The sections in order are:

1. **nav** — name (left, acts as home link) + section links (right) + CV link
2. **about** — photo placeholder, name, one-line tagline, 2–3 paragraph bio,
   meta row with email / GitHub / Scholar / Twitter / CV
3. **research** — list of papers and preprints. Each entry: title (linked),
   authors (italic), venue + year (mono), links to arXiv / PDF / code
4. **projects** — software and tools. Each entry: name, one-line tag
   (active / archived), 2–3 sentence description, links
5. **blog / writing** — flat list of posts: title (linked) + date (mono, right-aligned)
6. **contact** — two-column grid: label (mono) + value. Ends with a short
   open-to-collaboration note.
7. **footer** — name + year, last-updated date. Mono, faint.

Do not add sections without being explicitly asked. Do not reorder sections.

---

## Content guidelines

**Papers section**
- List papers in reverse chronological order (newest first).
- Always include: title, authors, venue/journal or "Preprint", year.
- Mark works in preparation as "In preparation · 2025" — do not hide them.
- Link text for paper links should be lowercase: `arXiv`, `pdf`, `code`,
  `draft`. Never uppercase.
- Do not add abstracts inline. If the user wants abstracts, they go behind
  a `<details>` toggle, not expanded by default.

**Projects section**
- The Research Alignment Platform is the primary project. Its description
  should always mention: agentic, synchronizes code + standards + paper (.tex),
  Claude Code-powered, SSH or local, single environment from idea to result.
- Keep descriptions factual and understated. Do not use marketing language
  ("revolutionary", "seamless", "powerful").

**Blog section**
- Posts are listed by title and date only. No excerpts, no thumbnails.
- If no posts exist yet, leave placeholder entries rather than hiding the
  section — it signals intent.

**About section**
- Tone: first-person, direct, modest. Not a CV summary. Not a sales pitch.
- Do not use the word "passionate". Do not use "I am excited to".
- Academic affiliations go in the meta row, not in the bio prose.

---

## File organization (when the site grows)

```
/
├── index.html          # main page
├── CLAUDE.md           # this file
├── resume.pdf          # linked from nav and about
├── blog/
│   └── post-slug.html  # individual blog posts, same CSS as index
└── assets/
    └── photo.jpg       # profile photo (replace placeholder div)
```

Blog posts should use the same CSS as the main page. Copy the `<style>` block
or link a shared `style.css` if the site grows beyond 2–3 pages.

---

## What to do when asked to make changes

1. Re-read this file first.
2. Check whether the change would violate any rule above. If it would, say so
   and propose an alternative that stays within the aesthetic.
3. Make the smallest change that achieves the goal. Do not refactor or
   "improve" unrelated parts of the file.
4. Do not add new CSS variables, fonts, or color values without explicit
   instruction.
5. Preserve all existing comments in the HTML.

## What never to do

- Do not add JavaScript beyond what is already in the file (currently: none).
- Do not add a CSS framework (Tailwind, Bootstrap, etc.).
- Do not change the font stack.
- Do not add a dark mode toggle (the site is light-mode only by design).
- Do not add a cookie banner, analytics snippet, or any third-party script
  without explicit instruction.
- Do not rewrite sections that were not mentioned in the request.
- Do not add placeholder content that looks like filler — if something is
  unknown, leave a clear `[bracket placeholder]` so the user can fill it in.
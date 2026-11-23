# Gunty Radio

Single-file internet radio player.

**File:** `index.html`
**Backed up:** 2026-09-30 11:36 EDT
**Source:** `~/Music/index.html`
**SHA-256:** `b54809647bb828de46417d45a873af608d8941138f27ca46988d37f2b7622284`

---

## ⚠️ Why this backup matters

**This file was not in git and not backed up anywhere.** It lived only at
`~/Music/index.html`, outside every repository, and nothing else on the machine
held the current version. Before this backup, losing it would have meant losing
it outright.

The only other copy on this machine was a **stale 27 KB August version** (kept
in deliverable 1 under `older-copies/`, and duplicated at
`~/Work/index.html`). The current version is 48 KB. If you restore from the old
copy you will lose over half the app.

Going forward, either put this file in a git repo or re-run this backup after
editing it.

---

## What it is

A single self-contained internet radio player. One HTML file, one `<style>`
block, one `<script>` block, **zero external assets** — no CDN, no web fonts, no
image files. Open it straight off the filesystem and it works.

- **48,431 bytes**, 1,385 lines
- **916 lines** of inline JavaScript (`node --check` passes)
- **~50 station streams** across 74 remote references (KEXP, WFMU, KCRW, WQXR,
  Radio Paradise, SomaFM, CBC, and others)
- Streams are **Icecast / Shoutcast** endpoints, mostly HTTPS, some plain HTTP
- Plays through a single `<audio id="audioPlayer" crossorigin="anonymous">`
  element; `audio.src` is set at line 1246
- Renders **525 station cards** in the DOM

## Restore

```bash
cp index.html ~/Music/index.html
```

That is the whole procedure — there is nothing to install and nothing to
configure. Needs an internet connection to actually stream audio, but the page
itself renders offline.

## Verified at backup time

| Check | Result |
|---|---|
| Byte-identical to source | ✅ `cmp` clean |
| JavaScript parses | ✅ `node --check` |
| Renders in Chromium | ✅ 105 KB DOM, 525 station cards |
| Audio element present | ✅ `#audioPlayer` |
| External asset dependencies | ✅ none |

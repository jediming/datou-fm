# datou-fm
datou.fm website

- `index.html` — the whole site, in both languages. Every piece of text carries a Chinese and an English version
  (`<span class="zh">…</span><span class="en" lang="en">…</span>`); `<html lang>` decides which is shown.
- `en/index.html` — **generated**, never edited by hand. After any change to `index.html` run
  `python3 tools/build-en.py` and commit both files (`--check` tells you if it is stale).
- Mandarin is always the default at `/`; English lives at `/en/`. The header switch flips the language in place.

Landing-page rule:
1. `/` opens in Mandarin and `/en/` in English — an explicit URL always wins.
2. First visit on `/`: if the browser lists no Chinese language at all, a small "Read in English →" hint appears
   under the header. Nothing switches on its own. Dismissing the hint is remembered.
3. A language chosen via the switch (or the hint) is remembered on that device and applied on later landings
   on `/` (the address bar is updated to `/en/` to match). Nothing is stored until the visitor chooses.

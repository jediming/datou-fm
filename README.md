# datou-fm
datou.fm website

- `index.html` — the whole site, in both languages. Every piece of text carries a Chinese and an English version
  (`<span class="zh">…</span><span class="en" lang="en">…</span>`); `<html lang>` decides which is shown.
- `en/index.html` — **generated**, never edited by hand. After any change to `index.html` run
  `python3 tools/build-en.py` and commit both files (`--check` tells you if it is stale).
- Mandarin is always the default at `/`; English lives at `/en/`. The header switch flips the language in place.

# Ufobang

Free mobile-first browser arcade game by Stop60, an original fixed-shooter inspired by the classic arcade alien-invasion genre:
defend the Earth – a laser cannon at the bottom against a marching fleet of 55 aliens, four erodible shields and a red mystery ship.

- Single self-contained `index.html` (inline JS/CSS, embedded stop60.no fonts, rendered art and QR generator; works offline once loaded)
- Languages: Norsk (bokmål, default), Polski (`/pl/`), English (`/en/`), flag switch in the header; `?lang=no|pl|en`
- 5×11 formation that marches side to side, drops a row at each edge and speeds up (also as aliens die); aliens fire back
- 4 shields with pixel-exact erosion (3 sub-pixels per game pixel) from both sides' shots and from aliens reaching them
- Red Manta mystery ship (100–500 bonus), 3 lives + extra lives, waves that start lower, score + best score, pause, autosave
- One-finger control: touch anywhere on the playfield or the pad below it and slide – the cannon follows 1:1 and fires while the finger is down (no scroll/zoom/pull-to-refresh on iOS); optional ◀ ▶ + Fire buttons in the menu; keyboard on desktop; synthesised sound with mute
- Opt-in online leaderboard (Top 50 / today / this week, nickname, NO/EN/PL) on the shared Stop60 Supabase table via the checked RPC in `supabase/supabase_skjold.sql`; the game works fully without it
- Free, no ads, no account, no cookies

© 2026 Stop60 — all rights reserved, see LICENSE. Third-party fonts/QR library: see THIRD-PARTY-NOTICES.md.
- Address: https://stop60.no/ufobang/

## Name history / internal keys
Ufobang was developed as Kosmoskjold / Cosmo Shield / Kosmiczna Tarcza (hidden test address /skjold/, now a noindex redirect from the
repo jtaczala-cmyk/skjold to /ufobang/). Internally the old key is kept on purpose: leaderboard rows use `game = 'skjold'` with the
functions `skjold_start` / `skjold_submit` (supabase/supabase_skjold.sql), and the browser storage keys are `skjold_*_v1`, so saved games,
best scores, leaderboard settings and database rows carry over unchanged. Players never see this key.

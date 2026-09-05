# AGENTS.md — brand

Official brand assets for kist: the logo and the colour palette. **Assets and a
README — no code, no build, no dependencies, no tests.**

## Layout

| Path | What lives there |
| --- | --- |
| `src/logo/` | Logo files (`kist.png`) |
| `README.md` | The palette table and usage guidance — the canonical written reference |

## Why edits here are wider-reaching than they look

Every other getkist repo hotlinks the logo straight out of this repo's `main`
branch:

```
https://raw.githubusercontent.com/getkist/brand/main/src/logo/kist.png
```

That URL appears in the README of `kist`, `kist-cli`, `kist.js.org`, `.github`,
`.github-private` and others. **Renaming, moving or deleting a file under
`src/logo/` breaks the header image of every one of those READMEs at once.**
Add new files rather than replacing paths; if a path must change, update the
consuming repos in the same batch. (Note that `www-getkist-com`'s README
currently points at a `master` branch instead of `main` — an existing
inconsistency, not a second convention to follow.)

The brown `#5e4d34` in the palette is also hard-coded into the shields.io badge
URLs across those READMEs, so a palette change is a find-and-replace across the
organisation, not a one-file edit here.

## Palette

| Name | Hex | Usage |
| --- | --- | --- |
| Kist Brown | `#5e4d34` | Primary brand colour (and every badge `labelColor`/`color`) |
| Kist Cream | `#f5f2ed` | Background, light surfaces |
| Kist Dark | `#2c2416` | Dark mode, text |

Accent colours are listed in `README.md`. Keep that table as the single source
of truth — if a value changes, change it there first.

## Conventions

- Keep source formats alongside exports where possible, and keep the README
  file table in sync with what is actually in `src/`.
- Do not commit large binaries casually; this repo is fetched by raw URL from
  many places.

## Related repos (siblings in this workspace)

Every getkist repo consumes the logo. `www-getkist-com` also uses brand assets
in its theme; `.github-private/res/` holds internal design files (`kist.ai`).

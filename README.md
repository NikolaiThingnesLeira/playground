# Digg motion kit — public host

Public host for the **Digg** developer-platform motion kit: animated, Posten-branded
SVGs referenced as images from GitHub issues/PR comments (rendered via GitHub's Camo
image proxy, which only fetches public URLs).

This repo holds only the **renderable assets**. Orchestration lives elsewhere.

## Layout

```
motion/
  status/      status badges (queued / creating / running / failed / warning)
```

Reference an asset by its raw URL, e.g.:

```
https://raw.githubusercontent.com/NikolaiThingnesLeira/playground/main/motion/status/running.svg
```

## Design notes

- **Transparent + theme-safe** — no surface fill; colours read on both GitHub light and
  dark. Animation is pure CSS `@keyframes` (Camo renders `<img>`-SVG with CSS/SMIL, no JS).
- **No per-instance data** — assets are generic. Anything specific to a run lives in the
  referencing comment, never baked into a hosted asset.

> Prototype host on a personal account. Productionizing to an org-owned repo is tracked separately.

# DESIGN.md — sawyervalin.com

How the site should look. Read this before changing any page.

## Mood

A studio portrait on a blue-slate backdrop. Quiet, editorial, cool blue-grey, one accent. The name is the
monument; everything below it is plain text on hairline rules. No cards, no gradients
outside the hero, no 3D, no icons.

## Color

| Token | Value | Use |
|---|---|---|
| `--ink` | `#23272E` | page ground |
| `--ink-2` | `#2A2F37` | raised surfaces (subpages only) |
| `--line` | `#373D47` | hairline rules between rows |
| `--text` | `#ECEEF2` | primary text |
| `--mute` | `#A3AAB6` | secondary text, descriptions |
| `--dim` | `#7B8391` | labels, past dates |
| `--accent` | `#A9BED6` | steel blue: display type, current dates, one highlight per section |

One accent only. Never add a second hue. Buttons on the accent use `--ink` text.

## Type

- One family: **Archivo** (Google Fonts, variable `wdth 62..100`, `wght 400..800`).
- Display (`.display`): weight 700, `font-stretch: 62%`, uppercase, line-height .82, steel blue.
  Used for the hero name and every section heading. Nothing else is set this way.
- Body: Archivo 400 at 100% width, 16px base, line-height 1.6.
- Numbers in dates and stats use `font-variant-numeric: tabular-nums`.
- IBM Plex Mono survives only on the project subpages for small labels.

## Layout

- Hero: full-bleed, 100svh, radial blue-slate "studio light". Portrait cutout centred on the
  bottom edge. First name left and behind the portrait, last name bottom-right and in front
  of it, tagline top-right. Pill nav top-left, Resume and Contact pills top-right.
- Phones and portrait tablets (`max-width: 760px` or `max-aspect-ratio: 4/5`): first name
  across the top, tagline under it, last name over the bottom of the portrait.
- Every section after the hero: a big display heading, then `.rows` (hairline-ruled grid:
  label · title · description · links). Expertise is a three-column list on the same rules.
- Content width `--wrap` (90rem), side gutter `--gutter` (16–64px). Equal left and right edges.

## Components

- `.pill`: the one button shape. 1px outline, fully rounded; hover fills with `--text`.
  `.pill.solid` fills with the accent for the single primary action (Email me).
- `.btn`: the same rounded shape at row scale for project links.

## Motion

- Hero enters once: names rise, portrait lifts, tagline and nav fade. Nothing else animates.
- Hovers change colour only. `prefers-reduced-motion` turns all of it off (`site.css`).

## Don't

- Don't add cards, shadows, glows, or gradient text below the hero.
- Don't reintroduce three.js/WebGL; the page should work as plain HTML and CSS.
- Don't put captions under the portrait or add stock photos.

# Stayful Presentations · Project Notes

## Stayful logo

Canonical brand logo lives at `assets/stayful-logo.png` (672×398 PNG, dark-green
cursive on `#d1d6bd` sage background).

When generating an action plan HTML, **always base64-encode this file and embed
inline** as the brand-bar image — never link to a remote CDN. Inline keeps the
file self-contained, works offline, and survives email forwards.

```bash
base64 -w0 assets/stayful-logo.png
```

Then:
```html
<img src="data:image/png;base64,…" alt="Stayful">
```

### Brand bar styling

Because the logo PNG has a baked-in sage background (`#d1d6bd`), the brand bar
should match — otherwise the logo looks like a sticker on a dark green strip.

```css
.brandbar { background: #d1d6bd; color: #5d8156; }
.brandbar img { height: 44px; }
```

Dark green (`#5d8156`) stays as the primary accent for buttons, stats, badges,
and section headers — only the brand bar uses the sage.

## Hosted action plans

Repo is served as static files from the root by Vercel (`vercel.json`,
`outputDirectory: "."`). Files at the root are public at
`https://stayful-presentations.vercel.app/[filename]`.

- Pre-meeting presentations: `[firstname-lastname]-[mondayid].html` at root
- Post-meeting action plans: pattern TBD — currently saved to `outputs/`
  pending decision on root vs `/action-plans/` subfolder

Nothing in `outputs/` is currently linked from emails — that's drafted locally
for now.

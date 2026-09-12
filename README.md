# gz-theme

Dark themes for Gazelle-based trackers, with the DesiGaane logo swapped in.

- `dg-green.css` — green accent
- `dg-red.css` — red accent

## Install

On the tracker, go to **Settings**, paste one of these into **External stylesheet URL**,
and click **Save profile**:

```
https://viseriondragon.github.io/gz-theme/static/styles/ops_dark/dg-green.css
```
```
https://viseriondragon.github.io/gz-theme/static/styles/ops_dark/dg-red.css
```

Use the GitHub Pages links above, not `raw.githubusercontent.com` — raw serves CSS as
`text/plain`, which browsers refuse to apply as a stylesheet.

If you prefer the [Stylus](https://add0n.com/stylus.html) extension, install *by URL*
rather than pasting the file's contents: the stylesheet references its icons with
relative paths, which only resolve when it is loaded from the URL above.

## On phones

Rather than the stacked mobile layout, these render the **full desktop layout scaled
down to fit** — the sidebar stays beside the content, and the header drops from 413px
tall to 94px on a 390px screen. Text is small; pinch to zoom.

The header's **MENU** dropdown is also replaced on mobile by a row of always-visible
icons. Upstream it opens on `:hover`, which never fires in Safari on iOS: Safari only
does tap-to-hover on genuinely clickable elements — a real link, a form control, or
something with a click handler — and the menu is an inert `<ul>`. No CSS can make an
element clickable, so the hover trigger is dropped and the ten links are laid out
directly instead. (`cursor: pointer` is enough for Chrome, but not for Safari.)

## Credits

Essentially all of the CSS here is the work of **[Ewol](https://github.com/EwolBash)**,
from the **[opsdark](https://github.com/EwolBash/opsdark)** theme. This repo is a thin
re-brand of it, not an independent theme — the styling, the layout work, the icon set
and the years of Gazelle-specific fixes are all theirs.

The stylesheets were taken from upstream as of **2026-05-29**:

| this repo | upstream source | upstream commit |
| --- | --- | --- |
| `static/styles/ops_dark/dg-green.css` | `static/styles/ops_dark/opsgreen.css` | [`4500467`](https://github.com/EwolBash/opsdark/commit/4500467) |
| `static/styles/ops_dark/dg-red.css` | `static/styles/ops_dark/redwithopslogo.css` | [`fbf1572`](https://github.com/EwolBash/opsdark/commit/fbf1572) |

Everything under `static/styles/assets/` is copied unmodified from opsdark.

Local changes on top of upstream:

- the header logo — the embedded image in the `#logo a, #extra5` rule, plus its
  `background-size` and `background-position`;
- five inherited CSS typos fixed (a stray note that killed a whole rule, a hex
  colour missing its `#`, `rgbga(` → `rgba(`, an argument-less `cubic-bezier`, and
  a doubled slash in an asset path) — all present upstream, none introduced here;
- the mobile behaviour described above.

If you like this theme, credit and thanks belong upstream.

## License

GPL-3.0, inherited from [opsdark](https://github.com/EwolBash/opsdark), which is also
GPL-3.0. See [`LICENSE`](LICENSE).

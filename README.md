# Tidemark theme for Unraid

The look of [Tidemark](https://github.com/tidemark-analytics/tidemark) for the Unraid WebGUI: Geist type, hairline borders, small radii, deep-water neutrals and a single Tide teal accent. It follows your browser's light/dark preference, like Tidemark's "system" theme.

## Install

**Plugin (recommended):** Plugins → Install Plugin, then paste

```
https://raw.githubusercontent.com/FoggyMtnDrifter/unraid-tidemark-theme/main/tidemark-theme.plg
```

**Manual:** copy `tidemark.css` to `/usr/local/emhttp/plugins/dynamix/styles/themes/` and `fonts/*` to `/usr/local/emhttp/plugins/tidemark-theme/fonts/`. This does not survive a reboot unless you re-copy it from `/boot` in `/boot/config/go`.

Then pick **Tidemark** under Settings → Display Settings → Dynamix color theme.

## How it works

Unraid builds the theme dropdown from `styles/themes/*.css` and loads `<name>.css` after its base stylesheets. `tidemark.css` defines Tidemark's tokens (`--tm-*`, values copied from Tidemark's `app.css`), maps them onto the variables Unraid's base CSS reads (`--text-color`, `--border-color`, `--dynamix-*`, ...), and restyles buttons, inputs, tables, dialogs and usage bars. Unraid's hardcoded brand orange is remapped to Tide teal; amber (`--tm-signal`) is used for warning-level usage bars.

## Known limits

- Written against the current Unraid WebGUI sources (`default-base.css`, `ThemeHelper.php`), **not yet tested on a live server**. Expect a few pages that need selector tweaks; open an issue with a screenshot.
- Unraid's `ThemeHelper` only knows its four built-in theme names, so a custom theme gets the top-navigation layout and no dark/light flag. Docker log text color is overridden in the CSS for that reason.
- Light/dark follows the OS/browser, not an in-app toggle.
- Update the `gitURL` entity in `tidemark-theme.plg` if you host the repo somewhere other than `FoggyMtnDrifter/unraid-tidemark-theme`.

Geist fonts are SIL OFL (see `fonts/GEIST-LICENSE.txt`).

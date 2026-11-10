# omarchy-dtp-bar

Omarchy's bar with one change: its glassy background is as solid as the theme says, instead of a fixed 0.35. The dtp menus, lists and flyouts read the same number, so they match the bar they attach to.

The number is `glass-alpha` in the `[dtp]` section of the shell settings, which `omarchy-dtp-theme` sets (`shell.dtp.toml`). Without the theme it falls back to 0.35, which is stock.

It replaces the stock bar while enabled. Only line 89 of `Bar.qml` differs from stock.

## Install

`omarchy-dtp-install` runs this. From GitHub:

```bash
omarchy plugin add https://github.com/dtpietrzak/omarchy-dtp-bar.git --enable
```

## After an Omarchy update

The bar is a copy, so Omarchy updates to the stock bar don't reach it. Copy the new `Bar.qml` (and `widgets/`, `indicators/`, `BarModel.js`) from `/usr/share/omarchy/shell/plugins/bar/` and change the `glassBackground` line again:

```qml
Math.min(background.a, Commons.Color.pickAlpha("dtp.glass-alpha", 0.35))
```

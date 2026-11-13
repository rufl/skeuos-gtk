# Attribution

Skeuos Square is a DINX port of the daniruiz/skeuos-gtk GTK theme to the Pearl community
theme format (schema 1). It is not affiliated with or endorsed by the upstream
authors.

- Upstream: https://github.com/daniruiz/skeuos-gtk
- DINX fork: https://github.com/rufl/skeuos-gtk
- Upstream license: GPL-3.0 (see LICENSE)

## Derivation

Palettes were derived from the upstream SASS color definitions:

- Skeuos: `src/sass/common/_colors.scss` and the Blue variant colors in
  `src/Makefile.inc` (`COLOR_Blue #2777ff`, `TEXT_COLOR_Blue #ffffff`).
- Orchis: `src/_sass/_colors.scss`, `src/_sass/_color-palette-default.scss`
  and `src/_sass/_tweaks.scss` (default palette, `$default_corner: 12px`).

SASS `darken`, `lighten` and `mix` were evaluated in HSL/RGB to obtain exact
hex values. Alpha-based text/border colors were blended over their upstream
backgrounds.

Pearl validates WCAG contrast of at least 4.5:1 for text, secondary text,
accent text and error colors. Where an upstream color falls below that floor,
the nearest passing shade was chosen by minimal HSL lightness adjustment:

- Skeuos accent `#2777ff` was darkened for white accent text in both variants.
- Skeuos dark error `#bf1717` was lightened against its error container.
- Orchis dark accent `#3281EA` was darkened for white accent text.
- Orchis light error `#E53935` was darkened, and dark error `#F44336`
  lightened, against their error containers.

All other colors are unmodified upstream values or direct SASS derivations.

## Shape

Card and control radii are 0 px (square variant). Both variants ship dark and light palettes; the square variant
keeps the same colors, borders and spacing with zero corner radii.

## Application profiles (schema 2)

The `profiles/` adapters (gtk, qt5ct, qt6ct, kcolorscheme, ghostty) are derived
from Pearl's bundled Material profiles, which are MIT licensed and attributed
to Pearl and AvengeMedia/DankMaterialShell contributors
(https://github.com/AvengeMedia/DankMaterialShell). The matugen templates are
used unmodified; they resolve against this theme's palettes, so application
colors follow the Skeuos/Orchis-derived scheme instead of Material purple.

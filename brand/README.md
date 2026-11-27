# Brand assets

`og.svg` is the source of `static/og.png`, the OpenGraph share card
(1200×630). It is the one artifact on this site with a derivation step, so
it is committed alongside its output.

Render it with the site's own typeface, no system fonts:

```sh
nix run nixpkgs#resvg -- brand/og.svg static/og.png \
  --font-family Inter \
  --use-fonts-dir "$(nix build nixpkgs#inter --no-link --print-out-paths)/share/fonts/truetype" \
  --skip-system-fonts
```

Palette matches `sass/site.scss`: `#17171a` canvas, `#00cfbe` accent,
`#f4f4f5` ink.

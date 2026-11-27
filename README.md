# journey.pm — The Deliberation Journey

The public website for **The Deliberation Journey** — a software-development
methodology for the agentic era. Built with
[Zola](https://www.getzola.org/), hand-rolled theme (no vendored theme).

The canonical statement of the methodology lives in the methodology
repository, not here: this site distils it for a public audience.

## Local development

```sh
nix run nixpkgs#zola -- serve
```

(`build` and `check` work the same way; `check` verifies internal links.)

## Contributing

Content is markdown in `content/`, the theme is `sass/site.scss` plus the
Tera templates in `templates/`. Pushes to `main` publish the site.

## Content and license

- **Content:** CC BY-SA 4.0.
- **Site code:** AGPL-3.0-or-later.

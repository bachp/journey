# journey.pm — The Deliberation Journey

The public website for **The Deliberation Journey** — a software-development
methodology for the agentic era. Built with
[Zola](https://www.getzola.org/), hand-rolled theme (no vendored theme),
served from GitHub Pages at <https://journey.pm>.

The canonical statement of the methodology lives in the methodology
repository, not here: this site distils it for a public audience.

## Local development

```sh
nix run nixpkgs#zola -- serve
```

(`build` and `check` work the same way; `check` verifies internal links.)

## Deployment — GitHub Pages + custom domain

`.github/workflows/pages.yml` builds with a pinned Zola, runs `zola check`,
and publishes `public/` through the Pages artifact API. Only pushes to
`main` publish — draft branches would otherwise go live.

The custom domain is set in **Settings → Pages → Custom domain**, not by a
file: with an Actions publishing source GitHub ignores any `CNAME` in the
artifact. `static/CNAME` is kept as documentation of the canonical domain
(and would be required if the publishing source ever changes to a branch).

At **Infomaniak**, the records for the apex are the four GitHub Pages A
records (optionally the AAAA set), plus a `CNAME` for `www`:

| Type | Name | Value |
|---|---|---|
| A | `journey.pm` | `185.199.108.153` |
| A | `journey.pm` | `185.199.109.153` |
| A | `journey.pm` | `185.199.110.153` |
| A | `journey.pm` | `185.199.111.153` |
| CNAME | `www` | `bachp.github.io` |

Do not use `DNAME`: it redirects names *below* its owner and leaves the apex
itself unresolved (RFC 6672 §2.3).

See <https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site>
for the authoritative values. Enable "Enforce HTTPS" in the repository's
Pages settings once the certificate is issued.

The repository must be public, or Pages requires a paid plan.

## Content and license

- **Content:** CC BY-SA 4.0.
- **Site code:** AGPL-3.0-or-later.

# journey.pm — The Deliberation Journey

The public website for **The Deliberation Journey** — a software-development
methodology for the agentic era. Built with
[Zola](https://www.getzola.org/), hand-rolled theme (no vendored theme),
hosted on [Codeberg Pages](https://docs.codeberg.org/codeberg-pages/) at
<https://journey.pm>.

`BRIEF.md` in the repo root is the design contract for this site: the pages,
the design direction, the deployment setup, and the verification bar.

## Local development

```sh
nix run nixpkgs#zola -- serve
```

(`build` and `check` work the same way; `check` verifies internal links.)

## Deployment — Codeberg Pages + custom domain

Deploys run from `main` via the Forgejo Actions workflow in
`.forgejo/workflows/pages.yml`: a pinned Zola 0.22 container builds the site,
then the official [git-pages action](https://codeberg.org/git-pages/action)
deploys `public/`. Pushes to any other branch never publish (draft branches
would otherwise go live).

### First deploy

1. Create the Codeberg repository and push this repo to it.
2. Point DNS at Codeberg. At **Infomaniak**, add these records for
   `journey.pm` (values from the Codeberg docs — they may change, so check the
   linked page rather than trusting this file):

   | Type | Name | Value |
   |---|---|---|
   | A | `journey.pm` | `217.197.84.141` |
   | AAAA | `journey.pm` | `2a0a:4580:103f:c0de::2` |
   | TXT | `_git-pages-forge-allowlist.journey.pm` | `"https://codeberg.org/<username>/journey.pm.git"` |

   Use a modest TTL (e.g. `3600`) so the host can be flapped during setup.
   The `<username>` is the Codeberg account (or organization) that owns the
   repo. See <https://docs.codeberg.org/codeberg-pages/using-custom-domain/>
   for the authoritative values and the CAA-record pitfall.

3. Push to `main` (or trigger the workflow); the first deploy bootstraps the
   TLS certificate. The `server: codeberg.page` parameter in the workflow is
   what makes that first custom-domain deploy possible — keep it.

### `www`

Deliberately **apex-only** for now. If `www.journey.pm` is ever wanted, the
docs describe the pattern: a `_redirects` file in the site redirecting
`www → apex`, plus a second Pages deploy target for the `www` host (with its
own DNS setup). See
<https://docs.codeberg.org/codeberg-pages/using-custom-domain/>.

## License

- **Content:** CC BY-SA 4.0 — placeholder decision, confirmable by the author.
- **Site code:** AGPL-3.0-or-later.

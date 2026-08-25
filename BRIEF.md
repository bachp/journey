# BRIEF — journey.pm static site (The Deliberation Journey)

You are building the public website for a software-development methodology called
**The Deliberation Journey**. It will be hosted at **https://journey.pm** on
**Codeberg Pages**. This brief is self-contained; read it fully before writing code.

## 1. What this site is

A prose-first methodology site: a handful of evergreen pages plus a blog.
No web app, no interactivity beyond links, no tracking. The audience is
software engineers and engineering leaders evaluating how to run development
with AI agents.

Non-negotiable constraints:

- **Zero external requests.** No Google Fonts, no CDN scripts, no analytics.
  System font stack only. (The methodology has a European-sovereignty flavor;
  a privacy-clean site is on-message.)
- **No JavaScript frameworks.** No JS at all unless strictly needed; none is expected.
- **Hand-rolled Zola theme** in this repo. Do not vendor a stock theme.
- **Never mention "Vitogee"** — that is a private implementation project and must
  not appear anywhere on the public site.
- NixOS environment: there is no pip. Build/verify with `nix run nixpkgs#zola -- build`
  (Zola 0.22.x). Shell scripts must run via `sh script.sh`, not `bash`.

## 2. Source material (read these first)

The methodology's canonical documents live outside this repo. Read all of them;
the site copy is distilled FROM them, quoting exactly where noted:

| File | Use for |
|---|---|
| `/home/pascal/Ideas/deliberation-journey-sdlc.md` | Core Model, axiom, metrics, references (the main doc) |
| `/home/pascal/Ideas/deliberation-journey-sdlc/elevator-pitch.md` | Front-page pitch (quote the 30-second version verbatim) |
| `/home/pascal/Ideas/deliberation-journey-sdlc/comparisons.md` | Comparisons page (condense; do not dump) |
| `/home/pascal/Ideas/deliberation-journey-sdlc/naming.md` | Vocabulary rules + the etymology story for a blog post |

Controlled vocabulary (from naming.md — follow strictly in all site copy):

- Say **Baseline** (capitalized), never "village", in normative text.
- Lifecycle frame: **departure → exploration → return** layered over state names.
- **Return** (the full act) is never used interchangeably with **merge** (the mechanic).
- **Record** = frozen journey-scoped artifact; **Registry** = living baseline component.

## 3. Site structure

Pages (top level, Zola pages not sections unless noted):

1. **`/` index** — Hero: the tagline "Every journey starts with a conversation.
   Every conversation ends as a record." then the 30-second pitch (verbatim from
   elevator-pitch.md), then three entry links (The Model / Invariants / Comparisons)
   and a subtle link to the blog. Also a short "tl;dr" box with the ten-second version.
2. **`/methodology/`** — The Core Model in your own concise words, distilled from the
   main doc's Core Model section: baseline / journey / return; the one-lift statement
   (trunk-based development, trunk = whole product, branch = journey over the whole
   product); the axiom (consensus binds to intent and observable behavior; code is a
   disposable projection); the two change regimes (evolving-and-governs vs
   frozen-and-explains); "a protocol, not a file format".
3. **`/invariants/`** — The three invariants as the conformance test, verbatim intent
   from the main doc's "Implementations vary; invariants don't" paragraph:
   (1) intent-like and behavior-like projections must exist; (2) both change regimes
   must exist; (3) journeys carry deltas plus decision and provenance artifacts.
   Close with: any implementation missing one is a file format, not the methodology.
4. **`/comparisons/`** — A condensed map of the landscape as **partial
   implementations**: trunk-based development (topology), OpenSpec / Spec Kit / Kiro
   (solo corners: data-model half, consensus assumed away), plus the one-line verdicts.
   Table + short prose. Link to the full comparisons doc on request is NOT possible
   (private); instead end with: "Detailed comparison write-ups are planned as blog
   posts."
5. **`/blog/`** — Section with tags taxonomy, RSS/Atom feed, reverse-chronological.
   Seed with two posts (write these from the sources, your own clear prose):
   - **"Hello, journey.pm"** — announcement: what the methodology is (use the
     30-second pitch), why a site, what's coming (comparison deep-dives, the metrics
     model). Keep under 400 words.
   - **"Why 'journey'"** — the naming story: the explorer analogy in two sentences,
     the round-trip requirement for the primitive's name (why task/branch/epic/quest/
     expedition/mission/sprint fail), the etymology (jornee = a day's travel;
     journal shares the root), and the Swiss legal precedent (AS/SR two-class split
     running at national scale). This is genuinely good material — do it justice,
     ~600-800 words, with the etymonline link from naming.md.
6. **`/about/`** — One screen: what this site is, who runs it (Pascal, a Swiss
   engineer — no more personal detail), the license line (see §6), and a contact
   placeholder (mailto: to be filled later — use a clearly-marked TODO comment in
   frontmatter, not visible text).

Also produce:

- **`404.html`** — on-brand: "This journey never returned." + link home.
- **`robots.txt`** — allow all, point to sitemap.
- **`llms.txt`** at site root (static file): a short markdown index of the site for
  agent ingestion — one-paragraph site summary, then a link list of every page with
  one-line descriptions, plus the Atom feed URL. On-message: a methodology about
  agents reading the trunk should let agents read its site.
- **`sitemap.xml`** — Zola generates this automatically; ensure it's in output.
- **Atom feed** for the blog (Zola: `generate_feeds = true`).
- A simple **SVG favicon**: a minimal "journey mark" — a circle (the baseline) with
  one line leaving it and returning to it. Monochrome, currentColor, 32x32 viewBox.
  Reuse it as the header mark at small size.

## 4. Design direction (documentation-grade, restrained)

- Light-first design with a real **dark mode** via `prefers-color-scheme`
  (define both token sets in CSS custom properties on `:root` and a
  `@media (prefers-color-scheme: dark)` override).
- Palette: near-black ink `#1c1e21` on warm paper `#fbfaf8`; single muted accent
  — deep clay/rust `#a8442a` — used ONLY for links, the journey mark, and small
  labels. No gradients, no glassmorphism, no drop shadows heavier than subtle.
- Dark mode: ink `#e8e6e1` on `#16181b`, accent brightened to `#d97a5d`.
- Type: system stack — `Georgia, 'Iowan Old Style', 'Times New Roman', serif` for
  body prose? NO — decide deliberately: use a **sans for UI/chrome** and **serif for
  long-form prose** (the site is prose; serif body at ≥18px/1.7 reads as considered).
  Headings sans, tight tracking. Monospace (`ui-monospace, 'JetBrains Mono', …`) for
  the few code-ish spans (state names like `departure → exploration → return`).
- Prose max-width ~68ch, generous paragraph spacing, `text-wrap: pretty` on prose.
- Header: wordmark "journey.pm" (lowercase, letterspaced) + the journey mark;
  nav links right: Model · Invariants · Comparisons · Blog · About.
  Footer: license line, Atom feed link, "hosted on Codeberg Pages" with repo link
  placeholder `https://codeberg.org/JOURNEY-PM-ORG/journey.pm` (TODO comment to fix).
- Responsive single column; nav collapses to a simple wrapped row (no hamburger JS).
- Accessible: real focus states, link underlines, AA contrast for both modes,
  hit targets ≥44px where interactive.

## 5. Zola specifics

- `config.toml`: `base_url = "https://journey.pm"`, `title = "The Deliberation Journey"`,
  `description` from the ten-second pitch, `default_language = "en"`,
  `generate_feeds = true`, `feed_filenames = ["atom.xml"]`,
  `taxonomies = [{ name = "tags", render = true, feed = true }]`,
  `compile_sass = true`. Do NOT enable search (needs JS).
- Templates: `base.html`, `index.html`, `page.html`, `section.html`,
  `blog/page.html` (post layout with date + tags), `404.html`. Tera.
- Sass: `sass/site.scss` → one stylesheet, all tokens as CSS custom properties.
- Blog posts front matter: `title`, `date` (use 2026-08-25), `[taxonomies] tags = [...]`.
- `.gitignore`: `public/`, `.zola_cache/` (if created).

## 6. Deployment — Codeberg Pages via Forgejo Actions

Create `.forgejo/workflows/pages.yml`:

- Trigger: push to `main` only (docs warn draft branches would publish).
- Build: recommend `container: image: ghcr.io/getzola/zola:v0.22.1` with
  `entrypoint: [""]`, steps `actions/checkout@v4` then `zola build` then the
  deploy step. If you find a more canonical runner setup, use it, but keep the
  Zola version pinned to 0.22.x.
- Deploy step uses the official action from the Codeberg docs
  (`https://codeberg.org/git-pages/action` — reference it exactly as the docs'
  "custom domain" case shows):
  `with: site: journey.pm, server: codeberg.page, source: public`,
  token from the runner-provided secret. The `server` parameter is REQUIRED for
  the first custom-domain deploy (TLS bootstrap loop) — keep it permanently.
- Validate the YAML parses (e.g. `python3 -c "import yaml,sys; yaml.safe_load(open('.forgejo/workflows/pages.yml'))"`).

`README.md` must document, in order:

1. What this repo is; the BRIEF is the design contract.
2. Local dev: `nix run nixpkgs#zola -- serve`.
3. First deploy: create the Codeberg repo, push, then set DNS at Infomaniak:
   - `A     journey.pm                 → 217.197.84.141`
   - `AAAA  journey.pm                 → 2a0a:4580:103f:c0de::2`
   - `TXT   _git-pages-forge-allowlist.journey.pm → "https://codeberg.org/<username>/journey.pm.git"`
   (exact values from Codeberg docs; note they may change — link
   https://docs.codeberg.org/codeberg-pages/using-custom-domain/).
   Suggest a modest TTL (e.g. 3600) so the host is flappable.
4. `www` handling: deliberately apex-only for now; note the `_redirects` +
   second deploy-target pattern from the docs for later.
5. License: content under **CC BY-SA 4.0** (placeholder decision — flag it in the
   README as confirmable), site code under **AGPL-3.0-or-later**.

## 7. Verification (do all, in order — this is the acceptance bar)

1. `nix run nixpkgs#zola -- build` exits 0 in the repo root.
2. `nix run nixpkgs#zola -- check` — no broken internal links (fix any).
3. `public/` contains: `index.html`, `methodology/index.html`, `invariants/index.html`,
   `comparisons/index.html`, `blog/index.html` + two posts, `about/index.html`,
   `atom.xml`, `sitemap.xml`, `robots.txt`, `llms.txt`, `404.html`, the stylesheet,
   and the favicon SVG.
4. The workflow YAML parses (command above).
5. `grep -ri vitogee content/ templates/ sass/ static/ README.md` returns nothing.
6. `grep -ri "village" content/ | grep -v blog/why-journey` — the word may appear
   only inside the naming blog post's analogy, nowhere in normative pages.
7. Valid HTML spot-check: every page has `<title>`, exactly one `<h1>`, and a
   canonical link (`<link rel="canonical">`).
8. Dark-mode tokens exist (grep for `prefers-color-scheme` in the built CSS).
9. Atom feed has both posts; sitemap lists all pages.
10. Commit everything on `main` with a clear message; leave the working tree clean.
    Do NOT push anywhere (no remote configured yet).

When done, print a summary: pages built, posts written, verification results
1–9 as PASS/FAIL each, and any deviations from this brief with one-line reasons.

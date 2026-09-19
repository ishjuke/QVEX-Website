# QVEX-Website
Website for the Queen's VEX U Robotics Team (QVEX)

A single-page promotional site for **QVEX**, Queen's University's VEX U robotics team.

Everything is in `index.html` — no build step, no dependencies, no framework. The only external
request is the Google Fonts stylesheet (Chakra Petch / IBM Plex Sans / IBM Plex Mono).

```
qvex-site/
└── index.html    # the entire site
```

## Running it locally

Open `index.html` in a browser. That's it. Or, if you want a local server:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Deploying

**GitHub Pages** (easiest, free, works with a custom domain):

1. Push this repo to the QVEX org on GitHub.
2. Settings → Pages → Source: `Deploy from a branch` → branch `main`, folder `/ (root)`.
3. Live at `https://<org>.github.io/<repo>/` within a minute or two.
4. To put it on `qvex.ca`: add a `CNAME` file containing `qvex.ca` at the repo root, then point
   the domain's DNS at GitHub Pages (`A` records to GitHub's four Pages IPs, or a `CNAME`
   record for `www`). Settings → Pages → Custom domain, then tick **Enforce HTTPS**.

Netlify, Cloudflare Pages and Vercel all work the same way — drag the folder in, or connect the
repo. No build command, publish directory is the repo root.

## Design notes

- **Palette** — purple-forward, per the engineering design team convention. Tokens live in the
  `:root` block at the top of the `<style>`: `--violet`, `--violet-bright`, `--plum`, `--lilac`,
  with purple-biased neutrals and `--gold` reserved *only* for judged awards.
- **Type** — Chakra Petch for display (angular, mechanical), IBM Plex Sans for body,
  IBM Plex Mono for labels, specs and data. All have real fallback stacks.
- **Committed dark theme.** The page paints its own background and every colour explicitly, so it
  renders identically regardless of the viewer's OS light/dark setting.
- **Field diagram** in the hero is hand-authored inline SVG — a top-down Push Back field (12 × 12
  ft, 6 × 6 tiles, long goals, centre goal, blocks, park zone) with an animated autonomous path.
  It respects `prefers-reduced-motion`.
- **Responsive** down to ~360px; every grid collapses to one column.

## TODO before this goes public

Placeholders are marked in the HTML with `class="tbd"` — dashed purple chips, easy to find with
a search for `tbd`. Delete the chip once the real content is in.

- [ ] **Photos.** There are none anywhere on the site right now. Needed: team shot, robot
      close-up, a competition action shot. Drop them in an `img/` folder and reference them.
- [ ] **Robot specs for QUEEN** — drivetrain, scoring mechanism, anything worth bragging about
      (Season → "Our robots" panel).
- [ ] **2025–26 results** as the season progresses (Results → first timeline entry).
- [ ] **Fix the years on two timeline entries.** The Queen's Robotics Cup and West Virginia
      entries say "Recent season" because the source they came from didn't specify a year.
- [ ] **Meeting times and lab/bay location** (Join section).
- [ ] **Open director roles** — currently only General Member and Software Project Lead are
      listed. Add or remove as postings open and close.
- [ ] **Verify the Software Project Lead link.** It points at the Linktree rather than the Clikk
      Apply posting directly; swap in the direct URL if you want it to survive Linktree edits.
- [ ] **OG preview image.** There's a commented-out `og:image` tag in the `<head>`. Add a
      1200×630 PNG and an absolute URL so links unfurl nicely in Discord and Slack.
- [ ] **Sponsor logos.** Currently text-only cards. Swap in logos if the sponsors have supplied
      brand assets.

## Content sources

Facts on this page were assembled from public QVEX material:

- [linktr.ee/qvex](https://linktr.ee/qvex) — social links, applications, robot reveal
- [qvex.ca](https://www.qvex.ca/) — team history, achievements
- [qvex.ca/sponsors](https://www.qvex.ca/sponsors) — sponsor list, sponsorship pitch
- [EngSoc general member posting](https://breezy.engsoc.queensu.ca/p/e928d89c4ac6-queen-s-vex-u-robotics-team-qvex-general-member) — sub-teams, "no experience necessary", contact

Anything not in those sources is marked as a placeholder. Nothing was invented.

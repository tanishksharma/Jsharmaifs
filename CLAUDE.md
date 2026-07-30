# Jsharmaifs

Public profile site for Dr Jagmohan Sharma, Indian Forest Service (1990, Karnataka cadre),
former Director of the Indira Gandhi National Forest Academy. The writing archive is the point
of the site; career and contact support it.

## URLs

| What | URL |
| --- | --- |
| **Live (production)** | https://www.jsharmaifs.in |
| Apex, 308s to www | https://jsharmaifs.in |
| Vercel production alias | https://jsharmaifs.vercel.app |
| Staging | https://staging-jsharmaifs.vercel.app (the `staging` branch) |

- Give out `https://www.jsharmaifs.in`. The apex redirects to it, so www is canonical.
- Deploys are GitHub-connected: a push to `main` builds production automatically; a push to
  `staging` builds the staging deployment.
- `staging-jsharmaifs.vercel.app` is a vercel.app domain pinned to the `staging` branch — the
  shareable staging URL. Note it only serves publicly while the project's Vercel Authentication
  (deployment protection) is off; manually-added vercel.app domains do NOT get the
  custom-domain exemption, so turning protection back on puts staging behind a Vercel login.
  The raw branch alias is `jsharmaifs-git-staging-tanishksharmas-projects.vercel.app`.

## Vercel

- Project `jsharmaifs`, id `prj_Bts70VilhPVvM1vQYF8r7HmIiKhS`
- Team `tanishksharmas-projects`, id `team_DIM6xuaq92YF06ZI5GIloNpV`
- No framework. Static files served from the repo root.

## Stack

- Plain HTML and CSS. No build step, no dependencies, no framework.
- **Facet is the design system** — the library at https://facet.tanishksharma.com, consumed
  by URL from `https://facet.tanishksharma.com/lib/facet.css` and `facet.js`. Source repo is
  `tanishksharma/facet`; the full component reference is at
  `https://facet.tanishksharma.com/llms.txt` — read that before inventing markup or CSS.
  Build new patterns here first, promote them there once they repeat.
- `styles.css` is the only project CSS: the forest-green accent override plus the three custom
  pieces Facet does not carry (`.lede`, `.pieces`, `.section-note`). Tokens only.
- `vercel.json` sets `cleanUrls`, so `career.html` serves at `/career`.

## Pages

| File | Route | Holds |
| --- | --- | --- |
| `index.html` | `/` | Landing (portrait, name, one credential line) and the writing list |
| `career.html` | `/career` | Six career entries, education last |
| `contact.html` | `/contact` | Contact form |

Navigation is Facet's `.tab-bar.tab-bar-top` on all three, with the name as the brand and three
link segments. Set `aria-current="page"` on the current page's segment.

## Content rules

- Every claim on this site is sourced. Do not add biographical detail, dates, or credentials
  that have not been verified against a published source.
- Columns link out to the publisher. Full text is not hosted here: the reprint rights for the
  Deccan Herald columns have not been cleared.
- Deliberately lean. The research turned up far more than is shown (17 journal papers, reports,
  talks, press coverage). Only add a section when he asks for it.

## Open items

- `CONTACT_EMAIL` in `contact.html` is `PLACEHOLDER@example.com`. The form does nothing until
  it holds a real address.
- The contact form has no backend; it composes a `mailto:` and hands off to the reader's mail
  client. Swap for a real endpoint if volume ever justifies it.
- Portrait is the 800x800 press photo from Garhwal Post, the same official portrait the
  government site uses. Replace if a higher-resolution original turns up.

# Bailey Terminals — baileyterminals.com

Same stack as deadbeta, wildlyoverrun, and turnvia: Eleventy static site,
built on Netlify, pushed from GitHub.

## What's in here

- `/` — home: network overview, plus a blurb card for each site (with
  photo, quick specs, and a link to that site's detail page)
- `/cartersville/` — full services + specs for the Cartersville, GA site
- `/memphis/` — full services + specs for the Memphis, TN site
- `/about/` — company background
- `/contact/` — Netlify Forms capacity-request form

Each site page is self-contained — services and location specs live
together on the same page, rather than split across a separate
"Services" and "Locations" page like the first draft. Add a third site
later by copying `cartersville.njk`, changing its front matter and
content, and adding a new blurb card to `index.njk`.

## Design

- **Palette:** slate steel (`#1C2630`), weathered concrete (`#EDEBE3`),
  signal-block green (`#2F7A52`) as the primary accent, corten rust
  (`#A34A28`) as the secondary accent — pulled from the rail yard itself,
  not a generic corporate palette.
- **Type:** Oswald for headlines (the same condensed lettering style
  stenciled on actual rail cars), Public Sans for body copy, JetBrains
  Mono for data/labels.
- **Signature element:** the "siding" bars used as section dividers — a
  literal rail-track motif, since railcar *spots* are the actual product
  being sold. The capacity strip on the home page renders real spot
  counts the same way a track diagram would.

## ⚠️ Before you publish — placeholders to fill in

A few things are marked as placeholders rather than invented, since this
is a real B2B site and false claims here are a real liability, not just
a copy nit:

- **Contact page** — phone/email for each site are `[phone / email]`
  placeholders. Fill in before launch.
- **Memphis capacity** — the home page and Memphis page don't state a
  specific railcar-spot or square-footage number because I don't have
  one from our conversation. Cartersville's "~60 spots" is the number
  you gave me directly.
- **Site photography** — real photos are now in place: `site-cartersville.jpg`
  (rail siding along the fence line), `site-memphis.jpg` (rail siding
  with tank cars, used as the primary Memphis image), and
  `site-memphis-ops.jpg` (container/trailer staging, used as a
  secondary shot on the Memphis page). Swap any of these for better
  shots later by replacing the file and keeping the same filename.
- **FTZ language** — the Cartersville services copy says the site "sits
  inside the Georgia FTZ service area" and invites an inquiry — it does
  **not** claim Bailey Terminals itself holds FTZ subzone status, since
  that hasn't been confirmed. If you do have (or get) an actual FTZ
  designation, update this to state it directly — it's a strong claim
  worth making explicitly once it's true.
- Swap `Send request` form action / thank-you behavior if you want a
  custom confirmation page instead of Netlify's default.

## Getting it live (same steps as your other sites)

1. Create a new GitHub repo, e.g. `github.com/alphado9/baileyterminals`.
2. Unzip this and drag **all** files/folders into that repo via the
   GitHub web UI.
   - ⚠️ GitHub's drag-and-drop uploader flattens nested folders. After
     the initial upload, manually verify (or re-create via "Add file →
     Create new file") that these nested files exist correctly:
     - `.eleventy.js`
     - `src/_includes/layouts/base.njk`
3. In Netlify: **Add new site → Import from GitHub** → pick
   `baileyterminals`.
   - Build command: `npm run build`
   - Publish directory: `_site`
4. Once deployed, go to **Site settings → Forms** in Netlify and confirm
   the `capacity-request` form is detected (it will auto-detect from the
   `data-netlify="true"` attribute on the contact form after the first
   deploy).
5. In Namecheap, point `baileyterminals.com` at Netlify the same way you
   did for turnvia.com (ALIAS/A record for `@`, CNAME for `www`), then
   set the domain in Netlify's domain settings.

## Local build (optional — you don't need this for the GitHub/Netlify flow)

```
npm install
npm run build      # outputs to _site/
npm run serve       # local dev server
```

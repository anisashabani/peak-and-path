# Peak & Path

### Find your trail. Follow your path. Discover your next adventure.

A hiking and trail discovery platform built only for Kosovo: every route, every map tile and every search stays inside Kosovo's borders.

`HTML5` · `CSS3` · `JavaScript (ES6+)` · `jQuery` · `Bootstrap 5` · `Leaflet + OpenStreetMap` · `React` (separate module)

[Live demo](#) · [Kanban board](#) · [Pull requests](../../pulls) · [React version](#)

</div>

---

## About the project

**Peak and Path** is a modern, interactive platform for hikers. It helps people discover, explore and plan time outdoors, with a special focus on Kosovo's mountains and trails: Rugova, Bjeshkët e Nemuna, Sharri, Gjeravica, Mirusha, Germia and more.

On each trail page you'll find the difficulty, distance, estimated time, elevation gain, a location on the map and practical details for the day out. The site works on desktop, tablet and mobile, for first-time walkers as much as for experienced mountaineers.

> **Our mission:** to inspire people to explore nature, discover Kosovo's hidden gems, and make every outdoor adventure easier to plan and more memorable.

### Kosovo only, by design

Peak and Path does not try to cover the whole world the way global apps do. It goes deep on a single country.

- The trail data layer (`js/api.js`) accepts only trails whose coordinates fall inside Kosovo's bounding box. Anything outside is rejected at load time.
- The interactive map is locked to Kosovo: you can't pan or zoom out beyond the country (`maxBounds` + `minZoom`).
- Regions, filters and search all work over Kosovo's own mountain areas.

---

## Key features

| Feature | What it does |
|---|---|
| 🧭 **Explore trails** | Browse every trail with its description, difficulty, distance and estimated duration |
| 🗺️ **Interactive map** | See where each trail starts and finishes on a map limited to Kosovo |
| 🔎 **Search and filters** | Filter by region, difficulty and length, search by name, and sort the results |
| 📋 **Trail details** | Stats table, map, gear list and a photo gallery for each trail |
| 📅 **Adventure planner** | A "Plan a hike" form with date, group size and level, fully validated |
| 👤 **User profile** *(stretch goal)* | Save favourite trails in the browser |
| 📱 **Responsive design** | Works on desktop, tablet and mobile |
| ♿ **Accessible** | Semantic HTML, labelled forms, keyboard navigation, visible focus, AA contrast |

---

## Pages

| Page | File | Owner | Highlights |
|---|---|---|---|
| Home | `index.html` | A1 (Lead) | Animated hero, quick search, 3 featured trails, regions, newsletter with email validation |
| Trails | `trails.html` | A2 | Trail list built from an array, filters, text search, sorting, result count |
| Trail details | `trail.html?id=…` | A3 | Trail lookup with `find`, data table, map, gear list, jQuery gallery |
| About us | `about.html` | A4 | Mission, team in CSS Grid, statistics with `reduce`, animated counters, FAQ with `slideToggle` |
| Contact | `contact.html` | A5 | Contact form and "Plan a hike" form with regex validation, date checks, success and error messages |
| React: Trails | `react/` | A2 + team | The Trails page rebuilt with React and React-Bootstrap |

The course asks for 1 main page + 4 functional pages. These five pages cover that.

---

## Tech stack

| Layer | Tools |
|---|---|
| Structure | Semantic HTML5 (`header`, `nav`, `main`, `section`, `article`, `footer`) |
| Styling | CSS3 with custom properties, Flexbox, Grid, media queries, transitions, transforms, keyframes; Bootstrap 5 for utilities and form components |
| Behaviour | Vanilla JavaScript (ES6+): `map`, `filter`, `reduce`, `find`, `setTimeout`, dates and strings; jQuery for DOM effects (`fadeIn`, `slideToggle`, lightbox) |
| Map | Leaflet + OpenStreetMap tiles, locked to Kosovo |
| React module | React + Vite + React-Bootstrap, using props and state |
| Quality | W3C validator, Lighthouse, tested in Chrome and Firefox |
| Workflow | GitHub Issues, GitHub Projects (Kanban), pull requests reviewed by the Lead |

---

## Project structure

```
peak-and-path/
├── index.html            # Home
├── trails.html           # Trail list + filters
├── trail.html            # Trail details (?id=)
├── about.html            # About us
├── contact.html          # Contact + Plan a hike
├── css/
│   ├── style.css         # Design tokens (CSS variables), base, header, footer, buttons
│   └── pages/            # One stylesheet per page (home.css, trails.css, ...)
├── js/
│   ├── main.js           # Shared: mobile menu, keyboard nav, footer year
│   ├── api.js            # Kosovo-only trail data layer
│   ├── map.js            # Leaflet map locked to Kosovo
│   └── pages/            # One script per page (home.js, trails.js, ...)
├── data/
│   └── trails.js         # Trail data (array of objects)
├── assets/
│   └── img/              # Optimised photos (with credits)
├── react/                # React + React-Bootstrap version of the Trails page
└── docs/                 # Screenshots, presentation, test report
```

---

## Getting started

```bash
git clone https://github.com/<OWNER>/peak-and-path.git
cd peak-and-path
```

Open `index.html` with the **Live Server** extension in VS Code, or run:

```bash
npx serve .
```

React module:

```bash
cd react
npm install
npm run dev
```

---

## Team

| Role | Member | GitHub | Page | Shared task |
|---|---|---|---|---|
| A1, Project Lead | [NAME] | @[username] | Home | Repo, Kanban, PR reviews, header/footer, README |
| A2 | [NAME] | @[username] | Trails | `data/trails.js`, React setup |
| A3 | [NAME] | @[username] | Trail details | Difficulty badges, trail card |
| A4 | [NAME] | @[username] | About us | Accessibility audit |
| A5 | [NAME] | @[username] | Contact | Cross-browser testing, presentation slides |

**Mentors (read access):** Dhurate Hyseni, Dalina Vranovci, Fjolla Gashi

---

## How we work

We manage the project on the **GitHub Projects** Kanban board: `Todo → In Progress → In Review → Done`.

1. **No direct pushes to `main`.** Every change goes through a pull request that the Lead approves.
2. **One task = one Issue = one branch**, e.g. `feature/24-trails-filter`.
3. Every PR description includes `Closes #<issue>`, so the issue closes automatically on merge.
4. Move your card to **In Progress** when you start and to **In Review** when you open the PR. After the merge it moves to **Done** on its own.
5. The Lead reviews PRs within 24 hours.
6. Each member works only in their own page's files. Ask the Lead for changes to `style.css`, the header or the footer.
7. Make small commits with clear messages, e.g. `Add difficulty filter to trails page`.

---

## Course requirements and where we cover them

*Programimi në Ueb nga Ana e Klientit, University of Prishtina, FIEK, 2026*

| Requirement | Weight | Where it is covered |
|---|---|---|
| GitHub management: Lead, PRs with approval, Kanban, 3 mentors | 5% | This repo, the Projects board, PR history |
| HTML: semantic tags, headings, forms, tables, lists, SEO, accessibility, 1 + 4 pages | 20% | All 5 pages; tables in Trail details and About; forms in Home and Contact |
| CSS: Flexbox, Grid, responsive, pseudo-classes, transitions, transforms, keyframes | 20% | Every page has Grid or Flexbox and one animation |
| JavaScript: validation, DOM, `map`/`filter`/`reduce`, `setTimeout`, dates and strings, jQuery | 20% | Filters on Trails, `reduce` on Details and About, dates on Contact, jQuery on 4 pages |
| React + UI library, props and state | 20% | `react/`, the Trails page with React-Bootstrap |
| Presentation with every member | 15% | `docs/presentation` |
| Usability: responsive, hover/focus states, clear form messages, `alt` text, 2 browsers | Part of HTML/CSS/JS | Test report in `docs/` |

---

## Timeline (20 days, 25 Nov – 14 Dec 2026)

| Phase | Days | Dates |
|---|---|---|
| 1. Setup | 1–2 | 25–26 Nov |
| 2. HTML | 3–6 | 27–30 Nov |
| 3. CSS | 6–10 | 30 Nov – 4 Dec |
| 4. JavaScript + jQuery | 10–14 | 4–8 Dec |
| 5. React + UI library | 13–17 | 7–11 Dec |
| 6. Testing, docs, presentation | 17–20 | 11–14 Dec |

---

## Credits

- Map data © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
- Photos from [Unsplash](https://unsplash.com) and [Pexels](https://pexels.com), credited in `assets/img/CREDITS.md`
- Trail information is for planning only. Always check conditions and weather before you go.


A student project at the University of Prishtina, Faculty of Electrical and Computer Engineering, 2026.

</div>

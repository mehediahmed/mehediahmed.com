<portfolio_design>
This is mehediahmed.com, the personal portfolio of Mehedi Ahmed, a Unity engineer
(games, VR, AR). It replaces an old Squarespace site. It is a static site
(index.html, styles.css, images/). No framework, no build step.

Who it's for, in this order: hiring managers and recruiters, then contract clients,
then a record of past work. Design for a hiring manager on a phone who wants to know
what he builds, how senior he is, where the proof is, and how to reach him. Anything
that doesn't help them with one of those doesn't belong on the page.

Structure
- One page: intro, Work (a timeline, newest first), Skills, Contact. The intro ends
  in the Leave No Witnesses gallery, above Work, so a visitor sees the work before
  any paragraph about it. Its caption sits above the shots and names the game in
  .gallery-name, so nobody has to guess what they're looking at, and links down to
  what he built for it.
- Each timeline entry is an <article class="entry">: h3 name, .role, .when (years and
  the platforms that job shipped on), then .entry-body. A game or app inside an
  employer's entry is a .project with an h4.
- The 2017–2018 games sit in a .reel inside Work: three entries side by side, each
  topped by its video poster, and on phones a small poster beside the years and
  title. In a reel entry the .media is a direct child of the article, between .when
  and .entry-body, so the grid can place it.
- Heading order: h1 is his name, h2 for sections, h3 for entries, h4 for projects.
- Entry ids keep the old Squarespace slugs (pop-ar, the-hollows, operation-viewpoint,
  the-virtual-memory-palace), so the host can redirect /pop-ar to /#pop-ar. pop-ar
  sits on POP AR's poster rather than its text, so the link lands on the poster.
- 404.html is the page GitHub Pages shows for a missing path. It's served at any
  depth, so every URL in it starts at the root (/styles.css, /favicon.svg).

Identity
- The site's one idea is the timeline's left column: years set in condensed Archivo
  with the hardware beneath them, which reads as the history of the headsets he has
  shipped on. Keep it the only typographic flourish. Don't add a second one.
- Related to Liminal Games Studio's site, not a copy of it. It shares Archivo and the
  studio's neutral colors. It does not use facets.js, the day and night worlds, or the
  studio's wide and condensed display titles.
- Type: Archivo only. Normal width for all text; the condensed width is only for the
  years and platforms. No second font family, no monospace, no all-caps labels.
- Color: every color is a token in styles.css :root. If you need a new one, add it
  there and to both dark-mode blocks (the prefers-color-scheme block and
  :root[data-theme="dark"]). No raw hex values in components. Screenshots and video
  posters carry the color; the page around them stays quiet.
- The palette is "Electric", and the two themes are twins: near-black on near-white,
  near-white on near-black, both faintly blue. One accent, --accent, goes on the
  timeline's years, the solid button, focus rings, selection and link underlines.
  It's one blue at hue 229: #7b93ff in dark, #163ff3 in light (darker so it reads
  on the light page). Don't spread the accent to more elements or add a second one.
- The favicon (favicon.svg, favicon.ico, apple-touch-icon.png) is Archivo's M at
  weight 800 in --bg on a --fg square, swapped in dark mode. It and the theme-color
  tags can't read CSS variables, so they repeat the hex values; change them together.
- No cards, shadows, gradients, icon rows or decorative dividers. A rule between
  timeline entries is the only divider.

Media
- Only current work gets a full-column image.
- Screenshots go in a figure.gallery around a ul.gallery-shots. Thumbnails run six to
  a row (three on phones), so within the timeline they're the same size in every
  gallery. The intro's Leave No Witnesses row is wider, under its full-width lead.
  - A game in current work gets .gallery.gallery--lead: its first shot runs the full
    column above the row, so keep the count at six beyond the lead.
  - An older professional role may carry a plain .gallery of its employer's images:
    thumbnails only, never full column, with the source credited in the figcaption.
  - Crop every shot in one gallery to the same aspect ratio so the row lines up.
- The list's data-title heads the #viewer dialog. Each link points at the largest
  file and carries data-caption: for the games, the short names from the Liminal
  site's thumbnail strip. Files are named <slug>-<width>.webp. The viewer assumes the
  Liminal widths (640 960 1280 1920); otherwise list them in data-widths on the link,
  or on the list when every shot shares them.
- Making new images: WebP at quality 80, never upscaled. Write -640 plus whichever
  larger widths the source allows.
- The link-preview image (og:image) is images/share-1200.jpg: the Leave No Witnesses
  club floor cropped from c05_floor_guard-1920.webp to 1200×630. It's a JPEG because
  some link previews don't show WebP.
- Videos start as a poster image that links to YouTube. The script swaps in a
  youtube-nocookie player on click, so nothing loads from YouTube until a visitor asks.
- Every image has width, height and alt text that says what's in the frame. Use
  loading="lazy" below the fold. Keep files small (WebP where possible, a few
  hundred KB at most).
- Leave No Witnesses and Poly Blockade screenshots come from the Liminal repo
  (~/Documents/Liminal, images/lnw and images/pb). Reuse its sizes and alt text
  rather than making new ones.
- SimX and WIN Reality images (images/simx, images/win) come from the companies'
  sites, downloaded 2026-10-13: simxvr.com/platform/virtual-manikin/,
  simxvr.com/features/ and the ad on simxvr.com's home page; winreality.com/train-vr/.
  SimX's instructor view dates from March 2024, while he was there; the hospital
  bay render is from October 2025. WIN's shots are from 2025, after he left in 2022.
  Each caption only credits the source ("From simxvr.com.", "From winreality.com.");
  he asked for nothing else there.

Copy
- Plain, concrete, first person. Say what he built and what it did: "Guard
  perception: sight and sound checks for 100 NPCs inside a 1 ms frame budget," not
  "Architected a high-performance perception framework." Rewrite résumé phrasing
  ("spearheaded", "leveraged", "architected") as plain sentences.
- Sources of truth: his résumés (~/Documents/Mehedi_Ahmed_Resume_2026_v3, _XR and _TA,
  .docx and .pdf), the Liminal Games Studio site for anything about the games, and the
  old project pages (Devpost for The Virtual Memory Palace). Game descriptions must
  match the studio site. simxvr.com and winreality.com are the sources for the
  images of those apps only (see Media), never for claims about his work.
- Never invent metrics, dates, roles, employers, clients, platforms or links. Use only
  the numbers the résumé states. Mark anything unconfirmed as
  <mark class="todo">[what's needed]</mark>; the draft banner appears automatically.
- No superlatives beyond what the résumé itself claims.

Privacy
- Never publish his phone number or street address. Location is city level only
  ("New York").
- The email address is assembled by script from data-user and data-domain so it never
  appears whole in the raw HTML. Keep it that way, including in the JSON-LD Person
  block in the head.
- The site links to Mehedi_Ahmed_Resume.pdf, his public résumé (no phone number). When
  he updates it, replace that file under the same name, and check the new copy has no
  phone number or street address before it goes in. Titles and dates on the page
  should match it.

Links
- nickquest.com (the old sites for The Hollows and Operation Viewpoint) is now a
  gambling spam domain. Never link to it. popar.app no longer resolves.
- Check that an external link still works and still shows the right thing before
  adding it.

Motion
- CSS first. The only script is the email assembly, the copy button, the video
  facade and the screenshot viewer (the JSON-LD block is data, not script). Don't add
  scroll animations or entrance effects.
- Every transition has a prefers-reduced-motion path, and the page is complete with
  motion and script off (videos fall back to links to YouTube, screenshots to the
  full-size image).

Constraints
- Design for phones first. Keep the --gutter side margin (16px minimum) and no
  horizontal scroll at 320px.
- Text meets WCAG AA contrast in both themes.
- No libraries or CDN scripts. Google Fonts and the click-to-load YouTube player are
  the only third-party requests.
- Semantic HTML and visible focus states.
- index.html and 404.html load styles.css with a ?v=N query so browsers don't pair new
  HTML with a cached old file. When styles.css changes, bump N in both.

Checking your work
- Headless Chrome won't make a window narrower than about 500px, so screenshot phone
  widths by framing the page in 390px and 320px iframes inside a wider window. Check
  both themes (set data-theme on <html>), and check that scrollWidth doesn't exceed
  clientWidth.
</portfolio_design>

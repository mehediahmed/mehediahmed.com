<portfolio_design>
This is mehediahmed.com, the personal portfolio of Mehedi Ahmed, a Unity engineer
(games, VR, AR). It replaces an old Squarespace site. It is a static site
(index.html, styles.css, images/). No framework, no build step.

Who it's for, in this order: hiring managers and recruiters, then contract clients,
then a record of past work. Design for a hiring manager on a phone who wants to know
what he builds, how senior he is, where the proof is, and how to reach him. Anything
that doesn't help them with one of those doesn't belong on the page.

Structure
- One page: intro, Work (a timeline, newest first), Skills, Contact.
- Each timeline entry is an <article class="entry">: h3 name, .role, .when (years and
  the platforms that job shipped on), then .entry-body. A game or app inside an
  employer's entry is a .project with an h4.
- Heading order: h1 is his name, h2 for sections, h3 for entries, h4 for projects.
- Entry ids keep the old Squarespace slugs (pop-ar, the-hollows, operation-viewpoint,
  the-virtual-memory-palace), so the host can redirect /pop-ar to /#pop-ar.

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
- No cards, shadows, gradients, icon rows or decorative dividers. A rule between
  timeline entries is the only divider.

Media
- Current work gets full-column images; older work uses .media--small.
- A game with several screenshots gets a .gallery: the first shot runs the full
  column, the rest sit in a row beneath it (six to a row, three on phones, so keep
  the count at six beyond the lead). Each links to its -1920.webp; the script opens
  them all in the #viewer dialog. Captions are the short names from the Liminal
  site's thumbnail strip, in data-caption.
- Videos start as a poster image that links to YouTube. The script swaps in a
  youtube-nocookie player on click, so nothing loads from YouTube until a visitor asks.
- Every image has width, height and alt text that says what's in the frame. Use
  loading="lazy" below the fold. Keep files small (WebP where possible, a few
  hundred KB at most).
- Leave No Witnesses and Poly Blockade screenshots come from the Liminal repo
  (~/Documents/Liminal, images/lnw and images/pb). Reuse its sizes and alt text
  rather than making new ones.

Copy
- Plain, concrete, first person. Say what he built and what it did: "Guard
  perception: sight and sound checks for 100 NPCs inside a 1 ms frame budget," not
  "Architected a high-performance perception framework." Rewrite résumé phrasing
  ("spearheaded", "leveraged", "architected") as plain sentences.
- Sources of truth: his résumés (~/Documents/Mehedi_Ahmed_Resume_2026_v3, _XR and _TA,
  .docx and .pdf), the Liminal Games Studio site for anything about the games, and the
  old project pages (Devpost for The Virtual Memory Palace). Game descriptions must
  match the studio site.
- Never invent metrics, dates, roles, employers, clients, platforms or links. Use only
  the numbers the résumé states. Mark anything unconfirmed as
  <mark class="todo">[what's needed]</mark>; the draft banner appears automatically.
- No superlatives beyond what the résumé itself claims.

Privacy
- Never publish his phone number or street address. Location is city level only
  ("New York").
- The email address is assembled by script from data-user and data-domain so it never
  appears whole in the raw HTML. Keep it that way.
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
  facade and the screenshot viewer. Don't add scroll animations or entrance effects.
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
- index.html loads styles.css with a ?v=N query so browsers don't pair new HTML with a
  cached old file. When styles.css changes, bump N.

Checking your work
- Headless Chrome won't make a window narrower than about 500px, so screenshot phone
  widths by framing the page in 390px and 320px iframes inside a wider window. Check
  both themes (set data-theme on <html>), and check that scrollWidth doesn't exceed
  clientWidth.
</portfolio_design>

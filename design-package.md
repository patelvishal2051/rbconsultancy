# Design Package: R.B Foods & Management Consultancy

The single creative deliverable. Written before any generation. Every viewer-facing line below ships verbatim into `index.html`.

Tier 2, three chained segments, 19.54 seconds of finished footage over a 1100vh pinned hero.

---

## 1. The brand premise

One idea runs the whole page: **he is still there on day 45, and on day 105.**

Buyers in this niche are not afraid of bad advice. They are afraid of being abandoned. The research is blunt about it: consultants take full payment and the salesperson disappears, lakhs are charged for ten to fifteen days of real work, vendor commissions get buried in the quote, and nobody stays to run the place once the doors open. R.B answers all four with facts it already has: a 45-day plan cut into four dated phases, seven areas of work handled inside it, zero royalty and zero convenience fee, and two full months of Rahul's team running daily operations after the opening.

So the page is not a brochure of services. It is a calendar. The visitor scrolls down the days, watches an empty concrete shell become a full dining room, and arrives at day 45 with the doors open and Rahul still standing there. Every section either marks a day or proves he stays. If a section does neither, it is cut.

## 2. The palette

**Deviation, stated out loud.** The skill bans near-black with a warm amber accent as a default reach. This palette lands near that family on purpose, and it is earned rather than reached for, because the film itself contains two light temperatures and the whole story is the change between them: a cold daylight shaft through a raw concrete shell, then warm pendant lamps coming on. The canvas is cold concrete, not black and not brown. The cold daylight is a real second color with real jobs (every drawn line, every mono label, the top of the spine), not decoration. The accent is the lamp, and it appears only where the page is asking for something. The banned look's other half, the high-contrast display serif, is refused outright: the display face is an expanded industrial grotesque.

**Locked, sampled from the finished film.** Every value below was pulled out of `assets/hero.mp4` after the video gate, not guessed. The method: median-cut quantisation on frames at 1.5s, 4s, 8.5s and 17.5s for the field colours, then targeted sampling of the warmest saturated pixels for the lamp and the brightest cool pixels for the shaft.

The footage came back cooler and bluer than the pre-visualisation assumed. Hue in the concrete sits at 202 rather than the 190 first written here, so the whole cold half moved off teal and onto slate. The lamp needed almost no correction: the sampled glow was `#CF9045` against a guess of `#D08A3C`.

```css
:root{
  --canvas:#131B20;        /* wet concrete in cold shade, sampled hue 202 */
  --canvas-deep:#0C1215;   /* the pocket the hero sits in */
  --panel:#1C262C;         /* cards and raised surfaces, straight off the 8.5s frame */
  --line:#2B373E;          /* hairlines and dividers, sampled exactly */
  --daylight:#9DAAB0;      /* the cold shaft: drawn SVG, mono labels, day markers before they land */
  --accent:#CF9045;        /* the pendant lamp glow: the CTA and rare emphasis only */
  --accent-hover:#E8A355;  /* toward the lamp core, sampled at #F48D06 */
  --accent-muted:#6A4A26;  /* whisper level: borders, glows, dust */
  --text-primary:#EAE6DF;  /* warm bone white, pulled back from the #EAD4BA highlight */
  --text-secondary:#A2AFB4;
}
```

Measured against `--canvas`: primary text 14.0:1, secondary text 7.7:1, daylight 7.3:1, accent 6.4:1, accent-hover 8.1:1. Canvas on an accent button is 6.4:1. All clear of the floor.

## 3. The type trio

- **Display: Archivo**, variable, width axis pushed to 112 to 125, weights 600 and 700. An expanded industrial grotesque. It reads like signage stencilled on a kitchen line, and it is the deliberate refusal of the high-contrast serif that this palette would normally attract.
- **Body: Newsreader**, weights 400 and 500, with the 300 italic for pull quotes. A quiet serif for body copy flips the usual pairing and carries the hospitality warmth the grotesque will not.
- **Mono: Martian Mono**, weight 400 only, at 10 to 12px with wide tracking. Day markers, phase labels, the ticker, form labels, and the counters.

Never Inter, never Roboto, and the old site's Instrument Serif is deliberately left behind.

## 4. The band map

Hero is 1100vh, so the scroll range is 1000vh and each band of 0.13 progress is 130vh. Ramps compute to 0.02 either side, which is 20vh, leaving a 90vh fully settled plateau per beat. Starting points, validated by the flick test.

Bands 2 through 6 share one deliberate shape: a day range, then three short clauses. That repetition is the device, not an accident. It turns the scroll into a countdown. Band 7 breaks it, which is how the arrival lands.

Captions live in the left third. The action lane is the center and right of frame, where the descent and the lamps are.

**Where the arrival comes to rest.** The third segment decelerates but never fully stops on its own. Measured frame-to-frame motion peaks at 10.1 and falls to 6.0 by the end, so the camera is still drifting when the footage runs out. Two fixes were tried. Retiming the tail with an easing curve was rejected after the motion trace came back alternating between 0.01 and 6.9, which is duplicated frames rather than a slowing camera, and it reads as stutter. The fix that shipped puts the deceleration in the scroll mapping instead: band 7 maps scroll to video time through an ease-out, so the last stretch of scroll advances the film less and less and settles on the final frame. That is continuous in the time domain, costs nothing, leaves the encode clean of duplicate frames, and is the same curve a camera operator would ride. The footage itself is untouched.

| Band | Range | Footage moment | Copy (verbatim) | Entrance |
|---|---|---|---|---|
| 1 | 0.00 to 0.13 | Top of the descent, hard daylight shaft, bare concrete, dust | Kicker: `8 years of corporate and QSR expertise` / H1: `Complete Food Business Consulting` / Sub: `From concept to grand opening.` | Drift-down, words falling into place as the camera falls. Band one gets the one-time load ramp. |
| 2 | 0.15 to 0.28 | Still falling through the raw shell, conduit and bare walls sliding past | `Today it is four walls and a lease you are already paying rent on.` | Blur-to-sharp. The room is not in focus yet, and neither is the sentence. |
| 3 | 0.30 to 0.43 | Descent continues, first hint of warm light at the frame edge | `Days 1 to 10. Location found. Market read. Layout drawn and licences already moving.` | Grid snap-align, characters sliding into reading order like a plan being set out. |
| 4 | 0.45 to 0.58 | The lamps ignite one after another down the room | `Days 11 to 25. Civil work done. Interiors in. Equipment delivered and installed.` | Word-punch with overshoot, one word landing per lamp. |
| 5 | 0.60 to 0.73 | Brass and timber resolving out of the dark, full warm light | `Days 26 to 35. Vendors locked. Staff hired. Every SOP trained on the floor.` | Weave, characters arriving alternating from above and below, like a line being staffed. |
| 6 | 0.75 to 0.86 | The move slows, golden hour reaching the far wall | `Days 36 to 45. Compliance cleared. Campaign live. Dry runs finished.` | Approach-from-depth, the line growing into place as the camera settles. |
| 7 | 0.88 to 1.00 | At rest on the finished dining room, tables laid, nobody in it yet | H2: `Day 45. You open.` / Sub: `Then Rahul's team runs your floor with you for the next two months. Zero royalty, zero convenience fee, no hidden charges.` / CTA: `WhatsApp Rahul` | Word-by-word rise into a staged settle: headline words rise, subline fades at k 0.66, the CTA row at k 0.78. |

## 5. The static-hero copy block

For phones, portrait tablets, coarse-pointer portrait, landscape phones, and reduced motion. Composed over the ending frame, not the poster, so small screens see the finished room rather than the empty shell.

- Kicker: `8 years of corporate and QSR expertise`
- Headline: `Complete Food Business Consulting`
- Subline: `From concept to grand opening in 45 days. Then Rahul's team runs your floor with you for two months after that.`
- Primary CTA: `WhatsApp Rahul`
- Secondary: `See the 45 days`

## 6. The below-fold outline

Thirteen sections. No two neighbours share a layout skeleton. Everything funnels to one anchor: a WhatsApp message to +91 90818 39191.

### 6.1 Settle and ticker

Immediately under the hero, sharing its background so the arrival is not interrupted.

- Marquee, repeating, mono, wide tracking: `ZERO ROYALTY • ZERO CONVENIENCE FEE • NO HIDDEN CHARGES`
- Lede: `Helping Restaurants, Cafes, Cloud Kitchens and QSR Brands build highly profitable, structured, and scalable businesses with world-class standard operating procedures.`

Layout: full-bleed marquee band, then a single centered paragraph at 62ch. No cards.

### 6.2 The four beats

The old site's four-step sequence, kept word for word, rebuilt as four markers hanging off the spine.

- `01 Concept` / `Raw ideas take a measurable form.`
- `02 Kitchen` / `The stainless line is drawn for yield.`
- `03 SOP` / `World-class procedures lock the service.`
- `04 Grand Opening` / `A storefront ready to receive guests.`

Layout: a horizontal four-column rail on desktop, each beat hanging from a short drawn stem off a horizontal rule. Mobile stacks them on the vertical spine.

### 6.3 Meet Rahul Bajpai

- Kicker: `Founder`
- H2: `Meet Rahul Bajpai`
- Body: `Expert hospitality advisory bringing global fast food standard operating procedures, yield equations, and ergonomic layout designs to independent food entrepreneurs across India.`
- Counter: `8` with label `years`
- Credentials, four, each a name and a role line:
  - `Burger King` / `Global QSR expertise`
  - `Pizza Hut` / `Operations and quality`
  - `Taco Bell` / `SOPs and systems`
  - `Zepto Cafe` / `Q-commerce cafe launch`

No photo exists, so no face is generated. The portrait slot holds a generated still of an empty stainless pass under warm light, and the name is set enormous in the display face across it. Layout: asymmetric split, image left at 42 percent bleeding off the page edge, text right, credentials as a 2x2 of hairline-separated rows with no card borders.

### 6.4 The 45-day roadmap

The spine's home, and the section the PDF exists to provide.

- Kicker: `Zero to inauguration`
- H2: `45 days, cut into four phases`
- Lede: `Every phase has a date on it. You always know what week you are in and what is finished.`

Four phases, each a day range, a title, and its scope:

- `Days 1 to 10` / `Site selection and planning` / `Location discovery, market analysis, the start of legal documentation, and the interior layout finalised.`
- `Days 11 to 25` / `Civil work, interiors and equipment` / `Store structure built, interiors executed, equipment delivered and installed.`
- `Days 26 to 35` / `Vendors, hiring and training` / `Raw material supply chain set up, staff recruited, and every on-site and off-site training module completed.`
- `Days 36 to 45` / `Marketing, dry run and inauguration` / `Legal compliance closed, the two-month marketing campaign launched, operational dry runs, and the grand opening.`

Layout: the spine runs vertically through the middle of this section and the day markers light as each phase enters. Phases alternate left and right of the spine. One generated still, a drafting table with a kitchen layout drawn on it, anchors the section top right.

### 6.5 Five ways to start

The old site's five services, kept word for word, with the em dashes replaced by full stops.

- `01 / 05` `Restaurant Launch` / `From concept through opening day. Rooms, recipes, and the line.`
- `02 / 05` `Cloud Kitchen Blueprints` / `SOP-driven dark kitchens planned for aggregator margins.`
- `03 / 05` `Ergonomic Kitchen Design` / `Yield-led layouts that keep the pass moving.`
- `04 / 05` `Standard SOP Playbook` / `World-class operating procedures, written for the floor.`
- `05 / 05` `Franchise Structure` / `Repeatable brand systems without hidden charges.`

Layout: five large offset cards in a staggered vertical cascade, each one indented further than the last so the eye walks down a stair. Big mono index numerals bleeding off the left edge of each card.

### 6.6 Seven things handled inside every mandate

From the PDF. The scope-of-work column, rewritten into plain language with the banned words removed.

- `01` `Location finding and site selection` / `Technical and commercial help identifying, analysing and picking a high-footfall site that suits your money and your format.`
- `02` `Interior design and basic structure` / `Basic store infrastructure built, layout planned, 2D and 3D interior design, and an outlet that matches the brand it is meant to be.`
- `03` `Equipment and vendor management` / `Reliable vendor connections for kitchen and serving equipment, and a supply chain set up for raw materials.`
- `04` `Team hiring and training` / `Qualified staff recruited for the floor and the kitchen, then trained on SOPs, customer service and kitchen management.`
- `05` `Legal documentation and process` / `Every legal procedure, licence, government paper and process fee handled end to end.`
- `06` `Marketing strategy and platforms` / `A dedicated plan for the first two months, with digital and local platforms set up to bring footfall in.`
- `07` `Two months of operations management` / `After the inauguration, Rahul's team manages daily operations, decisions and the store itself for the first two months.`

Layout: deliberately unlike 6.5. A ledger. Seven hairline rows, mono index left, title in display at row height, scope in body text in the right column, each row drawing its own rule as it enters.

### 6.7 Industries

All six, verbatim, with the one em dash replaced.

- `Fine Dining` / `Plated hospitality with a kitchen rhythm that holds through service.`
- `Specialty Cafe` / `Rooms for conversation and craft. Consistent, warm, repeatable.`
- `QSR Chains` / `High-volume systems drawn from corporate QSR practice.`
- `Cloud Kitchen` / `Delivery-first kitchens built around SOP and aggregator margins.`
- `Food Courts` / `Compact footprints with disciplined throughput on the line.`
- `Hotel F&B` / `Hotel restaurant and banquet operations, brought to order.`

Layout: a 3x2 grid of tall panels, each carrying a darkened generated or reused still with the label set across the bottom. On hover the still lifts and the accent hairline draws along the bottom edge.

### 6.8 PUFF KING

- Kicker: `Premium QSR case study`
- H2: `PUFF KING Franchise Design`
- Body: `Rahul Bajpai conceptualised and designed this high-yield quick service restaurant model.`
- Tagline, set as a device: `Eat, Laugh, Enjoy`
- Stat 1: `₹12.5L` / `Ultra-low capex setup`
- Stat 2: `High-margin` / `Capital growth model`
- CTA (secondary, not the page's primary): `Explore the investor deck` linking to the WhatsApp anchor with a deck-specific message.

Layout: full-bleed dark panel, the only place on the page that goes edge to edge with an image behind type. Stats sit in a single row along the bottom on a chip scrim.

### 6.9 The Concept and Culture Canvas

The one interactive moment. All copy from the old site, kept.

- Kicker: `Interactive co-creation`
- H2: `The Concept and Culture Canvas`
- Lede: `We reject cold, generic templates. Tell us about the soul, operational culture, and unique nature of your food brand. We will weave it directly into custom SOP playbooks.`

Step 1, label `01 · Select your business nature`:
- `Specialty Cafe / Bistro` / `Aesthetic spaces for conversation and craft brews`
- `High-Speed QSR` / `Fast service, neat packaging, high-volume consistency`
- `Casual Family Dine` / `Cozy spaces with diverse recipes and warm hospitality`
- `Delivery Cloud Kitchen` / `SOP-driven dark kitchens optimised for aggregator margins`

Step 2, label `02 · Define the brand vibe`:
- `Cozy & Community-Centric` / `Feels like a neighbourhood living room; high repeat loyalty`
- `Premium & Artisanal` / `Highly photogenic, slow-dripped luxury, customised details`
- `Energetic & Fast-Paced` / `Vibrant playlists, neon cues, zero idle delay`
- `Heritage & Soulful` / `Tells a traditional story; rooted in local organic ingredients`

Step 3, label `03 · Operational and customer culture`:
- `People First` / `Warm, conversational hospitality where staff remembers guest names`
- `Flawless Precision` / `Clockwork speed, spotless steel tables, strict portion controls`
- `Experimental / Trendy` / `Ever-changing secret menus, quirky artwork, digital-first presence`

Free text, optional, placeholder: `Tell us about your brand's story and spirit`

The portrait card, right hand side, updating live:
- Card kicker: `Brand vibe portrait`
- Card title: `Handmade by R.B Consultancy`
- Card body: `We optimise seating layouts and custom warm lighting to organically guide customers to feel completely at home.`
- Three readout rows: `Aesthetic blueprint`, `Atmospheric vibe`, `Operational culture`, each showing the live selection.

**The hold.** Under the card: `Ready to build this concept? Press and hold to commission the blueprint.` The visitor presses and holds; a brass arc fills around the button while held, eases back down if released early, and on completion the three readout rows light in sequence and the dispatch button appears: `Dispatch vibe to advisory line`, which opens WhatsApp with the three choices and the free text already written into the message. Reduced motion skips the hold and shows the completed state with the button live.

### 6.10 Proof

- Quote, verbatim: `Rahul's deep expertise in operational workflows completely restructured our kitchen line. We reduced our table ticket times from 22 minutes down to just 12 minutes, which increased our weekend customer capacity by 45%. His SOP development is absolutely world-class.`
- Attribution: `Amit Patel` / `Co-Founder`
- Counter 1: `12` with prefix label `Ticket time, minutes, down from 22`
- Counter 2: `45%` with label `More weekend capacity`

Layout: the quote set large in the body serif italic, left aligned against the spine, counters as two mono readouts beneath. No card, no quotation-mark graphic beyond a single drawn brass stroke.

### 6.11 The questions people actually ask

Written from the research, in the words buyers use.

- `How do I know you will not take the money and disappear?`
  `That is the fair question, and it is why the work is dated. The 45 days are cut into four phases you can check off, and the two months after your opening are Rahul's team running your floor. He is still on site long after the money has moved.`

- `Consultants charge lakhs for two weeks of work. What am I actually paying for?`
  `Seven areas of work over 45 days, then 60 days of operations management. Zero royalty, zero convenience fee, no hidden charges, and no commission taken out of any vendor in the network.`

- `Can you promise my outlet will make money?`
  `No. Anyone who promises that is selling you something. What is promised is the structure: a yield-led layout, a costed menu, trained staff, licences in hand, and a marketing plan already running on opening day.`

- `I have never run a kitchen. Can I still do this?`
  `Yes. That is exactly who the two-month operations handover is for. Rahul's team runs daily operations and decisions while you learn your own floor, instead of learning it on customers.`

- `Do you only work in Gujarat?`
  `The corporate office is in Surat. Mandates run pan-India.`

Layout: a two-column editorial list, question in display at small size, answer in body serif, hairline between. Open by default, no accordion, because hiding the answer to a trust question is the wrong instinct.

### 6.12 Book consultation

- Kicker: `Advisory line`
- H2: `Book Consultation`
- Lede: `One message gets you Rahul, not a sales desk.`
- Primary button, large: `WhatsApp +91 90818 39191`
- Form, secondary, fields: `Name`, `Phone`, `City`, `Business type` (select: `Specialty Cafe / Bistro`, `High-Speed QSR`, `Casual Family Dine`, `Delivery Cloud Kitchen`)
- Form button: `Send to advisory line`
- Form handling: the submit builds the message and opens WhatsApp with it prefilled, and the form itself shows a success state inline: `Opening WhatsApp with your details. If it does not open, call +91 90818 39191.`
- Contact block: `+91 90818 39191` / `Surat, Gujarat, India` / `09:00 AM to 08:00 PM IST`

### 6.13 Footer

- `R.B Foods & Management Consultancy. Pan-India Advisory Mandates.`
- `© 2026 R.B Foods & Management Consultancy. All Rights Reserved.`
- `Corporate Office: Surat, Gujarat, India. Pan-India Advisory Mandates.`
- `Website concept by Sutrava Software Solutions.`
- Disclosure line: `The hero film and section imagery on this page are generated. R.B Foods & Management Consultancy, Rahul Bajpai, and the work described are real.`

### Navigation

Fixed header, hairline bottom border, backdrop blur. Brand mark left. Links: `About`, `45 Days`, `Services`, `Industries`, `PUFF KING`, `Canvas`, `Contact`. One accent button right: `WhatsApp Rahul`.

## 7. The vector layer plan

**The signature: the spine.** One vertical line running from the settle to the footer, drawn by scroll with `stroke-dasharray`. Its gradient runs from `--daylight` at the top to `--accent` at the bottom, so the line warms as the visitor descends, exactly as the room does. Five day markers sit on it at the four beats and the four roadmap phases: `01`, `10`, `25`, `35`, `45`, each a small mono numeral on a short cross-stroke that switches from `--daylight` to `--accent` as it passes the viewport middle. Remove this line and the page becomes a normal stack of sections, which is the test.

Supporting vector work:

- Section rules that draw themselves outward from the spine on entry.
- The four beats in 6.2 hang from short drawn stems.
- The ledger rows in 6.6 each draw their own hairline left to right.
- The proof section's single brass stroke beside the quote.
- The hold button's brass arc in 6.9, an SVG circle driven by `stroke-dashoffset`.
- Whisper-level dust: a handful of slow-drifting motes in the hero surround and the Rahul section, echoing the daylight shaft. Opacity under 0.12, cycles of 40 seconds or longer, negative delays, paused off-screen and on hidden tabs.
- One fixed background environment layer: a very soft radial glow that drifts on a 90-second cycle so scrolling feels like moving through one room.

Reduced motion pins every one of these to its final drawn state and stops the drives.

## 8. The engineering list

The full standard from `references/scrub-pipeline.md`, named so the build cannot half-remember it:

- Streamed Blob fetch with the SVG loading ring, poster painted first, 20-second re-arming watchdog, hardcoded byte fallback, honest scroll chevron on failure.
- dt-normalised lerp in a rAF loop that rests when converged and when the hero is off-screen via IntersectionObserver.
- Gated seeks with newest-target coalescing and the error-handler deadlock escape.
- Delta-gated DOM writes everywhere, `--k` at 0.008, text throttled to 10Hz and only on change.
- Band pacing in vh with smoothstep ramps, first band no ease-in, last band no ease-out, validated by the flick test at 120, 240 and 360px.
- The four-layer legibility system: global radial scrim, per-band scrim riding `--k` with peak alpha tuned per band, the three-layer text-shadow token off on buttons, chip scrims for small text. Worst-frame audit at 3.5:1 minimum.
- All five static-hero gates, character-for-character identical in CSS and JS, armed and disarmed from live `change` listeners.
- Complete without the video: poster background carries every caption and section.
- `overflow-x: clip` on html and body with `hidden` first.
- Reduced motion honoured completely and live in both directions.
- Whole-site-animated standard: entrance per moment, staggers retired after entry with matching specificity, one living element per section, transform and opacity only.
- Quality floor: trimmed fonts with preconnect, `ch` sizing on text elements only, real contrast, semantic landmarks, skip link, decorative video hidden from assistive tech and the tab order, `:focus-visible` in the accent, 44px touch targets under coarse pointer, real title and meta, inline SVG favicon, `<!-- DEPLOY STEP -->` marker on the og tags.

## 9. The copy gate

Every viewer-facing line in this document ships verbatim. The built page must pass the grep gate before anyone sees it: zero em dashes, zero instances of leverage, seamless, empower, unlock, robust, actionable, data-driven or solutions as ordinary words. The one permitted match is the proper noun `Sutrava Software Solutions` in the footer credit. The PDF's own phrasing contained two banned words, and both have already been rewritten above: its "seamless, efficient and successful venture" and its "Robust Vendor Ecosystem". The old site's em dashes in the five services and the Specialty Cafe industry line have been replaced with full stops.

Deliberate brand devices stay: the repeated day-range triplet across bands 3 to 6, and the staccato three-clause rhythm in the roadmap phases.

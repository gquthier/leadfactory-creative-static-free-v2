# Native & High-CTR Ad Format Library

> **Why this matters**: On Meta 2026, native formats (screenshots, conversations, UGC) consistently outperform polished editorial creatives on cold traffic — because they don't look like ads. The most common mistake is delivering 10 creatives that all look the same.
>
> Use this library to build a **diverse mix**: 2–3 native (iMessage/Note/tweet/post), 1–2 UGC/portrait, 1–2 listicle/advertorial, 1 product/mockup, 1 testimonial, 1–2 data-viz/infographic, 1 pattern-interrupt. Never 12 variations of the same style.

**Rendering engine**: GPT Image 2 (`gpt_image_2`, quality `high`, 2k) — best for text, UI, screenshots.
**Ratios**: `3:4` (feed portrait, use instead of 4:5 — GPT Image 2 doesn't support 4:5) · `9:16` (Reels/Story) · `1:1` (square/carousel) · `16:9` (wide)

**Placeholders** — replace in every prompt:
- `{BRAND}` — brand name
- `{PRODUCT}` — precise product description (material, color, silhouette, price)
- `{PRICE}` — price
- `{ICP}` — ideal customer profile (e.g. "women 25–35", "e-commerce founders")
- `{HOOK}` — the opening line / headline
- `{LINE}` — a supporting line
- `{CTA}` — call-to-action in ALL CAPS (e.g. `SHOP NOW`, `GET A QUOTE`)
- `{ACCENT_HEX}` — brand accent color for CTA pill (e.g. `#BE7A52`)
- `{LANG}` — language (e.g. `US English`, `French`)

> **Text quality suffix** — append to every prompt:
> `"ALL embedded text in flawless {LANG}, perfectly legible, correct spelling, no gibberish, no stray letters."`

---

## Format 1 — iOS Note (confession / list)

**When to use**: Personal confession, "what nobody tells you about X", mistake lists, tips.
**Why it works**: Looks like an organic screenshot shared between friends — zero ad feel → high thumb-stop + trust.

```
A realistic iOS NOTES APP screenshot, authentic and low-fi, white note background
with the iOS Notes top bar and toolbar icons.
A typed personal note titled "{HOOK}" followed by a short bullet list:
"- {LINE}",
"- {LINE}",
"- {LINE}",
"- {LINE}".
Looks like a personal screenshot shared organically, NOT an ad.
Fills the full frame, no border.
ALL embedded text in flawless {LANG}, perfectly legible, correct spelling.
```

**Ratio**: 3:4 or 9:16. **Branding**: none (or brand name mentioned casually in the text).

**Live example** (OFFWOVEN e-com, bone linen set, $58):
> Title: "what no one tells you about linen sets"
> Bullets: "- real cotton-linen gets SOFTER every wash (cheap blends just pill)", "- oversized + wide-leg fits every body, zero sizing stress", "- one set = coffee, work, dinner. you stop overthinking outfits", "- $58 for the OFFWOVEN one. mine has paid for itself"

---

## Format 2 — iMessage Conversation (peer recommendation)

**When to use**: Social proof, friend-to-friend recommendation, objection → answer.
**Why it works**: Feels like reading a real conversation — implicit recommendation, ultra-native.

```
A realistic iMessage conversation screenshot on an iPhone, authentic native look,
iOS status bar, white background, grey and blue message bubbles.
Two {ICP} texting.
Grey bubble: "{HOOK}"
Blue bubble: "{LINE}"
Grey bubble: "{LINE}"
Optional: one small attached photo thumbnail of {PRODUCT}.
Casual, real, scroll-stopping — looks like a genuine shared screenshot, NOT an ad.
Fills the full frame.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 9:16. **Branding**: none (brand name in a bubble at most).

**Live example** (OFFWOVEN):
> Grey: "ok where is that linen set from?? you've worn it like 5 times 😅"
> Blue: "OFFWOVEN. the $58 one off TikTok — gets softer every wash, I live in it"
> Grey: "sending me the link rn"

---

## Format 3 — Tweet / X Review (viral statement)

**When to use**: Contrarian opinion, surprising claim, social proof with reach metrics.
**Why it works**: Instant read, pattern-interrupt, viral social proof signals (likes, views).

```
A realistic X (Twitter) post screenshot card on a clean off-white background.
A tweet from a credible {ICP} account: round avatar, display name, @handle.
Tweet text: "{HOOK}"
Small reply, repost and like counts (e.g. 1.2K likes, 219 reposts).
Native social pattern-interrupt — looks like a real viral tweet, not an ad.
Fills the full frame.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 1:1 or 3:4. **Branding**: none.

**Live example** (OFFWOVEN):
> @maradoesthings: "the offwoven linen set is the only thing i've worn in three weeks. it gets softer every wash and it was $58. send help."

---

## Format 4 — TikTok Shop Review Screenshot (channel proof)

**When to use**: E-com with TikTok presence. Especially powerful if the product has real TikTok traction.
**Why it works**: "As seen on TikTok Shop" tag = channel authority. Review = social proof. Zero editorial feel.

```
A realistic TikTok Shop product review screenshot, native mobile UI.
Product header row: small thumbnail of {PRODUCT}, name "{BRAND} {PRODUCT_NAME}", price "{PRICE}".
Below: a five-star review (★★★★★) from a verified buyer with a checkmark,
review text: "{HOOK}",
a buyer-uploaded photo of someone wearing/using {PRODUCT} in natural light,
and a small "As seen on TikTok Shop" badge.
Looks like a genuine app screenshot, not an ad.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4. **Branding**: product name in the header.

**Live example** (OFFWOVEN):
> Jenna R. ✓ Verified buyer: "Showed up all over my FYP and it lives up to it. Genuinely softer after every wash and the oversized fit is perfect. I LIVE in it."

---

## Format 5 — Listicle "N reasons" (quantified curiosity)

**When to use**: "3 reasons / 3 mistakes / 5 things". Works for all categories.
**Why it works**: Quantified curiosity drives clicks. Scannable. Entry point to longer content.

```
A native-looking listicle ad on a soft off-white or cream background.
Bold serif headline: "{HOOK}" (e.g. "3 reasons women live in this set").
Three numbered rows, each with a small {ACCENT_HEX} check icon:
"1. {LINE}",
"2. {LINE}",
"3. {LINE}".
Optional product photo on the right side.
Small "{BRAND}" wordmark and a {ACCENT_HEX} "{CTA}" pill at the bottom.
CTA placed directly below the headline in the same vertical column.
Editorial, scannable, curiosity-driven.
Edge-to-edge, no white margins.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 9:16. **Branding**: light.

---

## Format 6 — Stat / Data-Viz (price objection answer)

**When to use**: When price is the main objection. One big number that reframes value.
**Why it works**: A single striking statistic stops the scroll and answers "is it worth it?" instantly.

```
A clean bold data-viz ad on a cream or off-white background.
A very large {ACCENT_HEX} statistic "{HOOK}" (e.g. "$0.29") with a smaller label (e.g. "per wear").
Beside it, a simple elegant donut or bar chart.
Serif subhead in dark ink: "{LINE}" (e.g. "$58 over 200 wears. The set that earns its place.")
A small flat-lay or product thumbnail.
Small "{BRAND}" wordmark and a {ACCENT_HEX} "{CTA}" pill.
Premium, value-framed, no white margins.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 1:1 or 3:4. **Branding**: light.

**⚠️ Compliance note**: use market/context stats or cost-per-use calculations — never guaranteed income claims.

**Live example** (OFFWOVEN):
> "$0.29 per wear. $58 over 200 wears. The linen set that earns its place."

---

## Format 7 — Flat-lay / Knolling (product-first, image-only feel)

**When to use**: Product e-com. "One set, one click" simplicity angle.
**Why it works**: Premium overhead shot with minimal copy — pure product desire with a clear value prop.

```
A premium overhead flat-lay (knolling) product photograph on a warm cream or linen surface,
soft natural daylight from the side.
{PRODUCT} neatly laid out with a few minimal warm-toned accessories
(e.g. woven tote, flat sandals, gold hoop earrings, dried foliage).
Crinkled natural texture visible on the product.
A clean serif caption in a corner: "{HOOK}" (e.g. "One set. One click. Under $60.").
Small "{BRAND}" wordmark and a {ACCENT_HEX} "{CTA}" pill.
Editorial e-commerce flat-lay, no white margins.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 1:1 or 3:4. **Branding**: wordmark + CTA overlay.

---

## Format 8 — Native FB/IG Suggested Post (organic boosted post look)

**When to use**: Cold broad audiences. Especially effective when paired with a strong text hook.
**Why it works**: Looks like a recommended post, not an ad. Credibility of a real creator.

```
A realistic Facebook feed post screenshot (native, not a polished ad):
a round profile photo, name "{AUTHOR}" and a small "Suggested for you · Sponsored" tag.
A text post: "{HOOK} 👇".
Below, a link-preview card with a photo of {PRODUCT},
title "{PRODUCT_NAME} — {BRAND}",
subtitle "{BRAND_URL} · {PRICE}",
and a "Shop now" or "Learn more" button.
Looks organic and credible, not like a polished brand ad.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 1:1. **Branding**: in the link preview.

---

## Format 9 — UGC Selfie / Talking-Head Static (authenticity)

**When to use**: Testimonial, "I tried it", accessible authority.
**Why it works**: Human face = trust. Most resilient format on Meta 2026. Defuses fear on sensitive topics.

```
An authentic UGC-style selfie photo (slightly imperfect phone-camera look, NOT polished studio):
a credible {ICP}, natural setting (home / desk / café), natural window light.
A bold caption bar overlay near the top (white text on a semi-transparent dark strip): "{HOOK}".
A burned-in subtitle bar near the bottom: "{LINE}".
Optional small {ACCENT_HEX} CTA pill: "{CTA}".
Looks like a real creator ad, not a brand shoot.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 (feed) or 9:16 (Reels). **Branding**: CTA pill only.

---

## Format 10 — Testimonial Card (social proof)

**When to use**: Overcome trust objection. High-ticket, new brand.
**Why it works**: Testimonial = social proof signal #1. ⚠️ Focus on experience, never on financial results.

```
A clean premium testimonial card on an off-white background with subtle {ACCENT_HEX} accents.
A client quote in elegant serif: "{HOOK}".
Below: a small round avatar, "{NAME} · {ICP}", and five {ACCENT_HEX} stars.
Small "{BRAND}" logo in a corner.
Trust-focused, no money figures, no "I made X" claims.
Edge-to-edge, no white margins.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 1:1.

---

## Format 11 — Educational Infographic "1 frame" (authority)

**When to use**: Explaining a mechanism, B2B, finance, high-ticket services.
**Why it works**: Installs expertise, zero promise → fully compliant. Best format for regulated niches.

```
A clean minimal educational infographic on a light background.
Title: "{HOOK}".
A simple 3-step horizontal or vertical diagram with thin {ACCENT_HEX} connectors and small line icons,
each step a short label: "{LINE}" → "{LINE}" → "{LINE}".
Subtle {ACCENT_HEX} accents, small "{BRAND}" logo.
Authority/education angle, no promises.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 1:1.

---

## Format 12 — Advertorial / Article Screenshot (editorial, warms cold)

**When to use**: High-ticket cold, subject that needs education first.
**Why it works**: Editorial credibility. Most compliant format. Converts cold traffic by educating first.

```
A realistic screenshot of an online news/magazine article page — clean white background,
real editorial layout: serif headline, byline "By [Name] · [Section]",
a small article hero photo, two short body paragraphs,
and a highlighted call-out box.
Headline: "{HOOK}".
Sub: "{LINE}".
Looks like a native article, not an ad.
Optional small "{BRAND}" mention in the call-out box.
Fills the full frame.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 3:4 or 9:16.

---

## Format 13 — POV (Reels/Story vertical, 2nd-person immersion)

**When to use**: Awareness moment, "POV: you realize that…"
**Why it works**: 2nd person puts the viewer inside the scene. Native to Reels algorithm.

```
A vertical 9:16 UGC Story/Reels still, authentic phone-camera look:
a {ICP} POV in a real setting, natural light, candid.
Top caption (white text on a subtle dark strip): "POV: {HOOK}".
A burned-in subtitle lower third: "{LINE}".
A {ACCENT_HEX} CTA pill at the bottom: "{CTA}".
Native Reels feel, not polished.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 9:16 only.

---

## Format 14 — Pattern-Interrupt Text Shock (full-bleed typography)

**When to use**: Bold/contrarian statement. Anti-fast-fashion, category attack, market reframe.
**Why it works**: Read in < 1 second. Maximum thumb-stop. Cheap to produce in volume.

```
A bold full-bleed typographic statement on a solid background ({ACCENT_HEX} or dark neutral).
Huge {LANG} sentence in a strong serif or sans font: "{HOOK}",
with one key phrase highlighted in a contrasting color.
Minimal, high-contrast, lots of negative space.
Optional tiny "{BRAND}" logo in a corner.
Edge-to-edge, no white margins.
ALL embedded text in flawless {LANG}.
```

**Ratio**: 1:1 or 3:4.

**Live example** (OFFWOVEN carousel B, slide 1):
> "Your $40 'linen' set is 70% polyester."

---

## Carousel Formats

Carousels are rarely used in most product categories — which makes them a **white space opportunity**.

### Carousel A — Versatility / Styling ("1 set, N ways")
Best for fashion, lifestyle, any product with multiple use cases.

| Slide | Content |
|-------|---------|
| Cover (1/N) | Hero lifestyle photo + bold headline "One {PRODUCT}. {N} ways to style it." + swipe arrow |
| Look 01 (2/N) | Same product, Use Case A styling + label chip "01 · {TIME} — {OCCASION}" |
| Look 02 (3/N) | Same product, Use Case B styling + label chip "02 · {TIME} — {OCCASION}" |
| CTA slide | Closing offer + "{CTA}" pill + brand wordmark |

### Carousel B — Problem → Proof → Offer (persuasion sequence)
Best for overcoming a specific objection (price, quality, category skepticism).

| Slide | Content |
|-------|---------|
| Problem (1/3) | Bold pattern-interrupt: "{PROBLEM STATEMENT}" — contrarian, confident |
| Proof (2/3) | Evidence: product quality macro + review count + stars |
| Offer (3/3) | Product photo + price + CTA pill |

**Live example** (OFFWOVEN):
> 1/3: "Your $40 'linen' set is 70% polyester."
> 2/3: "This is 100% washed cotton-linen. Softer every wash. Rated ★★★★★ by 2,100+ women."
> 3/3: "One set. One click. $58 (was $78)." + SHOP THE SET

---

## Diversity Rule

A strong pack mixes:
- **2–3 native** (iMessage / iOS Note / Tweet / Native Post)
- **1–2 UGC** (Selfie / POV / Testimonial card)
- **1–2 value/objection** (Data-viz / Listicle / Flat-lay)
- **1 carousel** (Versatility or Problem→Proof→Offer)
- **1 pattern-interrupt** (text shock or advertorial)

Never deliver 10 creatives that all look the same. Iterate on winners (4–6 variants of the top performers) only after the first test.

## Technical Best Practices

- **3:4 for Meta feed portrait** (GPT Image 2 doesn't support 4:5 — 3:4 is visually identical)
- **Two crops minimum**: 3:4 (feed) + 9:16 (Reels/Story)
- **Hook in the first frame** (before "see more"), one idea per creative
- **Burn-in text** (85% watch without sound) — make it large enough to read at thumbnail size
- **Target hook rate**: 25–30%. Kill anything below 15% after $25 spend.
- **GPT Image 2**: best for text rendering, UI screenshots, native formats. Audit every PNG (text artifacts, distorted hands, hallucinated logos).

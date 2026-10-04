# Creative Pre-Flight Check: Rule Library Research

Sourcing key: **[OFFICIAL]** = fetched directly from the platform/regulator's own page this session. **[PRACTITIONER]** = industry consensus, primary page was JS-gated, 404, or paywalled. **[DISPUTED]** = commonly repeated but poorly sourced. A "Gaps" section at the end lists everything that could not be verified, so nothing below is padded with invented numbers.

Research constraint worth knowing: the session's WebSearch quota was exhausted early, so all of this came from direct WebFetch against known URLs. Meta Business Help Center, Amazon Ads help, TikTok help, Snap, Reddit, Pinterest and Walmart Connect are all JS-rendered single-page apps that return empty shells to a plain fetch. Meta's pages were partially recovered via the m.facebook.com mirror. The rest are flagged.

---

# PART 1: CHANNEL SPECS

## 1.1 Meta (Facebook / Instagram)

### Placement dimensions [OFFICIAL, facebook.com/business/ads-guide]

| Placement | Ratio | Recommended | Minimum | Tolerance | Source |
|---|---|---|---|---|---|
| FB Feed image | 4:5 | 1440x1800 | 600x750 | 3% | [image](https://www.facebook.com/business/ads-guide/update/image) |
| FB Feed video | 4:5 | 1440x1800 | 120x120 | 3% | [video](https://www.facebook.com/business/ads-guide/update/video) |
| IG Reels image | 9:16 | 1440x2560 | 500px wide | 1% | [ig-reels](https://www.facebook.com/business/ads-guide/update/image/instagram-reels) |
| IG Reels video | 9:16 | 1440x2560 | 250px wide (<30s) / 500px (>=30s) | 1% | [ig-reels-video](https://www.facebook.com/business/ads-guide/update/video/instagram-reels) |
| FB Stories image | 9:16 | 1440x2560 | 500px wide | 1% | [fb-story](https://www.facebook.com/business/ads-guide/update/image/facebook-story) |
| FB Stories video | 9:16 | 1440x2560 | 250px wide | 1% | [fb-story-video](https://www.facebook.com/business/ads-guide/update/video/facebook-story) |
| IG Stories image | 9:16 | 1440x2560 | 500px wide | 1% | [ig-story](https://www.facebook.com/business/ads-guide/update/image/instagram-story) |
| FB Right Column | 1:1 | 1080x1080+ | 254x133 | n/a | [right-column](https://www.facebook.com/business/ads-guide/update/image/facebook-right-hand-column) |
| FB Marketplace video | 1:1 | 1080x1080 | 120x120 | n/a | [marketplace](https://www.facebook.com/business/ads-guide/update/video/facebook-marketplace) |
| Audience Network image | 9:16 | n/a | 398x208 | n/a | [AN](https://www.facebook.com/business/ads-guide/update/image/audience-network-native/outcome-awareness) |
| FB In-Stream video | 16:9 or 1:1 | 1080x1080 | n/a | n/a | [in-stream](https://www.facebook.com/business/ads-guide/update/video/facebook-instream-video) |
| Messenger Stories video | 9:16 | 1080x1920 | 500px wide | 1% | [messenger](https://www.facebook.com/business/ads-guide/update/video/messenger-story/app-installs/mobile-app) |

Right Column explicitly states text-on-image is **not recommended** because of the small render size. Encode as a rule: right-column creative fails if it carries overlaid copy.

### Safe zones for Stories/Reels [OFFICIAL, with a live inconsistency worth encoding]

Meta's own pages disagree, which matters for a pre-flight tool:
- **FB Stories video page** still states **top 14% (250px) / bottom 20% (340px)**.
- **FB Stories image, IG Stories (image and video), IG Reels (image and video)** all state the newer unified **top 14% / bottom 35% / sides 6%**.
- **Messenger Stories**: roughly 14% (250px) top and bottom.

Recommended encoding: treat **14% top / 35% bottom / 6% sides** as the current standard (the wider bottom reserve clears the CTA button plus like/comment/share icons and captions), and surface the 20% figure as a legacy note. On a 1080x1920 canvas that is 269px top, 672px bottom, 65px each side.

### The 20% text-in-image rule [PRACTITIONER for history, no live official restatement found]

- Historically Meta capped image ads at 20% text coverage, enforced via a Text Overlay Tool grading images OK / Low / Medium / High.
- **September 2020**: Meta removed auction and delivery penalties for text-heavy images and retired the Text Overlay Tool.
- **Current status**: no hard percentage gate. Text density is now a soft input to estimated action rate / ad quality in the auction rather than an eligibility check. Meta still recommends minimal text.
- For a pre-flight product: this should be a **warning, not a blocker**, with the 20% grid still useful as a heuristic. No live Meta page restating this could be retrieved, so do not present it as a citable official rule.

### Character limits [OFFICIAL, per-placement ads-guide pages]

| Placement | Primary text | Headline | Description |
|---|---|---|---|
| FB Feed | 50-150 recommended | 27 | n/a |
| FB In-Stream | 125 max | 40 max | n/a |
| FB/IG Stories | 125 max | 40 max | n/a |
| IG Reels | 44 | n/a | n/a |
| Messenger Stories | 125 max | 40 max | n/a |
| FB Right Column | n/a | 40 | n/a |
| FB Marketplace | n/a | 25 | n/a |
| Audience Network | 125 | 40 | 30 |
| Carousel (per card) | 80 | 20 | 18 |

Feed truncation behind "See more" happens at roughly 125 characters but is **line-based, not character-based**: it varies by device width, font-size accessibility setting, language, emoji and manual line breaks. A pre-flight check should render-and-measure rather than count characters. [PRACTITIONER]

Marketing API field ceilings (partial fetch, treat as directional): `name` 100 chars, `link` URL 1,000 chars. [PRACTITIONER]

### File, format and duration limits [OFFICIAL, consistent across all spec pages]

- Image: **30MB max**, JPG or PNG.
- Video: **4GB max**, MP4 / MOV / GIF.
- Recommended encode: H.264, square pixels, fixed frame rate, progressive scan, stereo AAC at 128kbps+.
- Durations: FB Feed and Marketplace **1s to 241 min**; IG Reels **0s to 15 min**; FB Stories **1s to 3 min**; IG Stories **1s to 60 min** (videos over roughly 16s split across Story cards); Messenger Stories **1s to 60s**; FB In-Stream desktop **5-15s**, mobile **5s to 10 min** with anything over 15s truncated to a 15s ad plus a resume card.
- FB Stories images display for 8 seconds or until swipe; IG Stories images 5-16 seconds.

### Carousel [OFFICIAL, [carousel spec](https://www.facebook.com/business/ads-guide/update/carousel)]
2 to 10 cards; per-card image 1:1, min 1080x1080, 30MB, 3% tolerance; per-card video 1:1, 4GB, 1s to 240 min; each card requires its own landing URL.

### Captions and sound [OFFICIAL]
Every Meta video spec page carries "Video Captions: Optional, but recommended" and "Video Sound: Optional, but recommended" (Reels pages say sound is strongly recommended). Encode captions as a strong recommendation, not a hard gate.

---

## 1.2 Google Ads

### Performance Max [OFFICIAL]
Sources: [PMax specs](https://support.google.com/google-ads/answer/17091269), [image asset specs](https://support.google.com/google-ads/answer/14530211), [asset groups](https://support.google.com/google-ads/answer/10724492)

**Text**: Headlines min 3 / max 15 at **30 chars**, at least one headline **<=15 chars**. Long headlines 1-5 at **90 chars**. Descriptions 2-5 at **90 chars**. Business name required, **25 chars**, must match the domain or verified business name. CTA 1 required. Display URL path 1-2 at **15 chars** each.

**Images** (JPG/PNG, **5120KB / 5MB max**):

| Ratio | Recommended | Minimum | Count |
|---|---|---|---|
| 1.91:1 horizontal | 1200x628 | 600x314 | 4-20, required |
| 1:1 square | 1200x1200 | 300x300 | 4-20, required |
| 4:5 vertical | 960x1200 | 480x600 | 2-20, optional |
| 1:1 logo | 1200x1200 | 128x128 | 1-5, required |
| 4:1 logo | 1200x300 | 512x128 | 1-5, optional |

**Critical encodable rule [OFFICIAL]**: "Content needs to be in the **center 80% of the image**." This is Google's safe-area equivalent and is the single most checkable Google image rule. Google also recommends at least one image per aspect ratio with **no overlaid text or graphic elements**.

**Video**: 1-15 per orientation (16:9, 1:1, 9:16), **minimum 10 seconds**. Optional, but required for Excellent Ad Strength.

**Asset groups**: max 100 per campaign, min 1, not shareable across campaigns. Google's own best-practice floor: 20+ text assets, 7+ images (3 landscape, 3 square, 1 portrait), 1+ video.

### Demand Gen [OFFICIAL, [creative asset specs](https://support.google.com/google-ads/answer/13704860)]
Headlines 1-5 at **40 chars** (at least one <=30). Descriptions 1-5 at **90 chars**. Business name **25 chars**. Final URL **2,048 chars**. Images: 1.91:1 (1200x628 rec / 600x314 min), 1:1 (1200x1200 / 300x300), 4:5 (960x1200 / 480x600), 9:16 (1080x1920 / 600x1067 for Shorts). Logo 1:1 recommended 1200x1200, min 144x144 (**note: Google's own pages state 128x128 elsewhere, an inconsistency to handle**). Up to 5 videos; the asset-spec page says 10-60 seconds while another Demand Gen doc says min 5 seconds, with sub-10s ineligible for YouTube in-stream.

Key delta from PMax: headline max is 40 not 30, there is no 90-char long headline slot, minimums are lower (1 image / 1 headline), CTA is automated-only, and carousel plus product-feed formats exist.

### Responsive Display Ads [OFFICIAL, [best practices](https://support.google.com/google-ads/answer/9823397)]
Headlines up to 5 at 30 chars; 1 long headline at 90; descriptions up to 5 at 90; business name 25. Up to 15 marketing images at 1.91:1, 1:1, optional 9:16. Up to 5 logos (1:1 and 4:1). JPG/PNG, 5MB.

**On the "20% text" question for Google**: Google does **not** publish a numeric text-overlay cap for RDAs. Its current wording is to avoid overlaying text on images because it duplicates the headline and becomes unreadable at small sizes; naturally embedded text (a sign in a photo) is fine. Any "Google 20% rule" in circulation is borrowed from legacy Facebook guidance. Encode as a qualitative warning.

### Uploaded display ads [OFFICIAL, [specs](https://support.google.com/google-ads/answer/1722096)]
- **150KB max** per image ad. HTML5/AMPHTML: **600KB compressed ZIP**.
- Formats: GIF, JPG, PNG, HTML5, AMPHTML.
- **GIF animation max 30 seconds total, frame rate must be slower than 5 FPS.**
- Supported sizes: 200x200, 240x400, 250x250, 250x360, 300x250, 336x280, 580x400, 120x600, 160x600, 300x600, 300x1050, 468x60, 728x90, 930x180, 970x90, 970x250, 980x120, 300x50, 320x50, 320x100. Regional: Poland 750x100/750x200/750x300, Sweden 980x120 and 250x360, Denmark 930x180, Norway 580x400.

### Ad Strength [OFFICIAL tiers, PRACTITIONER on correlation]
Google's definition: Ad Strength "estimates the relevance, quantity, and diversity of your ad content." [overview](https://support.google.com/google-ads/answer/9142254)

PMax tiers: Incomplete, Poor, Average, Good, Excellent. Excellent requires 6+ sitelinks, self-uploaded video in all 3 orientations, all 15 headline slots, all 5 description slots. [PMax Ad Strength](https://support.google.com/google-ads/answer/14143250)

RSA levers Google names: keyword relevance (a keyword must fit entirely within one headline; long keywords belong in the 90-char description), asset quantity (up to 15 headlines / 4 descriptions), uniqueness (no repeated assets), and minimal pinning (recommend max 1-2 pins). [RSA Ad Strength](https://support.google.com/google-ads/answer/9921843)

**Important counter-evidence [PRACTITIONER]**: Optmyzr's analysis of roughly 20,000 accounts and 1M+ ads found higher Ad Strength had a **lower conversion rate 54.2% of the time**, with "Excellent" underperforming "Good" on CTR, CVR and Quality Score. [Optmyzr RSA study](https://www.optmyzr.com/blog/google-rsa-performance-study/). Google publishes no correlation data. A pre-flight product should treat Ad Strength as a compliance/completeness signal, not a performance predictor, and should say so.

### YouTube [OFFICIAL, [video ad specs](https://support.google.com/google-ads/answer/13547298), [companion banners](https://support.google.com/google-ads/answer/6293542)]
Skippable in-stream: no fixed max, skip appears after 5 seconds. Non-skippable in-stream: **15 seconds** general ceiling (some markets to 20s). Bumper: **6 seconds**. Companion banner: **300x60**, JPEG/GIF/PNG, **150KB max**, animated GIF under 5 FPS, desktop only.

---

## 1.3 Amazon Ads

### Sponsored Brands [OFFICIAL, [ecommerce specs](https://advertising.amazon.com/resources/ad-specs/ecommerce), [SB video](https://advertising.amazon.com/resources/ad-specs/sponsored-brands-video), [component-based creative](https://advertising.amazon.com/resources/ad-specs/component-based-creative)]

- **Headline: 50 chars max.** Must start with a capital letter, no repeated punctuation, no pricing claims, no exclamation points or forceful phrasing.
- **Brand logo: minimum 400x400, 1:1 required.** Must use Amazon's PSD templates with safe zones; content outside the safe zone is cropped. Separate ecommerce-display logo spec: min 600x100, max 1,000KB, JPG/GIF/PNG.
- Custom images, three responsive ratios: 1:1 (rec 1200x1200, min 600x600), 9:16 (rec 1000x1000 or 900x1600 depending on page, min 338x600), 1.91:1 (rec 1200x628, min 600x314). **Max 5MB.**
- **No more than 2 logos in a custom image. Total words in a custom image must be <=10 (40 characters in JP).**
- **Disclaimer: 60 chars max (28 JP), sentence case.**
- Component limits: Brand Store creative allows 1 headline / 1 body / 1 CTA / 3 images; Asset-Based creative allows 15 / 5 (100 chars, 50 JP) / 5 / 15. Brand name 25 chars (15 JP) in both.

**SB Video**: **6-45 seconds** (<=20s strongly recommended), 1280x720 / 1920x1080 / 3840x2160, **16:9 only**, **500MB max**, MP4 or MOV, H.264 or H.265, frame rates 23.976 through 30 progressive, **min bitrate 1 Mbps** (4+ recommended), audio PCM/AAC/MP3, min 96kbps, min 44.1kHz. **No customer reviews or star ratings in video creative, even Amazon's own.** Avoid black or blurred bars and avoid content in the lower-right corner (the mute button overlays it).

### Sponsored Display [OFFICIAL]
Governed by the same ecommerce creative spec: 50-char headline, logo min 600x100 / max 1,000KB, custom images at 1200x1200 / 900x1600 / 1200x628, min 600x600, 5MB, <=2 logos, <=10 words, 60-char disclaimer.

### Amazon DSP [OFFICIAL, [desktop specs](https://advertising.amazon.com/resources/ad-specs/dsp/desktop), [streaming TV](https://advertising.amazon.com/resources/ad-specs/dsp/video/streaming-tv-prime-video-ads)]

| Placement | Display size | Creative dims | Max file | Format |
|---|---|---|---|---|
| Medium Rectangle | 300x250 | 300x250 | 200KB HTML / 40KB static | JPG, PNG-8 |
| Leaderboard | 728x90 | 728x90 | 200KB / 40KB | JPG, PNG-8 |
| Wide Skyscraper | 160x600 | 160x600 | 200KB / 40KB | JPG, PNG-8 |
| Large Rectangle | 300x600 | 300x600 | 200KB / 50KB | JPG, PNG-8 |
| Billboard | 970x250 | 1940x500 @2x | 200KB | JPG, PNG-8 |

Static max drops to 50KB in FR/IT/ES/JP. Mobile requires 2x assets: Mobile Leaderboard 320x50 (640x100 @2x, 50KB); Mobile Detail/Search 414x125 (828x250 @2x, 100KB); Mobile Medium Rectangle 300x250 (600x500 @2x, 40KB); Tablet Leaderboard 728x90 (1456x180 @2x, 200KB).

**Streaming TV / Prime Video**: durations US/CA 15/30/45/60s; UK/DE/FR/IT/ES/BR/IN 10/15/20/30/40/60s; Japan 15/30s; third-party STV apps 6/10/15/20/30/45/60/75/90s. Min frame 1920x1080, 16:9, **500MB max**, Prime Video **min bitrate 15 Mbps** (50 recommended), Twitch/Fire TV/3P **min 8 Mbps**, frame rate 23.976 recommended / 24 / 25 / 29.97 constant, H.264 / MPEG-2 / MPEG-4, audio min 192kbps, 44.1 or 48kHz, min 2 channels, AAC.

### Amazon creative acceptance policy: the rules that actually get creative rejected
[OFFICIAL, [SB/SD moderation guide](https://advertising.amazon.com/library/guides/sponsored-brands-display-ads-moderation), [policy quick reference](https://advertising.amazon.com/resources/ad-policy/quick-reference), [claims substantiation](https://advertising.amazon.com/help/G4TYRJ5MN9NZKBBW)]

This is the densest, most rule-shaped policy set of any platform and should be the backbone of a retail-media pre-flight module:

1. **Superlatives**: "Superiority claims (the best, the most, the biggest, the tastiest, better than, etc.) will be rejected unless they can be substantiated." Includes "#1," "top-rated," "fastest," "cheapest."
2. **Pricing and savings**: "Superlatives like 'Huge savings' or 'Gigantic discounts' are not permitted. Neither are mentions of specific pricing, like 'Save 50%' or '$20 off.'" Permitted alternatives: "Great prices on [Product]," "Savings on [Product]," "Save now." Generic non-numeric savings language is allowed **only** in static ads pointing to a multi-ASIN landing page or Brand Store. Claims must match the landing page.
3. **"#1 Best Seller" and rankings**: treated as unsupported claims requiring documented evidence.
4. **Star ratings and reviews**: third-party reviews, star ratings, or anything confusable with Amazon Customer Reviews are barred from Store creative; reviews and ratings are barred from SB Video and Amazon Video Ads **even when sourced from Amazon**. Narrow exception for Fire Tablet wake-screen and Custom Landing Page ads with approval.
5. **Competitor references**: "Ads on Amazon cannot explicitly call out your competitors by name. You may include references to a 'leading brand' or other generic phrasing." Comparative claims that are made must cite an independent source dated **within the prior 12 to 18 months**, e.g. "America's best hat, Hat Makers magazine, 2017."
6. **Prohibited imagery**: excessive violence (blood, guns), skulls/skeletons/ghosts in traumatic context, full nudity or sexuality, suggestive undressing, any sexualization of minors including minors in swimwear or undergarments, unsafe product use by children without visible adult supervision, aftermath of physical trauma.
7. **Text in images**: custom images may not carry added text beyond what is naturally part of the product (on-package text is fine). Branding, CTA and headline text must live in the dedicated fields.
8. **Image quality**: must be "crisp, clean... not overly cluttered," no "overly bright or distracting colors," must contrast against white background or carry a 1px non-white border. Blurry, distorted, pixelated, smudged or stretched images are rejected.
9. **CTAs**: must be clear and action-oriented, sentence case. "Click here" is prohibited as non-specific. Pressure language ("Act now," "Last chance," "Don't miss out") is prohibited. Acceptable: "Shop now," "Learn more," "See more," "Get details." Billboard CTAs cannot be button-shaped.
10. **Time sensitivity and availability**: "Ads must not promote the sale of products that are out of stock or under recall, or services that are unavailable for purchase at the time that the campaign runs."
11. **Trademark**: "A brand logo must be your brand's registered logo. You have to have the legal right to use the logo of the brand you're promoting."
12. **Animation**: onsite placement animation cannot exceed **15 seconds**.

### Brand Store [OFFICIAL where cited, PRACTITIONER on module dimensions]
Images: 1:1 (rec 1200x1200, min 600x600), 9:16 (rec 1000x1000, min 338x600), 1.91:1 (rec 1200x628, min 600x314). Up to 3 images for Brand Store creative vs 15 for Asset-Based. Logo 1:1, min 400x400, PSD safe-zone templates required. Background video: min 1280x640, max height 1500px, **2-20 seconds**, autoplay looped, **no sound**. Video cover images: min 3000x1500 (3000x1688 at 300ppi recommended). [PRACTITIONER] Module images: 970x300 banners, 373x300 side-by-side, 225x225 grid; Feature 1 = 4 images at 220x220, Feature 2 = 3 at 300x300, Feature 3 = 4 at 135x135. Same creative acceptance policy applies.

---

## 1.4 Walmart Connect [PRACTITIONER, official pages are JS-gated]

- **Sponsored Brands**: headline **45 chars**; brand name capped at **35 chars** in one source. Square creative 1:1, 72 DPI, PNG/JPG, **max 1MB**, RGB. Logo PNG **<=200KB**; sources conflict between "300x180" and "min 450x450 transparent PNG, <=1MB," which suggests two different logo slots (banner vs square brand logo). Verify in Creative Builder before production.
- **Onsite Display**: built in Walmart's Creative Builder inside the Creative Platform. Exact pixel dimensions are not published in plain text; Walmart runs a "Walmart Creative Essentials Ad Certification" course partly because of this.
- **Off-site DSP display**: 300x250 static, **up to 200KB**, JPG/PNG/GIF/HTML5; also 728x90, 160x600, 300x600, 970x250, 320x50.
- **Vizio / OneView CTV**: up to 30s, 1920x1080 16:9, MP4/MOV, **500MB max**, H.264, 29.97fps (min 24fps), AAC.
- Brand hero banner: 1200x628 (1.91:1).
- **Policy gap**: no distinct Walmart Connect prohibited-claims document could be retrieved. [advertisinghelp.walmart.com](https://advertisinghelp.walmart.com/s/guides) returns a CSS error to automated fetch. The "Art of the Cart Display Ad Creative Guide" surfaced only creative-strategy content, not hard claims rules. **This is the single biggest spec gap in the research.**

---

## 1.5 TikTok

### Video specs [OFFICIAL, [in-feed ad specs](https://ads.tiktok.com/help/article/video-ads-specifications)]
- Vertical 9:16 recommended, **>=540x960**; horizontal 16:9 **>=960x540**; square 1:1 **>=640x640**.
- Formats: .mp4, .mov, .mpeg, .3gp, .avi.
- Duration: up to **10 minutes**, no stated minimum.
- File size: **<=500MB**. Bitrate: **>=516 kbps**.
- Ad caption: no clickable links, @ symbols or hashtags; fixed white font; **max 4 lines displayed**.
- **Caption truncation: <=50 characters for CN/JP/KR, <=100 characters for other languages.**
- **Account name / nickname: 1 line, 10 chars max for CJK, 20 chars max otherwise.**
- Profile photo: 98x98 (1:1), JPG/JPEG/PNG, **under 50KB**, key content within the inner **66x66** to survive circular crop.

### Safe zones: an important negative finding [OFFICIAL]
TikTok's own help article **does not publish numeric safe zone values**. It states the safe zone depends on dimensions, caption length and format, and provides only downloadable template ZIPs (In-Feed Standard LTR, In-Feed with Anchor, and Arabic/RTL variants). The widely circulated figures (roughly **top 130-150px, bottom 250-300px, right column 140px** on a 1080x1920 canvas) are [PRACTITIONER] derivations from those template files. A pre-flight product that claims pixel-exact TikTok safe zones should either ingest the actual template files or present its numbers as approximate. Note that the RTL template is a **separate file**, meaning the safe zone geometry differs for Arabic creative.

**Spark Ads** [OFFICIAL, [Spark Ads](https://ads.tiktok.com/help/article/spark-ads)]: no restrictions on ratio, resolution, file type, duration, bitrate or file size (it pulls the organic post). Caption is inherited from the organic video, max 4 lines including emoji, not editable.

---

## 1.6 LinkedIn, Pinterest, Snap, Reddit

### LinkedIn [OFFICIAL]
[Single image](https://business.linkedin.com/advertise/ads/sponsored-content/single-image-ads-specs): JPG/PNG/GIF, **5MB max**. 1.91:1 (min 640x360, max 7680x4320, rec 1200x628), 1:1 (min 360x360, max 4320x4320, rec 1200x1200), 1:1.91 vertical mobile-only (min 360x640, max 2430x4320, rec 628x1200). **Headline 70 chars guaranteed-display / 200 max. Intro text 150 guaranteed / 600 max.** Landing URL up to 2,000 chars.

[Video](https://business.linkedin.com/advertise/ads/sponsored-content/video-ads/specs): MP4, **75KB min to 500MB max**, **3 seconds to 30 minutes**, AAC/MPEG4 audio under 64kHz, 30fps recommended, **5% aspect ratio tolerance**. Ratios: 4:5 (360x450 to 1080x1350), 9:16 (360x640 to 1080x1920), 16:9 (640x360 to 1920x1080), 1:1 (360x360 to 1920x1920). Custom thumbnail JPG/PNG max 2MB.

[Carousel](https://business.linkedin.com/advertise/ads/sponsored-content/carousel-ads/specs): **1:1 only**, min 1080x1080, JPG/PNG **10MB per card**, **2-10 cards**, no video. **Card headline 45 chars. Intro text 255 chars.**

Document ads: [PRACTITIONER, unverified] PDF/PPT/DOC/DOCX/PPTX up to 100MB, up to 300 pages.

### Pinterest [OFFICIAL, [product specs](https://help.pinterest.com/en/business/article/pinterest-product-specs)]
Standard Pin **2:3 (1000x1500)**, max file **20MB desktop / 32MB in-app**, PNG or JPEG. **Title up to 100 chars** (first ~40 most reliably shown). **Description up to 500-800 chars** (Pinterest's own pages give both figures). Video: **4 seconds to 15 minutes** (6-15s recommended), MP4/MOV/M4V, H.264/H.265, **up to 2GB**, 1:1 or 2:3 / 4:5 / 9:16. Carousel: 2-5 images (up to 10 for Sales objective), 1:1 or 2:3, 20MB per image. Idea Pins: title 100 chars, on-page text 250 chars, video max 5 minutes, 1080x1920. Collections: hero 1:1 or 2:3 max 10MB, min 3 secondary creatives, hero video 4-15s up to 2GB.

### Snapchat [OFFICIAL, [ad formats](https://forbusiness.snapchat.com/advertising/ad-formats)]
9:16. **Snap's formats page states 720x1280 as the documented floor**; 1080x1920 is the commonly recommended upload target. .mp4/.mov (H.264 for Commercials), .jpg/.png. Durations: Single Image/Video and Story Ads **3-180 seconds**; Sponsored Snaps up to 180s (under 10s recommended); **Commercials 3-180s with a mandatory non-skippable first 6 seconds**; Collection video 3-180s. **Brand name up to 25 chars with spaces. Headline up to 34 chars with spaces** (25-28 for full display without truncation). AR Lenses: static PNG 945x2048; animated GIF 720x1560, 1-3 seconds.

Safe zones: not published with pixel values on the fetched page. The commonly cited **top ~7% / bottom ~11%** margins are [PRACTITIONER] and low confidence. Verify in Snap Ads Manager creative preview.

### Reddit [OFFICIAL-sourced but not re-verified against live HTML; the help portal is a Salesforce SPA]
Headline: Conversations placement **300 chars desktop / 100 chars mobile**; general title cap 300 chars. Card image **1200x1200**, JPG/PNG, **20MB max**. Thumbnail **400x300 (4:3)**, JPG, **500KB max**. **Caption text under the card image: 45 chars max.** GIF **3MB max, 3-10 seconds**. Video: .mov and .mp4; numeric resolution/duration/bitrate ceilings could not be captured. Confirm at [Reddit ad unit specs](https://advertising.reddithelp.com/en/categories/creating-ads/ad-unit-specifications).

---

## 1.7 CTV / OTT [mixed; Amazon's figures are OFFICIAL, the rest are PRACTITIONER]

Amazon's Streaming TV specs above are the one fully verified CTV spec set. General norms:
- Min resolution **1920x1080 (16:9)**; 4K masters increasingly requested.
- Standard durations **15s and 30s**, plus 6s bumpers.
- File size caps commonly **500MB to 2GB** depending on platform.
- **Audio loudness**: the CALM Act requires compliance with **ATSC A/85**, adopted as mandatory 4 Nov 2009, which is built on **ITU-R BS.1770** measurement. The practical industry target is **-24 LKFS +/- 2dB**. The statute itself expresses a relative-loudness principle rather than the numeric target. [CALM Act](https://en.wikipedia.org/wiki/CALM_Act); fcc.gov pages returned 403 to automated fetch.
- **Title-safe area 90% of frame (5% margin per side); action-safe 80% (10% margin)**. Standard broadcast convention.
- Text legibility for 10-foot viewing: roughly **28-30px equivalent minimum**, large high-contrast sans-serif, avoid thin weights. [PRACTITIONER]
- QR codes on CTV: commonly **15-20% of frame height** and **5-10 seconds minimum dwell**, often held through the last 5+ seconds of a :30. [PRACTITIONER, no codified IAB number found]

## 1.8 DOOH [PRACTITIONER; OAAA and DPAA sub-pages were not extractable]
- **"7 words or fewer"** is the classic OAAA roadside bulletin/poster copy guideline.
- Legibility rule of thumb: roughly **1 inch of letter height per 10 feet of reading distance** (some versions cite per 3ft), scaled by traffic speed.
- Typical dwell: roadside/highway **3-8 seconds**; transit/street-level **5-15 seconds**; place-based (elevators, waiting rooms, gyms) **30 seconds to several minutes**.
- Slot durations: roadside digital commonly **6-10 seconds** in an 8-slot loop (roughly 80s); indoor place-based commonly **10-15 seconds**.
- Motion: many DOT and municipal policies restrict full-motion video or fast animation on roadside digital boards, requiring static or slow-transition content with minimum hold times. Varies by jurisdiction, no single national standard.
- Contrast: high-contrast dark-on-light or light-on-dark for sunlight legibility.

## 1.9 IAB, web banners and email

**IAB** [PRACTITIONER; iab.com/guidelines/new-ad-portfolio and the PDF are account-gated, iabtechlab.com lists the specs only as PDF downloads]
- LEAN = **L**ightweight, **E**ncrypted, **A**dChoices supported, **N**on-invasive. [IAB Tech Lab](https://iabtechlab.com/standards/iab-new-ad-portfolio/) confirms LEAN and the consumer principles of Respect / Control / Choice [OFFICIAL], but not the numbers.
- New Ad Portfolio, first introduced **2017**, last updated **25 Feb 2025**, consolidates fixed sizes into flexible size categories (Portrait, Full Page Flex, Filmstrip Flex, Mobile Phone Flex, Leaderboard/Billboard Flex, Skyscraper Flex, Rectangle) alongside the fixed set: 300x250, 728x90, 160x600, 300x600, 970x250, 320x50, 300x50, 320x100.
- Initial ad load commonly cited at **150KB** with a polite/subload allowance after render. Animation commonly capped at **15 seconds and/or 3 loops**. Audio must not autoplay; initiate on user interaction. All of these should be re-verified against the gated PDF before shipping as hard rules.

**Email** [Mailchimp OFFICIAL, rest PRACTITIONER]
- **Max width 600px** is the standard recommendation ([Mailchimp](https://mailchimp.com/help/about-html-email/)); 600-640px is the practical range.
- Table-based HTML with **inline CSS** required, because Gmail, Yahoo and Outlook.com strip `<head>` and embedded stylesheets.
- Absolute image URLs on reliable hosts. **Alt text is mandatory in practice** because images are blocked by default in Outlook and other clients.
- Image-to-text ratio matters for deliverability; roughly 60/40 text-to-image is the conventional target.
- Dark mode: transparent-background logos, test against forced inversion in Apple Mail, Outlook and Gmail dark themes.
- CAN-SPAM required elements: accurate header/from info, non-deceptive subject line, identification as an advertisement where applicable, **valid physical postal address**, functioning opt-out honored **within 10 business days**, and responsibility for third-party senders.

---

# PART 2: WHAT ACTUALLY GETS REJECTED

## 2.1 Google Ads Safety Report 2024 [OFFICIAL, full figures extracted from the report PDF]

Source: [2024 Ads Safety Report PDF](https://services.google.com/fh/files/misc/ads_safety_report_2024.pdf)

**Headline numbers for 2024:**
- **5.1 billion ads removed**
- **9.1 billion ads restricted**
- **39.2 million advertiser accounts suspended**, "the vast majority of which were suspended before they ever served an ad"
- **1.3 billion publisher pages** actioned, plus site-level enforcement on **over 220,000 publisher sites**
- **Over 30 updates** to Ads and Publisher policies in the year
- Advertiser identity verification now covers **more than 200 countries and territories**, with **over 90% of ads** seen on Google coming from verified advertisers
- AI models contributed to detection and enforcement of **97%** of publisher pages actioned
- Over **50 enhancements** deployed to Google's LLM enforcement models

**Ads blocked or removed, by policy (2024):**

| Policy | Ads blocked or removed |
|---|---|
| Abusing the ad network | 793.1M |
| Trademark | 503.1M |
| Personalized ads | 491.3M |
| Legal requirements | 280.3M |
| Financial services | 193.7M |
| Misrepresentation | 146.9M |
| Gambling and games | 146M |
| Adult content | 122.5M |
| Healthcare and medicines | 104.8M |
| Copyright | 71.4M |
| Inappropriate content | 42M |
| Alcohol | 10.9M |
| Enabling dishonest behavior | 8.8M |
| Dangerous products or services | 7.2M |
| Counterfeit goods | 890k |

**Restricted ads, by policy (2024):** Legal requirements 428.8M, Financial services 268.3M, Copyright 115.1M, Gambling and games 108.9M, Healthcare and medicines 106.6M, Adult content 96M, Alcohol 34.2M.

**Publisher pages actioned (2024):** Sexual content 1.2B, Dangerous or derogatory 24.8M, Malicious or unwanted software 19.3M, Shocking content 13.6M, Weapons promotion 12.8M, Online gambling 8.8M, Tobacco 5M, Alcohol sale or misuse 3.6M, IP abuse 2.7M, Sexually explicit 1.1M.

**Scam and impersonation specifics (2024):** **415 million ads blocked or removed** and **over 5 million accounts suspended** under scam-associated policies. A dedicated team of **100+ experts** addressed AI-generated public-figure impersonation, leading to **over 700,000 advertiser accounts permanently suspended** and a **90% drop in reports** of that scam type. Elections: **8,900+ new election advertisers verified**, **10.7 million election ads removed** from unverified accounts.

**Product implication**: the highest-volume enforcement categories are not creative-design problems. Abusing the ad network, trademark, and personalized ads together account for 1.79B of 5.1B. A creative pre-flight tool cannot address those. The categories it *can* address, in order of volume, are **Misrepresentation (146.9M)**, **Healthcare and medicines (104.8M)**, **Financial services (193.7M blocked + 268.3M restricted)** and **Alcohol (10.9M + 34.2M)**. Position the product against those four, not against the headline 5.1B.

## 2.2 Meta enforcement data [OFFICIAL but thin on ads]

[Meta Transparency Center](https://transparency.meta.com/reports/community-standards-enforcement/) publishes precision, prevalence, proactive rate, content actioned, and appealed/restored content. As of H1 2026, **global enforcement precision averaged around 91% on Facebook and around 92% on Instagram**.

**Meta does not publish ad-specific rejection statistics.** The Community Standards Enforcement Report covers organic content, not paid. Notably, the ~91-92% precision figure implies an **8-9% error rate**, which is the most defensible number available for "ads get wrongly rejected." No published ad disapproval rate, appeal overturn rate or first-submission rejection rate exists for Meta from any credible source found.

## 2.3 Meta Advertising Standards structure [OFFICIAL, [ad standards](https://transparency.meta.com/policies/ad-standards/)]

Nine top-level categories: Community Standards; Unacceptable Content; Prohibited Commercial Practices; Restricted Goods and Services; Objectionable Content; Intellectual Property Infringement; Social Issue / Electoral / Political Advertising; Product- and Format-Specific Policies; Business Assets Policies.

**Personal attributes** [OFFICIAL]: ads "must not contain content that asserts or implies personal attributes," including race, ethnicity, religion, age, sexual orientation, gender identity, disability, health conditions, financial status, voting status, union membership, or criminal record. The encodable heuristic is second-person copy that asserts an attribute: "Meet other Christian singles" is compliant framing; "Are you a Christian and single?" is not. Copy detection should flag second-person constructions combined with a protected-attribute term.

**Landing page** [OFFICIAL]: "The products and services promoted in an ad must match those promoted on the landing page."

**Health and wellness** [OFFICIAL, [health and wellness policy](https://transparency.meta.com/en-gb/policies/ad-standards/restricted-goods-services/health-wellness/)]:
- Before-and-after imagery **is permitted** for cosmetic products and procedures when targeting 18+. This contradicts the widely repeated belief that before/after is banned outright. The real rule is narrower.
- **Prohibited**: "Close up on specific body area by pinching fat" for weight loss or gain products.
- Prohibited: "statements of inferiority about physical appearance" and content that attacks "an individual's appearance, specific body parts or hygiene."
- Weight loss products: 18+ targeting mandatory; may illustrate the impact of use with **clearly indicated timeframes**.
- Prohibited clickbait: "sensational language with exaggerated or extreme claims, or promises of specific outcomes within a set time frame without disclaimers or qualifiers."

## 2.4 Google Ads policy structure and the creative-relevant rules [OFFICIAL]

Four top-level areas ([policy overview](https://support.google.com/adspolicy/answer/6008942)): Prohibited Content, Prohibited Practices, Restricted Content and Features, Editorial and Technical. Enforcement uses "a combination of Google AI and human evaluation," with ad disapproval, account suspension, and an expanding strike system for repeat offenders.

**Editorial and technical** [OFFICIAL, [editorial policy](https://support.google.com/adspolicy/answer/6021546)] is the directly checkable set:
- Images that are "sideways, upside down, or that don't take up the entire space."
- Images that are "blurry, unclear, unrecognizable, or contain illegible text."
- "Strobing, flashing, or otherwise distracting images."
- Ads that "expand beyond the frame or otherwise encroach on the website or app."
- "Capitalization that isn't used correctly or for its intended purpose."
- Phone numbers in ad text are prohibited.
- Business names must be authentic, not promotional language disguised as a name.
- "Punctuation or symbols that aren't used correctly," "invalid or unsupported characters."
- "Omitting a space or adding extra spaces," "excessive or gimmicky use of spacing."
- "Non-standard, gimmicky, or unnecessary repetition of names, words, or phrases," including asset text repeated within the same ad group, campaign or account.
- A **7-day warning period** before account suspension for non-egregious violations.

**Destination requirements** [OFFICIAL, [destination policy](https://support.google.com/adspolicy/answer/6368661)]:
- Destination not working (HTTP errors to AdsBot).
- Destination mismatch: display URL must align with final and mobile URLs; redirects that take the user to a different domain are prohibited; tracking templates must match final URL content.
- Destination not crawlable by AdsBot.
- Destination not accessible in the targeted geography.
- Destination experience: no abusive experiences, no ad placements violating Better Ads Standards, no unnecessary friction, no direct download from an ad click.
- Insufficient original content: pages built primarily to display ads, replicated without added value, or acting only as redirects.

**Financial services** [OFFICIAL, [financial products policy](https://support.google.com/adspolicy/answer/2464998)]: personal loan ads must prominently display (1) minimum and maximum repayment period, (2) **maximum APR including interest plus fees**, and (3) a representative example of total loan cost with all fees. **Loans repayable in 60 days or less are prohibited. Loans at 36% APR or higher cannot be advertised in the US.** Location-specific verification required.

**Healthcare and medicines** [OFFICIAL, [healthcare policy](https://support.google.com/adspolicy/answer/176031)]: prescription opioids fully banned; unauthorized pharmacies prohibited with immediate account suspension; unapproved pharmaceuticals and supplements, ephedra and hCG weight-loss products prohibited; "promotion of speculative and/or experimental medical treatments" prohibited except FDA-approved cell/gene therapies in the US. Certification required via **LegitScript** or **NABP** for pharmacies, telemedicine and addiction treatment. Country-specific: Poland bans online pharmacy ads entirely, Ireland bans prescription-service pharmacy promotion, Australia and Canada require LegitScript or state/NABP accreditation.

**Alcohol** [OFFICIAL, [alcohol policy](https://support.google.com/adspolicy/answer/6012382)]: prohibited to target under legal drinking age; prohibited to imply alcohol improves "social, sexual, professional, intellectual, or athletic standing"; prohibited to suggest "health or therapeutic benefits"; prohibited to show excessive or binge drinking favorably; prohibited to depict consumption while operating vehicles or machinery or during tasks requiring alertness. Campaigns targeting only disallowed locations show **Disapproved**; mixed targeting shows **Eligible (limited)**. Certain low-ABV ads require certification with highest ABV stated on the landing page. Poland restricts alcohol informational ads to beer only.

## 2.5 Regulated-industry copy constraints

### Pharma
- **FDA final rule on the major statement in DTC TV/radio ads** could not be fetched (federalregister.gov redirects to an unblock gateway and govinfo 404'd). The rule's five standards for clear, conspicuous and neutral presentation, the dual-modality requirement, and compliance dates should be verified directly before encoding. **Flagged as an unfilled gap.**
- FDA claim framework confirmed via [FDA label claims](https://www.fda.gov/food/nutrition-food-labeling-and-critical-foods/label-claims-conventional-foods-and-dietary-supplements) [OFFICIAL] for the food/supplement side (below). The three DTC ad types (product claim, reminder, help-seeking) could not be re-verified against a live FDA page this session.

### Financial services
**FINRA Rule 2210** [OFFICIAL, [rule text](https://www.finra.org/rules-guidance/rulebooks/finra-rules/2210)]:
- Three categories: **Correspondence** (<=25 retail investors in 30 days), **Retail Communications** (>25 retail investors in 30 days), **Institutional Communications**.
- **Pre-use filing, 10 business days before first use**: new member firms in their first year for public-media retail communications; custom investment company performance rankings; security futures; **television or video communications, filed as draft storyboards**. That last one is directly relevant to a video creative pre-flight product: a storyboard, not the finished film, is the filing artifact.
- **Post-use filing, within 10 business days of first use**: registered investment company promotions, public DPPs, CMOs, structured/derivative securities.
- No filing required: correspondence, institutional communications, previously filed unchanged material, media-only press releases, SEC-filed prospectuses.
- Retail communications require **principal approval before use or filing**.
- Content standards: no "false, exaggerated, unwarranted, promissory or misleading" statements; **cannot "predict or project performance"**; testimonials must disclose paid status and non-representativeness; member name must be prominently displayed; BrokerCheck hyperlink required on websites.

**SEC Marketing Rule 206(4)-1** [OFFICIAL, [SEC marketing FAQ](https://www.sec.gov/investment/marketing-faq)]:
- Net performance must be presented alongside gross with **"equal prominence"** and **"in a format designed to facilitate comparison,"** using identical time periods, methodologies and return types.
- Performance must be shown for **one-, five-, and ten-year periods** ending no later than the most recent calendar year-end. Interim data permitted for up to one month after year-end.
- Compensated testimonials/endorsements barred where the endorser has a disqualifying event within the prior **10 years**; the adviser must know or through "reasonable care should know."
- Model fees must reflect expected charges where anticipated fees differ from historical.

**Regulation Z section 1026.24** [OFFICIAL, [CFPB Reg Z 1026.24](https://www.consumerfinance.gov/rules-policy/regulations/1026/24/)]:
- **Trigger terms** for closed-end credit: downpayment amount or percentage ("only 5% down"), payment period ("48-month terms," "30-year mortgage"), payment amount ("$103 monthly"), finance charge amount ("$500 total cost of credit").
- Any trigger term forces disclosure of: total downpayment as dollar amount or percentage; full repayment terms over the complete term **including any balloon payment**; the APR using the exact term "APR," with a note if it may increase after consummation.
- Rates must be expressed as "annual percentage rate"; **no other rate may be stated more conspicuously than the APR**; cannot advertise terms not actually available; cannot label a variable-rate product "fixed" without qualification.
- This is highly encodable: regex for trigger phrases, then require the presence of APR plus repayment terms in the same creative.

### Alcohol
- **DISCUS Code of Responsible Practices** and the **Beer Institute Advertising and Marketing Code** both require placement only where the audience is at least a defined percentage legal drinking age. The widely cited current figure is **71.6%** of audience aged 21+, updated upward from a historical 70% standard [PRACTITIONER, the DISCUS PDF is font-embedded and could not be text-extracted; discus.org redirects to an image file]. Note that **73.6%** also circulates. **Verify the current number before encoding.**
- Beer Institute Code core principles [OFFICIAL, [Beer Institute code](https://www.beerinstitute.org/responsibility/advertising-marketing-code/)]: legal compliance ("Beer advertising should not suggest directly or indirectly that any of the laws applicable to the sale and consumption of beer should not be complied with"), "contemporary standards of good taste," responsible corporate citizenship in "themes, creative aspects, and placements," and explicit opposition to "abuse or inappropriate consumption." The detailed standards live in a linked PDF that did not render.
- **France, Loi Évin (1991)** [PRACTITIONER]: alcohol ads must carry *"L'abus d'alcool est dangereux pour la santé, à consommer avec modération"* plus heavy channel and content restrictions.

### Food, nutrition and supplements
**FTC Health Products Compliance Guidance (2022)** [OFFICIAL, [FTC guidance](https://www.ftc.gov/business-guidance/resources/health-products-compliance-guidance)]:
- Substantiation standard: **"competent and reliable scientific evidence,"** defined as "tests, analyses, research, or studies that (1) have been conducted and evaluated in an objective manner by experts in the relevant disease, condition, or function... and (2) are generally accepted in the profession to yield accurate and reliable results."
- **Randomized controlled human clinical trials are the gold standard.** Animal and lab studies are insufficient without human confirmation. Epidemiological studies acceptable only where RCTs are infeasible.
- **Totality of evidence**: cherry-picking favorable studies is a violation.
- **The four Ps for disclosures: Prominent, Proximate, Persistent, Perceptible.** This maps almost directly onto a design check: font size and contrast (prominent), spatial adjacency to the claim (proximate), on-screen duration for video (persistent), plain language (perceptible).
- Vague qualifiers like "may," "promising" or "preliminary" **do not** adequately communicate scientific limitations.
- **"The DSHEA disclaimer does not cure deceptive advertising under FTC law."**
- Advertisers remain liable for claims made via consumer testimonials or expert endorsements.

**FDA claim categories** [OFFICIAL, [FDA label claims](https://www.fda.gov/food/nutrition-food-labeling-and-critical-foods/label-claims-conventional-foods-and-dietary-supplements)]:
- **Health claims**: three pathways, NLEA authorized (significant scientific agreement), FDAMA authoritative statements (not available for supplements), and qualified health claims (require qualifying language).
- **Nutrient content claims**: "free," "high," "low," "more," "reduced," "lite" must be FDA-authorized. **"Healthy" is an implied nutrient content claim** with defined fat, cholesterol and sodium standards.
- **Structure/function claims**: not pre-approved, require manufacturer substantiation.
- **The exact DSHEA disclaimer, verbatim**: *"These statements have not been evaluated by the Food and Drug Administration. This product is not intended to diagnose, treat, cure, or prevent any disease."* Encode as an exact-string presence check whenever a structure/function claim is detected.

**FTC Endorsement Guides, 2023 update** [OFFICIAL, [FTC endorsement FAQ](https://www.ftc.gov/business-guidance/resources/ftcs-endorsement-guides-what-people-are-asking)]:
- Material connections must be disclosed whenever a relationship exists that consumers would not expect: paid relationships, free product, affiliate commissions, employment.
- Clear and conspicuous means strategic placement, readable font, contrasting background, unambiguous language. **Platform-provided disclosure tools do not guarantee compliance.**
- Space-limited platforms: "Ad:" or "#ad" at the **beginning** of the post is generally acceptable.
- **Inadequate**: disclosures buried in video descriptions, below truncated text, in comments, in hyperlinked buttons; brand tagging alone; saying "thank you"; ambiguous hashtags like "#ambassador"; a single home-page disclosure when reviews are reachable individually.
- Multi-part endorsements across platforms each require their own disclosure.
- Exceptional or above-average results require clear communication of generally expected outcomes.
- Advertisers cannot delegate liability to agencies; reasonable training, monitoring, periodic audits and pre-approval are expected.

### EU
**Directive (EU) 2024/825, Empowering Consumers for the Green Transition** [OFFICIAL, [EUR-Lex](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202400825)]:
- **Banned generic environmental claims** unless recognised excellent environmental performance is demonstrated: "environmentally friendly," "eco-friendly," "green," "nature's friend," "ecological," "climate friendly," "gentle on the environment," "carbon friendly," "energy efficient," "biodegradable." A specific verifiable claim like "100% renewable energy" is permitted. **This is a directly encodable banned-phrase list.**
- Bans sustainability labels "not based on a certification scheme or not established by public authorities."
- Future-performance claims require "clear, objective, publicly available and verifiable commitments set out in a detailed and realistic implementation plan" with third-party verification.
- **Bans offsetting-based claims** that a product has "a neutral, reduced or positive impact on the environment in terms of greenhouse gas emissions."
- Bans presenting legally mandated features as differentiators.
- **Transposition deadline 27 March 2026. Application date 27 September 2026.**
- Other EU layers [PRACTITIONER]: Price Indication Directive 98/6/EC (unit pricing), Omnibus Directive (EU) 2019/2161, UCPD, DSA advertising transparency and ad repository obligations, GDPR consent for targeting.

### Children
**COPPA** [OFFICIAL, [FTC children's privacy](https://www.ftc.gov/business-guidance/privacy-security/childrens-privacy)]: applies to under-13s, covers child-directed sites and general-audience sites that attract children, requires verifiable parental consent before collecting personal information, and gives parents control over collection. The FTC provides a Six-Step Compliance Plan. The specific 2025 amendment details could not be confirmed from this page.

**UK CAP Code** [OFFICIAL, [advertising codes](https://www.asa.org.uk/codes-and-rulings/advertising-codes/non-broadcast-code.html)]. The creative-relevant sections: **02 Recognition of Marketing Communications** (ad labelling), **03 Misleading Advertising** (substantiation, pricing, availability, comparatives, testimonials), **05 Children**, **11 Environmental Claims**, **12 Medicines, Medical Devices, Health-Related and Beauty Products** (very high evidence standard for medicinal claims), **15 Food, Food Supplements and Associated Health Claims**, **18 Alcohol**. The code requires "all qualifying information remains legible and accessible to the intended audience," which is a direct legibility hook for a design checker.

**UK HFSS restrictions** [PRACTITIONER, date unconfirmed]: legislated under the Health and Care Act 2022, comprising a 9pm TV watershed for HFSS product advertising and a ban on paid-for online HFSS advertising with no time-of-day exemption. The policy was delayed repeatedly (originally January 2023, most recently targeted at October 2025). **Verify the current effective date at gov.uk or asa.org.uk before encoding.**

**Germany ad labelling** [PRACTITIONER]: UWG section 5a Abs. 4 requires commercial communications, including influencer posts that promote or tag a brand, to be labelled **"Werbung"** or **"Anzeige"** unless the commercial nature is obvious from context. Actively litigated by the Wettbewerbszentrale.

**France food health messages** [PRACTITIONER]: Loi de santé publique n°2004-806 requires food and beverage ads to carry one of a fixed rotating set of messages, e.g. *"Pour votre santé, mangez au moins cinq fruits et légumes par jour," "Pour votre santé, pratiquez une activité physique régulière," "Pour votre santé, évitez de manger trop gras, trop sucré, trop salé," "Pour votre santé, évitez de grignoter entre les repas."* Advertisers omitting the message pay a levy historically cited at **1.5% of ad spend** to Santé publique France. Legifrance returned 403; verify wording before encoding.

## 2.6 Accessibility: encodable thresholds

All [OFFICIAL] from W3C unless noted.

| Rule | Threshold | Source |
|---|---|---|
| Text contrast, normal | **>=4.5:1** | [SC 1.4.3](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) |
| Text contrast, large | **>=3:1** | SC 1.4.3 |
| Large text definition | **>=18pt regular (~24px) or >=14pt bold (~18.5px)**; 1pt = 1.333px | SC 1.4.3 |
| Text contrast AAA, normal | **>=7:1** | [SC 1.4.6](https://www.w3.org/WAI/WCAG22/Understanding/contrast-enhanced.html) |
| Text contrast AAA, large | **>=4.5:1** | SC 1.4.6 |
| Non-text / UI / icon contrast | **>=3:1** vs adjacent colors | [SC 1.4.11](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html) |
| Text resize | must survive **200%** | [SC 1.4.4](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html) |
| Line height | **>=1.5x font size** | [SC 1.4.12](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html) |
| Paragraph spacing | **>=2x font size** | SC 1.4.12 |
| Letter spacing | **>=0.12x font size** | SC 1.4.12 |
| Word spacing | **>=0.16x font size** | SC 1.4.12 |
| Touch target AA | **>=24x24 CSS px** | [SC 2.5.8](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html) |
| Touch target AAA | **>=44x44 CSS px** | SC 2.5.5 |
| Flash rate | **<=3 flashes per 1-second period** | [SC 2.3.1](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html) |
| Captions | required for prerecorded synchronized media | SC 1.2.2 |

**Critical implementation detail [OFFICIAL, from the SC 1.4.11 page]**: "the computed values should not be rounded (e.g. 2.999:1 would not meet the 3:1 threshold)." A checker must not round up.

**Exceptions that matter for ad creative [OFFICIAL]**: "Text that is part of a logo or brand name has no contrast requirement." Incidental text is exempt: inactive UI, pure decoration, not visible, or "part of a picture that contains significant other visual content." Any pre-flight tool must region-tag logos and decorative type before running contrast, or it will produce false positives on every wordmark.

**Images of text**: SC 1.4.5 (AA) requires real text unless customizable or essential, and explicitly states **"Logotypes (text that is part of a logo or brand name) are considered essential."** SC 1.4.9 (AAA) removes the customizable escape hatch. For ad creative this means baked-in headline and CTA type is an AA flag unless it is a logo. [SC 1.4.5](https://www.w3.org/WAI/WCAG22/Understanding/images-of-text.html)

**Photosensitivity, full parameters [OFFICIAL]**: general flash = opposing luminance change **>=10%** of max relative luminance where the darker frame's relative luminance is **<0.80**; area threshold **0.006 steradians within any 10 degree visual field**, equal to **25% of a 10 degree field**; reference screen patch **341x256px = 87,296 CSS px squared**; elements smaller than 0.1 degree of visual field are exempt.

**Platform minimums**:
- Apple HIG [OFFICIAL, [typography](https://developer.apple.com/design/human-interface-guidelines/typography)]: minimum font size **iOS/iPadOS 11pt, macOS 10pt, tvOS 23pt, visionOS 12pt, watchOS 12pt**. Body defaults 17 / 13 / 29 / 17 / 16pt. Apple's published minimum control size is **28x28pt** on iOS/iPadOS/visionOS/watchOS, 20x20pt macOS, 56x56pt tvOS, with 12pt padding around beveled and 24pt around non-beveled elements to reach a comfortable hit area. The familiar **44x44pt** figure is Apple's older guidance and remains the safe practitioner default. Apple aligns contrast to WCAG AA explicitly: <=17pt requires 4.5:1, >=18pt or any bold requires 3:1. Text must enlarge to **200%** (140% watchOS).
- Material 3 [OFFICIAL]: touch target **>=48x48dp** (roughly 9mm; "7-10mm" recommended), pointer target **>=44x44dp**, target spacing **>=8dp**. A 24x24dp icon typically gets a 48x48dp target via padding. The full M3 type scale token table is image/JS-rendered and could not be extracted; the commonly published defaults (Display Large 57sp/64, Headline Large 32sp/40, Title Large 22sp/28, Body Large 16sp/24, Body Medium 14sp/20, Label Large 14sp/20) are [PRACTITIONER].
- APCA / WCAG 3 [PARTIAL]: minimum font size by tier per readtech.org/ARC is **Bronze none specified, Silver 13px (x-height ratio 0.5), Gold 18px**. APCA remains beta and is not a ratified SC. Encode as advisory only. The Lc lookup table could not be retrieved.

**Contrast over photographs** [synthesis, no single official procedure exists]: the standard engineering approach is to sample the region directly behind each glyph or line (plus a small bleed), compute contrast against **both the lightest and darkest pixels** in that footprint, fail if either extreme fails, and where variance is high require a scrim (typically 30-60% opacity black or white, or a solid plate behind the text) and re-measure against the flattened composite. This is a practitioner implementation of SC 1.4.3, not a W3C-published method.

**Captions** [OFFICIAL, [FCC internet captioning](https://www.fcc.gov/consumers/guides/captioning-internet-video-programming)]: FCC rules apply to full-length TV programming redistributed online substantially in its entirety, plus clips from captioned TV programming on a distributor's own site. **Consumer-generated media is exempt**, which means most social ad creative is outside FCC scope and governed only by WCAG 1.2.2 and platform recommendation. Live clip caption delay allowances: up to 12 hours live, 8 hours near-live. Archival caption-add deadlines tightened from 45 to 30 to **15 days** after 30 March 2016. Burned-in open captions are the practitioner standard for social because of sound-off autoplay; keep them inside a roughly 10% title-safe inset with a plate or stroke to guarantee contrast, and clear of platform UI in the lower third.

## 2.7 Localization and cultural failure

### Text expansion

Source-length table [OFFICIAL, [W3C text size article](https://www.w3.org/International/articles/article-text-size/) quoting IBM's Guidelines to Design Global Solutions]:

| English characters | Average expansion |
|---|---|
| Up to 10 | **200-300%** |
| 11-20 | **180-200%** |
| 21-30 | **160-180%** |
| 31-50 | **140-160%** |
| 51-70 | **151-170%** |
| Over 70 | **130%** |

Note these IBM figures are expressed as **total resulting length**, not added length. The widely used practitioner restatement is **+30% to +35% on long strings and +100% to +300% on short UI strings** such as buttons and CTAs. Both framings appear in the literature; a product should pick one and label it.

W3C also gives a concrete worked example: the single word "views" in Flickr [OFFICIAL]:

| Language | Translation | Ratio to English |
|---|---|---|
| Korean | 조회 | **0.8** |
| English | views | 1.0 |
| Chinese | 次檢視 | **1.2** |
| Portuguese | visualizações | **2.6** |
| French | consultations | **2.6** |
| German | -mal angesehen | **2.8** |
| Italian | visualizzazioni | **3.0** |

The key insight, stated directly by W3C: **"the smaller the source message, the higher the likely translation length."** For ad creative this is the dominant failure mode, because headlines and CTAs are exactly the short strings that expand 2-3x.

Per-language planning figures [PRACTITIONER, directional]:

| Language | Expansion vs English |
|---|---|
| German | +10% to +35%, compounds push short strings toward +100% |
| French | +15% to +20% |
| Spanish | +15% to +30% |
| Italian | +15% to +20% |
| Portuguese | +15% to +30% |
| Russian | +10% to +15% |
| Polish | +20% to +30% |
| Finnish | **+20% to +60%**, among the most expansive (agglutinative) |
| Dutch | +10% to +20% |
| Greek | +10% to +30% |
| Turkish | +20% |
| Vietnamese | +20% to +30% (diacritics add width) |
| Thai | +10% to +15%, but **no inter-word spaces so line-wrapping is the real risk** |
| Arabic | -10% to -25% characters, but needs more vertical space |
| Hebrew | -10% to -20% characters, same caveat |
| Japanese | -10% to -55% characters, needs taller line-height |
| Korean | -10% to -15% |
| Chinese | roughly -50% characters |

**The CJK/Arabic trap worth encoding**: character-count contraction is not space savings. Arabic typically needs **+10% to +20% larger point size and +20% to +30% more leading** than the equivalent Latin setting because of connected cursive forms, tashkeel diacritics and a deeper ascender/descender range. CJK needs taller line-height. A layout that shrinks to fit the character count will be illegible. [PRACTITIONER]

### RTL

What mirrors [PRACTITIONER, Material and Apple HIG consensus; both primary pages 404 or are JS-only]: text alignment, layout order (nav, tabs, form fields, list chevrons), directional icons implying reading flow (back/forward, next/previous, send, undo/redo), progress bars, sliders, loading indicators, toggle switches.

What does **not** mirror: **brand logos and lockups** (never flip horizontally, reposition instead), digit sequences (Unicode bidi reads them LTR inside RTL text), real-world-object icons with fixed orientation (clocks, cameras, play/pause), charts and axes unless explicitly localized.

Ad-specific breakages:
- Logo plus CTA pairing must flip order while the logo mark itself stays unmirrored.
- Chevron direction must flip: "Shop Now >" becomes "< تسوق الآن".
- **Eastern Arabic-Indic digits (٠١٢٣) vs Western digits (0123) is a per-market choice**, not a mirroring rule. Gulf commercial contexts often use Western digits.
- **Mixed LTR brand names inside Arabic strings** reorder incorrectly without direction isolation. The W3C fix [OFFICIAL, [inline bidi markup](https://www.w3.org/International/articles/inline-bidi-markup/)]: wrap every opposite-direction phrase, e.g. `<span dir="ltr">BrandName</span>`, append U+200E (`&lrm;`) for legacy rendering, and use `dir="auto"` or `<bdi>` when direction is unknown at authoring time.
- Arabic punctuation has its own forms: Arabic comma (،) and question mark (؟). Reusing LTR glyphs is a visible error.
- TikTok ships a **separate RTL safe-zone template**, which means safe-zone geometry itself is direction-dependent on at least one platform.

### Locale formats [OFFICIAL, [CLDR date-time patterns](https://cldr.unicode.org/translation/date-time/date-time-patterns), [Microsoft number formatting](https://learn.microsoft.com/en-us/globalization/locale/number-formatting)]
- Date order: MDY (US), DMY (most of Europe, LatAm), YMD (Korea, Japan, China; CLDR example 2010年12月5日) plus ISO 8601.
- 12-hour with AM/PM (US) vs 24-hour (most of Europe, LatAm). CLDR patterns: `h:mm a` or `K` for 12-hour, `H:mm` / `HH:mm` or `k` for 24-hour. Sub-locales override: **Spanish in the US uses 12-hour despite Spain preferring 24-hour.**
- Decimal separator: comma in continental Europe, period in US/UK. **Switzerland uses comma generally but period for currency.** Germany's everyday thousands separator is a period (12.345) while DIN 1333 specifies a space from 5 digits (12 345). **India groups after the first 3 digits then every 2** (10,00,00,000).
- Currency position: **€ -1.234,56 in the Netherlands vs -1 234,56 € in France**, same currency, opposite symbol placement and separators.
- Metric everywhere except US imperial; UK is hybrid (miles on roads, metric elsewhere).
- Paper: Letter 8.5x11in (US/Canada) vs A4 210x297mm.
- Name order: family name first in Japan, China, Korea and Hungary, which breaks "{FirstName} {LastName}" personalization tokens.

### Color symbolism [PRACTITIONER, Joe Hallock's "Colour Assignments" 2003 is one of the few systematic cross-country studies, http://www.joehallock.com/edu/COM498/index.html]

| Color | Western | Contrasting market |
|---|---|---|
| White | Purity, weddings | Mourning in China, Japan, India, broader East/South Asia |
| Red | Danger, passion | Luck and prosperity (China), bridal purity (India) |
| Green | Nature, eco, "go" | Sacred in Islam; **a green hat (戴绿帽子) signals cuckoldry in Chinese slang, so avoid green headwear in China-directed creative** |
| Purple | Royalty, luxury | Mourning/widowhood in Thailand and parts of Brazil |
| Yellow | Happiness, caution | Imperial/sacred in China; mourning in parts of Egypt and Myanmar |
| Blue | Trust, corporate default | Protective evil-eye (nazar) associations in Turkey and the Middle East |

### Documented localization failures

| Case | Market / year | What happened | Consequence | Confidence |
|---|---|---|---|---|
| Dolce & Gabbana | China, Nov 2018 | Video showed a Chinese model struggling to eat Italian food with chopsticks; co-founder's Instagram allegedly posted racist remarks | Shanghai show cancelled; ambassadors Wang Junkai, Dilraba Dilmurat and Zhang Ziyi cut ties; **Alibaba and JD.com delisted the brand; Yangmatou delisted roughly 58,000 D&G products**; founders' video apology 23 Nov 2018 | [OFFICIAL, [Wikipedia](https://en.wikipedia.org/wiki/Dolce_%26_Gabbana)] |
| H&M "Coolest Monkey in the Jungle" | UK/South Africa, Jan 2018 | Black child model in a hoodie with that copy | **Stores vandalized and looted in South Africa, temporarily closed**; The Weeknd and G-Eazy ended collaborations | [OFFICIAL, [Wikipedia](https://en.wikipedia.org/wiki/H%26M)] |
| HSBC "Assume Nothing" rebrand | Global, 2018 | Rebrand criticized as near-identical to what it replaced | Widely reported at **approximately $10 million** (Adweek headline corroborates the figure; article body did not load) | [PRACTITIONER] |
| HSBC "world's local bank" | Global, retired 2013 | Positioning abandoned; CEO Stuart Gulliver cited "spiraling" associated costs | Strategy formally dropped | [OFFICIAL, Wikipedia, limited detail] |
| Pepsi / Kendall Jenner | US, Apr 2017 | Jenner defuses a protest by handing an officer a Pepsi | **Pulled within about 24 hours**, public apology | [PRACTITIONER, extensively covered but no live fetch succeeded] |
| Nivea "White is Purity" | Middle East, Apr 2017 | Copy pairing "purity" with "white" | Pulled, public apology | [PRACTITIONER] |
| Heineken "Sometimes, lighter is better" | US, Mar 2018 | Bartender slides a beer past Black patrons to a lighter-skinned woman | Pulled, apology, amplified by Chance the Rapper | [PRACTITIONER] |

**Flag these as [DISPUTED] and do not ship them as fact:**
- **Chevrolet Nova "no va"**: a documented urban legend. Spanish speakers do not parse "Nova" as "no va" any more than English speakers parse "notable" as "no table," and Latin American Nova sales were not notably depressed.
- **Pepsi "brings your ancestors back from the grave"**: listicle staple with no named market, date or contemporaneous coverage.
- **KFC "eat your fingers off"**: same, no credible primary source.

These three appear in almost every localization marketing deck. A product that repeats them loses credibility with anyone who has checked.

## 2.8 Typography and layout quality heuristics

| Rule | Threshold | Source |
|---|---|---|
| CSS `orphans` default | **2 lines** minimum at bottom of fragment | [MDN orphans](https://developer.mozilla.org/en-US/docs/Web/CSS/orphans) |
| CSS `widows` default | **2 lines** minimum at top of fragment | [MDN widows](https://developer.mozilla.org/en-US/docs/Web/CSS/widows) |
| Body line length | **~60-70 characters per line** | [Smashing Magazine](https://www.smashingmagazine.com/2020/07/css-techniques-legibility/) |
| Classic typographic range | 45-75 chars, ideal ~66 | [PRACTITIONER, Bringhurst] |
| Default browser line-height | 1.2, with an x-height-derived optimum generally landing 1.4-1.6 | Smashing Magazine |

Note both `orphans` and `widows` are unsupported in Firefox, so they are useful as reference values rather than enforcement mechanisms. For display type, the encodable rule is: no single-word final line in a headline, and rebalance line breaks rather than relying on CSS.

**Visual hierarchy** [OFFICIAL, [NN/g visual hierarchy](https://www.nngroup.com/articles/visual-hierarchy-ux-definition/)]:
- **No more than 3 contrast levels.** Never rely on color alone.
- **Use <=3 size levels.** NN/g's stated example ranges: **14-16px body, 18-22px subheader, up to 32px header**.
- **Limit to <=2 dominant "big" elements** per layout to avoid competing focal points.
- Roughly 2 primary plus 2 secondary colors in simple layouts.
- Grouping: more space between unrelated groups, less between a heading and its content; elements with more surrounding whitespace draw more attention.
- [NN/g Gestalt proximity](https://www.nngroup.com/articles/gestalt-proximity/) adds a directly relevant warning: grouping unrelated items can visually camouflage a component users would otherwise notice. In ad creative this is exactly the failure where a CTA button gets grouped with legal disclaimer text and stops reading as a button.

Directly encodable: `count(distinct_font_sizes) <= 3`, `count(dominant_elements) <= 2`, `count(high_contrast_accent_colors) <= 2`, and `gap(unrelated_blocks) > gap(related_blocks)`.

**Logo rules** [PRACTITIONER, no cross-brand standard exists]:
- Clear space is conventionally defined as a multiple of a feature of the logomark itself (a letterform's height, the "x," the icon width), typically **0.5x to 1.0x the logo height** on all sides, scaling with the logo. Encode as `min_clear_space = k * logo_height` with k configurable per brand.
- Minimum reproduction size typically floors at roughly **16-24px height** for a favicon-class mark and **80-120px width** for a standard lockup digitally, or 0.5 to 1 inch in print. **There is no universal constant**; this must come from the advertiser's own brand guideline. A pre-flight product should ingest brand guidelines rather than hardcode a number.

**Focal point and multi-ratio cropping** [PRACTITIONER, engineering pattern per [Cloudinary](https://cloudinary.com/documentation/resizing_and_cropping)]:
- `g_auto` (automatic gravity) keeps the most important content in frame; `gravity:face` / `gravity:faces` anchors the crop to detected faces; `c_fill` plus `ar_<ratio>` derives each target ratio from one master.
- The encodable QA rule: when one master is resized to multiple aspect ratios, verify (a) a focal point or face bounding box was detected and used as the crop anchor rather than a default center crop, and (b) **the focal point or face bounding box remains fully inside the crop frame for every derived ratio**. Flag any ratio where it is clipped.
- This is the single highest-value check for the modern workflow, because the dominant production pattern is one master asset fanned out to 1:1, 4:5, 9:16, 1.91:1 and 16:9, and center-crop silently decapitates people in the vertical variants.

**Creative-effectiveness research: a deliberate negative finding.** All four major sources failed to return substantive content: Meta's mobile creative insights page (404), Think with Google creative effectiveness (301 to an empty client-rendered shell), Kantar LINK AI (404), and Nielsen insights (no matching articles in the index). **No "first 3 seconds," "logo within X seconds," or "brand asset visibility +Y% recall" figure should be encoded or cited** from this research pass. These heuristics are widely repeated in industry commentary but none could be traced to a live primary source. If the product needs them, they require a dedicated research pass against the specific report PDFs, most of which sit behind lead-capture forms.

---

# PART 3: REVIEW TIMELINES AND THE COST OF MID-FLIGHT REJECTION

## 3.1 Stated review SLAs

| Platform | Stated SLA | Source |
|---|---|---|
| **Google Ads** | "Most ads are reviewed within **one business day**." Check status after "more than 2 full business days"; contact support after a week. | [OFFICIAL](https://support.google.com/google-ads/answer/1722120) |
| **Meta** | "Most ads are reviewed within **24 hours**, although in some cases it may take longer." | [OFFICIAL](https://www.facebook.com/business/help/204798856225114), via m.facebook.com mirror |
| **LinkedIn** | "We strive to review ads and forms as soon as possible and **usually within 24 hours**." Contact support if past 24h, especially for time-sensitive campaigns. | [OFFICIAL](https://www.linkedin.com/help/lms/answer/a421048) |
| **Google DV360** | No timeframe stated. Rejection reasons include unacceptable video format, uncrawlable destination, non-SSL, invalid tag, "destination mismatch due to inactive placements or incorrect flight dates." | [OFFICIAL](https://support.google.com/displayvideo/answer/12726387) |
| **TikTok** | Widely cited as 24 hours, **could not be verified**; help articles are JS-gated. | [PRACTITIONER] |
| **Amazon** | Commonly cited 24-72 hours, Brand Stores up to 72h+. **Could not be sourced to an official page.** | [PRACTITIONER, unverified] |
| **Pinterest, Snap, Reddit, Walmart Connect** | Not retrievable. All are Salesforce SPAs or JS-gated. | Gap |

## 3.2 What re-triggers review and what resets learning

**Meta, the single most important operational rule** [OFFICIAL, help/204798856225114]:
> "Edits to targeting, creative, optimization, or billing events trigger new reviews, though **budget or bid adjustments do not**."

Meta's review examines creative assets (images, video, text), targeting parameters, ad destination and landing page, special ad categories, and advertiser permissions. Ads scheduled for the future enter review immediately but do not deliver until the start time, which is the mechanism that makes pre-flight valuable: **you can burn the review window before the flight starts rather than during it.**

**Meta learning phase** [OFFICIAL, [learning phase](https://www.facebook.com/business/help/112167992830700), via m.facebook.com mirror]:
- Learning concludes "after about **50 [results]** in the week after the ad set's **last significant edit**."
- Re-entry triggers: "Creating new ads or ad sets," "making significant edits to existing ones," "edits that meaningfully change how your ad set might perform in the future," and "**frequent budget changes**."
- Direct warning: "By editing an ad, ad set or campaign during the learning phase, you **reset learning** and delay our delivery system's ability to optimize."
- **Learning Limited**: the Delivery column reads "Learning limited" when an ad set cannot accumulate enough results to exit learning.
- Shops ads special case: "**a minimum of 17 purchases through your website and 5 through Meta**" to complete learning.
- Meta's own advice: "Wait to edit your ad set until it's out of the learning phase."

Note the apparent contradiction with the review rule: budget changes do **not** trigger re-review, but **frequent budget changes do** re-enter learning. These are two independent penalties with different triggers, and a product should model them separately.

**Google** [OFFICIAL]: "Edits to your ads or assets **restart the review process** and may cause delays." Fixing a disapproved ad means editing to comply and selecting Save, which auto-resubmits. Which edits reset Smart Bidding machine learning (a distinct concept from review) could not be sourced to an official page and should be treated as a gap.

## 3.3 Appeals

**Google** [OFFICIAL, [fix a disapproved ad](https://support.google.com/google-ads/answer/1704381) and [appeals](https://support.google.com/adspolicy/answer/9338593)]:
- Appeal via Policy Manager or the Ads page: "Appeal policy decision," then "Dispute decision" or "Made changes to comply with policy."
- Turnaround: "In progress: Your appeal is currently under review. **Check back in 24 hours** for an updated status."
- **Maximum 3 appeals per ad**; after three unsuccessful attempts, contact support.
- **Wait at least 24 hours between appeals** or they are marked duplicates. Too many unique appeals within 24 hours can suspend appeal processing.
- Outcomes: Successful, Partially successful, Failed ("None of the ads in your appeal are able to run"), Duplicate.
- Fallback when appeals fail: "a minor edit to your ad's text or final URL" forces a fresh system review.
- **Policy change: starting 21 July 2026, appealing a policy decision made more than 6 months prior is no longer available in-account.**

**Google account-level** [OFFICIAL, [suspensions](https://support.google.com/adspolicy/answer/7187501)]: "A disapproved ad won't be able to run until the policy violation is fixed and the ad is reviewed." On suspension, "all ads in the suspended account will stop running." For non-egregious violations, the warning "will be sent **at least 7 days before suspension action**." Egregious violations are suspended "immediately, without prior warning." Google also states it continues "to expand a strike system for repeat offenders," but the specific strike tiers and hold durations could not be retrieved.

**Meta** [OFFICIAL]: recourse is to "request another review in Meta Business Support Home." No SLA is stated. Meta acknowledges "both machines and people make mistakes." No account-restriction tiering page could be retrieved.

**LinkedIn** [OFFICIAL, [ad policies](https://www.linkedin.com/help/lms/answer/a414962)]: "Advertisements that don't meet our advertising policies will be removed from the site and the advertiser may be restricted from further advertising on LinkedIn." Rejected ads are labeled in Campaign Manager with an emailed reason and an appeal option. No turnaround stated.

**DV360** [OFFICIAL]: advertisers can "dispute the decision," and "an appeal may lead to a manual review and approval." No SLA.

## 3.4 The cost of mid-flight rejection

What can be stated from official sources:

1. **Zero delivery during disapproval.** Google: a disapproved ad "won't be able to run until the policy violation is fixed and the ad is reviewed." Dark time equals detection lag plus fix time plus re-review time. Re-review itself is "most... within one business day," but detection lag is the variable that dominates, and nothing in a platform UI actively alerts a media team the way a monitoring tool would.

2. **Editing to fix re-triggers everything.** On Meta, a creative edit triggers a new review **and** counts as a significant edit that resets the learning phase. So a mid-flight creative rejection costs the review window **plus** a full re-accumulation of roughly 50 optimization events (or 17 web + 5 Meta purchases for Shops ads) before delivery efficiency returns. During learning, Meta states performance "remains unstable and isn't predictive of future results."

3. **The compounding shape of the cost** (inference from the official mechanics above, not a published figure): review window at 1 business day, plus learning re-accumulation which on a low-volume ad set can take most of a week to reach 50 events, plus budget under-delivery and the subsequent pacing catch-up. For a 14-day flight, a single mid-flight creative rejection can plausibly compromise a third to a half of the flight. **This is a modeled shape, not a measured number, and should be presented that way.**

4. **A pre-flight product's actual leverage** comes from Meta's scheduling behavior: ads scheduled for a future start enter review immediately but do not deliver until the start time. Catching a violation before submission converts a mid-flight outage into zero cost. Catching it after launch costs review plus learning reset.

**Honest negative finding on quantification.** No published or credibly sourced number could be found for: the percentage of campaigns that hit a disapproval, average days lost per rejection, the cost of a rejected flight day, first-submission disapproval rates, or appeal overturn rates. Every candidate source (Tinuiti, Smartly, Search Engine Land, AdEspresso, WordStream, Jon Loomer) either 404'd, returned 403, or contained only qualitative guidance. Tinuiti's ad-specs article yielded exactly one actionable line: "Schedule a refresh before performance decline creates a rushed production cycle," with no cadence number.

The defensible quantified claims available are:
- **Google 2024**: 5.1B ads removed, 9.1B restricted, 39.2M accounts suspended. [OFFICIAL]
- **Meta H1 2026**: enforcement precision ~91% Facebook, ~92% Instagram, implying an **8-9% error rate** on enforcement decisions. [OFFICIAL]
- **Google appeals**: max 3 per ad, 24h minimum between attempts, 24h status cadence. [OFFICIAL]
- **Google suspension**: 7-day warning for non-egregious, immediate for egregious. [OFFICIAL]
- **Meta learning**: 50 events per ad set per week, reset by any significant edit. [OFFICIAL]

**Creative fatigue and refresh cadence**: no verified benchmark could be sourced. Treat any cadence number in the product as a configurable assumption, not a cited fact.

---

# GAPS: what could not be verified and should be re-researched

Ranked by how much it matters for a rule library:

1. **Walmart Connect creative policy.** No prohibited-claims document retrievable at all. The entire Walmart policy module is currently unsourced.
2. **Amazon official SLA and the policy page itself.** The creative acceptance rules above came from Amazon's moderation *guide* and quick reference; [advertising.amazon.com/resources/ad-policy/en](https://advertising.amazon.com/resources/ad-policy/en) returns only a tracking pixel. Moderation turnaround has no official source.
3. **FDA DTC final rule** on the major statement (five standards, dual modality, effective dates). federalregister.gov redirects to an unblock gateway; govinfo 404'd. This is the highest-value unfilled regulatory item.
4. **DISCUS and Beer Institute audience-composition percentage.** 71.6% vs 73.6% both circulate. The DISCUS PDF is font-embedded and not text-extractable; discus.org's code URL redirects to a PNG.
5. **TikTok numeric safe zones.** Official position is that there are no published numbers, only template files. Ingest the templates.
6. **IAB New Ad Portfolio numbers.** File weight, animation limits and flexible size ranges are behind an IAB account login. The LEAN principles are confirmed; the numbers are not.
7. **UK HFSS effective date.** Delayed repeatedly; verify at gov.uk at time of use.
8. **Google strike system tiers and hold durations.** Confirmed to exist, numbers not retrievable.
9. **Meta's current official restatement of the text-in-image position**, and Meta account-restriction tiering.
10. **Creative-effectiveness research from Meta, Google, Kantar and Nielsen.** All four unreachable. Do not ship any "first 3 seconds" or logo-timing threshold without a fresh pass.
11. **Material 3 type scale tokens** (image/JS-rendered), **APCA Lc lookup table**, **Reddit video specs**, **Snap file size and safe zones**, **LinkedIn document ads**, **CTV platform specs** for Roku, Samsung Ads and Hulu/Disney, and **OAAA/DPAA legibility documentation**.

A follow-up pass needs either a fresh WebSearch budget or a rendering browser, since the common failure mode was JS-gated help portals rather than missing information.

---

# Product notes for the pre-flight feature

Three things fell out of this research that should shape the design:

**The highest-value checks are not the ones people expect.** Aspect ratio and file size are table stakes that every DAM already handles. The checks with real leverage are: (a) focal point / face survival across derived aspect ratios, since one-master-to-five-ratios is the dominant production pattern and center-crop silently decapitates people; (b) safe zone intrusion on 9:16, where Meta's own pages currently disagree with each other; (c) claims-language scanning against Amazon's list and Reg Z trigger terms, which are unusually literal and regex-shaped; and (d) rendered-text measurement rather than character counting, because Meta truncation is line-based and every localized string expands.

**Several famous rules are wrong.** Meta's 20% text rule has been unenforced since 2020. Meta permits before-and-after imagery for cosmetics at 18+; what it bans is pinching fat and close-ups on body areas. Google has no numeric text-overlay cap. Google's Ad Strength does not correlate with performance in the largest independent study. A tool that enforces the folk version of these rules will be wrong in ways practitioners notice immediately.

**Be explicit about what is a blocker versus a warning.** The research divides cleanly into hard gates (dimensions, file size, duration, character maximums, DSHEA disclaimer presence, Reg Z trigger-term completion) and soft signals (text density, Ad Strength, line length, hierarchy heuristics). Mixing them destroys trust. Worth also surfacing source and confidence per rule in the UI, since a meaningful fraction of this library rests on practitioner consensus rather than a citable page, and users in regulated verticals will need to know which is which.

# Research dossier: creative assistance for ad creatives at scale

Evidence base for `02_Solution_Thesis_and_Journey.md`.
Raw agent reports preserved in `research-raw/`. Proposed data schemas in `sample-data/`.

**How to read the labels.** Quoted text is verbatim from the cited source. `[unverified]` means a vendor or third-party claim I could not independently confirm. `[synthesis]` means my own inference, not in any source. Where I could not verify something, it says so rather than being quietly smoothed over.

---

## Part 1. What Typeface actually is and has

Sourced from typeface.ai directly and from a full product walkthrough recording (3m31s, brand used throughout is a hypothetical CPG called "Ziv Sparkling Water").

### 1.1 The architecture

Four named components: **Arc Graph, Arc Fabric, Arc Agents, Arc Loop.**

**Arc Graph** is described as *"a dynamic system that learns and remembers everything about your brand"* and summarised elsewhere as *"Your brand guidelines, audiences, assets, and campaign learnings, held as structured intelligence agents can act on and enforce."*

Five layers:
| Layer | What it holds, verbatim |
|---|---|
| Brand Graph | "guidelines, approved assets, audience data, and performance signals" as "a single, continuously updated source of truth" |
| Knowledge Graph | "products, campaigns, objectives, channels, and frameworks that give Arc Graph the context to think like a marketer inside your organization" |
| Audience Data | "Segments, personas, and behaviour are directly taken from your connected data" |
| Asset Management | "approved brand assets... connected to the guidelines and permissions that govern their use" |
| Design System | "logo usage, color palette, typography, and imagery style, pulled from your brand book" |

A flag-and-suggest primitive already exists conceptually: when content deviates, the system *"flags the issue and suggests a correction, so the fix happens in the flow of work rather than in a separate review cycle."*

**Arc Loop** is the post-launch feedback loop: it *"brings real campaign performance back into Typeface,"* *"writes what it learned into your next brief,"* and *"Published learnings flow into Arc Graph as structured, reusable knowledge."*

**Arc Agents** named: Ad, Email, Web, Creative, Image, Ideation, Video, Localization. The Localization Agent *"translates ad copy and creatives for global markets while maintaining brand safety."*

### 1.2 What the Brand Hub actually contains

The header chips summarise the entire kit for the demo brand: **6 colors, 7 fonts, 5 logos, 3 image styles, 15 guidelines, 2 terms to avoid.**

Structure observed:
- **Copy Guidelines:** Brand Voice, Brand Messaging, Style and Formatting, Terms to Avoid
- **Design System:** Color palettes, Fonts, Logos, Image styles, Components, Channels and sizes
- **UI Kits:** Ad layouts, Email layouts, Web layouts, HTML layouts, Email modules, Web modules, Push notification layouts, Messaging layouts
- **Campaign Channels:** add a channel by defining a size, used for file resizing

Guidelines are numbered natural-language rules, each carrying a **scope tag** of `global` or `ads / Social Ads`. Actual examples:
- "Write in a casual, first-person or second-person tone in all brand communications." (global)
- "Use short, punchy sentences for impact in all written content." (global)
- "Begin with an action or imperative phrase where possible." (ads / Social Ads)
- "Ensure local translations of social media content capture the spirit of the brand, not just the words." (global)

Colour is genuinely structured (swatch, name, hex, six entries). **Terms to Avoid contains exactly two entries: "diet" and "guaranteed."**

### 1.3 The most revealing moment in the recording

The marketer asks in chat: *"what are the primary fonts and colors of the brand?"* After **"Thought for 31 seconds"**, the assistant returns the colour table, then says:

> "Your brand kit has a **Font** entry under Typography, but it's stored only as uploaded font asset files. The design guidelines don't record a named typeface or any usage rules (e.g. which font is for headings vs. body). So I can confirm a primary brand font is defined via those assets, but I can't give you its name from the guidelines as they stand. If you'd like, you can add the font's name and usage rules to the brand kit so it shows up here going forward."

**The brand kit is asset-rich and rule-poor.** Seven fonts uploaded, not one named, none with a role. Fifteen guidelines and two banned terms for an entire CPG brand. The assistant is admirably honest about the gap and then pushes the authoring burden back to the user, which is the one thing a marketer under deadline will not do.

Guidelines are also prose rather than constraints. "Use short, punchy sentences" cannot be checked. "Body copy is Inter 400, minimum 24px on mobile feed" can.

`[synthesis]` There is a live contradiction sitting in the demo data right now. The Feel-Good Parent persona carries the message *"Ziv brings real fruit refreshment with zero guilt,"* while Brand Messaging says *"Make health benefits feel exciting and not clinical"* and Terms to Avoid bans *"diet."* "Zero guilt" is the same diet-adjacent register. Nothing flags it, because personas and guidelines are never checked against each other.

### 1.4 Evaluation already exists in the product

This is the finding that reframed the whole exercise. Verbatim from in-product tooltips:

> "Typeface can use a **complex rubric** to generate marketing assets, by **encoding brand standards, messaging requirements, compliance rules, or performance criteria into a structured evaluation framework**."

> "Typeface can then **evaluate and score how each asset aligns with the rubric to ensure only compliant assets are generated**."

> "Typeface **integrates with marketing activation channels, DAMs, CDPs, ESPs, CMSs, and platforms, to seamlessly publish generated assets directly into each system**, enabling rapid multi-channel deployment without manual handoffs."

And demonstrated. The marketer typed a rubric into chat as free prose. The assistant returned:

> "**Rubric evaluation.** I measured cross-email distinctness using pairwise word-overlap (0.00 = no shared words = maximally distinct) plus a qualitative angle/structure check. **The rubric was met on iteration 1**, so I used 1 of the 3 allowed iterations."

Rendered as a table: **Rubric objective | Overlap score | Verdict**, with pass ticks.

A quality bar with a fabrication guard also exists: assets were *"held to the email quality bar (score + fact-fidelity audit) before saving,"* and one variant *"Scored 94/87 after a revision that removed an invented 'six flavors' count."*

**Agent Studio** is a node-based workflow builder whose tool palette includes **Content: Generate, Evaluate**. The `Evaluate` node is shipped.

### 1.5 Latency, observed

"Thought for" times recorded across the session: **31 seconds, 2m19s, 3m24s, 4m55s, 8m32s.**

`[synthesis]` This is a hard design constraint, not a performance footnote. A chat-driven, per-asset review of 64 variants is arithmetically impossible. Verdicts must be pre-computed and already on screen.

### 1.6 The four gaps

1. **Rule coverage.** Arc Graph holds brand-relative rules. Channel specs, retailer policies and legal rules were not found on the product pages. That is the objective, citable, auto-fixable class, and it is exactly the class a non-designer can act on with zero taste.
2. **Grain.** Flag-and-suggest operates on "every piece of content." At 64 variants that is 64 notifications for 6 underlying problems.
3. **Loop direction.** Arc Loop runs post-launch into the next brief. Nothing brings precedent to the ship decision on the creative in front of her.
4. **Evidence.** Typeface's stated philosophy is that *"brand governance happens in the background instead of a review queue."* Right for generation, wrong at the ship decision. The marketer **is** the review queue now, and background governance leaves her with no instrument and no record. Invisible governance produces exactly the anxiety the brief describes.

`[synthesis]` The V1 is therefore not "add a review queue back." It is: make the governance that already runs legible and citable at the one moment she has to decide, and leave her a record she can defend. That is consistent with their architecture rather than fighting it.

### 1.7 The company, briefly, and why it matters to the pitch

Founded 2022 in Delaware as **Cortex6, Inc.**, emerged from stealth 27 Feb 2023. Sole publicly named founder: **Abhay Parasnis**, former CPO and CTO of Adobe, still CEO as of Sept 2026. Funding: **$65M** (Feb 2023, Lightspeed lead, with GV, M12, Menlo) and a **$100M Series B at $1B post-money** (Jun 2023, **Salesforce Ventures** lead). **No round since June 2023.** No disclosed ARR or customer count, ever.

Three things worth knowing before quoting anything about them:

- **There is essentially no public user-review corpus.** Total confirmed public reviews: **one**, and it is 1 out of 5 stars. `[Correction worth propagating]` The widely-circulated "G2: 4.4/5 from 20 reviews" is almost certainly **a different product**, a macOS font manager also called Typeface (typefaceapp.com), whose G2 listing references an "extensive font library" and lists RightFont and Font Book as alternatives. Do not cite it.
- **No named customer has a quantified outcome attached.** There is no /customers or /case-studies page and never has been. All eight customer stories are anonymised ("Fortune 100 Financial Services"). The same 93% CTR figure appears attributed to a "Fortune 500 telecom," a "media conglomerate" and a "Fortune 100 telecom" on different pages.
- **Contraction signals since mid-2026:** open roles down roughly 45% (29 to 16), headcount peaked and turned down, Sydney office delisted, and Tracxn marks the company at **$600M against the $1B 2023 post-money** `[third-party estimate, not a priced round]`.

**The one real review is worth reading in full, because it is about exactly this problem.** A Brand Manager at a 10,000-19,999 employee company, weekly user for 6-12 months, July 2025, 1/5 on design, ease, features and support:

> "Despite claims of brand training capabilities, **we were unable to generate content that reflected our brand voice.**"
> "found it unusable, **especially when compared to ChatGPT/Claude**."

`[synthesis]` Hold that next to the schema limits in 1.8. **The brand-voice complaint and the 10-rule cap are plausibly the same fact.** If the data model can only hold five values, five tones and ten find-and-replace rules, then "we could not get it to sound like us" is not a model quality problem. It is a capacity problem in the context layer. That is a much better problem to have, because it is fixable by design rather than by waiting for better models.

### 1.8 The Brand Kit schema, and the ceiling nobody talks about

From the public API reference, which is more credible than any marketing page:

```
Brand Kit style type enum: Text, Image, Palette
Text style subType: BrandVoice
  brandValues: [{name, description}]
  brandTones:  [{name, description}]
  brandRules:  [{type: "termsToAvoid", value: [{source, replacement}]}]
```

**Hard constraints, verbatim from the docs:** *"Only 1 text style and logo style could be created for each Brand Kit."* And from Typeface Academy: *"Get started with adding up to 5 Values, 5 Tones, and 10 Rules."*

Read that `brandRules` shape carefully. The only rule type is `termsToAvoid`, expressed as source-and-replacement pairs. **That is find-and-replace, not constraints.** There is nowhere in this schema to put "body copy is minimum 24px on mobile feed," "logo clear space is 1x cap height," "halo-cream on halo-citrus fails contrast," or "this claim requires a disclaimer in-creative in the US."

The **Audience** schema is similarly thin: `name`, `ageRangeMin`, `ageRangeMax`, `gender` (Male / Female / Neutral), `preferences` (free strings), `spendingBehavior` (enum). **No market, no locale, no channel habit, and no record of what has worked for this audience before.** A sample from the docs is `"name": "Adults in Chicago"`.

`[synthesis]` This is the most actionable finding in the entire dossier. The demo brand's "15 guidelines, 2 terms to avoid" was not a lazy demo setup. **It was close to the schema ceiling.** Any pre-flight product has to extend the context model before it can extend the checks, and that work is not glamorous but it is the foundation. It also raises the value of Arc Graph for every other agent on the platform, which makes it easier to fund.

### 1.9 What already exists that I initially missed

Three capabilities that change what V1 has to build versus surface:

- **Brand Linting.** Verbatim: *"Validates the extracted rules themselves, flagging schema violations, duplicate rules, contradictions, broken cross-references, and boundary conditions before they can produce the wrong content."* This is QA **on the guidelines**, not on the output. I found no direct competitor claiming it. It does not appear to extend to cross-object contradictions (the persona-says-"zero guilt" versus terms-avoid-"diet" case in 1.3), which is a small, cheap extension.
- **Visual Brand Evaluator**, shipped May 2026: *"evaluates images against guidelines."* This materially softens my biggest open question. The primitive may already see pixels.
- **Citation at generation time already exists.** Verbatim: *"Brand Graph scans every draft in real time. Banned terms are blocked outright... **When a rule fires, Brand Graph names which rule and why.**"* So "cite, do not assert" is not a new principle I am introducing. It is an existing behaviour that stops at generation and never reaches the ship decision. **Building on it is a much easier internal sell than proposing it.**

Also confirmed, and it changes scope:

- **Arc Spaces has genuine approval workflow**, not just marketing copy. Confirmed API objects: `getWorkflows`, `getWorkflowSteps`, `getDocumentAssignees`, `updateDocumentWorkflowStatus`. Their published governance model is graduated by risk: low risk single approval 2-4 hours, medium risk marketing plus compliance 1-2 days, high risk legal and executive 3-7 days. **So the Ship Report should plug into this, not replace it.**
- **Arc Loop specifics.** Channels: **Email, Social Ads, Search Ads.** Named sources: Google Ads, Salesforce Marketing Cloud, HubSpot, BigQuery, Salesforce Data Cloud. Metrics: opens, clicks, CTR, open rate, conversions. Two modes: upload a performance export, or connect the platform. Output is ranked, explainable variants requiring **human approval**. `[Note: Meta is not in the named source list, and no retail media source appears anywhere.]`
- **Pre-flight performance scoring is confirmed absent.** Arc Loop is explicitly retrospective. The only forward-looking rubric found anywhere in the product is the AEO Analyzer's 25-point structural rubric.
- **No numeric brand-compliance score, confidence value or severity ranking exists.** The product does binary blocking plus flagging with explanations. `[synthesis]` My three-tier severity model is therefore genuinely additive rather than a reskin.

**Two documented limits that bear directly on a batch product**, from Typeface's own docs: *"Collection Loops iterate over at most the first 100 assets"* and **activity logs are retained for only 7 days** (*"Anything older is deleted automatically each day at 02:00 UTC"*). A batch of 64 fits inside the first limit with little headroom. The second means a Ship Report needs its own durable store, because the platform's own audit trail evaporates in a week.

### 1.10 The hiring signal

Typeface's Greenhouse board as of 23 Sept 2026 carries a live **Senior Product Manager, Ads** role in Palo Alto, $165,000-$210,000 base, requiring 5+ years in ads or marketing tech and explicitly **"ad platform and programmatic advertising experience."** It mentions removing **partnership** blockers and finding gaps in **ad automation**. `[Notable absence: no retail media, no Amazon Ads, no DSP language anywhere in the posting.]`

Three adjacent roles point the same direction:
- **Staff PM, Design and Intelligence** ($170-230k): build an *"AI-native, multi-modal content design engine"* that **comprehends brand guidelines and design systems**, and create *"AI-native end-to-end and closed-loop content workflows."*
- **Senior PM** ($180-210k): *"Balance shipping velocity against **accuracy, latency, and cost** trade-offs."*
- **Principal ML Engineer** ($230-260k): *"evaluation, safety, and reliability frameworks at scale."*
- **Staff PM** ($200-230k): a company *"defining a new category"*, shaping *"AI system development, **evaluation**, and improvement processes."*

`[synthesis]` Evaluation infrastructure, design-system comprehension, closed-loop workflows and an explicit latency-accuracy-cost tradeoff are all being staffed right now. A proposal built on the existing `Evaluate` primitive is aligned with where the company is already spending, not asking it to turn.


### 1.11 The integration reality, and the retail media hole

Confirmed from two independent directions, and it should change V1 scope.

**The ad integration set is Google-first plus Meta.** The Ad Agent page names **Campaign Manager 360, Google Ads and Meta Ads.** The Solutions Architect job posting names **Google Workspace, Salesforce, Adobe Experience Cloud and Campaign Manager 360.** Arc Loop's named data sources are Google Ads, Salesforce Marketing Cloud, HubSpot, BigQuery and Salesforce Data Cloud.

**No retail media network appears anywhere.** No Amazon Ads, no Walmart Connect, no Criteo, no DV360, on the site or in any of the 16 live job postings. There is no PM hired against Commerce, Retail Media or Video, despite a Video Agent shipping.

`[synthesis]` This matters for MVP discipline. Retail media is where creative spec pain is worst, where rejection is most expensive, and where my most vivid failure stories live. It is also where Typeface has no connector, no roadmap signal and no one hired. **Scoping V1 to Meta, Google Ads and CM360 is the honest call**, and naming retail media as the deliberate V2 wedge is more credible than pretending the plumbing exists.

**A tell worth carrying into any pilot.** Arc Loop's own copy offers that users can *"upload performance exports directly without any setup"* **or** *"connect your ad platforms and marketing data sources."* Leading with the manual CSV path suggests the automated connectors are still thin. Pair that with the two Reddit complaints about Salesforce Marketing Cloud integration requiring real developer work despite being pitched as plug-and-play, and the SourceForge line that *"claimed integrations are either minimal or entirely absent,"* and integration depth is the thing I would probe hardest.

### 1.12 Packaging, and a correction

**Confirmed tier names: Essentials / Teams / Enterprise.** Source is the Azure Marketplace catalog API, which returns machine-readable data where the HTML pages 403. Offer created Feb 2024, last modified Dec 2025. Term ladder: Essentials 2yr, Teams 1yr, Enterprise 1mo / 1yr / 3yr. Monthly billing only on Enterprise. `hasFreeTrials: false`, `hasFreePlans: false`.

All three plans list at $1 to $3 and carry an identical description stating that subscribing *"is not purchasing Typeface, you are requesting for more information."* These are token SKUs to make the offer transactable. Real transactions run as private offers at non-public values.

`[Correction, do not repeat]` A widely reproduced **"$49 to $99 per user per month"** figure should be **struck, not downgraded**. It traces to a page that cites no source and simultaneously states *"Public Pricing Page: no"* and lists *"No transparent public pricing page"* as a con. The plan names do not match the real tiers. Treat as fabricated. `typeface.ai/pricing` returns a genuine 404.

`[Unresolved]` The Azure offer says no free trial exists and `app.typeface.ai/signup` returns 404, yet the July 2025 reviewer says *"we signed up for a free trial via the website, our credit card was charged immediately."* Most likely a self-serve trial existed and was removed as the company went fully sales-led, but that is inference.

**A smallness signal worth knowing.** The Google Workspace Marketplace listing for Typeface was **last updated 23 October 2023 and shows 260 users.** Separately, Typeface has **zero presence across seven SaaS benchmarking platforms** (Vendr, Spendflo, Tropic, Sastrify, Cledara, Spendhound, NachoNacho), **no SAM.gov registration**, and **no public procurement record** in USAspending or NYC Checkbook. These are reliable negatives, searched via each vendor's own sitemap rather than blocked lookups.

`[synthesis]` None of this is disqualifying and none of it belongs in the exercise deliverable. It matters for one reason: **the gap between the logo bar and demonstrable deployed footprint is wide**, which makes a feature that produces a defensible, attributable outcome number more valuable to this company than another generation capability. That is an argument for this V1, not against it.


---

## Part 2. How marketers actually think and feel

Sourced from Reddit (r/PPC, r/FacebookAds, r/marketing, r/graphic_design, r/branding), LinkedIn, practitioner blogs, named industry surveys and trade press. Full report with URLs in `research-raw/marketer-voice.md`.

### 2.1 The volume trap

> "targeting is basically advantage+ deciding everything, bidding is automated, placements are automated. the only place i can actually still move the needle is how many creative angles i can put in front of the algo each week. feels like the whole game collapsed into a creative testing race."
> r/FacebookAds, Jul 2026

The shipping doctrine that follows from it, stated plainly by a practitioner: *"Creative volume > Creative perfection. 3 polished ads you 'hope' will work vs 30 good-enough ads you TEST to find winners."*

`[synthesis]` This matters for scoping. The bar is not "is this beautiful." It is **"is this good enough that it will not embarrass us."** Those are different checks, and the second is far more automatable. A product that tries to raise taste will be rejected. A product that prevents embarrassment will be adopted.

**Capacity, quantified.** Superside, n=206 enterprise creative and marketing leaders: **78%** say creative demand exceeds the team's capacity; **70%** say their most talented creatives spend time on tasks below their skill level; 86% say their team is at or over capacity. A follow-up found **92% of executives asking for higher quality work and 94% expecting it faster.** `[vendor-commissioned, real sample]`

### 2.2 The defect vocabulary

The single best quote in the corpus, from r/FacebookAds, Jul 2026:

> "when an ad is generated rather than built, **the brand usually comes out slightly wrong. colours that are near your palette but not actually it, or a logo that's been redrawn.** for software it's worse, half the time there's a **screenshot of a dashboard that doesn't exist in the product.** none of that registers as fake to someone scrolling, so the click still happens. then they land on the site and it doesn't look like the ad they clicked, and **that gap is where you lose them.**"

It names the failure class, explains why it survives review, and ties it to a revenue mechanism.

Other recurring defects in practitioners' own words: *"weird hand movements, products that warped mid-frame, uncanny valley smiles"*; *"the face drifting between clips. jawline or skin tone shifts slightly when two generations get stitched together. viewers cannot name it but they stop trusting the person"*; *"a hand has six fingers lol. One weird detail can make the buyer question everything else."*

And the governance gap, from r/branding, unprompted:

> "**most people don't have brand guidelines that are actually usable by an AI tool. They have a mood board and a color palette. That's not governance. Governance is: here's what we sound like, here's what we never sound like, here's how to check if something drifted.**"

That user then describes hand-building "40 rules that constrain generation during production, not after... **Mechanical stuff you can check before anything ships.**" `[synthesis]` Someone independently invented this product with no tooling. Strong demand signal.

### 2.3 The preview lies, and a customer catches it

The most product-relevant anecdote in the entire research set. r/FacebookAds, Jan 2026:

> "**A customer actually reached out to me to say my Instagram ad looked strangely cropped and blurred.** ... It's blurring edges, auto-cropping, and **cutting off text in some placements.** In Ads Manager my creative looks fine, but **in real Instagram placements the image is clearly altered.**"

Follow-up from the same person:

> "**I was so embarrassed when a potential customer sent me a screenshot of my ad. It was a total mess, with half of the text cut off, and the other half of the image was just blurred. Not only have I been losing money from this AI crap, but it's also affecting my reputation. It makes my business look so unprofessional.**"

Related, from another thread: *"I noticed performance drop since last week, turns out the images are getting stretched automatically which causes text to get chopped off. CTR has increased ten fold for some campaigns and conversions are almost next to 0."*

There is a **manual ritual** people describe performing on every publish: *"after i publish i wait until approved and then double check, sometimes these features flip back on."*

### 2.4 Approving is not reviewing

The top answer in a thread asking designers for their worst shipped mistake:

> "**Misspelled the name of the company, in 72 point headline type, on a full-page ad that ran in Newsweek magazine. The whole agency signed off on it, three people in the client company signed off on it. No one caught it and it went out the door. Who saw it first? The CEO.**"

More, each one a clean example of a machine-checkable defect that humans missed:
- **$14,000 Pantone error.** A brand style guide built from a previous client's template: *"I successfully swapped everything out except for one Pantone color number."* Bags printed in the wrong colour. The creative director approved it too. *"They did proceed to remind me and the entire team about my error at every Monday morning standup we had for 6 months until I eventually quit."*
- **5,000 brochures**, for a proofreading company, with a single inserted letter turning "ourselves" into a typo. *"CMYK + 2 spots, typeset to death, retouched to hell, and proofread to the hilt."*
- **15,000 copies with the wrong phone number.** *"There were 50 iterations, everything had to be checked by every single person in the client company including the janitor... Nobody proofread the fucking phone number on the back."* Two days of the entire company applying stickers.
- **The untested CTA.** *"no one thought to actually dial the phone number... for about a week, customers calling to order medical textbooks were routed to an adult phone chat line."*

And the counter-intuitive finding on process:

> "Small mistakes like this often happen because of over micro management. **People get burned out following too many instructions and more mistakes happen. People also start to rely on the micro-manager to catch mistakes because they're so involved anyway, surely someone else will catch the mistake.**"

Plus the most honest description of what sign-off often is:

> "i make sure it's at least 5 other people... **i refuse to take the blame, at least alone.** And the final review of information is done by the owner, and **he approves without actually looking at things.**"

`[synthesis]` Adding reviewers is defensive, not diagnostic. The industry's own published QA guidance agrees: limit final sign-off to one or two people because *"too many cooks can spoil the broth."* The safety net is deliberately thin. A machine layer is the only way to get both fewer reviewers and more coverage.

### 2.5 The emotional core

> "**10 years in marketing. I still get the sweats when I am about to hit send, even after the team has looked over the final (final) draft.**"
> Reply: "**I call it senders remorse. That feeling of dread when you hit go.**"

`[synthesis]` The felt benefit is not "saves time." It is the removal of dread. That should shape the copy and the ship gate, not just the roadmap.

### 2.6 The governance gap, quantified

**IAB in partnership with Aymara**, survey of 125 US advertising executives at companies with 50+ employees, fielded July 2024, published Aug 2025. The single most on-point dataset found:

- **"Over 70% of marketers have encountered an AI-related incident in their advertising efforts, including hallucinations, bias, or off-brand content, yet less than 35% plan to increase investment in AI governance or brand integrity oversight."**
- Consequences: **"40% had to pause or pull ads, over a third dealt with brand damage or PR issues, and nearly 30% had to conduct internal audits."** Only 6% said the impact was minimal.
- **"Nearly 90% say they feel prepared to catch AI issues before launch."** IAB's own read: *"given that 70% have already had incidents, it also suggests a false sense of security."*
- **"Only 6% believe current safeguards are enough."**
- **"14% say no one owns AI governance."**
- Asked whether they would consider a third-party solution to evaluate hallucinations, bias or off-brand content: **"over 90% said yes."** Stated motives: *"peace of mind"* and *"reduce risk to our brand and business."*

`[synthesis]` The 90%-feel-prepared against 70%-already-incident gap is the most quotable tension in the whole dossier. It is a named-source version of "approving is not reviewing."

### 2.7 Flag or fix: what they actually want

The clearest statement, unprompted, from 2023, about Google's auto-generated assets:

> "**What would be nicer is the same feature but given as recommendations that you can alter. Not pure AI but more computer assisted help.**"

The pattern across every auto-enhancement thread: practitioners are **not** hostile to AI assistance in principle. They are hostile to **AI changes applied without consent, silently, after approval, and invisibly in the preview.**

> "They apply almost all their AI bullshit to my ads after opting out at the account level and campaign level."
> "By default meta has turned on letting them experiment with AI that will always override your ad settings."
> "Go into ad account's advertising settings and uncheck the 'Test new enhancements' box. **It allows Meta to serve ads with the tools enabled without you knowing.**"

**Academic grounding.** Dietvorst, Simmons and Massey (2015), *Algorithm Aversion*, Journal of Experimental Psychology: General: people lose confidence in algorithmic forecasters faster than in human forecasters after observing **the same magnitude of error**, and will choose an inferior human as a result.
Follow-up work: **algorithm aversion is reduced when people can modify the algorithm's output, even slightly.**

Two direct product consequences:
1. **False positives cost more than false negatives.** Precision over recall, and make every flag inspectable so the user can verify rather than believe.
2. **Let the user adjust the fix before accepting it.** The adjustability is the trust mechanism, not a convenience.

A useful counter-citation to have ready: MIT Center for Collective Intelligence found that on average, AI-human combinations do not outperform the best of either alone. `[synthesis]` The escape hatch is that the meta-analysis concerns *joint decision quality*, not *mechanical verification offload*, which is the task class here.

### 2.8 Marketer and designer

Designers describe a reputational asymmetry: *"They think their design is better so they post it on the company's linkedin... I get ashamed because I think everyone thought I made those horrible designs when my designs just get ignored. I have been called snippy for voicing my opinion."*

From the designer side of the production chain: *"As the last in the chain of a creative product, designers usually have to rely on the content that's given to us... we have the tightest deadlines because the schedule won't move for us... it's not our job to proofread content."*

Why teams route around agencies (Superside): **51% of leaders have lost faith in traditional agencies; only 13% say the partnership works well; 37% say agencies move too slowly, 34% cite quality, 31% say briefing the agency takes longer than briefing the internal team.**

`[Evidence gap, stated honestly]` I could not find clean public quotes of a marketer saying "I did not want to bother the designer again." The mechanism is well supported indirectly but under-quoted, almost certainly because admitting you skipped a review is admitting negligence. **This one should come from customer interviews, not public sources.**

### 2.9 Named public incidents worth citing

- **Google, Super Bowl LIX (Feb 2025).** A Gemini ad contained a hallucinated statistic about Gouda cheese consumption. Google quietly re-edited the YouTube version before the game after users flagged it. `[synthesis]` A factual error in creative, caught by the public rather than internal review, on the most expensive media buy of the year.
- **Coca-Cola "Holidays Are Coming," 2025 AI remake.** Business Insider: *"the famous Coca-Cola trucks appear to change shape as they roll through the festive village. The trucks also appear to gain or lose wheels in each scene."* Production scale: *"just five AI specialists refined 70,000 video clips to create the ad in 30 days."* An independent specialist called the issues *"inexcusable."* Coca-Cola's global VP for generative AI: *"There will be people who criticize, we cannot keep everyone 100% happy."* Measurement split: System1 gave it 5.9 stars; DAIVID found it more likely to evoke distrust than industry norms. `[synthesis]` The definitive case: object inconsistency across shots and brand asset geometry are exactly the class a machine catches and a human reviewing 70,000 clips cannot.
- **McDonald's** pulled an AI-generated Christmas ad, Dec 2025. Guardian quoted a consumer: *"Ruined my Christmas spirit."*
- **Converse**, Sep 2026, pulled an ad after users said the lighting created a silhouette resembling a KKK hood. `[synthesis]` Worth naming as the limit case: unintended silhouettes and negative space are a defect class nobody has a checklist for, and we should not imply we can catch them.
- **Distorted logo from an agency**, r/graphic_design, 604 upvotes: *"they posted an ai generated image instead of a video and the company logo looks distorted and there are all kinds of weird visual inconsistencies with the image. it immediately reads as AI."*

### 2.10 Consumer-side risk, measured

- **DAIVID** evaluated 21 fully or partly AI-generated ads from Volvo, Microsoft, Puma and others: **3% less likely to generate intense positive emotions and 12% more likely to generate feelings of distrust** than industry norms.
- **NielsenIQ's** global ad effectiveness practice lead: *"Brains have a prototype or a blueprint for everything we experience. **If there's something slightly different in that blueprint, it sends a signal to us that something's just off.**"* Most sensitive areas: human faces, human motion, human connection.
- **Pew, Sep 2025:** only **12%** of Americans are confident they can tell AI from human content, while 50% are more concerned than excited about AI in daily life.

`[synthesis]` *"Something's just off"* is the consumer-side name for the same defect class the product catches. The artifact is small; the trust penalty is not.

### 2.11 Retail media

`[Evidence gap]` This was the weakest area. Public practitioner discussion of retail media is overwhelmingly about bids, ACOS and keywords, not creative specs. What is confirmed:
- *"the lack of standardization across retailers (ad formats, how to buy)"* and *"every retailer speaks a different language."*
- IAB is producing **Retail Media Standards and Flexi Ad Sizes Guidelines** aimed at easing *"creative production, and operational strain."* Worth chasing at iab.com as the most citable acknowledgment that the problem is named.
- **A direct competitor is already positioned on exactly this.** Cape.io, profiled in IAB UK's AI in Ad Tech Ecosystem, sells **"Zero Platform Rejections: Ensures creative assets meet the completely divergent specifications of Linear TV, CTV, and social media from a single upload point, virtually eliminating failed uploads and missed SLAs due to creative."** They maintain *"a Global Spec Database: thousands of living technical specifications for every broadcaster, streamer, and social platform globally."*
- Both Amazon and Walmart Connect are moving into creative generation themselves. `[synthesis]` A threat, and also a tailwind: more machine-generated retail media creative means more defects, and brands will not trust the retailer to grade its own homework.

### 2.12 The REI case, and why checking the master file is not enough

**This is the strongest single story in the dossier, and I verified both quotes directly rather than relying on the research pass.**

In June 2026, REI ran an Instagram ad for a Van Rysel bicycle. The image was a legitimate, vendor-supplied product photograph. Meta's **Dynamic Media** system silently regenerated it. The shipped ad contained a second pair of handlebars growing out of the saddle, illegible text on the frame, a missing crank arm, and disc brakes mounted on the wrong side of the wheel. Reddit users catalogued at least ten structural impossibilities.

It ran for roughly a week, **15 to 22 June 2026**. It was caught by Reddit and Instagram users and then the cycling press, not by REI.

REI's statement, 22 June 2026:
> "**Meta auto-enrolled us in an AI personalization tool that produced an inaccurate and inappropriate alteration of a vendor-provided image in some of our ads.**"

Meta's spokesperson, via MediaPost:
> "**AI can make mistakes and it is the advertiser's responsibility to review the AI outputs.**"

Dynamic Media became the default for Advantage+ Catalog ads on **1 September 2025**, with full enforcement by **20 October 2025**, adapting product images across 25 placements.

`[synthesis]` Three things follow, and the third changes V1 scope.

1. **The approved master was fine.** Every defect was introduced after approval, by the platform, in delivery. A product that checks only the file the marketer approved would have passed this ad cleanly.
2. **The accountability gap is explicit and unresolved.** Meta auto-enrols the advertiser, alters the creative, does not surface the variants, and states on the record that reviewing the output is the advertiser's job. There is no surface on which to discharge that responsibility. **That gap is a product.**
3. **Scope consequence: check the served creative, not just the master.** This is the enterprise-scale version of the r/FacebookAds anecdote in 2.3 where the in-tool preview looked fine and a customer sent a screenshot of the real thing. AdExchanger's summary of the Business Insider reporting adds a further class: silent alterations to real product imagery that are *"less visible to consumers but serious for brand reputation."* Checking the approved file is necessary and insufficient.

`[Evidence note]` A Business Insider piece, "Meta's AI advertising dreams have become a nightmare for brands" (13 July 2026), is based on eight named advertiser and agency-executive sources and is paywalled. It is probably the densest single source for this thesis and is worth reading with a subscription.

### 2.13 Other incidents worth having in the back pocket

`[Reliability caveat]` I verified the REI quotes above myself. The items below came from a research pass that was blocked from Reddit, X and LinkedIn and used automated page extraction. Treat them as **lead-quality** and re-verify against the URL before any of them goes in a deck.

- **Ram (Stellantis), June 2026.** A $29.95 "Ram Patriotic T-shirt" whose AI artwork depicted a **2016-2023 Toyota Tacoma**, identified by grille, headlights, rear-window kink and mirror trim. The flag carried roughly 35 stars instead of 50 and 11 to 12 stripes instead of 13. Pulled same day. CarBuzz: *"Ram hasn't ever built a pickup truck like that. But Toyota did, from 2016 through 2023."* `[synthesis]` The cleanest case in the whole set for the product, because **every single defect is machine-checkable**: a competitor's product in your own creative, and a miscounted national symbol.
- **Tourism Malaysia, June 2026.** An AI promo video with the national flag rendered **mirrored**. Deleted 48 hours later, no statement. The Malaysian actor Harith Iskander: *"What concerns me most is not that maybe this was a cost-saving measure. It's scary because the decision makers sat around, looked at this AI ad and said to themselves, 'That's good enough.'"* `[synthesis]` Arguably the best line in the dossier for the question of how anyone decides something is ready to ship. A room full of people looked at a mirrored national flag and said yes.
- **Skechers in Vogue print, Dec 2024.** Warped faces, physically impossible clothing, illegible background text. **It cleared every gate and went to print.** Caught by a TikTok user. A commenter identifying as an ad industry worker: *"As someone in advertising, it's getting bad. literally have fights explaining how bad AI is and everyone just wants the cheapest/quickest option."* Repeated April 2026 on New York subway placements, with an inconsistent logo across executions.
- **Equinox, Jan to Jul 2026.** Flagged within weeks by Asian American communities, publicly disputed by the brand (who accused the critic of manufacturing outrage "for clicks"), image removed and apology issued in July. `[synthesis]` **Six months of detection-to-remediation latency**, which is a usable number when arguing for pre-flight.
- **Coors Light, Jan 2025.** "Refershment" on national out-of-home including Toronto's most prominent billboards. The brand leaned in and temporarily rebranded as "Mondays Light," carrying it into the Super Bowl LIX campaign. The recovery-playbook case rather than the failure case.
- **Amazon Marketplace, Jan 2024.** Live listing titles that were raw LLM refusals: a dresser titled *"I'm sorry but I cannot fulfill this request it goes against OpenAI use policy"*, and chairs with unfilled template slots reading *"can be used for a variety of tasks, such [task 1], [task 2], and [task 3]."* Amazon now requires sellers to label AI-generated people in listing images, in response to a New York law.
- **Nintendo "My Mario," Jan 2026. A false positive, and it matters.** Fans accused Nintendo of using AI based on "uncanny smiles" and "reality-bending thumb angles." Nintendo: *"AI has not been used in any of the My Mario promotional images."* One of the actual human models posted: *"I can promise you this is not AI guys."* `[synthesis]` **Reputational risk now exists even when you did not use AI.** Brands are starting to need to prove a negative. That argues for provenance and attestation as a second surface, which is a different feature from defect detection and worth flagging as a V2 candidate rather than quietly folding into V1.

### 2.14 More defect vocabulary, from a different practitioner population

`[Same lead-quality caveat.]` Hacker News partly fills the Reddit gap with a different population:

- *"I've been seeing Reddit ads with clearly AI generated marketing images and it just makes me assume the company is an unserious fly-by-night operation."*
- *"Any serious company would manage their brand seriously... Using AI generated images says to me that you take shortcuts."*
- *"The generations are so basic that they make the brand look cheaper."*
- On AI typography specifically: the **"softness" and "inconsistency" of AI lettering, where the same letter shape varies slightly across a word.** `[synthesis]` A precise, checkable signature for garbled text-in-image.
- *"you could tell it was AI by the way it reset it's face to the same position every sentence... 'Lady walking with smile', slap the brand assets on it, hide the AI hands, done."*
- **A useful nuance:** *"There is a big difference between using AI generated food pictures versus taking real pictures and using AI to create a menu design."* Practitioners distinguish generated **content** from AI-assisted **layout**, and are far more tolerant of the latter.
- **A strong product signal:** AI output lacks editability in professional software like InDesign, so clients cannot get modifications made. Generated output is not a working file.

### 2.15 Trust and control, in the industry's own words

`[Same lead-quality caveat.]`

- Tom Goodwin, marketing consultant: *"Meta making ads with AI (with no human in the loop) is about the dumbest thing you could ever do in advertising."* He calls the output **"average-vertising,"** advertising that *"kind of works and no-one is going to get fired,"* made with *"no pride and no craft,"* and warns of **"brand damage at scale."**
- An agency, Jan 2025: *"What kind of brand guardian is going to just wave away control of messaging and imagery for convenience sake?"*
- Anonymous agency executives, originally via The Verge: **"no clients will trust what they spit out as they are basically checking their own homework."** `[synthesis]` This is the articulated reason brands will not accept a retailer or platform grading its own creative output. Amazon and Walmart Connect are both moving into creative generation. That sentence is the opening in retail media.
- Crissi Cupak, Head of Product at PMG, on the Coca-Cola ad: *"Visual glitches and mismatched styles disrupted the experience and signaled a lack of control."* Her closing line is the best pull-quote in the dossier: **"Consumers aren't rejecting AI. They're rejecting indifference."**
- An ads consultant living with the Meta glitches: *"Meta's still the best platform. It has the best data."* `[synthesis]` The stickiness quote. Brands complain and stay. This product sells into that resignation, not against it.

`[Corrections, so nobody repeats them]`
- **Drop the "Coca-Cola sixth finger" framing.** No credible sourcing. The documented 2024 defects are gliding truck wheels that do not rotate, scale errors on AI people and warped faces; the 2025 defects are trucks changing appearance shot to shot and a fireplace with no chimney opening.
- **No evidence** was found for a "Bon Appetit / Kraft AI images" incident. Do not cite it.
- **The Google Gemini Gouda case has a wrinkle.** Google's President of Cloud Applications argued the output was *"grounded in the Web"* and *"not a hallucination,"* because the identical claim appeared on the featured business's own website as early as 2020, and the correction was reportedly prompted by that business owner rather than by Google's review. `[synthesis]` That makes it a **sourcing and fact-check failure rather than a pure hallucination**, which is arguably the more relevant failure mode for creative QA and a better story for us, not a worse one.


---

## Part 3. The competitive picture

Full report with URLs in `research-raw/competitive-landscape.md`.

### 3.1 Nobody holds more than two of the four pieces

A ship-ready verdict requires four things. No vendor has more than two.

| Capability | Who does it | Who does not |
|---|---|---|
| Brand / spec / accessibility check before launch | Adobe GenStudio Brand Check, CreativeX, Vidmob, Veeva and Red Oak in regulated verticals | Canva, Creatopy, Arcads, Creatify, Foreplay, all platform-native tools |
| Predicted performance of an unlaunched variant | AdCreative.ai, Pencil Pro, Atria, Dragonfly, Neurons, Kantar LINK AI, System1 | Adobe, Frontify, Bynder, Ziflow, Motion, Smartly, all platform-native |
| Multi-stakeholder approval workflow | Adobe GenStudio, Ziflow, Filestage, Lytho, Smartly, Bynder | AdCreative.ai, Atria, Arcads, Creatify, Neurons |
| Non-designer UX at a price a mid-market team pays | AdCreative.ai, Atria, Canva, Creatify, Foreplay | Adobe, CreativeX, Vidmob, Kantar, Superside, Pencil |

### 3.2 The closest competitor, and its ceiling

**Adobe GenStudio for Performance Marketing** is the strongest existing pre-ship gate. Brand Check inspects generated content against three rule sets: uploaded brand guidelines (voice, tone, channel rules), platform guidelines (Meta, LinkedIn specs and policy), and accessibility (alt text, contrast, reading level, jargon). It produces a **Brand Score as a percentage = guidelines passed / guidelines tested**, plus pass/fail on platform and accessibility. Scores auto-update on edit. Multi-stage approval routes through creative, legal and marketing ops.

`[synthesis]` Its ceiling is the score itself. Guidelines-passed-over-guidelines-tested averages a legal blocker with a nice-to-have, and it answers "is this on-brand and legal," never "is this any good" or "which of these 40 should I run." It will happily pass a compliant but broken AI variant. It is also enterprise-only and requires Adobe stack commitment.

### 3.3 The five failure modes across the whole market

1. **Compliance without judgement.** Adobe, CreativeX, Frontify, Bynder, Ziflow, Filestage all answer "does this violate a rule someone wrote down." **No vendor found in this research detects genAI craft defects.** This is the cleanest unowned problem.
2. **Prediction without governance.** AdCreative.ai, Atria, Pencil, Neurons, Dragonfly predict something about performance and check no brand, legal or spec rule.
3. **Post-hoc masquerading as pre-flight.** Motion, Foreplay Lens, Canva Grow insights, Meta diagnostics, TikTok Smart+ rankings all require spend first. Marketers routinely buy these believing they solve the pre-ship problem. **They cannot, by construction.**
4. **Rules without perception.** CreativeX counts best practices. Vidmob's scoring function is PASS/FAIL against guidelines. Both are checklists. The genAI era broke the assumption that compliant equals correct.
5. **Human judgement priced out of reach.** Superside starts at $15,000/month; Kantar, System1 and Swayable are panel studies with multi-day turnarounds. **Generation cost fell roughly 100x. Review cost did not move.**

### 3.4 The two scores everyone cites do not do what buyers think

- **Google Ad Strength.** Google's own documentation states it does not determine serving eligibility and **is not used in Ad Rank, Quality Score, or auction wins.** It is a completeness checklist computed from asset-keyword relevance and combinatorial diversity. Independent critiques note it penalises pinning, which is how regulated industries lock mandated copy.
- **Meta Ad Relevance Diagnostics.** Three rankings requiring roughly **500 impressions** to populate, driven by negative user feedback rather than brand fit or design quality. By construction they cannot inform a pre-ship decision.

`[synthesis]` The market lacks clear vocabulary for **before spend** versus **after spend**. That confusion is itself a positioning opportunity.

### 3.5 The seat is being vacated

The two companies with the best scoring technology are both leaving the end-user surface.
- **Vidmob** is the only vendor found with a documented hard block: a Creative Scoring API wired into ad-server QA so that *"any asset scoring below a mandatory threshold is automatically flagged or blocked from deployment."* But in April 2025 its president reframed Vidmob's creative data as *"a good input into AI agents,"* repositioning as a data supplier to other people's creative AI tools. Funding history supports the pivot reading: $110M Series D in 2021, then an $8M round in 2025.
- **CreativeX** owns the word "pre-flight" and the most credible published correlations (from a study of 1M+ ads: a 10% CQS increase associates with 4.7% lower CPM, 4.6% higher ad recall, 17.4% lower CPCV). But its Creative Quality Score is a **platform-best-practice checklist**, it is Fortune-500 priced, and its reporting posture is retrospective dashboards for governance leadership.

**Neither is sitting in front of the person about to click publish.**

### 3.6 The analogy is proven, and absent here

- **Print preflight** is a mature 25-year-old category: Adobe Acrobat Preflight, Enfocus PitStop, callas pdfToolbox. Deterministic checks with fix-ups. Every commercial printer runs one.
- **Broadcast has automated QC**: Telestream Vidchecker, Venera, Interra Baton.
- **Software has linters, spell-checkers and CI.**
- **Digital advertising has no equivalent.** The nearest things check trafficking specs at delivery, not creative content.
- The one true "linter for marketing" got acquired and absorbed: **Red Marker into IntelligenceBank, July 2024.** `[synthesis]` The strongest single signal that the category is real, small, and currently unowned.

### 3.7 Analyst framing

**Forrester, "Ad Creative Is A Technology Problem And Opportunity," Nikhil Lai, 2 June 2026.** Close to a thesis statement for this exercise:
- **"Creative quality is the greatest determinant of media's performance, outweighing ads' targeting or placement."**
- Three trends: productivity to performance, fragmentation to integration, assets to systems.
- **Vendors named in the specialist set: AdCreative.ai, ad-machina, Pencil, Pixis, and Typeface.**

**Notable absence:** there is **no Forrester Wave or Gartner Magic Quadrant for creative automation, creative QA, or genAI ad creative production.** The category has no square to be a leader in. `[synthesis]` A go-to-market problem and a confirmation that the category is pre-consolidation.

**Forrester / 4As, June 2026:** nine in ten US agencies use generative AI; barriers to scaling are **63% accuracy and bias concerns, 62% legal concerns**. Forrester's own framing is that the industry's productivity focus *"is undermining marketing effectiveness and creativity."* `[Sample size and methodology not publicly disclosed.]`

### 3.8 Sizing, stated conservatively

`[Caution]` Named-firm creative-automation market sizing could not be verified. The reports that surfaced were report-mill quality. What is defensible:

- **Global ad market: roughly US$1.19 trillion**, growth upgraded to +8.9% (WARC, Dec 2025). The denominator.
- **Adobe**, n=2,841 marketing professionals across 7 markets, Feb-Mar 2024: nearly two-thirds expect content demand to grow **at least 5x**. `[vendor-sponsored but methodologically disclosed]`
- **The best waste proxy**, from CreativeX: average Fortune 500 brands operate at **20-30% Creative Quality Score**, with roughly **70% of digital budget behind low-quality content**, and *"more than 50% of media budgets are spent on ads that aren't fit-for-platform."* `[vendor-published, not independently audited]`
- **Nielsen Catalina Solutions, 2017**, roughly 500 CPG campaigns: creative accounts for **47%** of a campaign's effectiveness (media planning and buying 36%, brand factors 15%). **For digital specifically, creative accounts for 56% of sales lift.** `[Cite with the date and sample. The 2017 vintage is now a liability and predates algorithmic creative selection. Avoid the free-floating "creative drives 70-80%" variants, which are misreadings of Nielsen's conditional figure.]`

**Stats to avoid without verification:** "IAB Tech Lab says nearly 1 in 3 display ads contain serious quality issues" traces only to a single vendor blog and is probably a zombie stat. The April 2026 CMO Survey AI-usage figures were retrieved secondhand.

---

## Part 4. Where to win

The gap, stated precisely:

> **There is no product that takes a batch of AI-generated ad variants and returns, per variant, a plain-language ship or hold verdict a non-designer can defend to their boss, covering brand identity, craft defects, channel specs and likely effectiveness, in seconds, without live spend.**

Ranked by defensibility:

**A. The genAI defect linter.** Detect the failure modes only AI-adapted creative produces: malformed text rendering, logo redrawn rather than placed, product geometry inconsistency, bad crops of the focal subject, localisation that broke the layout. **Zero vendors do this.** Perceptual, demonstrable in a demo, and instantly legible to a non-designer: "we caught 6 of your 40 variants before they shipped."

**B. The per-variant verdict layer, not the dashboard.** The seat Vidmob and CreativeX are vacating.

**C. Brand identity as a learned representation, not a rule list.** Everyone encodes brand as rules because rules are what a DAM can store. Nobody encodes what the brand's good work actually looks like, which is what a designer uses. Technically feasible now; does not exist commercially.

**D. Owning the channel and retailer rule library.** Cape.io is already positioning here with a "Global Spec Database." `[synthesis]` This is the compounding asset. Whoever maintains versioned, machine-readable channel and retailer rules has something a competitor cannot copy in a quarter, and it is the only thing that makes automated pre-flight trustworthy rather than advisory.

### Risks worth stating plainly
- **Adobe from above.** GenStudio Brand Check is the right shape and Adobe owns the enterprise creative stack.
- **Canva from the side.** $4B ARR, 265M MAU, B2B growing roughly 100%, already has a Brand Hub and variant generation. Every ingredient, unassembled.
- **Platforms from below.** TikTok made Symphony free globally. Amazon is explicitly building for non-marketers: *"We're not talking about professional marketers. These are customers that really need our help growing their business."*
- **Validation is the moat and the burden.** Every score in this market is unaudited. AdCreative.ai claims 90%+ accuracy with no published methodology; Frontify's "ratings" have no disclosed basis. Whoever publishes real validation first defines the trust standard.
- **History.** Forrester's own read is that creative adtech has *"struggled to translate technological promise into business outcomes"* since 2021. Adacado, RevJet and Jivox failed at precisely this step.

---

## Part 5. What I could not verify

Listed so nobody builds on sand.

- **Typeface commercial traction.** Genuine public practitioner commentary is thin. G2, Gartner Peer Insights, Glassdoor, TrustRadius and Capterra were not reachable in this research. Roughly 20 G2 reviews exist and remain unread. One unverified negative insider comment surfaced and **I have deliberately excluded it**: it rests on a single anonymous line of unknown proximity to the company that could not be confirmed on reddit.com across six retrieval routes, and it would be doing far too much work if cited.
- **Typeface pricing.** A "$49/user/month Team tier" and "low six figures annually" for enterprise appear in a machine-generated LinkedIn article with no named byline and no hands-on testing. Directionally consistent with one real third-party review mentioning a $350,000 quote, but that is convergence, not confirmation. Typeface publishes no pricing.
- **Gartner Peer Insights page for Typeface**: probably absent, not conclusively.
- **Retail media practitioner voice**: nearly absent from public forums. Go to the Path to Purchase Institute community or agency contacts at Tinuiti, Skai or Pacvue directly.
- **The political cost of asking a designer to re-review**: real, well supported indirectly, not publicly quotable. Get it from interviews.
- **Creative automation market sizing**: no credible named-firm figure verified.
- **Several vendor claims** are flagged inline as `[unverified]`, including AdCreative.ai's accuracy figure, Creatify's variant scoring (not substantiated on Creatify's own page), and Ziflow's brand-standards auto-detection (marked "coming soon," not shipped).

**Corrections to common assumptions**, worth knowing before anyone repeats them:
- **Realeyes has exited advertising attention measurement entirely** and now sells identity verification. Do not list it as a creative scoring vendor.
- **Jasper's $125M / $1.5B figures are stale.** Internal valuation cut roughly 20% in 2023, revenue fell from roughly $120M to $55M ARR, founder-CEO departed.
- **AdCreative.ai is owned by Appier** ($38.7M, closed March 2025), not independent, and carries significant self-serve billing complaints.
- **Creatopy is now "The Brief" (thebrief.ai)** as of Oct 2025.
- **Bynder's PE owner is Thomas H. Lee Partners**, not Thoma Bravo.

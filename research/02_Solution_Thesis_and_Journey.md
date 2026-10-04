# Arc Proof: the creative assistance experience for ad creatives

Working thesis, marketer journey, design principles and V1 scope.
Companion to `01_Research_Dossier.md` (evidence) and `sample-data/` (proposed context schemas).

---

## 1. The reframe

The brief says: help the marketer know what needs attention, what to do about it, and when they are ready to ship.

The obvious reading is: score each creative, show a badge, let them edit. That is the safe ship, and it fails for a reason that is easy to miss.

**A score is an opinion, and a marketer cannot take an opinion to their CMO.**

The marketer in this scenario is not actually blocked on judgement. She is blocked on **defensibility**. She is about to put her name on 64 things she cannot fully evaluate, and the thing she needs is not a number. It is a case she can defend if someone senior asks why.

That reframing changes what we build. We are not building an AI art director. We are converting design judgement into **cited evidence**.

Every flag names its authority. Brand book page 14. Meta spec effective 1 Nov. Legal rule owned by legal@, updated 15 Oct. Q3 2025 campaign, 22% below control. She is not being asked to develop taste in an afternoon. She is being handed a file.

---

## 2. The thing the teardown changed

I went through the Typeface product recording before writing this. It moved the thesis materially, so it belongs up front.

**Typeface already ships the evaluation primitive.** Verbatim from the product:

> "Typeface can use a **complex rubric** to generate marketing assets, by **encoding brand standards, messaging requirements, compliance rules, or performance criteria into a structured evaluation framework**."

> "Typeface can then **evaluate and score how each asset aligns with the rubric to ensure only compliant assets are generated**."

And it was demonstrated. The marketer typed a rubric into the chat box as prose. The assistant returned a real evaluation artefact: *"The rubric was met on iteration 1"*, rendered as a table of **Rubric objective | Overlap score | Verdict**. Elsewhere, assets were *"held to the email quality bar (score + fact-fidelity audit) before saving"* and one scored *"94/87 after a revision that removed an invented 'six flavors' count."* Agent Studio has an **`Evaluate`** node sitting next to `Generate`.

So the honest V1 is not "build an AI creative critic." The engine exists. The problem is where it sits:

| | Today | What V1 changes |
|---|---|---|
| **Who writes the rubric** | The marketer, in prose, in a chat box | Compiled from the Arc Graph. She reads it, she does not write it. |
| **When it runs** | At generation, to filter what gets made | At generation **and** at the ship decision, as a standing verdict |
| **What it covers** | Copy: distinctness, fact fidelity, tone | Copy **plus** layout, spec, legal, localisation, craft |
| **What grain** | One document at a time | The whole batch, clustered by root cause |
| **Who sees it** | Whoever asked | The person about to click publish |

**V1 turns the rubric from a prompt into a product.**

That framing matters for one more reason. The marketer in this brief is precisely the person who **cannot write the rubric**. She does not know that German runs 35% longer than English, that Halo Grotesk has no CJK glyphs, that Amazon rejects unsubstantiated superlatives, or that the brand book specifies 1x clear space. Asking her to specify the quality bar is asking her to already have the expertise the brief says she lacks. The Arc Graph is supposed to hold that knowledge. Right now it holds it and does not spend it.

---

## 3. What is actually in her head

Three fears, and none of them are about beauty:

1. Something ships that is objectively broken (text clipped, disclaimer missing, wrong pack shot) and it is **visible**.
2. The platform or retailer **rejects it** and she loses flight days in peak week.
3. The brand team or the CMO sees something off and **she has no answer** for why she shipped it.

The research backs all three, and the third is the one people underrate. A designer with 30 years of production behind them put it plainly: *"no sign off should really depend on one person."* A marketer with ten years in: *"I still get the sweats when I am about to hit send, even after the team has looked over the final (final) draft."* Someone else named it **"sender's remorse."**

And the fear is rational. In a widely-read thread about the worst mistakes people had shipped, the top answer was a company name misspelled in 72-point type on a full-page magazine ad. *"The whole agency signed off on it, three people in the client company signed off on it. No one caught it... Who saw it first? The CEO."*

Eight approvers. 72-point type. Still shipped.

**More human reviewers is not the fix.** The industry's own best-practice guidance says the opposite: limit final QA to one or two people, because *"too many cooks can spoil the broth."* Another practitioner: *"People also start to rely on the micro-manager to catch mistakes because they're so involved anyway, surely someone else will catch the mistake."* And the most honest description of what sign-off actually is: *"he approves without actually looking at things, so it's always 'hey, is this piece as you wanted it to be?' and he just goes yep... so he doesn't get mad when something goes wrong."*

The safety net is deliberately thin and everyone in the chain knows it is theatre. A machine layer is the only way to get both fewer reviewers and more coverage.

---

## 4. Three tiers, and why they must never be one number

The single most important structural decision in this design: **do not sum the tiers into a score.**

Adobe GenStudio's Brand Check computes a Brand Score as guidelines-passed over guidelines-tested. That averages a legal blocker with a nice-to-have. AdCreative.ai returns a Conversion Score with no published methodology. Frontify ships "ratings" with no disclosed basis. Every one of these hands a non-designer a number she still cannot defend.

Three tiers, three different truth values, three different default behaviours:

### Tier 1: Spec. Objective.
Channel specs, safe zones, text overflow, contrast ratios, font glyph coverage, file limits, character truncation, legal mandatories, prohibited claim patterns.

- **Truth value:** computable and externally citable. Meta's published spec. WCAG 2.2. The font file's own glyph table. Amazon's creative policy.
- **Verdict:** pass or fail. There is no judgement here.
- **Default:** propose the fix, pre-applied in a diff, one click to accept.
- **Why:** never make a non-designer adjudicate a contrast ratio. She has no basis to disagree and no reason to want to.

Roughly 70% of findings and roughly none of the judgement.

### Tier 2: Brand. Relative.
Colour drift beyond tolerance, logo clear space, off-palette accents, non-brand typeface, voice violations against the never-say list, imagery style drift from the approved corpus.

- **Truth value:** measured against the Arc Graph, which is the customer's own stated position. Carries a measured delta, not a vibe: `deltaE 6.2, tolerance 3.0`.
- **Verdict:** conforms or drifts, with the magnitude shown.
- **Default:** propose the fix, she adjusts it, she accepts it. Override is allowed and **records a reason**.
- **Why:** these are the customer's rules, so the customer can waive them. But waiving needs a trail.

### Tier 3: Craft and precedent. Judgement.
Two distinct things, deliberately kept apart.

**3a. Craft defects.** The genAI failure class: garbled text rendered into an image, a logo redrawn rather than placed, product geometry inconsistent across a set, hands, face drift between stitched clips, a crop that cuts the focal subject.
- **Verdict:** never a verdict. "This needs your eyes," with the region highlighted and zoomed.
- **Default:** never auto-fix. Regenerate or escalate.
- **Why:** this is the one class where the machine is least reliable and the human is most capable. Pointing is honest; judging is not.

**3b. Precedent.** Arc Loop's learnings, brought forward to the ship decision rather than to the next brief.
- **Verdict:** never a verdict. "This hook ran to this audience in Q3 2025 and delivered 22% below control."
- **Default:** no action. Evidence, displayed, ignorable.
- **Why:** a predicted CTR that is wrong once destroys trust in Tiers 1 and 2, which were correct. The asymmetry is brutal and well documented. Do not spend Tier 1's credibility on Tier 3's guesses.

**The rule:** Tier 1 is a fact, Tier 2 is a position, Tier 3 is a prior. They get different colours, different verbs, different default actions, and they are never averaged.

---

## 5. Design principles, each one earned

### 5.1 Cite, do not assert
Every finding names its authority and deep-links to it. No finding ships without a source.

Because the blocker is social, not cognitive. *"Your brand book, page 14, specifies 1x clear space"* is something she can forward. *"This looks off"* is something she has to own alone.

**Product consequence:** an uncited finding is a bug. Track "% of findings with a resolvable authority" as a health metric.

### 5.2 Cluster by root cause, not by asset
64 variants is not 64 problems. It is typically five or six problems repeated. Twelve German variants overflow because one box was sized for English. Nine CTAs fail contrast because one colour pairing was chosen once.

So the entry surface is a **triage queue clustered by cause**, where the unit of work is "fix once, apply to twelve." The gallery exists, but it is the second screen.

This is what makes the complex feel simple: **64 decisions collapse to 6.**

There is a second reason, and it is arithmetic. Observed thinking times in the product recording: 31 seconds, 2m19s, 3m24s, 4m55s, **8m32s**. A chat-first, per-asset review of 64 variants is not slow, it is impossible. **Verdicts have to be pre-computed and already on screen when she opens the campaign.**

And a third reason. The $14,000 Pantone story is one wrong token copied from a previous brand's template, invisible to two humans, printed onto bags. Cluster-level review is how you catch the thing that propagated, rather than catching it once and missing eleven siblings.

### 5.3 Flag by default, fix on consent, always show the diff
This is the principle with the most evidence behind it, and it is a warning.

This market has learned to hate exactly one behaviour: **AI silently mutating approved creative.** The Meta Advantage+ threads are unambiguous:

> *"A customer actually reached out to me to say my Instagram ad looked strangely cropped and blurred... In Ads Manager my creative looks fine, but in real Instagram placements the image is clearly altered."*

> *"I was so embarrassed when a potential customer sent me a screenshot of my ad. It was a total mess, with half of the text cut off... It makes my business look so unprofessional."*

> *"They apply almost all their AI bullshit to my ads after opting out at the account level and campaign level."*

There is a manual ritual people describe performing on every single publish: ship, wait for approval, go back in, re-check that the platform has not silently re-enabled its own enhancements.

**So: nothing changes without her seeing it change.** Every applied fix renders as a before/after diff. Opt-outs persist and are honoured. Auto-apply exists but is opt-in per rule class and always logged.

Note the second half of that first quote, because it is the most product-relevant sentence in the whole research set: **the in-tool preview lied, and a customer caught it.** Which gives us the next principle.

### 5.4 Preview in real placement chrome
Not on a white canvas. In the actual Reels UI, with the caption bar, the profile row, the CTA button and the right-hand action rail overlaid, at phone scale.

The dominant discovery-too-late mechanism is that the preview is honest about the file and dishonest about the placement.

And it goes further than cropping. In June 2026 REI ran an Instagram ad built from a legitimate vendor-supplied photograph of a Van Rysel bicycle. Meta's Dynamic Media system silently regenerated it. The shipped ad had a second pair of handlebars growing out of the saddle, a missing crank arm, and disc brakes on the wrong side of the wheel. It ran for a week. Reddit caught it, not REI.

> "**Meta auto-enrolled us in an AI personalization tool that produced an inaccurate and inappropriate alteration of a vendor-provided image in some of our ads.**"
> REI, 22 June 2026

> "**AI can make mistakes and it is the advertiser's responsibility to review the AI outputs.**"
> Meta spokesperson

The approved master was fine. Every defect was introduced after approval, in delivery, by the platform. **A product that checks only the file she approved would have passed that ad cleanly.**

So the scope is the **served** creative, not only the master. Post-publish verification, re-checking what the platform actually rendered against what she approved, and alerting on drift. Meta has stated on the record that reviewing the output is the advertiser's job while giving the advertiser no surface on which to do it. That gap is a product. A practitioner's own workaround: *"build a 4:5 with a 1:1 safe zone and keep all text/logos inside the center square... so the crop logic can't surprise you."* We should do that for her, and show her.

### 5.5 Let her adjust the fix before she accepts it
Not flag-only, which is useless to someone who does not know what to do. Not auto-fix, which this market has learned to distrust. **Suggest, let her tune, she applies.**

This is grounded, not stylistic. Dietvorst, Simmons and Massey (2015) established that people abandon algorithms faster than they abandon humans after equivalent error. Their follow-up work found that **algorithm aversion drops measurably when people can modify the output, even slightly.**

A practitioner arrived at the same conclusion unprompted, about Google's auto-generated assets: *"What would be nicer is the same feature but given as recommendations that you can alter. Not pure AI but more computer assisted help."*

The adjustability is not a nicety. It is the mechanism that buys the trust.

### 5.6 Precision over recall, deliberately
Same literature, direct consequence: **our false positives cost more than our false negatives.**

One wrong "this logo is warped" costs more trust than one missed defect, because the miss is invisible and the false alarm is not. So Tier 1 ships only at high precision. Tier 3 craft findings are framed as *"look at this"* rather than *"this is broken"*, which makes them unfalsifiable in the right way: pointing at a region is never wrong, calling it a defect can be.

Counter-metric, tracked from day one: **false-flag rate**, measured as flags dismissed as incorrect. If it climbs, we are losing regardless of what the other numbers say.

### 5.7 Show what passed, not only what failed
Collapsed, but present. "47 checks run, 44 passed" with the list expandable.

Typeface's stated philosophy is that *"brand governance happens in the background instead of a review queue."* That is the right call for generation and precisely the wrong call at the ship decision. Invisible governance gives her nothing to see, so **silence reads as risk rather than safety.** Her fear is unknown unknowns; the cure is a visible manifest of what was checked.

The IAB/Aymara data makes this concrete. Over 70% of marketers have already had an AI-related incident. Nearly 90% say they feel prepared to catch AI issues before launch. That gap is a false sense of security, and it closes only when someone can see what was and was not inspected.

### 5.8 The designer is absent but present
The designer never comes back into the loop. Their judgement does, captured once at handoff:

- **Locked elements**, each with a stated rationale. *"Logo position is fixed across the New Year system so the set reads as one campaign."*
- **Flexible elements**, with stated latitude.

This costs the designer minutes, once. It is what lets the marketer override safely, because she can read **why** before she breaks it.

Overriding a locked element requires a reason. That reason is the escalation signal: if three marketers override the same lock, the designer gets **one notification, not thirty review requests.** The designer scales by writing down why, once, instead of re-reviewing forever.

This also defuses a real relationship problem. Designers describe watching marketers publish edited versions of their work under their name, and being called *"snippy"* for objecting. Locks with rationale give the designer a voice in the room they are not in, without making them a bottleneck.

---

## 6. The journey, end to end

**Monday. Campaign: New Year Reset. Designer handed off two approved concepts three weeks ago and moved on. Typeface generated 64 variants across 4 channels, 4 formats and 4 markets. Flight starts Thursday. Media is booked.**

**1. Open the campaign.** Not a gallery. A readiness board.
> 38 ready to ship. 21 need attention. 5 blocked.
> Grouped into 6 issues.

She has not clicked anything and already knows the shape of her Monday.

**2. Work the queue.** Each issue is one card:
- **What:** "German headline overflows the text box."
- **How many:** 12 variants, shown as thumbnails.
- **Why it happened:** "Source headline is 34 characters in English, 44 in German. The 9:16 box was sized for English."
- **Who says so:** computed layout, 62px over.
- **What it costs:** for the missing-disclaimer cluster, "Meta disapproval or post-launch takedown. Historically 3 to 5 lost flight days."
- **Fix options, with side effects named:** use the approved shorter German headline (preserves brand voice and the designer's layout) / grow the box 18% (reduces logo clear space, will trigger a second flag) / drop to 72px (below brand minimum, blocked).
- **Scope:** this variant / these 12 / all German variants in the campaign.

She adjusts the suggested headline by two words. Applies to 12. One diff, twelve assets.

**3. Drop into canvas only when it needs eyes.** The 4 Japanese variants have a craft flag. Element pre-selected, region zoomed, rendered in real placement chrome. The brand face has no CJK glyphs and the renderer was silently substituting. One click to the approved Noto Sans JP.

**4. The precedent pass.** Optional, and clearly marked as advisory. "Six variants use a hook that ran to this audience in Q3 2025 and delivered 22% below control. An alternative from the same segment delivered +31%." She takes four, ignores two, because she knows something about this quarter that the data does not.

**5. The ship gate.** Blockers at zero, or explicitly overridden with a reason. She overrides one: the logo clear space on Reels, because the platform chrome covers the top area anyway and the brand team approved it verbally yesterday. She types that sentence. It is recorded.

**6. The Ship Report.** Generated automatically. 47 checks run, 44 passed, 1 override with the reason and who gave it, rule versions used, 1 designer escalation, 34 minutes from open to ship-ready. She attaches it to the launch ticket. **This is the artefact that replaces designer sign-off socially.**

**7. Publish.** Direct to channel. This already works in Typeface today and does not need rebuilding.

**8. The loop closes.** Performance and any platform rejection flows back through Arc Loop and recalibrates this brand's thresholds. If the German overflow rule fires and is dismissed as wrong four times, its threshold adjusts. The product gets quieter and sharper per customer.

### Where chat sits
Not the primary surface. A marketer with 64 variants and a Thursday deadline does not want a conversation, and at 8-minute thinking times cannot afford one.

Chat is the **explainer and the escape hatch**:
- *"why is this flagged"* returns the citation
- *"fix all the German ones"* is a batch action she can phrase instead of click
- *"show me the ones like last year's winner"* is a query over precedent

The board and the canvas do the work. Chat handles the long tail and the why.

---

## 7. V1 scope

**In:**
- Auto-compiled Ship Rubric from brand x channel x market x audience
- Tier 1 spec and legal checks for **Meta, Google Ads and Campaign Manager 360 only**
- Tier 2 brand conformance against the Arc Graph design system and voice rules
- Tier 3a craft defect detection on static image creative
- Tier 3b precedent from Arc Loop, surfaced at the ship decision
- Cluster-based triage board, batch apply, adjustable fixes, visible diffs
- Real-placement-chrome preview
- Designer locks with rationale, override capture, escalation digest
- Ship Report

**Out, and why:**
- **Generating net-new concepts.** The seed comes from the designer. That boundary is what makes the designer relationship work.
- **A predicted performance number.** Precedent only. A wrong predicted CTR would spend the credibility that Tiers 1 and 2 earned. Revisit once we have per-brand calibration data.
- **Full design editing.** Fix the flag. Do not become Photoshop.
- **Video beyond first-frame, safe-zone and caption checks.** Face drift across stitched clips is the highest-value video defect and the hardest. V2.
- **Multi-stakeholder approval routing.** The Ship Report is the artefact; routing it is V2. Note the research warning here: longer approval chains correlate with worse catching, not better.
- **Media buying, budget, bidding.** Not our surface.
- **Retail media (Amazon, Walmart, Criteo), and this one is a deliberate, uncomfortable cut.** Retail media is where creative spec pain is worst and rejection is most expensive, and my most vivid failure stories live there. But Typeface has **no retail media connector, no roadmap signal and nobody hired against it**. The Ad Agent integrates Campaign Manager 360, Google Ads and Meta Ads; no RMN appears anywhere on the site or in any of the 16 live job postings. Building checks for channels we cannot publish to or read performance from would be a demo, not a product. **Retail media is the V2 wedge**, and it is a good one: brands will not accept a retailer grading its own creative output, which is exactly the objection an independent checker answers.
- **Unintended-meaning detection** (the silhouette class, e.g. the Converse pull). We cannot promise this and should not imply we can.

**The V1 dependency nobody will want to hear:** the rules have to get thicker before the checks can get sharper, and this is a schema problem before it is a content problem.

The demo brand had **7 fonts, none named, with no usage rules, 15 guidelines and 2 terms to avoid.** That looked like a lazy demo setup. It is not. From the public API reference, a Brand Kit permits **only one text style and one logo style**, and the product's own documentation says *"Get started with adding up to 5 Values, 5 Tones, and 10 Rules."* The only rule type in the schema is `termsToAvoid`, expressed as source-and-replacement pairs.

**That is find-and-replace, not constraints.** There is nowhere in the current model to put "body copy is minimum 24px on mobile feed," "logo clear space is 1x cap height," or "this claim requires an in-creative disclaimer in the US."

Hold that next to the one real public user review of Typeface, from a brand manager at a 10,000-plus-person company: *"Despite claims of brand training capabilities, **we were unable to generate content that reflected our brand voice**."* **The brand-voice complaint and the ten-rule cap are plausibly the same fact.** If so, that is good news, because it is a design problem rather than a model-quality problem.

So V1 ships with a **Rule Compiler**: a schema extension plus an onboarding pass that reads the existing brand book and asset library and proposes structured, checkable constraints for the brand team to confirm. This is not a nicety. It is the difference between a product and a demo, and it is the unglamorous half of the work.

It is also the easiest part to fund, because it makes the Arc Graph more valuable to **every other agent on the platform**, not just this one. Typeface already ships **Brand Linting**, which validates the extracted rules themselves for *"schema violations, duplicate rules, contradictions, broken cross-references."* A richer schema makes that existing feature worth more too.

---

## 8. How we would measure it in 90 days

**North star: Unassisted Ship Rate.**
Share of generated variants that reach launch with **no designer round-trip** and **no post-launch correction or pull within 14 days**.

One number, and it moves only if all three of certainty, quality and speed move together. A marketer who ships fast and gets pulled does not count. A marketer who ships clean because she escalated everything to a designer does not count either.

| | Metric | Why it |
|---|---|---|
| **Speed** | Median hours from batch generated to batch ship-ready | The efficiency the platform promises and currently loses at review |
| **Quality** | Defect escape rate: defects found post-launch / total defects found | The only honest measure of whether the check works |
| **Quality** | Platform and retailer rejection rate per 100 variants | Objective, dated, already logged somewhere, and costs real flight days |
| **Certainty** | Share of batches shipped with zero designer escalation | The brief's actual ask |
| **Trust (leading)** | Fix acceptance rate | Do they take the suggestion. Predicts everything else. |
| **Trust (guardrail)** | **False-flag rate**: flags dismissed as incorrect | The counter-metric. If this rises, stop and fix it. |
| **Coverage** | Share of findings with a resolvable cited authority | An uncited finding is an opinion, and opinions do not travel |
| **Foundation** | Brand rule density: checkable constraints per brand | Leading indicator for every other number above |

**90-day plan:**
- **Days 0-30.** Ship the Rule Compiler and the readiness board against 3 design partners with high variant volume and at least two markets. Instrument everything. Do not ship auto-apply yet. Baseline the current rejection rate and time-to-ship, because without a baseline none of the above is provable.
- **Days 31-60.** Turn on clustering, batch apply and adjustable fixes. Target fix acceptance above 60% and false-flag below 5%. If false-flag is above 5%, narrow the rule set rather than tuning the UI.
- **Days 61-90.** Ship the Ship Report and designer locks. Read out Unassisted Ship Rate against baseline. The decision this informs: does the check earn a place in the default flow, or does it stay opt-in.

**What would make me kill it:** fix acceptance under 40% with false-flag under 5%. That combination means the findings are correct and still not worth acting on, which means we solved a problem nobody has.

---

## 9. Where this wins, honestly

The competitive picture is unusually favourable and I want to state it without overclaiming.

- **Compliance without judgement.** Adobe GenStudio, CreativeX, Frontify, Bynder, Ziflow and Filestage all answer "does this violate a rule someone wrote down." None of them perceive. A variant can pass 100% of brand rules and still be unshippable because the AI melted the product or garbled the text. **No vendor found in this research detects genAI craft defects.** That is Tier 3a, and it is genuinely unowned.
- **Prediction without governance.** AdCreative.ai, Atria, Pencil, Neurons and Dragonfly predict something about performance and check no brand, legal or spec rule. An enterprise cannot ship on a Conversion Score.
- **Post-hoc sold as pre-flight.** Motion, Foreplay, Canva Grow insights, Meta's diagnostics and TikTok's Smart+ rankings all require spend first. Meta's rankings need roughly 500 impressions to populate, so by construction they cannot inform a ship decision. Google's own documentation states Ad Strength is not used in Ad Rank, Quality Score or auction wins. The market lacks clear language for **before spend** versus **after spend**, and that is a positioning opening.
- **The seat is being vacated.** The two firms with the best scoring technology are both walking away from the marketer's screen. Vidmob has repositioned as a data layer feeding other people's AI agents. CreativeX sells retrospective governance dashboards to global brand leadership. Neither is sitting in front of the person about to click publish.
- **Typeface is already in the frame.** Forrester's June 2026 piece names Typeface in the creative adtech specialist set, and opens with the line this entire brief rests on: *"Creative quality is the greatest determinant of media's performance, outweighing ads' targeting or placement."*

**The structural argument, in one line:** generation cost fell roughly 100x and review cost did not move at all. Every vendor in this market solved generation. The review bottleneck they created is still open.

**Risks I would not hide from the team:**
- Adobe is the closest and has the right shape already. If GenStudio adds perceptual defect detection and a per-variant verdict, the window narrows fast.
- Canva has every ingredient (Brand Hub, variant generation, enormous distribution) and has not assembled them. That is a matter of time, not capability.
- Platforms are commoditising from below and are free.
- Every score in this market is unaudited. AdCreative.ai claims 90% accuracy with no published methodology. Frontify's ratings have no disclosed basis. **Whoever publishes real validation first defines the trust standard**, and that is a reason to be conservative about what we claim, not just a marketing opportunity.
- Forrester's own read is that creative adtech has struggled to convert promise into outcomes since 2021. The vendors that failed at this (Adacado, RevJet, Jivox) failed at exactly this step. That history is a warning, not only an opening.

---

## 10. What is original here

Five things I have not seen anywhere in the research:

1. **The rubric as a compiled artefact, not a prompt.** Context becomes constraints automatically. The marketer reads the quality bar instead of authoring it. This inverts who does the specification work, and it is the only version that works for someone who lacks the expertise by definition.
2. **Three tiers with different epistemics, deliberately never summed.** Everyone else ships one number. A non-designer does not need a score. She needs to know which findings are facts, which are her company's positions, and which are bets, because those carry different consequences when she is challenged.
3. **Evidence as the unit of delivery, not the verdict.** The product's output is a defensible case file. The real blocker is social, not cognitive.
4. **Review the cause, not the asset.** 64 becomes 6. This is the difference between a feature and a workflow.
5. **The adjustable fix as a trust mechanism, not a convenience.** Grounded in the algorithm-aversion literature and independently voiced by practitioners. Neither flag-only nor auto-fix. The tuning step is what buys adoption, and it is also the thing that distinguishes us from the behaviour this market has learned to resent.

# How creative-assistant / creative-QA products name and report checks to a non-technical marketer

**Labels:** [VERBATIM] = exact quoted UI/doc string with source. [PARA] = paraphrase of a source. [UNVERIFIED] = inference or unconfirmed.

**Routes that worked:** vendor sitemaps (`/sitemap.xml`, `/page-sitemap*.xml`) were the single best discovery tool. `llms.txt` + appending `.md` to doc URLs (Markup AI, Smartly, Rocketium). Raw GitHub markdown for Adobe docs (`AdobeDocs/genstudio-for-performance-marketing.en`). `gh search code` for shipped UI string tables (C2PA). Intercom help centres via `__NEXT_DATA__` JSON and `/en/search?q=` (Vidmob, Frontify, Lytho, Air). Zendesk's **open** `/api/v2/help_center/...articles.json` on help centres whose HTML is 403 (Ziflow, Jasper, Bynder). Veeva's **unauthenticated Elastic App Search** endpoint. Reading product screenshots as images (Veeva, Ziflow, Filestage). JS bundle string extraction (CreativeLens).

**Correction to the brief:** `web.archive.org` **is** reachable via `curl` and the CDX API, though WebFetch refuses it. It was essential for Adobe helpx (403 direct), Veeva's 25R3 screenshots, and Filestage's Cloudflare-blocked images.

---

## 1. CreativeLens.ai

**Important caveat:** creativelens.ai is a single-page Lovable-built marketing site with no docs, no help centre, no app access. Every string below is [VERBATIM] extracted from the production JS bundle (`/assets/index-DND5gTrn.js`), but they are the **marketing site's simulated product mockups**, not observed product UI. Treat as the vocabulary they intend, not confirmed shipped behaviour.

**(a) Category names.** Two parallel sets exist in the bundle.

Positioning copy, [VERBATIM]: *"CreativeLens automatically reviews content before publishing and flags issues across four critical dimensions"*, then the four labels: `Brand consistency`, `Legal compliance`, `Platform requirements`, `Performance best practices`.

Scorecard mockup uses shortened forms, [VERBATIM] as a data array: `[{label:"Brand Consistency",score:92},{label:"Legal Compliance",score:78},{label:"Platform Specs",score:95},{label:"Performance",score:80}]`.

Rule-level taxonomy ("Rule Builder", header [VERBATIM] `Active Rules` with `12 rules`), [VERBATIM]: `[{name:"Logo safe zone",type:"Brand"},{name:"Disclaimer check",type:"Legal"},{name:"Min font size",type:"A11y"},{name:"Color contrast",type:"A11y"}]`. Note the fourth rule type `A11y` does not appear in the four marketing dimensions.

Four feature names, [VERBATIM]: `Pre-flight Review`, `Smart Rule Engine`, `Multi-Modal AI Analysis`, `Actionable Feedback`. Their sub-bullets, [VERBATIM]: `Detect missing disclaimers`, `Flag unsafe logo placement`, `Identify compliance risks`, `Upload brand books and policies`, `AI extracts rules automatically`, `Apply rules across image and video`, `Frame-level video checks`, `Visual + text analysis`, `Context-aware feedback`, `Explain what's wrong`, `Suggest exactly how to fix it`, `Link to relevant guidelines`.

**(b) Finding wording.** Two-line pattern: bold defect name, then an imperative remedy. [VERBATIM] pairs:
- `❌ Missing required disclaimer` / `Add FTC-compliant disclosure below CTA`
- `⚠ Logo spacing violation` / `Increase clear space by 8px on all sides`
- `✓ Color palette matches brand` (pass state, no second line)
- `Missing disclaimer text` / `Required legal disclaimer not found in image`
- `Logo outside safe zone` / `Brand logo placement violates minimum margin rules`

Floating badges, [VERBATIM]: `⚠ Missing disclaimer`, `🔍 Low contrast`, `📐 Logo out of safe zone`. On-image pins, [VERBATIM]: `⚠ No disclaimer`, `⚠ Logo zone`.

**(c) Score + count + list, all three.** [VERBATIM] header `Content Score` with `85%`, then four per-dimension bars each with a percentage. Separately [VERBATIM] chips `2 Issues` and `1 Passed`, and a subtitle `3 assets · 2 issues found`. Dashboard tiles, [VERBATIM]: `Reviewed` 127, `Issues Found` 23, `Approved` 104.

**(d) Report screen.** Three named screens, [VERBATIM] titles and descriptions: `Dashboard` / `Track all content reviews at a glance`; `Review Screen` / `See flagged issues with suggested fixes`; `Rule Builder` / `Create custom review rules from brand guidelines`. Dashboard also carries campaign rows with statuses [VERBATIM] `Approved`, `In Review`, `Pending`.

**(e) Auto-fixed vs needs-attention: no.** Nothing in the bundle distinguishes them. The tagline is [VERBATIM] `Not just issues — clear fixes`, but fixes are **suggestions to the human**: [VERBATIM] `Suggest exactly how to fix it`, and `Get issues, suggestions, and approvals — all in one place. Fix and publish with confidence.` The user fixes.

**(f) Provenance: strongest single claim of any product in this set.** [VERBATIM] FAQ answer to *"Can CreativeLens explain why content was flagged?"*: **`Yes. Every finding includes the triggering rule, severity level, explanation, and suggested remediation.`** That is a four-part finding contract. Also [VERBATIM]: `Link to relevant guidelines`, and on rule origin: `Upload brand guidelines, compliance policies, and other documents. CreativeLens uses AI to extract rules and applies them automatically during content reviews.` Custom rule scopes, [VERBATIM]: `company-specific, campaign-specific, platform-specific, and industry-specific rules`.

**Naming convention: mixed, and inconsistently so.** Dimension at the summary layer (`Brand Consistency`), defect at the finding layer (`Logo spacing violation`, `Low contrast`), artefact-or-rule at the rule layer (`Logo safe zone`, `Min font size`). No agents. The dimension set differs between marketing copy and the scorecard (`Platform requirements` vs `Platform Specs`), and `A11y` exists only at rule level.

---

## 2. Adobe GenStudio for Performance Marketing

Source: `https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/guidelines/brand-validation` and the raw repo `AdobeDocs/genstudio-for-performance-marketing.en`.

**Terminology note:** the feature is **"brand validation"**; the user-facing surface is **"Content check"**. "Brand Check" is not the shipped label. "Brand score" survives only in release notes and a disabled-button note, [VERBATIM]: *"The Canvas Brand button is now disabled when brand scores are not generated for an experience."*

**(a) The three guideline sets.** [VERBATIM], as the three toggles under the `Content type` icon:
- `Brand`, described [VERBATIM] as *"Performs the checks associated with Brand guidelines"*
- `Platform guidelines`, [VERBATIM] *"Performs the checks associated with the channel-specific platform, such as Meta"*
- `Accessibility`, [VERBATIM] *"Performs the checks associated with ADA accessibility standards"*

Then [VERBATIM] `Apply`. Underlying doc names them [VERBATIM] `ADA accessibility` and `Platform compliance`, and specifies [VERBATIM] *"GenStudio for Performance Marketing currently references ADA Level AA copy (text) accessibility standards."*

Brand guideline categories are [VERBATIM] `[!UICONTROL]` labels in a `Guideline category` column: **Brand voice**: `Tone of voice`, `Brand values`, `Editorial guidelines`, `Editorial restrictions`. **Image**: `Description`, `Content type`, `Composition`, `Environment`, `Color`, `Lighting`, `Mood`, `Restrictions`. **Channel sections**: `General`, `Subject`, `Preheader`, `Headline`, `Sub-headline`, `Description`, `Body`, `On-image text`, `Call-to-action (CTA)`. Plus `Logos` and `Colors` tabs.

The five accessibility checks, [VERBATIM] verbatim sentences: *"Images provide an `<alt>` attribute."* / *"Generated text has 4.5:1 contrast against its background."* / *"Words or phrases used in an unusual or restricted way, including idioms and jargon, are avoided."* / *"Expanded forms or meaning of abbreviations are available."* / *"Content is readable at a lower secondary education level."*

Default channel guidelines are literal constraint strings, [VERBATIM] for Meta: `Limit to 40 characters or less` (Headline), `Limit to 125 characters or less` (Body), `Limit to 5-6 words` (On-image text); for LinkedIn: `Limit to 70 characters or less to avoid truncation`, `Maximum of four emojis`, `Limit to 255 characters or less`.

**(b)+(c) How the score is computed and displayed.** [VERBATIM]: the `Content check` summary displays *"Percentage of compliance with your Brand calculated as **the number of guidelines that passed validation versus the number of guidelines tested**"*, plus *"`Pass` or `Fail` result for the platform guidelines, such as Meta or LinkedIn"* and *"`Pass` or `Fail` result for ADA accessibility standards"*. So: **a ratio percentage for Brand, and binary Pass/Fail for the other two.** [VERBATIM]: *"The scores auto-update as you make edits to the variants or other content."*

**(d) The panel, and the exact "Needs review" vs "Passed" wording.** [VERBATIM]: the `Content check` panel displays *"**Needs review** section displaying the number of failed guidelines and detailed information about each guideline needing revision"* and *"**Passed** section displaying the number of passed guidelines and detailed information about each passing guideline"*. So both sections carry a count plus per-guideline detail, and passing checks are shown, not hidden.

Drill-down sections are named after the content slot, [VERBATIM]: *"Click to expand and inspect each check that needs review in available sections such as **Headline**, **Color**, and **Brand voice**."* Scope caveat, [VERBATIM]: *"The Brand voice guideline noted in the Content check panel applies to the entire variant, not an individual section. The whole content variant is highlighted for suggested improvement."*

Action label, [VERBATIM]: `View and fix issues`. Re-run, [VERBATIM]: **`Recheck score`**, and the outcome messaging is unusually explicit: *"If the revised items pass validation, a green banner appears at the bottom of the Canvas to confirm the score was updated. **If there was no change after a re-check, the banner confirms there was no change to the score.**"* Section heading [VERBATIM] `Improve brand alignment`.

**(e) Auto-fixed vs needs-attention: it never auto-fixes, so everything is needs-attention.** [VERBATIM] *"Click to fix guidelines that are not currently compliant."* The human fixes; the `Needs review` / `Passed` split is the closest thing.

**(f) Provenance: reasoning per check.** [VERBATIM]: *"**Use the reasoning provided for each check** to guide you in revising images and variants."* No rule ID, no severity, no confidence.

**Bonus, and highly relevant to the provenance hunt.** GenStudio has two separate provenance surfaces beyond Content check.

`Generative context` panel, [VERBATIM]: *"The Generative Context section shows what information was used to generate the experience, such as the `Prompt` used during the Create process."* Contents [VERBATIM]: *"`Brand`, `Product`, and `Persona` parameters selected during the Create process"*, *"`Subject line` and `Preheader` for email experiences"*, *"`Headline` and `Body` for Meta ads"*. And [VERBATIM]: *"You cannot edit the prompt once the content is approved."* `History` section, [VERBATIM]: *"a timeline of approvals and activity"*, rendered as `Approved / December 10, 2024 at 6:00 PM by Username`.

Content Credentials / C2PA, [VERBATIM]: *"GenStudio for Performance Marketing applies Content Credentials globally to all assets, automatically. There is no setup step and no per-asset setting to turn on."* Badge label [VERBATIM] `Brand signed`. Metadata shown [VERBATIM]: *"published brand, recorder, tool used, timestamp"*. Lineage, [VERBATIM]: *"the new credential links to the original"* and *"The embedded credential records the assets that the export was derived from, so an exported experience can be traced back through its edits to the original imported asset."*

Approval statuses, [VERBATIM]: `Notified`, `Needs work`, `Approved`. Detected-tag caveat, [VERBATIM]: *"apply attributes to ads and media based on a probability of correctness"* and *"You cannot edit tags that are detected and automatically applied."*

**No coverage or distinctness reporting.** `manage-variants.md` and `logo-swap.md` document swapping and regenerating but report nothing about how many placements were produced or how different variants are.

**Naming convention: dimension at the top, content-slot in the middle, nothing at defect level.** `Brand` / `Platform guidelines` / `Accessibility`, then `Headline` / `Color` / `Brand voice`. Findings are called "issues"; the sections are `Needs review` / `Passed`.

---

## 3. CreativeX

**(a) The six digital suitability fundamentals**, [VERBATIM] from `https://www.creativex.com/creativex-glossary`: *"these are the 6 digital suitability fundamentals that are the common denominator for all digital platforms and comprise the CQS:"*

`Brand early` · `Frame for Mobile` · `Optimal length` · `Optimize for Sound Off Consumption` · `Supers Present` · `Safe Zones`

**The five advanced principles**, [VERBATIM]: *"As brands become more sophisticated and consistent in applying these fundamentals, they can add 5 more core principles to their CQS. These are:"*

`Brand Audio Mention` · `Close Up` · `Pacing` · `CTA: Platform Button` · `Thumbnail Branding (Meta only)`

**Naming is not stable across surfaces.** The product page `https://www.creativex.com/products/creative-quality` lists a different set with different wording, [VERBATIM]: `Aspect Ratio`, `Brand Early`, `Safe Zones`, `Sound On`, `Supers Present`, `Video Length`, `Brand Audio Mention`, `CTA: Platform Button Close Up`, `Pacing`, `Thumbnail Branding`, `Close Up`, `And More Custom Guidelines`. Note `Aspect Ratio` replaces `Frame for Mobile`, `Sound On` replaces `Optimize for Sound Off Consumption`, `Video Length` replaces `Optimal length`, and `CTA: Platform Button Close Up` appears to be a rendering collision of two separate principles.

**(b)+(c) CQS is a single percentage, reported as an adoption rate.** [VERBATIM]: *"The Creative Quality Score, or CQS, measures an ad's digital suitability. CQS is calculated by tracking the presence of statistically validated digital suitability fundamentals, which are the common denominator across the biggest digital online platforms, and serve as the floor for effective digital ads."* And [VERBATIM]: *"Every metric that matters: tracked, scored, and condensed into a single Creative Quality Score (CQS) for your marketers and agencies to focus on."*

The percentage is explicitly a share-of-content figure, [VERBATIM]: *"the average Fortune 500 brand has a 20-30% CQS. **Only 20-30% of their content has incorporated basic digital creative best practices.**"* And [VERBATIM]: *"only 20% of an average Fortune 500 brand's ad incorporates all 6 basic digital best practices, and around 70% of their digital budget is invested into content that has a low CQS."* Band language is `low CQS` / `high CQS`, [VERBATIM]: *"shifting as much as 60% of their budget from digitally unsuitable ads (low CQS) to digitally suitable ones (high CQS)."*

**(d) Report structure.** Two named evaluation stages, [VERBATIM]: `Pre-flight evaluation` (*"Accelerate and de-risk your creative production by automatically checking all new content before it goes live"*) and `In-flight evaluation`. Glossary describes three uses, [VERBATIM]: *"To get started"* (historical baseline over 6 to 12 months), `Pre-Flight`, `In-Flight`. Named tool, [VERBATIM]: `CreativeX Pre-Flight tool`. Four feature labels, [VERBATIM]: `Centralize Content & Data`, `Global Visibility`, `Quality Control`, `Benchmark Your Wins`. The reporting cut dimensions, [VERBATIM]: *"by brand, market, platform, agency, and more"*.

**(e) No auto-fix, no auto-fix reporting.** CreativeX measures and gates spend; it does not modify creative.

**(f) Provenance: tags, not rule traces.** [VERBATIM]: *"All your content is labeled and tagged for the platform-specific creative attributes that comprise the Creative Quality Score. The CreativeX platform uses a combination of visual, text, and audio detection to determine and analyze the creative variables that are present."* Authority is attributed to the platforms, [VERBATIM]: *"Some of these are known as the Facebook Brilliant Basics or the YouTube ABCDs, but together, they map to the Creative Quality Score"*, and [VERBATIM]: *"validated in some fashion by platform partners, 3rd party research providers, CreativeX, and our clients."*

[UNVERIFIED] I found no public page showing the per-ad pass/fail rendering or the Pre-Flight result screen. The exact per-principle verdict label is unconfirmed.

**Sibling product vocabulary, useful for the master list.** `Creative Salience` names distinctive brand assets (DBAs) as, [VERBATIM]: `Sonic`, `Icon`, `Tagline`, `Color`, `Mascots`, `Packshots`, `Logos`, and [VERBATIM] defines them as *"visual, verbal, or auditory cues that trigger brand recognition without needing to say the brand name."* Three named failure modes, [VERBATIM]: `The Attribution Gap`, `The Multiplier Effect`, `The Loaned Brand`. `Inclusive Representation` reports [VERBATIM] *"by age, gender, and skin type as well as various situational settings."*

**Naming convention: the practice, stated as an imperative or a state.** `Brand early`, `Frame for Mobile`, `Supers Present`, `Safe Zones`. Not the dimension, not the defect, not an agent. This is the only product in the set that names practices, and it is the cleanest naming in the whole comparison. Glossary describes them, [VERBATIM], as *"the frame"*.

---

## 4. Vidmob

Richest published check taxonomy of any product here. Source: `help.vidmob.com` collection "Understanding Creative Scoring".

**(a) Guideline category names.** Vidmob's structure is `Category` → `Default Guideline Name` → `Guideline Description`. [VERBATIM] categories and their guidelines from `https://help.vidmob.com/en/articles/6519983-what-guidelines-are-available-for-creative-scoring`:

- **`Category: Brand Visibility`** → `Brand Name or Logo Early`, `Brand Name or Logo Present`, `Brand Visibility Threshold`, `Brand Name Mention`, `Brand Name Mention Late`, `Brand Name or Logo Late`
- **`Category: Formatting`** → `Video Length Within Range`, `Fits Aspect Ratio`, `Audio Present`, `Max File Size Met`
- **`Category: Key Visuals`** → `Human Early`, `Human Present`, `Positive Emotion Early`, `Positive Emotion Present`, `Scene Changes Early`, `Motion Early`, `User-Generated Content Present`, `User-Generated Content Early`, `User-Generated Content Late`
- **`Category: Messaging Effectiveness`** → `Word Limit Per Frame`, `Call to Action Present`, `Text Present`, `Text Visibility Threshold`, `Text and voice Early`, `Text and voice Present`, `Promotional Offer Present`
- **`Category: Product Visibility`** → `Product Benefit Present in Text`, `Product Benefit Present in Audio`, `Product Claim Present in Text`, `Product Claim Present in Audio`, `Product Feature Present in Text`, `Product Feature Present in Audio`
- **`Category: Regulatory & Compliance`** → `Disclaimer(s) Present in Text`, `Disclaimer(s) Present in Audio`, `Legal Terms and Conditions Present in Text`, `Legal Terms and Conditions Present in Audio`
- **`Configurable Guideline` / `Category: Other`** → `Custom Text Present`, `Custom Audio Present`, `Custom Color Present`. [VERBATIM]: *"Any client-specific custom guideline will be under the 'Other' category as well"*

A second, parallel taxonomy called **`Category Tags`** (descriptive, not pass/fail), [VERBATIM]: `Category Tags: Strategic Expression` (`Benefit` → Functional/Emotional/Promotional/Educational/Pricing; `CTA Type` → Engagement/Informational/Conversion/Other; `Tone` → Formal/Friendly/Engaging/Expressive); `Category Tags: Creative Approach` (`Production Type` → Live Action/Animation/CGI; `Production Level` → `Low (UGC)`/`High (Commercial)`; `Story Type` → Educational/Entertainment/Aspirational/Promotional); `Category Tags: Creative Components` (`Sound Type` → Music/Sound FX/Speech/No Sound).

Plus per-channel **`Channel Best Practices`** bundles, [VERBATIM] names: `Amazon Advertising Best Practices`, `Amazon DSP Best Practices`, `DV360 Best Practices`, `Google Ads Best Practices`, `LinkedIn Best Practices`, `Meta Best Practices`, `Pinterest Best Practices`, `Reddit Best Practices`, `Snapchat Best Practices`, `TikTok Best Practices`, `X Best Practices`. Their contents are written as natural-language assertions, [VERBATIM] examples: `Brand name or logo present in the first 2 seconds`, `Motion in first 3 seconds or text in first 3 seconds`, `Creative contains between 5 and 10 words per frame`, `Humanise the Story`, `Focused Messaging`, `Emotional Relevance`.

Rule construction, [VERBATIM] from the `Guideline Builder`: rule type is `Has` (*"The creative contains the selected guideline"*) or `Does Not Have`, and *"guideline types are grouped by categories, such as Branding, Audio, or Human Presence."*

**(b)+(c) PASS/FAIL, surfaced with an unusually complete state machine.** Methodology, [VERBATIM]: *"Creative scoring allows clients to set up scoring rules for their brands and submit media for **PASS/FAIL scoring** against those rules"*, and *"the media is sent to the content audit scoring function where **PASS/FAIL scores are automatically assigned**"*.

The per-guideline status has five values, [VERBATIM]: *"**Guideline Met Status**: Indicates if the asset meets the guideline (**Yes, No, Processing, Not Available, Not Run**)."*

Scores as well as pass/fail, [VERBATIM]: *"**Overall Score**: An aggregate score indicating the asset's overall performance across all guideline for a specific channel"* and *"**Individual Scores**: Detailed scores for each specific criterion."* Computation, [VERBATIM]: `Scoring(%) = (Sum of All Asset Compliance Scores ÷ Number of Assets)` and `Creative Score % = Passed Guidelines ÷ Applicable Guidelines`. Crucially, [VERBATIM]: *"**Total Guidelines** refers specifically to the **Total Applicable Guidelines**, meaning guidelines are only considered if relevant to the creative format."* And [VERBATIM]: *"Optional guidelines are displayed but do not contribute to the total count or overall calculation."*

Three named scoring methodologies, [VERBATIM]: `Scoring`, `Weighted Impression Scoring`, `Media Investment Scoring`, the last bucketing assets into [VERBATIM] `High-`, `Medium-`, or `Low-scoring tier`. Consideration labels, [VERBATIM]: `Mandatory` (weight 1+) and `Optional` (weight 0), with weights `0–100`.

Notably, Vidmob publishes a misreading warning, [VERBATIM]: *"Common misconception: 'Does 95% mean 95% of creatives are perfect and 5% failed?' No. It means the average creative score, weighted by impressions, is 95%. ... This percentage is not saying that impressions 'passed' or 'failed'."*

**(d) Report screens, named.** [VERBATIM]: `Adoption Report`, `Scoring Report`, `Impressions Scoring Report`, `Pre Flight Checks`, `In Flight Checks`, `Media Investment Report`, plus surfaces [VERBATIM] `In-flight Check`, `Pre-flight Check`, `Impression Scoring`, `Asset Investment`, `Creative Manager`, `Dashboard widgets`, `CSV exports`.

The per-asset screen is [VERBATIM] `Single Asset View`, with [VERBATIM] *"a top-line metric showing the percentage of guideline met per applicable channel"* and two tabs, [VERBATIM] `Guideline Score` and `Creative Elements`. The second is a locator: [VERBATIM] *"For videos and GIFs, a timeline indicates where and when creative elements are detected within the asset"*, and [VERBATIM] `View safe zone overlay` with *"The unsafe areas will appear in red on your creative."*

**(e) No auto-fix.** Vidmob scores and locates; it does not modify.

**(f) Provenance: the best "why this has no result" reporting anywhere in this set.** Vidmob publishes a 13-row table mapping `Reason` → `Status Pill Text` → `Why This Happens` → `Next Step`. [VERBATIM] status pill texts: `Rescore Needed`, `Not Applicable`, `Missing Data`, `Processing Issue`, `Access Issue`. [VERBATIM] example rows: `New Guideline Added After Scoring` / `Rescore Needed` / *"A new scoring rule was introduced after the media was last scored."* / *"Rescore the media to ensure all current guideline are applied."*; `Missing Brand Identifiers` / `Missing Data` / *"A brand identifier is required for scoring certain guidelines."* / *"Add the missing identifier to the Brand."*; `Race Condition Preventing Organization Guideline Scoring` / `Missing Data` / *"A system timing conflict caused guidelines to be skipped."* Also [VERBATIM] the framing: *"This tooltip enhancement provides clear explanations for why a creative receives an unavailable score, helping you determine whether this outcome is expected or if further action is needed."*

Detection provenance, [VERBATIM]: *"Content recognition analyzes each media item (statics, videos and GIFs) in the batch and **tags various elements (logo detected at X, audio beats per minute, etc.)** that are the inputs to the scoring functions. AWS, Google, and custom SageMaker models are leveraged."* Custom high-priority guidelines can carry a [VERBATIM] *"custom brand icon to highlight your unique, high-priority guideline, making it easy to spot your most important guidelines in reports."*

**Naming convention: dimension for the category, practice-as-state for the guideline.** `Brand Visibility` / `Messaging Effectiveness` are dimensions; `Brand Name or Logo Early`, `Audio Present`, `Fits Aspect Ratio` are states-of-the-creative. Never defects. Every guideline name is phrased as a condition that can be true.

---

## 5. Jasper Brand IQ

**(a) Names.** Hierarchy, [VERBATIM] from nav on `https://www.jasper.ai/brand-iq`: `Jasper IQ` / *"Governed marketing decision surface embedding context, rules, and brand logic."* containing `Brand IQ` → `Brand Voice`, `Visual Guidelines`, `Style Guide`; siblings `Marketing IQ`, `Product IQ`, `Knowledge`, `Governance`. [VERBATIM] from `help.jasper.ai`: *"Jasper IQ has six components"* (Brand Voice, Knowledge Base, Audiences, Visual Guidelines, Style Guide, Product IQ).

Dimensions named to the marketer, [VERBATIM]: *"Easily engage with and fine-tune brand settings like **voice, tone, style, and visual guidelines**, so that every output looks and sounds like you."*

Style Guide is the only place Jasper names individual rules, [VERBATIM] as section headings: `Oxford Comma`, `Em-Dash Rules`, `Case Sensitivity`, `Hyphen Normalization`, `Abbreviation Rules`, `Grammar & Punctuation`. Build buckets, [VERBATIM]: `Grammar & Punctuation Settings`, `Rules Extraction`, `Custom Style Instructions`.

**(b) Violation wording.** [VERBATIM], the only documented finding UI: *"The system will provide feedback based on your guidelines: If all images pass the guideline check, it will say **'All images approved'**. If some images do not pass the guideline check, **they will be listed along with the reason for not passing**."* Per-image verdict chips, [VERBATIM] from screenshot alt text: `Meets Guidelines` / `Doesn't Meet Guidelines`.

Marketing-level claims only, no example sentence published, [VERBATIM]: *"Jasper flags brand violations and suggests on-brand replacements"*; *"Jasper flags instances where the tone is off-brand and provides recommended adjustments"*; *"The only AI platform that can catch brand image violations and proactively recommend ways to fix them"*. The failure noun is **"brand violation"**.

**(c) Split: no score in-product, a score in the lead-gen diagnostic.** In-product, Visual Guidelines is pass/fail plus a list of failures with reasons; Style Guide is not reported at all. Context is summarised by a count, [VERBATIM]: *"you'll see a count of what's currently active, so you always know what's being applied."*

The free diagnostic at `https://www.jasper.ai/diagnostics/brand-compliance` is scored. [VERBATIM] CTA `Get Your Brand Score`. [VERBATIM]: *"**Get your Brand Compliance Score** / Receive an overall score plus **findings on voice, tone, style, and messaging alignment** powered by the same intelligence behind Jasper IQ."* And [VERBATIM]: *"Enter your company URL to get your **compliance score, findings, and recommended fixes** in under two minutes."* A conflicting name, `Brand Integrity Score`, appears on their blog. [UNVERIFIED] numeric range, as the report is gated behind an email.

**(d) Report screen.** [VERBATIM]: *"The Brand Compliance Score reflects how consistently your published content aligns with a unified brand voice, style, and messaging framework. It **surfaces specific areas where content drifts, such as tone inconsistencies, conflicting messaging, or stylistic variation across pages**, and provides AI-generated recommendations for how to bring content back on-brand."* Plus [VERBATIM]: *"delivers a scored report with specific findings, including **examples of where your content drifts off-brand and how to fix it**"*, and *"Every diagnostic generates a unique shareable link... Each link is permanent."*

For contrast, the sibling GEO Diagnostic does publish named sub-dimensions, [VERBATIM]: `Brand Presence`, `Citation Rate`, `Brand Sentiment`, each finding with *"supporting evidence, severity, and a recommended fix"*. Brand Compliance publishes no equivalent sub-dimension list.

**(e) Jasper is the one product that auto-fixes, and it deliberately does not report it.** [VERBATIM]: *"Jasper now applies style rules **automatically at generation time**... **You no longer need to manually apply suggestions after content is created.** Style is woven in from the first draft."* There is no diff, log, or changelog of what was auto-applied. Where Jasper does flag needs-attention, it is about its own config, [VERBATIM]: *"Automatic Style Guide Setup is an AI-recommended starting point, not a guaranteed auto-import. **Always review and refine** all three parts of the generated Style Guide after setup; Jasper may miss or misinterpret some rules."*

**(f) Provenance: weakest of the mature products.** Free-text reason only ([VERBATIM] *"along with the reason for not passing"*). No rule ID, no cited clause, no record of what the AI changed. Rule *origin* is shown at setup: a Style Guide is built from [VERBATIM] *"1-3 source documents"* via upload, URL, or Knowledge Base.

**Naming convention: the governance artefact, not the check.** `Brand Voice`, `Visual Guidelines`, `Style Guide`, `Product IQ` are all things you configure. Verdicts are phrased as conformance to the artefact (`Meets Guidelines`). No defect-level naming anywhere.

---

## 6. Filestage Review Agents

Source: `https://filestage.io/review-agents/`. **Filestage's help centre has zero Review Agents documentation** (485 English article URLs enumerated, no matches), so evidence is the marketing page plus its UI mockups.

**(a) The six agent names**, [VERBATIM] under the heading *"See what our Review Agents can do"*:

`Forbidden Terms Agent` · `Grammar Agent` · `Barcode Agent` · `Mandatory Images Agent` · `CLP Compliance Agent` · `Custom Prompt Agent`

There is **no "Brand Agent"** and no general compliance agent. Brand checking is folded into `Forbidden Terms Agent` and `Mandatory Images Agent`. `CLP Compliance Agent` is narrow (EU Classification, Labelling and Packaging) and is [VERBATIM] *"in early access"*.

**(b) What each reports**, [VERBATIM]:
- `Forbidden Terms Agent`: *"Checks files against your brand guidelines and compliance standards"* / *"Automatically enforces language rules across projects"*
- `Grammar Agent`: *"Catches spelling and grammar mistakes instantly"* / *"Saves your team manually proofreading content"*
- `Barcode Agent`: *"Scans QR and barcodes for broken links and unreadable data before review"* / *"Flags issues on packaging and product designs before they go to print"*
- `Mandatory Images Agent`: *"**Confirms every element is present**, including certification marks, recycling symbols, allergen icons, and brand logos"* / *"Frees up review time for real creative feedback"*
- `CLP Compliance Agent`: *"Automatically scans packaging designs for regulatory requirements"* / *"Flags compliance issues before they reach a human reviewer"*
- `Custom Prompt Agent`: *"Write your own review criteria as a prompt, or start from a ready-made ruleset"* / *"Your rules are applied automatically to every review"*

Headline, [VERBATIM]: *"Scale your reviews without missing a thing. Review Agents flag mistakes in copy, design, and compliance instantly."*

**(c)+(d) No score, no pass/fail, no report screen: findings are comments.** [PARA] from the product screenshots (`file-review-with-AI-reviewers.webp`, `project-dashboard-with-AI-reviewer-group.webp`): agent findings appear as **comment cards in the file viewer's comment sidebar, interleaved with human comments**, each card carrying a distinct per-agent glyph in place of an avatar, with the same resolve and thumbs-up affordances as a human comment, and offending copy highlighted inline in red. On the project dashboard the agents are a review step named [VERBATIM] `Filestage AI`, positioned before a human step column, and its roll-up uses ordinary approval vocabulary, [VERBATIM] `Approved`.

Their own noun for the output, [VERBATIM]: *"the output from any **AI comments**"*. The metaphor is explicit, [VERBATIM]: *"A Review Agent is basically an **automated version of your human reviewers**. They analyze your work based on set rules and criteria, then they offer comprehensive feedback."* Metering is per-review, [VERBATIM]: *"One review costs one credit, no matter the file size."*

**(e) No distinction, by design.** [VERBATIM] under the heading *"Own every decision"*: *"**Review Agents never sign off on anything.** They speed up human review by flagging issues, so your team can make the final call. That means **every review decision comes with a documented human sign-off**."*

**(f) Provenance: which agent authored the comment, plus the inline highlight.** No rule ID, no quoted clause, no confidence. Rule source described only at setup, [VERBATIM]: *"you can feed in company knowledge like forbidden words, writing guidelines, or mandatory images for designs."*

**Naming convention: the agent, named after the defect class it hunts.** Pattern is `<Defect or Artefact> + "Agent"`. The generic role noun is `Review Agent`; the workflow step is `Filestage AI`; findings inherit the existing primitive, comments.

---

## 7. Ziflow ReviewAI

Best-documented of the review-and-approval tier. Source: `help.ziflow.com` Zendesk API plus `https://www.ziflow.com/reviewai`.

**(a) Checklist categories are customer-authored, not vendor-supplied.** [VERBATIM]: *"ReviewAI analysis starts with your Ziflow checklists. It uses prompts that you add to your checklist items and compares those specified requirements against the proof content."*

Ziflow's own suggested categories, [VERBATIM] under *"ReviewAI works best for structured, rules-based checks such as:"*: `Brand compliance`, `Required disclosures`, `Grammar and spelling`, `Layout consistency`, `Presence or absence of required content`, `Packaging and labeling checks`.

Real UI from their screenshot: the panel is titled [VERBATIM] `Content Review`, and items sit under collapsible category headings with fraction counters, [VERBATIM]: `Compliance  0 / 1` → `Use approved legal disclaimer`; `Copywriting  2 / 4` → `Spelling and grammar correct`, `Product images match description`, `Detect regional spelling variations`, `Must contain the word "subscription"`; `Logo  1 / 1` → `Logo appears in the correct position`.

So a marketer sees **customer-written positive assertion sentences** under **customer-written dimension headings**.

Three named modules, [VERBATIM]: `ReviewAI for Checklists` (available), `ReviewAI for Change Verification` (`COMING SOON`), `ReviewAI for Brand Standards` (`COMING SOON`). The last, [VERBATIM]: *"Upload your curated brand standards and ReviewAI will automatically be able to flag violations during a review, from logo placement to tagline usage to fonts and colors."* Checklists is described as [VERBATIM] *"ensuring **completeness, consistency, and brand alignment**"*.

**(b) Two-layer finding: a verdict, then a written analysis and a pinned comment.** [VERBATIM] verdict definitions: *"**Pass**: The proof meets the checklist item requirement. / **Fail**: The proof does not meet the checklist item requirement. / **Not Relevant** [optional]: The checklist item is not relevant for the proof being reviewed (limited to 10-page static proofs)."* Their term of art, [VERBATIM]: *"ReviewAI uses your latest description to make pass/fail suggestions (called **suggested results**)."*

[VERBATIM]: *"To view more details about the AI suggestion, expand the checklist item. **ReviewAI includes text explaining why ReviewAI made its suggestion.**"* And [VERBATIM]: *"Every result from ReviewAI came with a **written analysis and a comment pinned to the exact frame or page**."* A real finding, [VERBATIM]: the ad *"failed 'Safety and imitability.' The checklist flagged that running outdoors in headphones is copyable behavior that reduces awareness of traffic and surroundings."* A real suggested comment, [VERBATIM]: author chip `AI`, body *"Could you please check the logo's color to ensure it matches the brand guidelines?"* Exclusion string, [VERBATIM]: *"the check results will explicitly state, 'This check was excluded from ReviewAI evaluation.'"*

**Ziflow is the only product that lets an admin dictate finding wording**, via documented `Comment Directives`, [VERBATIM]: *"Tone: Professional, neutral, non-blaming. / Voice: Imperative (e.g., "Update…", "Replace…", "Remove…"). / Length: comment\title ≤ 6 words; comment\body ≤ 30 words, single sentence. / Audience: Junior copywriter; avoid jargon. / Must Include: Quote the offending text in single quotes. / Must Avoid: Hedging ("maybe", "consider"), emojis, exclamation points."* With worked output, [VERBATIM]: *"Good title: "Disclaimer Missing" / Good body: "Add the legal disclaimer 'Terms apply' beneath the CTA." / Bad body: "It might be a good idea to maybe add a disclaimer here!""*

**(c) All four at once: pass/fail per item, fraction per category, progress bar per proof, and a reliability band per check.** [VERBATIM]: *"A progress bar at the top of the checklist shows the total number of items and how many have been reviewed (the color indicates passed, failed, and reviewed)."* Counter format [VERBATIM] `3 / 7`. [VERBATIM]: *"Not relevant results count toward the total item count but don't affect the pass/fail percentage."*

The reliability metric is a rare and notable pattern, [VERBATIM]: *"The reliability level is **the percentage of times that the ReviewAI suggestion agrees with the human review decision**. Run ReviewAI at least 10 times on the same checklist to generate a Reliability level: **Perfect** = 100% of the time. **High** = between 90-99%. **Medium** = between 70-89% and requires improvement. **Low** = below 69%. **Not evaluated**: There is not enough data collected."* Prompt-test labels, [VERBATIM]: `Correct`, `Incorrect`, `Unknown`.

**(d) The report is the checklist panel inside the Proof Viewer.** Contents, [VERBATIM]: panel title `Content Review`; a run button that becomes `AI checked`; standing disclaimer *"ReviewAI may make mistakes. Always double-check its results."*; progress bar plus `3 / 7`; category rows with fractions; per-item pass/fail buttons plus reviewer avatar once answered; expandable rationale; suggested comments authored by a pseudo-user, [VERBATIM] *"display in the comments section of the Proof Viewer as user 'ReviewAI'"*. Exports, [VERBATIM]: *"The Comments CSV export now includes the **Checklist Item Template ID and ReviewAI's suggested result** for each checklist item"* and *"**ReviewAI Suggestion and ReviewAI prompt version**... enables administrators to analyze the effectiveness of automated checks."* Audit, [VERBATIM]: *"provides audit-ready documentation for every AI-assisted result."*

**(e) Never auto-fixes; the named distinction is AI-suggested vs human-confirmed.** [VERBATIM]: *"ReviewAI suggestions are not final decisions. Reviewers: **confirm** correct suggestions / **override** incorrect suggestions."* And [VERBATIM]: *"Select Pass or Fail manually to verify or change the suggestion as required. When you do so, the suggestion changes to your decision. You can still view the AI suggestion by expanding the checklist item."* Comment-level, with authorship transfer, [VERBATIM]: *"When you verify the checklist item suggestions, you can choose to **post or ignore** the suggested comments... When you post a ReviewAI suggested comment, **the comment author changes from ReviewAI to your name**."* Un-adjudicated output is marked visually, [VERBATIM] *"AI highlighting"*.

**(f) Provenance: the strongest rule-level trace in the review-tool tier.** Rationale text per item; **versioned prompts**, [VERBATIM]: *"Each time you edit and save the checklist item description, a new major version is stored (V1 -> V2). Each time you edit and save the ReviewAI prompt description, a new minor version is stored (V1.0 -> V1.1)"*; the prompt version is exported alongside the result; location provenance via pinned comments, [VERBATIM] *"comments that apply to a page without a specific markup location (for example, a missing disclaimer) are displayed as pins beside the proof"*. Input provenance includes Proof Brief text, Custom Property data, asset metadata, and font metadata.

A documented two-field separation of human-facing and AI-facing rule language, [VERBATIM]: *"**Checklist item description** | Human-readable reviewer guidance. Example: 'Disclosure appears on the first page.' | Reviewers"* versus *"**ReviewAI prompt description** | Detailed AI prompt instructions used during ReviewAI analysis. Example: 'Pass only if the exact disclosure text appears fully visible on page 1.' | ReviewAI"*.

Their stated philosophy of flagging rather than deciding, [VERBATIM]: *"The check treats health content as flag-worthy by default and **hands the call to a person instead of deciding quietly in its machine brain**."*

**Naming convention: engine plus surface, then customer-named checks.** `ReviewAI for <Surface>`. Verdicts `Pass` / `Fail` / `Not Relevant`; output is a `suggested result` plus a `suggested comment`; run state is `AI checked`.

---

## 8. Frontify

Frontify has **no shipped brand-check product**. Its `Agentic hub` capability list contains no compliance checker, [VERBATIM] the eleven entries: `MCP for AI Tools`, `Brand Assistant`, `Automations`, `AI Translations`, `Enhanced Image Search`, `Auto-tagging`, `Duplicate Detection`, `Image Generation`, `Predictive Metadata`, `Content / Guidelines API`, `OCR-based Content Search`. `Brand Assistant` is a chat interface, [VERBATIM] *"trained on your brand guidelines to answer questions, draft content, and ensure brand consistency"*, not a checker.

**What the "ratings" actually are.** They belong to an experimental Marketplace app, documented on Frontify's "Kitchen" (their R&D publication), `https://www.frontify.com/en/kitchen/brand-check-with-specs-the-reviewer-that-knows-your-guidelines`, updated February 9, 2026. [VERBATIM]: *"This led us to our first experiment, the **Brand Check app**, which analyzes your assets against your guidelines and reports issues automatically. After installing the app from the Frontify Marketplace, users can set up automations in a library or project and run the brand check when new assets are created or when the workflow status of an asset is changed. When users view an asset, they open the app to get **a detailed report including visualizations, issues, and ratings**."*

That single clause is the entire published description of the ratings. [UNVERIFIED] what scale the ratings use, what they are attached to, or what the report screen looks like. No screenshot, no help article, no label list exists publicly.

**The successor is an agent, named `Specs`.** [VERBATIM]: *"**Specs is an AI agent that knows your guidelines inside and out** and has a sharp set of (proverbial) eyes."* and *"rather than adding another chat interface, **Specs lives in your workflows** and collaborates like any other team member."*

**(a) Checks are natural-language tasks written by the customer.** [VERBATIM]: *"you create review workflows with statuses like "Design review," and set up checklists with tasks in plain language:"* then the five examples: `Check text for spelling and grammar`, `Review logo usage and placement`, `Verify fonts after a rebranding`, `Flag images with certain content`, `Ensure text follows tone of voice guidelines`.

**(b)+(d) Findings are comments; completion is a checked-off task.** [VERBATIM]: *"**Specs reviews and reports**: When assets come in, Specs analyzes them, **leaves comments about issues, and makes suggestions with references to your guidelines. Then it checks off completed tasks.**"*

**(e) Frontify is the only product in the set that names handled-vs-escalated as a design goal.** [VERBATIM]: *"Specs **catches the clear-cut issues** that would otherwise slow everyone down **and delegates the task to the right people when human judgment is needed**."* With the consequence spelled out, [VERBATIM]: *"A creative director can focus on impact rather than checking disclaimers. A brand manager can hone in on positioning rather than measuring logo clear space. **A legal reviewer only sees assets that have already passed technical screening.**"* Note this is routing, not auto-fixing, and it is still [VERBATIM] *"still in development"*.

**(f) Provenance:** [VERBATIM] *"suggestions with references to your guidelines"*, and at setup [VERBATIM] *"You can **reference specific guideline pages**, include assets as references, or delegate tasks to creative directors or someone from the legal team."*

**Naming convention: the agent, given a human name (`Specs`), plus customer-written task sentences.** Reviewer-as-teammate metaphor, [VERBATIM] *"Invite Specs as a collaborator... just like any team member."* No dimensions, no defect names, no published rating labels.

---

## 9. Bynder Brand Compliance Agent

**Name correction:** there is no "Compliance Agent". The agent is `Brand Compliance Agent` and the capability is `Brand Compliance`. [VERBATIM] article title: *"Brand Compliance Agent: Automated Brand and Regulatory Review"*. [VERBATIM] picker label: *"**Brand Compliance**: Ensure consistency inside your DAM."*

**(a) Categories the agent audits against are customer-authored free text, with Bynder examples.** [VERBATIM]: *"The agent evaluates each asset against your rules, **grouped into categories you control**. For example:"* then a `Category` / `What it looks at` table:

| Category | What it looks at |
|---|---|
| `Visual identity` | *"Logo placement, size, clear space, and color treatment; logo integrity (distortion, effects, proportions); brand color palette; typography; iconography"* |
| `Typography in PDF documents` | *"Font family, weight, style, and size, read directly from the document's embedded font data rather than from an image scan."* |
| `Photography and imagery` | *"Photography and stock image guidelines"* |
| `Voice and messaging` | *"Tone of voice and brand voice; messaging and layout"* |
| `Regulatory and legal` | *"Regulations; market claims; accessibility"* |
| `Format` | *"Channel specifications"* |
| `Safety` | *"PPE (Personal Protective Equipment Compliance), hazard-depiction compliance for industrial customers"* |

A **second, non-matching** list appears in Bynder's own rule-writing guide, [VERBATIM] under `Good Rules Usually Check`: `Logo`, `Color`, `Typography`, `Layout`, `Photography`, `Iconography`, `Brand Voice`, `Technical Specs`, `Asset Properties`. The inconsistency between two published Bynder lists confirms these are typed labels rather than a fixed taxonomy.

Marketplace example-agent names are defect-or-object flavoured, [VERBATIM]: `Accessibility Compliance Validation`, `Logo & Brand Detection Agent`, `Brand Guidelines Checker`, `Asset Hygiene Detection Agent`, `Restricted Objects Detection Agent`, `Text Policy Compliance Agent`, `Sustainability Claims Detection Agent`, `PPE & Safety Detection`, `Safety Compliance Agent`, `Loi Evin Compliance Agent`.

**(b) The finding text is the customer's own rule sentence, whose grammar Bynder mandates.** [VERBATIM] template: *"[If condition applies:] [subject] must/must not [requirement] [visible criteria, exact values, examples, or exception]."* [VERBATIM] examples: *"If the logo is present: it must not be rotated from its original horizontal orientation."*; *"If a headline is present: it must not be written in all caps."*; *"Dominant brand colors must come from the approved palette: Brand Blue #047DBA, Dark Blue #004656, White #FFFFFF, Green #90FFBB, and Yellow #E0FF48."* Per-rule decision, [VERBATIM]: *"For each rule, the agent needs to decide: **the asset follows the rule / the asset breaks the rule / the rule does not apply to this asset**."* Operative adjective is `non-compliant`.

[UNVERIFIED] No screenshot or sample rendered finding exists publicly. Genuine gap.

**(c) A four-value categorical verdict per asset, and the customer must build the field by hand.** [VERBATIM]: *"Set up a compliance metaproperty. In your taxonomy, create a new metaproperty (any name you like) as a single-select field with **four options: 'Compliant', 'Non Compliant', 'Partially Compliant' and 'Not Applicable'**. The agent writes its results here."* No score. [VERBATIM] on N/A as first-class: *"PDF without extractable text | Font rules are marked as **not applicable rather than pass or fail**."* Score language appears only in a marketing prompt example (*"Generates compliance score"*) and is contradicted by the knowledge base.

**(d) Report screens.** [VERBATIM]: *"Open the report on any asset to see the **rule-by-rule breakdown, which rules passed, which failed, and why**."* Run screen, [VERBATIM]: *"Each asset shows its **proposed** compliance status"* and *"Review the **side-by-side comparison** screen showing: **Current content**: your existing asset metadata. **Agent suggestions**: the new edits proposed by the agent."* Bulk controls [VERBATIM] `Discard all` / `Accept all`; per-row `N suggestion(s)`. Actions [VERBATIM]: `Approve` (*"applies the suggestion and updates the asset's metadata"*), `Discard` (*"leaves the asset unchanged"*), `Edit`. Page-level provenance, [VERBATIM]: *"PDF issues include the relevant page number, and PDFs can be previewed directly in the compliance report."* Published limits, [VERBATIM]: `Assets per run | 1,000 maximum`, `PDF page count | Up to 30 pages per document`, `Maximum 50 rules or 10K characters per agent`.

**(e) No auto-fix; the axis is proposed vs approved, and Bynder keeps both records.** [VERBATIM]: *"A run doesn't change your taxonomy on its own, unless Auto-apply is enabled... The agent only **proposes** a compliance status per asset; someone with Manage Agents permission reviews it before anything updates, and has the final say."* And [VERBATIM]: *"**Auto-apply removes the review step, not accountability.**"* The best disagreement-preservation language found anywhere, [VERBATIM]: *"**Even if you override the agent's conclusion, its original report stays available on the asset's detail page, so anyone can see what the agent found versus what a human ultimately decided.**"* Plus [VERBATIM]: *"Overrides are auditable. Any compliance decision you change gets logged in the agent's **History tab**, giving you a full record of **proposed-versus-final status** for every asset."* Re-check loop, [VERBATIM]: *"**Compliance Re-check**: When you upload a corrected version of a non-compliant asset, the brand compliance agent automatically re-runs to make sure the new version passes."*

Needs-attention queue is customer-built, [VERBATIM]: *"build a saved smart filter or smart collection scoped to the compliance metaproperty... For example, 'all Partially compliant' as an in-review queue, or 'all Non-compliant' as the backlog that still needs action."*

**(f) Provenance: rule-level only, no citation to a source guideline document.** [VERBATIM]: *"Each rule is evaluated on its own."* Evidence attachment, [VERBATIM]: *"Add a Reference Asset to a Rule... Each rule can reference one asset"*, used to [VERBATIM] *"extract and compare logos against a master reference"*. Explicitly not a guideline transcription, [VERBATIM]: *"**The aim is not to rewrite your full brand guidelines.** The aim is to write clear rules that tell the agent exactly what to inspect and what counts as compliant or non-compliant."*

**Naming convention: agent plus dimension, with no defect vocabulary.** Four layers: capability/agent → customer-typed dimension → four-value verdict → the customer's `must` / `must not` sentence as the finding. "Violation", "error", "severity" and "issue type" do not appear as UI labels.

---

## 10. Veeva Vault PromoMats Quick Check Agent

Confirmed as the most mature rule-based reporter in the set, and the most instructive, because **Veeva shipped defect-category naming and prescriptive advice and then deliberately deleted both.**

**(a) The named checks.** Panel header [VERBATIM] `QUICK CHECK AGENT`. The checks, [VERBATIM] from `https://commercial.veevavault.help/en/gr/848672/`:

`Spelling` · `Grammar` · `Phrase Assessment` · `Boxed Warning (United States Only)` · `Important Safety Information (United States Only)` · `Privacy Policy Link` · `Unsubscribe Link` · `Accessibility`

Hard constraint, [VERBATIM]: *"**Note: Veeva defines these quality checks. You cannot edit these checks or add custom ones.**"* This is the opposite of Bynder, Ziflow and Frontify.

Two agents, [VERBATIM] `Quick Check Agent` and `Content Agent`. The five guideline dimensions claimed, [VERBATIM]: *"Quickly surface **editorial, brand, market, channel, and compliance** considerations before content reaches MLR."* Named internal actions surfaced to admins, [VERBATIM]: `ISI Identification`, `ISI Analysis`, `Reviewer Summary`, `Ask Questions`, `Analyze Images`, `ISI Extraction`.

**(b) Finding wording, current (26R1): page number, then verbatim quoted source text, then a neutral observation.** Format is `Page <n>: <quoted document text>` with the page number as a hyperlink, then a bullet prefixed `Suggestion:`. [VERBATIM]:
- `Page 2: Natevba offers durable efficacy for XA+ NHL patients unresponsive to conventional therapy (rrXA+ NHL)1`
  - `Suggestion: Uses a comparative qualifier ("unresponsive to conventional therapy") applied to a patient population.`
- `Suggestion: Uses a comparative quantifier ("Fewer than 10%") applied to a safety attribute.`

**The de-escalation, documented and dated.** The 25R3 screenshot shows the same check with a **defect-category heading** above each finding and **prescriptive advice**, [VERBATIM]: heading `Absolute/Superlative` → `Page 9: the only treatment to target X-antigen` → `Suggestion: Confirm that this exclusivity claim is accurate and supported by a comprehensive competitive landscape analysis...`; heading `Comparative Assertion` → `Page 12: Minimal toxicity compared to chemo`.

In 26R1 both the category headings and the advisory voice are gone, and the doc states the new rule, [VERBATIM]: *"**This check provides a plain description of the wording it has identified via neutral observations with no advisory-style suggestions or regulatory categorization.**"* The label `Suggestion:` survives even though the content is no longer a suggestion.

Corroborating the trend: the product was formerly named `MLR Bot` and this check was formerly `Red Flag Phrases`, [VERBATIM] from a 2025-09-09 Wayback snapshot: *"**Red Flag Phrases** | This check identifies phrases that could indicate non-compliance with regulators, such as unsubstantiated claims, risk minimization, and off-label uses."* Renamed to `Phrase Assessment`, [VERBATIM]: *"This check identifies wording and phrases that **may require further scrutiny**, including those suggesting promotional or potentially misleading language."*

Their own marketing is stale and contradicts the shipped UI, [VERBATIM] from the Features Brief: *"Phrase Assessment... **Categorizes findings and provides advisory suggestions** to guide compliant rewording or balancing."*

**(c) No score. Three-state icon per check plus a defect count.** [VERBATIM]: *"When the quality checks are complete, **each check displays an icon to indicate whether the check passed () or identified issues ()**. Click the check title to expand or collapse the section. Quick Check Agent displays  **if it encounters an error**, such as when the document exceeds the page limit or the LLM responds with an invalid message."* Icon semantics from the raw HTML: passed is a green `fa-check-circle` (#539137), issues is an amber `fa-exclamation-triangle` (#cc6600), error is a red `fa-exclamation-circle` (#ce1400).

Counts sit in the collapsed row title, [VERBATIM]: `Spelling (6)`, `Grammar (2)`, `Phrase Assessment (9)`, `Important Safety Information (9)`, `Accessibility (3)`.

The only rating in the product rates **the reviewer's workload, not the asset**, [VERBATIM]: *"The **Complexity Assessment** section can calculate a **review difficulty rating of Low, Medium, or High**, based on specific evidence from the document, such as the number of clinical charts requiring data verification or the presence of comparative claims, for up to three supporting points across **data density, claim rigor, and regulatory risk**. This helps reviewers understand and estimate the effort required because they can see exactly what has driven the complexity rating."*

**(d) Report screen, field by field**, [VERBATIM] top to bottom: header `QUICK CHECK AGENT` plus a help `?` and a re-run icon; one collapsed accordion row per check that ran (amber triangle, underlined check name, count); a separator label **`Not Applicable:`** below which inapplicable checks appear **with no icon and no count** (`Boxed Warning`, `Privacy Policy Link`, `Unsubscribe Link`); a timestamp `Generated on 14 Oct 2025 10:23 PM CDT`; and a footer disclaimer **`Large Language Models can make mistakes. Always verify results.`**

The `Not Applicable:` bucket is the standout design move: inapplicable checks are neither hidden nor scored, they are demoted to a labelled, countless, iconless group. [VERBATIM]: *"If the document is not for the United States, the Boxed Warning check is hidden and does not run"* and *"If there is no related ISI document, Quick Check Agent determines this check to be Not Applicable."*

Per-finding action menu with single-key accelerators, [VERBATIM]: `Copy Suggestion  C` · `Annotate  A` · `Learn Term  L`. [VERBATIM]: *"**Learn Term**: Creates a new Allowed Term record based on the selected text, automatically populating the record with all the document's Brand and Country values."*

ISI findings carry their own four-state vocabulary, [VERBATIM]: *"...to see if each statement is **present, present but reworded, missing, or if there are statements in the material that are not found in the Related ISI document**."*

**(e) Auto-fixes nothing, and by default persists nothing.** [VERBATIM]: *"**By default, Vault does not save any detected issues to the document**, but you can choose to save specific issues as comment annotations by clicking the **Save As Annotation** () button."* And [VERBATIM]: *"**The Quick Check Agent quality check outcomes are not audited, and are not reportable.** Quality check results are specific to the document version being assessed."*

The closest thing to a fix is a suppression-and-learning loop, [VERBATIM]: *"users can convert specific findings into **Allowed Terms**, effectively telling Quick Check Agent not to raise these items again in the future"*, with the inverse [VERBATIM]: *"Business Admins can also define **Prohibited Terms**... Quick Check Agent displays the specific term matches and **whether the match is exact or a close variant**."* Gating happens in the lifecycle, [VERBATIM]: *"you can add the **Quick Check Agent** entry criteria to any document lifecycle state."*

**(f) Provenance, for the non-technical user, is exactly three things: the clickable page number, the verbatim quoted source text, and the `Suggestion:` line naming the pattern.** No rule ID, no confidence score, no severity, no link to a source guideline. [VERBATIM]: *"To navigate to an identified issue, click the page number to jump to the issue or the page the issue is on."*

Notable scope-provenance strings, [VERBATIM]: *"This check flags a document only when it contains data collection content, such as a form, a sign-up call to action, or a statement regarding how personal data is used, and **points to the specific text and page that trigger the finding**."*; *"Quick Check Agent integrates directly with your **Claims Library**, automatically treating Eligible Claims as Allowed **to prevent false positives**."*; and explicit over-flagging suppression, *"If the document is a Prescribing Information or labeling document, the check does not flag language that appears in the document's safety sections... Promotional-language patterns in an attributed quotation or patient testimonial also are not flagged."* One check cites external authority, though only in marketing, [VERBATIM]: *"**citing relevant CFR regulations**."*

Deep provenance exists but is admin-only JSON, not marketer-facing: `Tracing Agent Actions` with [VERBATIM] `Trace Session ID` → `Agent Action Traces` → `Requests` → `Messages` → `Role` (`System`/`User`/`Assistant`) → `Content Blocks`, and a redaction string [VERBATIM] *"You cannot access this information"*.

**Bonus: Veeva Falcon MLR** (the acquired Copli product, `falconmlr.veeva.com`) uses a **different** structure that adds what Quick Check deliberately lacks. [VERBATIM] from its DOM: left-panel tabs `Findings` | `Anchors`; findings grouped under `PAGE 3`, `PAGE 6`; per-finding severity dots; right panel `Document Summary`, `Finding Detail`, a badge reading **`Medium Risk`**, and a **`Sources`** section. Tagline [VERBATIM]: *"With **Agentic MLR™**, target a 70%+ reduction in manual labor"* and *"Every local code. One upload. FDA, ABPI, ENLI, automatically checked."*

**Naming convention: the dimension or artefact for the check, the act for the agent, and defect names actively deleted.** Checks are bare noun phrases naming what is inspected (`Spelling`, `Boxed Warning`, `Privacy Policy Link`), never the defect. One check is named after the act of judging (`Phrase Assessment`), explicitly chosen over the defect-flavoured `Red Flag Phrases`. Findings are called `issues`; the run is `quality checks`. "Violation" and "severity" do not appear in the Quick Check UI.

---

## 11. Papirfly, Lytho, Air, Brandfolder, Smartly, Celtra

### Lytho: the strongest find in this tier

**(a)** The checking entity is an **`AI Reviewer`** and each check is a **`Skill`**, under two headings, [VERBATIM] from `https://help.lytho.com/ai-reviewers`:

`Regulatory Compliance Skills`: `AI Disclosure & Transparency (Image + Text)`, `Call-to-Action Clarity (Image + Text)`, `Email Opt-Out & Sender ID (Image)`, `Footer Elements (Image + Text)`, `Grammar & Placeholder Detection (Image + Text)`, `Image Quality (Image)`, `Prohibited Words & Phrases (Image + Text)`, `Promotional Messaging (Image + Text)`, `Required Words & Phrases (Image + Text)`, `Unverified Claims (Image + Text)`

`Brand Compliance Skills`: `Brand Colors (Image)`, `Brand Typography (Image)`, `Brand Voice & Tone (Image + Text)`, `Logo Usage (Image)`

The `(Image + Text)` / `(Image)` suffix is part of the user-visible label, declaring the modality inspected.

**(b)** Three named statuses, each with its own definition, [VERBATIM]: *"**Fail**: The content does not meet compliance requirements and requires updates."* / *"**Flagged**: A potential issue was detected, but **the AI Reviewer is not fully certain**."* / *"**Pass**: The content meets the selected compliance criteria and no issues were detected."* The middle state is a **confidence hedge**, not a medium severity. That is the only calibrated-uncertainty label found in this entire study.

**(c)+(d)** No score. [VERBATIM]: *"An overview of the AI Reviewers applied, along with their finding statuses, will be available for each asset where AI Reviewers were used."* Placement, [VERBATIM]: *"Open the Review to view AI Reviewer findings, which **appear as annotations with comments alongside human feedback**."* Report columns include [VERBATIM] `# of Reviewer Comments`, `Total # of Assets`, `Reviewer Approval Status`, `Overall Version Status`, `Proof Status`.

**(e)+(f)** No auto-fix. Each finding comment has exactly three named parts, [VERBATIM]: **`Analysis`**, **`Flagged Items`**, **`Suggested Fix`** (reason, pinpoint citation, remedy). Positioning, [VERBATIM]: *"**AI handles the checks, your team makes the decisions**"*, *"flag brand, legal, and regulatory issues before approval"*, and *"Track every check, comment, and approval, automatically"*.

Adjacent Lytho AI units use capability naming, [VERBATIM]: `Project Summary`, `Activity Recap`, `Status Update Generation`, `Risk Assessment`, `Blocker Identification`, `Comment & Feedback Triage`.

Naming convention: **agent (`AI Reviewer`) + skill (the check) + three-state status**.

### Papirfly: one real checker, preventive elsewhere

**(a)** `Image Quality Checker` with dimensions [VERBATIM]: `Ratio`, `Resolution`, `Format`, `Sharpness`, `Orientation`, plus a sixth named defect on their AI page, [VERBATIM] *"asset resolution, format, sharpness, product orientation, and **hard blur**"*. Other AI units [VERBATIM]: `Auto-tagging`, `Duplication manager`, `Image quality checker`, `Facial recognition for GDPR compliance`.

**(b) through (f): nothing published.** Only marketing result-language, [VERBATIM] *"Instantly identify the good, bad, and ugly"*.

Papirfly's brand compliance is **preventive, so there is no report by design**, [VERBATIM]: *"Lock in key brand features that must never change"*, *"Create flexible elements where users choose from pre-approved options"*, *"brand elements are locked down"*.

### Air: nothing on brand checks

AI is named `Intelligence`, [VERBATIM] help titles: *"Explore Image Intelligence"*, *"Explore Video Intelligence"*. Output fields [VERBATIM]: `Smart Summary`, `Smart Tags`. Approvals are **manual status fields, not checks**, [VERBATIM] values: `To Review`, `Approved`, `Changes Requested`, `Final`, `Needs Approval`, `Changes Needed`.

### Brandfolder: nothing on brand-guideline checking

`Brand Intelligence` exists but is tagging and analytics, [VERBATIM] tagline *"Brand-specific, AI driven tagging and analytics"*, capabilities *"automated tagging"* and *"duplicate detection"*. The only score term is [VERBATIM] `asset score`, and it is a usage metric, not compliance. help.brandfolder.com now 301s to help.smartsheet.com/brandfolder/, whose category list contains no Brand Intelligence or guidelines-check article. Control is templating plus proofing, like Papirfly.

### Smartly: no rule-compliance check; "pre-flight" means prediction

Product names [VERBATIM]: `Template Editors`, `AI Studio`, `Producer`, `Creative Insights`. The closest thing to preflight is predictive, [VERBATIM]: *"AI-powered **pre-flight insights** like **heatmaps, attention scores, and decay curves**"* that *"predict what will perform before you go live"*. Also [VERBATIM] *"Brand governance built into every workflow"*. A keyword pass over `docs.smartly.io/llms.txt` found **no** article titled with validation, check, preflight, spec, brand, quality, review, or score. [UNVERIFIED] whether ad-spec validation exists in-product.

### Celtra: `Celtra Score` exists as a label and is nowhere defined

Feature names [VERBATIM]: `Creative Automation`, `Dynamic Product Ads`, `Creative Enablement`, `Celtra Score`, `Node-based GenAI design`, `agentic workflows`, `AI creative intelligence`. No page describes Celtra Score's dimensions or output; `celtra.com/celtra-score/` is 404 and neither sitemap contains a score, QA or validation page. **No "Design QA" exists anywhere.** [UNVERIFIED] what Celtra Score measures.

### Also checked, both negative

**Rocketium**: `docs.rocketium.com/llms.txt` has no brand-check, compliance, score, review or audit article. Brand Kit is preventive, [VERBATIM] *"ensure 100% brand compliance through access roles"*. **Storyteq** support is login-gated; **Bannerflow** has no reachable help centre. Neither yielded check vocabulary.

---

## 12. Canva: unreachable

Every Canva help, newsroom, sitemap and canva.dev URL returned **403** to both WebFetch and curl with full browser headers, including `canva.com/sitemap.xml`. **No Canva brand-check vocabulary was obtained.** Zero verbatim evidence for "off-brand", "brand controls" or "Brand Guidelines check" as Canva UI strings. [UNVERIFIED] in full. This session has Canva MCP tools available (`list-brand-kits`, `get-brand-template-dataset`), which would expose Brand Kit *data* structure but not the marketer-facing check copy, so it is only a partial substitute. Closing this gap needs a real browser or different egress.

---

## BONUS: Markup AI (formerly Acrolinx), not on the list but the purest agent-naming example found

Acrolinx rebranded to **Markup AI**; `docs.acrolinx.com` now 302s to `docs.markup.ai`. It is the cleanest agent-convention specimen in existence, with 15 named agents each carrying a one-line promise and a category.

**(a)** [VERBATIM] from `https://docs.markup.ai/agents.md`, an `Agent` / `What it does` / `Category` table:

`AI Voice` (*"Make AI-assisted drafts sound like you wrote them."*, `Content Integrity`) · `Brand Terms` (*"Keep every word on the approved list."*, `Brand`) · `Brand Voice` (*"Sound like your brand, everywhere."*, `Brand`) · `Claims` (*"Catch risky claims before compliance does."*, `Accuracy`) · `Date & Time Accuracy` (*"Catch dates and times that can't be right."*, `Accuracy`) · `Fluff` (*"Get to the point, and stay on it."*, `Content Integrity`) · `Freshness` (*"Never publish stale facts again."*, `AI Visibility`) · `Key Takeaways` (`AI Visibility`) · `Link Integrity` (*"Every link goes where it says it goes."*, `Accuracy`) · `Persona` (*"Read your content through your buyer's eyes."*, `Brand`) · `Q&A Optimization` (`AI Visibility`) · `Sentence Clarity` (`Content Integrity`) · `Snippet Readiness` (`AI Visibility`) · `Source Authority` (`AI Visibility`) · `Style` (*"Your whole style guide, applied in one pass."*, `Brand`)

So: four dimensions (`Brand`, `Accuracy`, `Content Integrity`, `AI Visibility`) over fifteen agents.

**(b)+(c) `Risk-based scoring`, and an explicit refusal to invent numbers.** [VERBATIM]: *"each issue they surface is assigned a risk level, **High**, **Medium**, **Low**"*, with a published meaning table, [VERBATIM]: *"**High** | Issues that are very likely wrong and could undermine credibility, compliance, or brand standards. **Address these first.**"* / *"**Medium** | Issues that may confuse readers or create inconsistency."* / *"**Low** | Stylistic refinements that improve polish and readability. Address these when time allows."* Rationale, [VERBATIM]: *"Risk levels give you a **consistent way to prioritize across every agent**. No matter which agent flags an issue, the same High/Medium/Low scale lets you triage at a glance."*

The numeric score is optional and gated, [VERBATIM]: *"If your organization has numeric scoring enabled, the action layers a **0-100 quality score and a per-goal breakdown (Clarity, Grammar, Tone, Consistency, …)** on top of the risk view, **never replacing it**. Otherwise you'll see the risk-based assessment alone, **with no fabricated scores**."*

**(d) A fully published report structure.** [VERBATIM]: *"Each file gets a risk label derived from its worst issue, **🔴 High**, **🟡 Medium**, **🟢 Low**, or **✅ No issues**, alongside a breakdown of issue counts by severity. **The overall risk is the worst level across all analyzed files.**"* The rendered example, [VERBATIM]:

```
🔍 Markup AI Analysis Results
| File      | Risk      | Issues | Breakdown                  |
| README.md | 🔴 High   | 13     | High: 9, Medium: 4, Low: 0 |
📊 Summary
Overall Risk: 🔴 High
Files Analyzed: 4
Total Issues: 31 (High: 9, Medium: 14, Low: 8)
```
Plus a one-line status, [VERBATIM]: `Risk High | Files 2 | Issues 107 (High: 71, Medium: 36, Low: 0)`.

**(e) The clearest fixable-vs-not distinction found anywhere.** [VERBATIM] per-issue actions: *"**Apply Change**: replace the flagged text with the suggested fix."* / *"**Add Suggestion**: insert the fix as a Google Docs suggestion (tracked change) for someone to accept or reject."* / *"**Add Comment**"* / *"**Mark as Resolved**: **available when an issue has no one-click fix**; use it to clear an issue once you've handled it yourself."* / *"**Dismiss**: set an issue aside without changing your document."* And [VERBATIM]: *"**Will the extension change my document without asking?** No. It only edits your document when you choose Apply Change or Add Suggestion."*

**(f)** [VERBATIM]: *"Each issue shows **the agent that found it, a severity badge, the flagged text, and an explanation**, and the text is highlighted in your document, color-coded by severity."* Two run modes, [VERBATIM] `Guided` (*"Choose the goal you are trying to accomplish and Markup AI selects the right agents for that goal"*) and `Manual`.

---

## SPECIAL HUNT 1: AI generation provenance and decision trace

**Adobe Content Credentials / C2PA is the only mature, fully specified vocabulary.** The complete shipped user-facing string set lives in `github.com/contentauth/verify-site/blob/main/locales/en-US.json`.

Panel and field labels, [VERBATIM]: `Content Credentials` · `Content summary` · `About this Content Credential` · `Issued by` · `Issued on` · `Process` · **`App or device used`** · `Actions` · **`Ingredients`** · `Credit and usage` · **`Produced by`** · **`AI tool used`** · `Social media accounts` · `Web3 addresses` · `AI model usage` · `Camera capture details` (`Capture date`, `Approximate location`, `Creator`, `Copyright`) · `Advanced` / `Show all data` · `Compare` (`Side by Side`, `Slider`) · `Possible matches`. Explanatory lines, [VERBATIM]: *"The app or device used to produce this content recorded the following info:"* and *"The producer chose to share the following info:"*

**Content-summary sentences, which is the actual "generated new vs reused" vocabulary**, [VERBATIM]: *"This image was generated with an AI tool."* · *"**This image combines multiple pieces of content. At least one was generated with an AI tool.**"* · *"This image was generated with a custom model."* · *"AI was used to generate speaker voices."*

**Gap and integrity vocabulary, the "what wasn't recorded" language**, [VERBATIM]: *"**Some edits or activity may not have been recorded.**"* · *"The current Content Credential can't be viewed because changes occurred that couldn't be or weren't recorded. Previous Content Credentials may be available."* · *"This file may have been tampered with."* · *"The Content Credential issuer couldn't be recognized."* · status words `Incomplete` / `Invalid` / `Unrecognized` / `No Content Credential` · CTA *"Background check your content"*.

**The action labels (the decision trace itself)**, [VERBATIM] `{label, description}` pairs as shipped: `Created` (*"The asset was created."*), `Edited`, `Color adjustments` (*"Changes made to tone, saturation, or exposure."*), `Cropped`, `Filtered`, `Resized`, `Orientation changed`, **`Imported`** (*"Other assets were combined into this one."*), `Drawing`, `Format converted`, `Content removed`, `Audio/Text modified`, `Published`, `Watermarked`, `Redacted`, `Metadata changed`, `Opened`, `Saved`, **`Unknown action`** (*"An unknown edit or activity occurred."*), and **`Created using reference content`** (*"Created new content using reference content"*).

The C2PA spec's normative recommendations differ slightly from what ships, [VERBATIM] from `spec.c2pa.org` Table 3: `Color or exposure edits`, `Other edits`, `Filter or style edits`, `Changed orientation`, `Unknown edits or activity`, `Repackaged` (*"Changed container file format without transcoding"*). Table 2 [VERBATIM]: `Content Credentials`, `Signed by / Signer`, **`Edits and activity`**, `Assets used / Assets`, `Additional manifests`. Table 5 proposes consumer-friendly swaps, [VERBATIM]: *"Signer, signed by"* → **`Content Credentials issued by`**, and *"Assertion"* → **`Details`** / **`Information`**.

Adobe's four information categories, [VERBATIM]: `Recorder`, `Identity`, **`Creative process`** (*"Share how your content was edited, including changes to color, exposure, or cropping, as well as any added elements like files or screenshots."*), `Generative AI training and usage preference`. Also [VERBATIM] v2 widget strings: `Recorded by`, `Verified by`, `AI Info`, **`Created without generative AI`**, `Camera-captured`, `This file has unrecorded changes.`

**GenStudio adds `Generative context` and `History`** (both quoted in section 2), which together are the closest thing to a marketer-facing record of what the model was given.

**Typeface: "Copy Evolution Tracking" does not exist.** High-confidence negative: 454 URLs in the current sitemap and **7,462 distinct archived URLs in the Wayback CDX for the whole typeface.ai domain, zero containing "evolution"**. `docs.typeface.ai` and `help.typeface.ai` do not resolve.

What Typeface actually has is better named than the phantom feature. **`Brand Graph`** (formerly Brand Agent), [VERBATIM] section eyebrow `REAL-TIME ENFORCEMENT`, heading *"Enforcement that explains itself, in real-time"*, and the key sentence: *"Brand graph scans every draft in real time. **Banned terms are blocked outright**, rules and tone are injected directly into generation... **When a rule fires, brand graph names which rule and why.**"* Plus [VERBATIM] *"with an explanation for every rule it applies"*. Eyebrow **`BRAND LINTING`**, [VERBATIM]: *"Brand graph validates the extracted rules themselves, flagging **schema violations, duplicate rules, contradictions, broken cross-references, and boundary conditions**"* (note: this lints the *guidelines*, not the creative). Eyebrow **`HIERARCHY RESOLUTION`**, [VERBATIM]: *"resolves rule inheritance, and surfaces conflicts for interactive resolution, so your team **approves overrides, removals, and additions rule by rule**."* The user gesture, [VERBATIM]: *"Ask **"Is this on-brand?"** and get instant feedback on what needs fixing and why."*

Also `Content Explainability` (eyebrow `CONTENT INTELLIGENCE`), [VERBATIM]: *"**detailed explanations for each highlighted sentence**"* and *"performance scores, next-best actions, and feedback loops"*. Audit surfaces [VERBATIM]: *"an **audit trail** for content creation activity"* (chat threads), *"**Workflow history** provides a complete audit trail of every status change"* via `Updates history`, and **`Agent Activity Monitor`**. Trust page [VERBATIM]: *"C2PA credentials verify the source and history of AI-generated content."*

**Google Ads has real, if minimal, provenance: a `Source` column.** [VERBATIM]: *"Google customized text assets... **can be identified through the designation "Automatically created" in the "Source" column**"*, reported on the Asset page and the **`Combination Report`**. Also [VERBATIM]: *"Text customization uses a combination of **extractive techniques and generative AI technology that are grounded in your landing page content**"*, and *"**Google customized text assets will only serve if they're predicted to perform better than the headlines and description lines you uploaded.**"* Docs draw human-vs-AI attribution side by side, [VERBATIM] headings: *"Advertiser provided header and description assets:"* versus *"Google will automatically create headline and description assets:"*

A rare **"the rule blocked everything, here is why"** message, [VERBATIM]: *"**Text guidelines**: If you define text guidelines such as words to exclude or themes to avoid, the preview panel automatically filters the generated assets to meet your guidelines. **If your guidelines are too restrictive and block all potential assets, you'll receive a prompt to adjust or remove rules to view preview assets.**"* And a pre-commitment preview, [VERBATIM]: *"see **whether generated text assets conform to your defined brand and text guidelines before you opt in**"*.

**Microsoft Copilot Studio has the strongest general-purpose trace vocabulary outside C2PA.** Feature name [VERBATIM] **`activity trace`**: *"shows you exactly how your agent processes each message. Use it to understand your agent's **chain-of-thought reasoning**, verify **knowledge source attribution**, confirm **tool execution**, and troubleshoot errors."* [VERBATIM]: *"**Each step in the trace appears as a node that shows what the agent did and why.**"* Node types [VERBATIM]: `User message`, `Agent response`, `Knowledge` (rendered as a *"**Searched knowledge**"* collapsible card *"showing sources for each knowledge source accessed, and citation links when available"*), `Ran action` (*"showing the connector, **filled input parameters**, and delivery duration"*), `Tool`, `Connector`, `Flow`, `Skill`, `Error`, `Complete`. Node detail shows [VERBATIM] *"The input the agent sent to the step"*, *"The output or result returned"*, *"Processing time and metrics"*, *"Error details if the step failed"*.

**Writer: thin.** Agent name [VERBATIM] `Product claims checker`, reporting *"a comprehensive breakdown of every claim in your content. **It will clearly mark what's approved and what's not** according to the document you uploaded."* No audit-log or observability page located.

**Not obtained: Meta.** All `facebook.com/business/help` article-ID attempts 404'd, the help centre returns HTTP 400 to non-browser clients and is JS-rendered, and `transparency.meta.com/features/how-ai-content-is-labeled/` 404'd. **Report as not obtained, not as non-existent.** Do not quote any Meta label from this study. **Not obtained: Salesforce** Einstein Trust Layer / Agentforce trace, as help.salesforce.com serves only a JS shell. **Not attempted: Persado.**

---

## SPECIAL HUNT 2: auto-fixed versus escalated

**This is genuinely rare. No product in this study reports a count or ledger of "N fixed automatically, M escalated."** What exists, ranked by closeness:

1. **Markup AI** comes closest at the item level: `Apply Change` (one-click fix) versus **`Mark as Resolved`**, which is [VERBATIM] *"available when an issue has no one-click fix"*. That is an explicit fixable-versus-not flag per finding, plus `Add Suggestion` as a third, tracked-change path.
2. **Frontify Specs** names the intent most clearly as routing, [VERBATIM]: *"Specs **catches the clear-cut issues**... **and delegates the task to the right people when human judgment is needed**"*, with the consequence *"A legal reviewer only sees assets that have already passed technical screening."* Still in development.
3. **Microsoft Copilot Studio** has the only shipped escalation *metric*, [VERBATIM] `Topic outcomes`: *"A chart of session outcomes, **`Escalated`, `Resolved`, and `Abandoned`**... A high proportion of `Escalated` or `Abandoned` outcomes can mean the topic needs improvement."* Not creative, but it is the vocabulary to borrow.
4. **Bynder** reports proposed-versus-final rather than fixed-versus-escalated, and does it well, [VERBATIM]: *"**Even if you override the agent's conclusion, its original report stays available**... so anyone can see what the agent found versus what a human ultimately decided"*, logged in a `History` tab as *"a full record of **proposed-versus-final status** for every asset."* Also [VERBATIM] *"Auto-apply removes the review step, not accountability."*
5. **Typeface** names two paths without tallying them, [VERBATIM]: *"Banned terms are **blocked outright**, rules and tone are **injected directly into generation**"* (auto-applied) versus *"flags the issue and suggests a correction"* (escalated).
6. **Google Ads** distinguishes reviewed from unreviewed generation, [VERBATIM]: a *"**suggested assets review space**"* with add/dismiss, *"You can **manually review each suggested Google optimized asset before it appears in your ads**, even if you opt out of fully automated asset optimization"*, contrasted with *"If you opted into the asset optimization feature... **These suggested assets don't need to be reviewed before saving**."*
7. **Jasper** is the notable anti-pattern: it is the only product that genuinely auto-fixes at scale (Style Guide applied at generation time) and it reports **nothing** about what it changed. [VERBATIM]: *"You no longer need to manually apply suggestions after content is created."*

Everyone else is emphatically all-escalation, and several say so as a selling point, [VERBATIM]: Filestage *"Review Agents never sign off on anything"*; Ziflow *"ReviewAI suggestions are not final decisions"* and *"hands the call to a person instead of deciding quietly in its machine brain"*; Lytho *"AI handles the checks, your team makes the decisions"*; Veeva *"By default, Vault does not save any detected issues to the document"*.

---

## SPECIAL HUNT 3: coverage/completeness and distinctness

**Coverage is reported by exactly three products, and only Google names it as such.**

**Google Ads `Asset coverage table` is a direct hit.** [VERBATIM]: *"the **Asset coverage table** helps **find gaps in your assets and fix those gaps that would make the most impact** on your account's Ad Strength."* Columns [VERBATIM]: `Asset Group`, `Campaign`, `Status`, `Headlines`, `Descriptions`, `Images`, `Videos`, `Sitelinks`, `Logo`, `Clicks`, `Impr.`, `CTR`, `Avg. CPC`, `Cost`, **`Recommended Actions to achieve Excellent Ad Strength`**. Worked example [VERBATIM]: *"If you're running a campaign that currently has 2 descriptions, the Asset coverage table may suggest **adding 2 more descriptions** to achieve excellent Ad Strength."* Section heading [VERBATIM] `Additional assets for Excellent ad strength`. Ad Strength itself encodes coverage in its rating definitions, [VERBATIM]: `Incomplete` = *"This asset group lacks minimum assets to serve"*; `Average` = *"The asset group has all asset types to serve all available inventories, **however it lacks variety** for better performance"*.

**Filestage's `Mandatory Images Agent` is the creative-QA equivalent**, [VERBATIM]: *"**Confirms every element is present**, including certification marks, recycling symbols, allergen icons, and brand logos."* Element-presence coverage, not placement coverage.

**Ziflow names completeness as a goal**, [VERBATIM]: ReviewAI for Checklists *"ensuring **completeness**, consistency, and brand alignment"*, and lists [VERBATIM] `Presence or absence of required content` as a use case. The fraction counters (`2 / 4`) are a coverage display for checks performed, not for placements produced.

**Distinctness is reported by exactly one product, in one phrase.** Google Ads, [VERBATIM]: `Good` Ad Strength = *"This asset group has all asset types, **good asset varieties, and good text diversification**"*, and [VERBATIM] *"Those asset groups also feature **strong text diversification** and a wide variety of assets for both **breadth and depth**."* Google also names the anti-pattern, [VERBATIM]: *"**Avoid pinning identical or very similar text to the same slot**, as this restricts the system and can lower your Ad Strength."*

**No product exposes a named "distinctness", "diversity", "variant similarity" or "near-duplicate" metric to a marketer.** The closest adjacent features are `Duplicate Detection` (Frontify) and `Duplication manager` (Papirfly), both of which find duplicate *library assets*, not insufficiently different *variants*. **No product reports whether it produced all the placements or sizes you asked for.** This is the single largest white space found in the study.

---

## COMPARISON TABLE: naming conventions

| Product | Names the… | Top-level unit | Verdict vocabulary | Score? | Provenance shown |
|---|---|---|---|---|---|
| **CreativeLens** | **dimension** at summary, **defect** at finding, **rule** at config | `Brand Consistency`; `Logo spacing violation`; `Logo safe zone` | icons only (`❌ ⚠ ✓`) + `2 Issues` / `1 Passed` | yes, `Content Score` 85% + 4 sub-scores | claimed: triggering rule, severity, explanation, remediation |
| **Adobe GenStudio** | **dimension**, then **content slot** | `Brand` / `Platform guidelines` / `Accessibility`; then `Headline`, `Color`, `Brand voice` | `Needs review` / `Passed`; `Pass` / `Fail` | yes, % = passed ÷ tested, Brand only | *"reasoning provided for each check"*; plus `Generative context`, `History`, Content Credentials |
| **CreativeX** | **practice** | `Brand early`, `Safe Zones`, `Supers Present` | `low CQS` / `high CQS` | yes, `CQS` as an adoption % | tags from visual/text/audio detection; platform-attributed authority |
| **Vidmob** | **dimension** for category, **practice-as-state** for check | `Brand Visibility` → `Brand Name or Logo Early` | `PASS`/`FAIL`; `Yes, No, Processing, Not Available, Not Run` | yes, 3 methodologies + High/Medium/Low tiers | 13-row why-unavailable table with status pills; element timeline; safe-zone overlay |
| **Jasper Brand IQ** | **governance artefact** | `Brand Voice`, `Visual Guidelines`, `Style Guide` | `Meets Guidelines` / `Doesn't Meet Guidelines`; `All images approved` | only in the free diagnostic (`Brand Compliance Score`) | free-text reason only; weakest of the mature set |
| **Filestage** | **agent, named after the defect class** | `Forbidden Terms Agent`, `Grammar Agent` | none per finding; step status `Approved` | no | which agent authored the comment + inline highlight |
| **Ziflow ReviewAI** | **engine + surface**, checks named by customer | `ReviewAI for Checklists`; `Compliance` / `Copywriting` / `Logo` | `Pass` / `Fail` / `Not Relevant` | no asset score; `Reliability level` per check (Perfect/High/Medium/Low/Not evaluated) | rationale text + **versioned prompt** + pinned location + CSV export of suggestion and prompt version |
| **Frontify** | **agent, humanised** (`Specs`), tasks by customer | `Specs`; `Review logo usage and placement` | task checked off | *"ratings"*, undefined | *"suggestions with references to your guidelines"* |
| **Bynder** | **agent + dimension**, no defect vocabulary | `Brand Compliance Agent`; `Visual identity`, `Voice and messaging` | `Compliant` / `Non Compliant` / `Partially Compliant` / `Not Applicable` | no | rule-by-rule + page number + reference asset; keeps proposed-vs-final |
| **Veeva Quick Check** | **dimension/artefact** for check, **act** for agent; defects deliberately deleted | `Quick Check Agent`; `Spelling`, `Boxed Warning`, `Phrase Assessment` | icon: passed / identified issues / error; plus a `Not Applicable:` bucket | no (only a reviewer-workload `Low/Medium/High`) | clickable page number + verbatim quoted text + neutral observation. Nothing else. |
| **Lytho** | **agent + skill** | `AI Reviewer`; `Logo Usage (Image)` | `Pass` / **`Flagged`** / `Fail` | no | `Analysis` / `Flagged Items` / `Suggested Fix` |
| **Papirfly** | **checker + quality dimension** | `Image Quality Checker`; `Ratio`, `Sharpness` | none published | no | none |
| **Markup AI** | **agent, grouped by dimension** | 15 agents over `Brand`/`Accuracy`/`Content Integrity`/`AI Visibility` | risk labels `🔴 High` / `🟡 Medium` / `🟢 Low` / `✅ No issues` | optional 0-100, *"no fabricated scores"* otherwise | agent + severity badge + flagged text + explanation |
| **Google Ads** | **rating + imperative recommendation** | `Ad Strength`; `Repairs` category | `Poor`/`Average`/`Good`/`Excellent`/`Incomplete` | yes, ordinal | `Source` = `Automatically created`; conformance to *"Google's best practices"* |

**The five conventions, ranked by how many products use them:**
1. **Agent** (Filestage, Bynder, Lytho, Frontify, Veeva, Markup AI, Typeface, Ziflow). Now dominant, and almost always `<something> Agent`.
2. **Dimension** (CreativeLens, Adobe, Vidmob, Bynder, Markup AI, Veeva). Used at the grouping layer above individual checks.
3. **Practice** (CreativeX, and Vidmob's guideline names). Rarest and clearest. `Brand early`, `Safe Zones`, `Supers Present` are imperatives or states, not defects.
4. **Governance artefact** (Jasper). Names what you configure, not what runs.
5. **Defect** (CreativeLens findings, Filestage agent names, Papirfly's `hard blur`). **Actively declining.** Veeva shipped defect categories (`Absolute/Superlative`, `Comparative Assertion`) and then deleted them in 26R1, documenting the intent [VERBATIM] as *"no advisory-style suggestions or regulatory categorization."* Bynder and Veeva both avoid the words "violation" and "severity" in UI entirely.

**Three cross-cutting patterns worth stealing:**
- **`Not Applicable` as a first-class outcome, never folded into pass or fail.** Veeva demotes it to a labelled, iconless, countless bucket. Bynder makes it one of four verdicts. Ziflow excludes it from the percentage while counting it in the total. Vidmob has five statuses so that "no answer" is distinguishable from "fail".
- **Uncertainty as a distinct state, not a severity.** Only Lytho does this: [VERBATIM] `Flagged` = *"A potential issue was detected, but the AI Reviewer is not fully certain."*
- **A standing fallibility disclaimer inside the report panel.** Veeva [VERBATIM] *"Large Language Models can make mistakes. Always verify results."*; Ziflow [VERBATIM] *"ReviewAI may make mistakes. Always double-check its results."*

---

## MASTER LIST: every distinct check category name found

**Brand and visual identity:** Brand Consistency · Brand consistency · Brand compliance · Brand Compliance Skills · Brand Visibility · Brand Visibility Threshold · Brand early / Brand Early · Brand Name or Logo Early / Present / Late · Brand Name Mention / Mention Late · Brand Audio Mention · Brand Voice · Brand Voice & Tone · Brand voice guidelines · Brand values · Brand Terms · Brand Colors · Brand Typography · Brand Standards · Visual identity · Visual Guidelines · Logo Usage · Logo safe zone · Logo · Logos · Colors · Color · Color and tone · Typography · Typography in PDF documents · Iconography · Layout · Thumbnail Branding · Distinctive Brand Assets (Sonic, Icon, Tagline, Color, Mascots, Packshots, Logos)

**Legal, regulatory, compliance:** Legal Compliance · Legal compliance · Regulatory & Compliance · Regulatory Compliance Skills · Regulatory and legal · Compliance · Disclaimer check · Disclaimer(s) Present in Text / in Audio · Legal Terms and Conditions Present in Text / in Audio · Required disclosures · Boxed Warning (United States Only) · Important Safety Information (United States Only) · Privacy Policy Link · Unsubscribe Link · Email Opt-Out & Sender ID · Footer Elements · Prohibited Words & Phrases · Required Words & Phrases · Forbidden Terms · Unverified Claims · Claims · Generic Claims · Product Claim Present in Text / in Audio · CLP Compliance · Loi Evin Compliance · Sustainability Claims Detection · Text Policy Compliance · Phrase Assessment (formerly Red Flag Phrases) · AI Disclosure & Transparency · Restricted Objects Detection

**Platform, format, specs:** Platform requirements · Platform Specs · Platform guidelines · Platform compliance · Format · Formatting · Channel specifications · Channel guidelines · Technical Specs · Asset Properties · Fits Aspect Ratio · Aspect Ratio · Video Length · Video Length Within Range · Optimal length · Max File Size Met · Frame for Mobile · Safe Zones · Resolution · Ratio · Orientation · Sharpness

**Copy, language, editorial:** Grammar · Spelling · Grammar & Punctuation · Grammar & Placeholder Detection · Copywriting · Editorial guidelines · Editorial restrictions · Style · Style Guide · Tone of voice · Tone · Voice and messaging · Sentence Clarity · Fluff · AI Voice · Oxford Comma · Em-Dash Rules · Case Sensitivity · Hyphen Normalization · Abbreviation Rules · Word Limit Per Frame · Text Present · Text Visibility Threshold · Text and voice Early / Present · Supers Present · Detect regional spelling variations · Persona · Brand Messaging Test

**Accessibility:** Accessibility · A11y · Color contrast · Min font size · Accessibility Compliance Validation · ADA accessibility

**Performance and effectiveness:** Performance · Performance best practices · Messaging Effectiveness · Ad Strength · Creative Quality Score (CQS) · Attention scores · Heatmaps · Decay curves

**Content, subject matter, imagery:** Key Visuals · Photography and imagery · Human Early / Human Present · Positive Emotion Early / Present · Motion Early · Scene Changes Early · Close Up · Pacing · Composition · Environment · Lighting · Mood · Background · Restrictions · Image Quality · Audio Present · Sound On · Optimize for Sound Off Consumption · Sound Type (Music, Sound FX, Speech, No Sound) · User-Generated Content Present / Early / Late · Production Type (Live Action, Animation, CGI) · Production Level (Low UGC, High Commercial) · Story Type (Educational, Entertainment, Aspirational, Promotional) · Inclusive Representation (age, gender, skin type, situational settings)

**Product and claims:** Product Visibility · Product Benefit Present in Text / in Audio · Product Feature Present in Text / in Audio · Product IQ · Product claims checker

**CTA and conversion:** Call to Action Present · Call-to-Action (CTA) · Call-to-Action Clarity · CTA: Platform Button · CTA Type (Engagement, Informational, Conversion, Other) · Promotional Offer Present · Promotional Messaging

**Safety and integrity:** Safety · Safety and imitability · Distressing imagery · PPE & Safety Detection · Asset Hygiene Detection · Content Integrity · Link Integrity · Date & Time Accuracy · Freshness · Source Authority · Accuracy

**AI-search / GEO (adjacent but named the same way):** AI Visibility · Key Takeaways · Q&A Optimization · Snippet Readiness · Brand Presence · Citation Rate · Brand Sentiment

**Custom / catch-all:** Other · Custom Text Present · Custom Audio Present · Custom Color Present · Custom Prompt · And More Custom Guidelines · Configurable Guideline

---

## FLAGGED: not reached or not verified

- **Canva (item 12): complete failure.** 403 on every help, newsroom, sitemap and canva.dev URL, to both WebFetch and full-browser-header curl. No vocabulary obtained at all.
- **Meta:** not obtained. Help centre returns HTTP 400 to non-browser clients and is JS-rendered; all article-ID guesses 404'd; `transparency.meta.com` 404'd. Do not quote any Meta label from this study, including plausible-sounding ones.
- **Salesforce** Einstein Trust Layer / Agentforce trace: help.salesforce.com serves only a JS shell. Nothing verified.
- **Frontify ratings:** the existence of *"visualizations, issues, and ratings"* is [VERBATIM], but the rating scale, what it attaches to, and the report layout are all [UNVERIFIED]. It is an experimental Marketplace app documented only on their R&D blog.
- **Celtra Score:** appears as a nav label; no page defines it. `celtra.com/celtra-score/` is 404.
- **CreativeX per-ad verdict rendering:** the six fundamentals and CQS definition are solid, but I found no public page showing the Pre-Flight result screen or the per-principle verdict label.
- **Bynder finding text:** no screenshot or rendered sample exists publicly. The rule *grammar* is documented; the rendered finding is not.
- **Jasper Brand Compliance Score range:** gated behind URL plus name plus email.
- **CreativeLens overall:** all strings are from marketing-site mockups in the JS bundle, not observed product UI. There is no help centre, no docs, and no app access. Treat as intended vocabulary.
- **Smartly** in-product ad-spec validation: absent from all public docs; cannot confirm it does not exist in-product.
- **Persado:** not attempted.
- **Google Ads** per-recommendation detail screen contents, and `answer/10725056` / `answer/13872527` on asset reporting: not reached. No verbatim "Needs attention" string found in Google Ads; their equivalents are the `Repairs` category name and the `Fix…` verb.
---

## ADDENDUM: Frontify (supersedes section 8)

**Specs has not shipped.** Three hard confirmations, all [VERBATIM] from
https://help.frontify.com/en/articles/13673117-inside-frontify-january-2026:
- "Specs is something Frontify is currently exploring internally. What you saw in the Keynote was an early prototype."
- "Is Specs in beta or early access? No. Specs is not in beta or early access. It's still in development, and customers can't use it yet."
- "Specs is currently not available in the Frontify Marketplace."
- "Are the Specs features and workflows final? No. Specs is still evolving."

Corroborated by the Agentic hub inventory (no check), the Apps/Marketplace collections (Brand Check absent), and the shipped governance page being workflow only: [VERBATIM] "Frontify provides approval workflows, role-based permissions, and asset rights tracking."

**Correction on "ratings".** The word belongs to the earlier Brand Check app prototype, NOT to Specs. It appears exactly once in Frontify's entire web and help corpus, as the third item in "visualizations, issues, and ratings". Help-centre searches for `rating` and `score` return zero brand-compliance hits. Scale, labels and level count remain UNVERIFIED. The three Specs demo video elements are empty in both the live HTML and the sole Wayback capture, and all images carry alt="", so no screenshot exposes a rating label.

**Element vocabulary, from the FAQ.** [VERBATIM] "It uses vision-language models to understand things like logos and their placement, text content, colors, fonts, and overall layout... verifying logo usage, color accuracy, font consistency, and text rules." And "flag potential issues, such as unsuitable subject matter, visual style mismatches, or other defined criteria." Convention: element-based lowercase prose, never a fixed capitalised dimension set.

**Frontify's shipped MCP path puts provenance on the user as prompting discipline.** All [VERBATIM] from
https://help.frontify.com/en/articles/16982451-how-to-use-the-frontify-mcp-use-cases-and-prompts, use case "3. Brand compliance checks":
- "List every line that conflicts, quote the rule it breaks, and suggest a replacement."
- "Cite the guideline page for each point you make."
- "**Ask for the rule alongside the verdict. A flagged line you can trace back to a guideline page is something you can act on, or push back on.**"
- "Quote the rule behind each flag."
- Caveat: "Grounding reduces error, it doesn't eliminate it. The MCP returns structured brand data. The AI tool still interprets it, and it can misread or invent."

Vocabulary to add to the master list: flag (noun and verb), verdict, "the rule it breaks", conflicts, "cite the guideline page".

**Gate phrase.** Closest thing to a pass concept is [VERBATIM] "technical screening", in "A legal reviewer only sees assets that have already passed technical screening."

**Sibling prototype**, /en/kitchen/spot-the-gaps-on-your-brands-digital-presence, tagged "Sparks": [VERBATIM] "Think of it as 'Consistency as a Service.'", names only two axes [VERBATIM] "from visual identity to tone of voice", frames output as [VERBATIM] "a fast, visual pulse".

**Revised comparison-table row.** Frontify names an agent-as-persona (`Specs`); app in title case ("the Brand Check app") with the action lowercase ("run the brand check"); defect nouns are only `issues` / `problems` / `flag`, with no "defect", "violation", "infraction" or "error class" anywhere. **The structural point: Frontify dissolves the report into existing review-workflow objects (comments, checklist ticks, delegation) rather than building a scorecard. The interesting idea is structural, not lexical.**

**Technique note.** help.frontify.com is Intercom-hosted with server-rendered search; the enumerable endpoint is https://help.frontify.com/en/?q=<urlencoded>. The /en/kitchen/* path (8 posts, linked only under Resources) is where unreleased Frontify capabilities appear first, tagged by programme: "Dynamo" for Specs, "Sparks" for innovation week. Wayback CDX for *brand-check* and *compliance* on frontify.com returned zero rows.

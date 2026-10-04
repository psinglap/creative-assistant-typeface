# Creative Assistance for Ad Creatives

**A trust and confidence layer for AI-generated ad creatives.** It sees every variant, names every problem in plain words, fixes what's safe, asks before anything else, and tells the marketer when the batch is ready to ship.

Product exercise for the Senior Product Manager, Ads role at [Typeface](https://www.typeface.ai).

**Created by Pallavi Singla** · September 2026 · Licensed [CC BY 4.0](LICENSE): free to download, use and adapt with credit to Pallavi Singla.

| | Link |
|---|---|
| **Live prototype (Arc Proof)** | **[psinglap.github.io/creative-assistant-typeface/prototype](https://psinglap.github.io/creative-assistant-typeface/prototype/)** |
| **One-pager (live)** | [psinglap.github.io/creative-assistant-typeface](https://psinglap.github.io/creative-assistant-typeface/) · [⬇ download the .docx](docs/downloads/Creative-Assistance-for-Ad-Creatives_Pallavi-Singla.docx) |
| **70 defects, classified (Classes A to H)** | [CSV in this repo](data/defect-classes-A-H.csv) · [XLSX](data/defect-classes-A-H.xlsx) · [Google Sheet](https://docs.google.com/spreadsheets/d/1P-sl-Q_MRY_gXsLshoe3Nleqs5H3Z6jXBEI4XqTdKFA/edit) |
| **114 context parameters (the 10 reference docs)** | [data/context-parameters/](data/context-parameters/) |
| **Research (~93,000 words, sourced)** | [research/](research/) |

---

## Contents

1. [The problem](#1-the-problem)
2. [Research: how this was grounded](#2-research-how-this-was-grounded)
3. [The solution](#3-the-solution)
4. [The prototype](#4-the-prototype)
5. [The data: defect library and context model](#5-the-data-defect-library-and-context-model)
6. [How we measure success](#6-how-we-measure-success)
7. [Out of scope for V1](#7-out-of-scope-for-v1)
8. [Repository map](#8-repository-map)
9. [Running locally](#9-running-locally)

---

## 1. The problem

At scale, one approved master becomes **200+ variants** across formats, audiences, channels and markets. The marketer is accountable for every one of them, but the marketer is not a designer.

**Why now.** AI has raised creative volume faster than quality control. **88%** of marketers make more creative since adopting AI, but only **45%** see better quality (WARC for TikTok, n=400). When AI gets it wrong, **40%** of teams have had to pause or pull ads.

### The persona: Romil, Marketer

Owns 50 campaigns a quarter across 4 channels and 2 to 5 markets. Reports to a Director of Growth on pipeline and CPA, not on craft. Romil is **table-native**: the day is rows with statuses, yet every creative tool offers a canvas, because every creative tool descends from a design tool.

| | |
|---|---|
| **Trained in** | Audience strategy, performance analysis. Not typography, colour theory, composition or accessibility |
| **Works in** | Meta Ads Manager and Google Ads (both tables), a spreadsheet, Slack, the brief doc |
| **Measured on** | Launching on time, hitting CPA |
| **Fear** | Putting the brand in trouble |

### The four P1 pains

| # | Pain | In their words |
|---|---|---|
| 1 | **Too many to review** | "I check the first ten properly. The others, I skim or go back to designer with high-level inputs." |
| 2 | **No design vocabulary** | "Something's off, but I can't name it... So I write 'make it pop' and designer go round again." |
| 3 | **AI quietly misses the brand** | "The colors are almost ours, and it looks a bit AI." |
| 4 | **Low confidence to ship** | "I am not confident in when it's ready. I ship with fear." |

> "10 years in marketing. I still get the sweats when I am about to hit send, even after the team has looked over the final (final) draft."

**So the Creative Assistant has to give the marketer the confidence to click Ship, not just save time.** That shapes every design choice below.

### All eight pains, prioritised

| # | Pain | Frequency | How it's solved today | Priority | What the Creative Assistant does |
|---|---|---|---|---|---|
| 1 | 200 variants, no way to triage | Per batch | High-level notes back to the designer | **P1** | Clusters by cause: 70 known problems roll up into 8 decision classes (A to H). Approval happens per cluster |
| 2 | "Something is off and I can't name it" | 5 to 15x per batch | Shares a feeling, not a detail | **P1** | Plain-language vocabulary for every defect, citing the rule ("Brand book p.14", not "low contrast") |
| 3 | AI output is subtly off-brand or reads as AI | Continuous | Eyeballing, which misses it | **P1** | Exact brand and quality checks cited to the rule (Classes E, G, H) |
| 4 | Doesn't know when it's ready to ship | Per batch | Gut feel, Slack sign-offs, platform rejections | **P1** | Ship-readiness verdict per variant and per batch: *Ready / Fix first / Needs a person* |
| 5 | Can't judge a market she doesn't know | Per campaign | Slow agency loop | P2 | Market persona agent that says what it lacks and asks the local reviewer only those gaps |
| 6 | Review tools are too slow | Continuous | Waits, or skips review | P2 | Background checks at generation; chat reads stored results. Target under 60s p95 per batch |
| 7 | Can't tell if a claim is legal in-market | Per market launch | Slack to legal, or guess | P3 | Legal & claims agent; legal's answers become rules |
| 8 | The context kit has gaps she can't see | Per campaign | Found as bad output | P3 | Flags checks with no rule to compare against, asks the brand owner once, adds the answer to the kit |

---

## 2. Research: how this was grounded

The work combines **primary conversations with practitioners** and **desk research across about 93,000 words of sourced material**. Every claim in the research files carries an inline URL or a source tag (`[VERBATIM]`, `[PARA]`, `[OFFICIAL]`, `[PRACTITIONER]`, `[FLAG]`), and gaps are listed explicitly rather than smoothed over.

### 2.1 Primary research: marketers and creative practitioners

Conversations with practising marketers, plus the designers and copywriters they hand off to, covered how they review variants, decide something is "ready", give feedback, and what they fear. The participant profiles, as labelled in the one-pager's [Primary Anecdotes](https://psinglap.github.io/creative-assistant-typeface/#anecdotes):

| Profile | Themes contributed |
|---|---|
| Marketer, 10+ years (global sportswear brand) | Fear at the moment of shipping, even after team review |
| Marketer, 5+ years (global sportswear brand) | Briefs and reviews scattered away from the asset; the personal cost of one mistake; AI imagery spotted by Gen Z |
| Marketer, 8+ years (CPG brand) | Defensive review ("at least 5 other people"); owner approves without looking; team feedback rounds feel worthless |
| Designer, 10+ years | Feedback arrives as "this doesn't feel right" |
| Copywriter, 12+ years | "They think they'll know it when they see it" |

These conversations were combined with voice-of-customer mining from practitioner forums (2.2) and paraphrased into the four P1 pain statements in section 1.

### 2.2 Voice of customer: practitioners in their own words

Sources: Reddit (r/marketing, r/PPC, r/FacebookAds, r/graphic_design, r/branding, r/SocialMediaMarketing), LinkedIn, practitioner blogs and trade press, 2025 to 2026. Organised by theme: reviewing volume, AI quality defects, ads that shipped with visible mistakes, marketer and designer handoff, how "good enough to ship" is decided, fear, and flag-versus-fix trust. Includes counter-evidence from marketers who say this is not a problem.

→ [`research/raw/marketer-voice.md`](research/raw/marketer-voice.md) · [`research/raw/voc-ai-creative-review-2026.md`](research/raw/voc-ai-creative-review-2026.md)

### 2.3 Typeface product teardown and company profile

A hands-on teardown plus a company, customer, pricing and roadmap profile. Findings that changed the design:

1. **The `Evaluate` primitive already exists.** Typeface can score an asset against a rubric, and Agent Studio has an `Evaluate` node. V1 is a surfacing and compilation problem more than a build problem.
2. **The Brand Kit schema caps at 5 values, 5 tones and 10 rules**, with `termsToAvoid` as the only rule type. That is find-and-replace, not constraints.
3. **Observed generation latency of 31s to 8m32s.** Chat-driven review of 64 variants can't work at that speed, so verdicts must be pre-computed.

→ [`research/raw/typeface-company-profile.md`](research/raw/typeface-company-profile.md)

### 2.4 Competitive landscape

Four tiers mapped: AI ad creative production, creative automation and DCO, brand governance/DAM/review, and platform-native tools. Also covers creative scoring systems and market sizing. **Nobody detects genAI craft defects**, and the two firms best placed to own the marketer's seat (Vidmob, CreativeX) are moving away from it. A companion study looks at how 15+ creative-QA products (Adobe GenStudio, CreativeX, Vidmob, Jasper, Frontify, Bynder, Ziflow and others) name and report checks to a non-technical marketer.

→ [`research/raw/competitive-landscape.md`](research/raw/competitive-landscape.md) · [`research/raw/creative-assistant-reporting-ux.md`](research/raw/creative-assistant-reporting-ux.md)

### 2.5 Channel specs and what actually gets rejected

The rule library behind the defect classes covers official specs for Meta, Google, Amazon, Walmart Connect, TikTok, LinkedIn/Pinterest/Snap/Reddit, CTV, DOOH and IAB, plus Google's Ads Safety Report, Meta's enforcement data, regulated-industry copy rules and encodable accessibility thresholds. **The channel, accessibility and localisation numbers in the data are real and sourced.**

→ [`research/raw/channel-specs-and-rejections.md`](research/raw/channel-specs-and-rejections.md)

### 2.6 Secondary market indicators

| Indicator | Figure | Source |
|---|---|---|
| Marketers reporting higher creative volume since adopting AI | 88% | WARC for TikTok |
| Marketers reporting a significant improvement in quality | 45% | WARC for TikTok |
| Cite difficulty maintaining brand voice or visual identity | 26% | WARC for TikTok |
| Cite inconsistency across assets in the same campaign | 23% | WARC for TikTok |
| Cite excessive human editing requirements | 21% | WARC for TikTok |
| Brands that made video ads in 2026 | 78% | Bannerflow |
| Brands that ran those video ads | 46% | Bannerflow |
| Ad executives who believe Gen Z and Millennials feel positive about AI ads | 82% | IAB |
| Gen Z and Millennial consumers who actually do | 45% | IAB |
| Perception gap, 2024 to 2026 | 32 to 37 points | IAB |

*Sources:* WARC for TikTok, n=400 marketers in creative production decisions, UK/US/AU/BR, May 2026. Bannerflow platform analysis, 300+ brands, 2.33M creative assets, Jan to Aug 2026. IAB, "The AI Ad Gap Widens", n=505 US Gen Z/Millennial consumers plus 104 US ad executives, Oct 2025 to Jan 2026.

### 2.7 The incident that set the scope

**REI, June 2026.** Meta silently regenerated an approved vendor photograph into a bicycle with two sets of handlebars, and it ran for a week. Meta's position: *"it is the advertiser's responsibility to review the AI outputs."* The approved master was fine, so **checking only the master would have passed it.** The scope is the served creative, not only the master.

### 2.8 Synthesis documents

| File | What it is |
|---|---|
| [`research/01_Research_Dossier.md`](research/01_Research_Dossier.md) | The evidence base: Typeface teardown, marketer voice, named incidents, competitive map, sizing, and an explicit list of what could not be verified |
| [`research/02_Solution_Thesis_and_Journey.md`](research/02_Solution_Thesis_and_Journey.md) | The product thinking: the reframe, three tiers, eight design principles each tied to evidence, the end-to-end journey, V1 scope, 90-day metrics |
| [`research/03_New_Market_Journey.md`](research/03_New_Market_Journey.md) | The new-market launch journey: the nine dimensions of market context, and graduated autonomy by coverage |

---

## 3. The solution

**The trust and confidence layer: a creative quality standard that keeps the marketer in control.** Every variant is checked in the background, and findings are grouped by cause. All known issues roll up into **8 decision classes**, so hundreds of findings become a handful of decisions.

For every issue, the Creative Assistant runs the same loop:

| Step | What the Creative Assistant does |
|---|---|
| **1. Identify** | Checks every variant in the background against pre-defined rules |
| **2. Classify** | Sorts it into one of 8 decisions: **A** Image quality · **B** Content accuracy · **C** Layout & cropping · **D** Readability · **E** Brand adherence · **F** Platform policies · **G** AI-slop · **H** Batch health |
| **3. Say it in marketer words** | Uses the pre-defined vocabulary and cites the rule and reference doc |
| **4. Set the action** | **Auto-fix** when measurable and reversible · **Ask permission** when it changes the creative · **Flag for review** when it's a judgement call · **Designer needed** when it needs craft |

### Graduated autonomy by coverage

The agent's permission to act depends on how much context it holds, scored per market and per dimension. **Above 0.8** coverage it checks and auto-fixes. **Between 0.5 and 0.8** it proposes but never applies. **Below 0.5** it refuses to issue a readiness verdict, runs only the checks that don't depend on missing context, names every dimension it can't assess, and requires a named human attestation before the ship gate clears.

That's the honest answer to "can AI judge cultural appropriateness?" It can't. But it can know that it can't and say so, which is more useful than a confident guess. **A green tick on a market the system knows nothing about is the worst output the product can produce.** The prototype's Japan campaign demonstrates this.

---

## 4. The prototype

**[▶ Open Arc Proof](https://psinglap.github.io/creative-assistant-typeface/prototype/)** · single self-contained HTML file, no build step, no backend.

Arc Proof is a working, clickable model of the Creative Assistant sitting on top of a campaign's generated variants. The data is illustrative; the rules, thresholds and channel specs are real.

### What's in it

| Campaign | Variants | Channels | What it shows |
|---|---|---|---|
| **Pegasus 41 Launch** (sportswear, illustrative) | 48 | Amazon Ads, Walmart Connect, Google Display, Meta | Retail-media and display sizes from 160x600 to 1940x500: product cropped in tall slots, headline below 14px on thin banners, retail price mismatch, upscaling, malformed AI lace structure |
| **New Year Reset** (US & DE, illustrative) | 64 | Meta, Google, CM360 | German headline overflow, missing health disclaimer, wrong promo %, CTA contrast 2.9:1, a designer-locked logo, a precedent hook that underperformed |
| **New Year Reset JP** | 16 | Meta, Google, TikTok | Thin-context market: missing CJK glyphs, a US disclaimer that doesn't apply in Japan, reversed name order, and a seasonal concept the assistant **refuses to judge** |
| **Spring Refresh** | 24 | Meta, Google | Arrives mostly cleared, so the overview shows a real spread of states |

### Things to try

1. **All campaigns overview.** See which campaigns are ready, blocked or need review.
2. **Open a campaign canvas.** Variants are laid out by channel and format with real placement chrome. Pan, zoom, click a variant, hover for comment bubbles.
3. **Status tab.** Findings are grouped into the 8 decision classes, each with its action level (Auto-fix / Ask permission / Flag for review / Designer needed), a plain-language description and the cited rule.
4. **Chat.** Try *"What needs my review?"*, *"Is this ready to ship?"*, *"Why is this flagged?"*, or **`@typeface fix everything you can`**. Answers are instant because the checks ran at generation.
5. **Overrides.** Override a designer-locked element: you have to give a reason, and the reason is recorded.
6. **Ship.** Only the ready variants go out. Held-back variants stay untouched, and the ship report lists what was fixed, what was overridden, and who decided.
7. **Light/dark theme** toggle in the top bar.

### Design principles visible in the prototype

- **Pre-computed verdicts.** Chat reads stored results and never runs checks.
- **Cluster by cause.** One fix applies to many variants as one diff.
- **Every finding cites an authority**: a brand book page, a channel spec, a legal rule with an owner and date, or a computed measurement. An uncited finding is a bug.
- **Flag by default, fix on consent.** Every change is a visible diff, and originals are untouched.
- **Designer intent is respected.** Locked elements carry their rationale, and an override notifies the designer once, not per variant.
- **It says what it can't assess.** Low-coverage markets get advisory output only, plus a named reviewer.

---

## 5. The data: defect library and context model

### 5.1 The 70 defects, classified ([`data/defect-classes-A-H.csv`](data/defect-classes-A-H.csv))

Every known way an adapted ad breaks at scale, across formats, channels, audiences and markets. Worked example: a global sportswear brand's "Run Your City" campaign, **64 variants** from 2 approved seed concepts × 4 channels × 4 formats × 2 local markets (DE, JP), localised from one en-US master. *Brand details are illustrative, not any brand's actual guidelines, claims or data.*

| Class | Defects |
|---|---|
| A · Image quality | 9 |
| B · Content accuracy | 16 |
| C · Layout & cropping | 7 |
| D · Readability | 6 |
| E · Brand adherence | 7 |
| F · Platform policies | 5 |
| G · AI-slop | 12 |
| H · Batch health | 8 |
| **Total** | **70** |

**Who settles each defect:** Assistant 40 · Your call 15 · Flag only 15.

Each row has 8 columns:

| Column | Meaning |
|---|---|
| Class | One of the 8 decision classes |
| Defect | Technical name |
| What marketer sees | The Creative Assistant's plain-language vocabulary, e.g. *"The German headline is cut off"* |
| Why it happens / Threshold / Example | Root cause at scale, with the numeric threshold where one exists |
| Detect by | How the assistant identifies it (arithmetic, rendered measurement, perceptual model, cross-reference) |
| Who settles it | `Assistant` (auto-fix), `Your call` (marketer decides), `Flag only` (human judgement) |
| Reference doc | Which of the 10 context docs, and which field, the check cites |
| Also see | Secondary reference doc |

### 5.2 The 10 contextual reference docs: 114 parameters ([`data/context-parameters/`](data/context-parameters/))

The context the assistant needs in order to check anything. Each parameter has the same 13 fields: ID, element, parameter name, what it is, format/allowed values, example, context type, scope (global / local override / per market), when it's captured, refresh cadence, owner, priority (P0 to P2), and what it's used for (generation constraint, pre-flight check, ranking, context only).

| # | File | What it holds | Params |
|---|---|---|---|
| 1 | [Design system](data/context-parameters/01_design-system.csv) | Colour tokens, fonts, type scale, logo variants, layout templates, image style rules | 20 |
| 2 | [Brand context](data/context-parameters/02_brand-context.csv) | Voice, never-say list, approved imagery, competitor set | 12 |
| 3 | [Legal & claims](data/context-parameters/03_legal-and-claims.csv) | Approved and prohibited claims, disclaimers, asset rights, approved talent | 9 |
| 4 | [Audience](data/context-parameters/04_audience.csv) | Segments, merge tokens, representation guidelines | 12 |
| 5 | [Market & locale](data/context-parameters/05_market-and-locale.csv) | Language, local formats, text expansion, protected symbols, cultural sensitivities | 12 |
| 6 | [Campaign brief](data/context-parameters/06_campaign-brief.csv) | Offer, key message, placements, variant plan, landing pages, flight dates | 18 |
| 7 | [Product & offer](data/context-parameters/07_product-and-offer.csv) | Product catalogue, approved product shots, price, promotion, availability | 7 |
| 8 | [Channel specs & policies](data/context-parameters/08_channel-specs-and-policies.csv) | Resolution, aspect ratios, safe zones, text limits, file specs, ad policies | 10 |
| 9 | [Performance history](data/context-parameters/09_performance-history.csv) | Past results and element map | 7 |
| 10 | [Governance & review](data/context-parameters/10_governance-and-review.csv) | Reviewers, local reviewers, override log, variant naming schema | 7 |
| | [**All, in one file**](data/context-parameters/all-context-parameters.csv) | | **114** |

### 5.3 Proposed JSON schemas ([`data/sample-schemas/`](data/sample-schemas/))

Seven earlier machine-readable schemas, with a hypothetical brand ("Halo Nutrition", also used in the prototype's New Year Reset campaigns): brand context, audience and market context, the creative variant object, pre-flight findings, performance history, the channel spec rule library (real, sourced numbers) and market context with coverage scoring.

---

## 6. How we measure success

**North star: time to ship one campaign** (brief → all variants approved). **Target: −50% vs baseline in 90 days.**

*Why this metric:* review loops (vague feedback, designer rounds, platform rejections) are where campaigns lose weeks, and every Creative Assistant capability (clustering, auto-fix, one-brief designer handoff, ready-to-ship verdict) exists to remove a loop. Time to ship is the single number that moves only if the assistant works.

*Why −50%:* if the assistant closes most issues without a human and cuts designer rounds to one, roughly half the review time goes away. It's an ambitious but credible 90-day bar, to be confirmed against the week 1 to 2 baseline.

### Fine-grained metrics

| Dimension | Metric | Definition and how we measure | 90-day target |
|---|---|---|---|
| **Speed** | Iterations to launch a campaign | Median revision rounds per campaign across all variants before approval | **−2 rounds** |
| **Trust** (leading) | Fix acceptance rate | Suggested fixes applied ÷ fixes shown | **>60%** |
| **Efficiency** | Human editing time | Hands-on edit time per campaign, marketer + designer, from canvas and design-tool session logs | **−50%** |
| **Certainty** | Designer escalation rate | Batches with at least one "Designer needed" item ÷ all batches | **<15%** |
| **Coverage** | Assistant catch rate | Issues the assistant flagged first ÷ all issues found by assistant or human | **>80%** |

### Guardrails

| Guardrail | Definition | Limit |
|---|---|---|
| False-flag rate | Flags dismissed as incorrect ÷ all flags raised | **<5%** |
| Override rate | Blockers overridden ÷ blockers raised | **<20%** |
| Ad platform rejection rate | Disapprovals per 100 variants submitted | **−50%** |

---

## 7. Out of scope for V1

The P2 and P3 pains (rows 5 to 8 in the pain table): the market persona agent, faster review tooling, the legal & claims agent, video/motion/audio editing, and post-launch monitoring.

---

## 8. Repository map

```
.
├── README.md                          ← you are here
├── docs/                              ← served by GitHub Pages
│   ├── index.html                     ← the one-pager, live
│   ├── prototype/index.html           ← Arc Proof, the interactive prototype
│   └── downloads/                     ← the one-pager .docx and defect sheet .xlsx
├── data/
│   ├── defect-classes-A-H.csv         ← 70 defects × 8 columns
│   ├── defect-classes-A-H.xlsx        ← same, with reference-doc hyperlinks
│   ├── context-parameters/            ← 10 reference docs, 114 parameters
│   └── sample-schemas/                ← 7 JSON/CSV schemas (Halo Nutrition)
└── research/
    ├── 01_Research_Dossier.md
    ├── 02_Solution_Thesis_and_Journey.md
    ├── 03_New_Market_Journey.md
    └── raw/                           ← 6 full research reports with inline URLs
```

## 9. Running locally

No build step. Clone and open the files:

```bash
git clone https://github.com/psinglap/creative-assistant-typeface.git
cd creative-assistant-typeface
open docs/prototype/index.html   # the prototype
open docs/index.html             # the one-pager
```

---

## Author and license

Created by **Pallavi Singla**. © 2026 Pallavi Singla. Licensed under [CC BY 4.0](LICENSE): you may download, share and adapt anything here, including the one-pager, prototype, research and data, as long as you credit **Pallavi Singla** and link back to this repository.

**Cite as:** Singla, P. (2026). *Creative Assistance for Ad Creatives: a trust and confidence layer for AI-generated ad creatives.* https://github.com/psinglap/creative-assistant-typeface

*Brand names in examples (sportswear, "Halo Nutrition") are illustrative and don't represent any company's actual guidelines, claims or data. Typeface is referenced as the subject of a product exercise; this is an independent piece of work, not affiliated with or endorsed by Typeface.*

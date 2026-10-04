# The new-market journey, and what an agent needs to run it

Written from the seat you asked me to sit in. This is the answer I would give if I ran product here, including the parts that are inconvenient.

Companion to `02_Solution_Thesis_and_Journey.md`. The schema is in `sample-data/07_market_context_and_coverage.json`.

---

## 1. One correction before the journey, because it changes the model

Your framing says: *"the audience signals we have carry and are able to highlight the cultural context."*

I would not build it that way, and I think you will hit a wall in the second market if you do.

**Market and audience are orthogonal.** "Time-poor parents, 35 to 49" exists in Germany, Japan and the UAE. The persona is roughly stable. What changes is everything around it: the register you address them in, the claims you are allowed to make, the calendar their year runs on, the script their language renders in, the colour that means mourning.

If cultural context hangs off the persona, three things go wrong:

1. **Combinatorial explosion.** Eight personas across twelve markets is ninety-six persona objects, each of which has to be maintained separately.
2. **Nothing is reusable.** German comparative-advertising restrictions apply to every persona you sell to in Germany. Encoded on the persona, that fact gets written eight times and corrected once.
3. **The join disappears.** The interesting content is not "who is this person" or "where are they." It is the intersection: this audience, in this market, responds to this framing. If you collapse the two you can never express the intersection because there is nothing left to join.

So: **market is its own first-class node.** The cultural claim belongs to the market. The behavioural claim belongs to the audience. Generation joins them.

I have modelled it that way in `sample-data/07_market_context_and_coverage.json`.

`[What I found in the product]` The current Audience schema is `name`, `ageRangeMin`, `ageRangeMax`, `gender` (Male / Female / Neutral), `preferences[]`, `spendingBehavior` (enum). The documentation's own sample is `"name": "Adults in Chicago"`. **I found no market or locale object anywhere in the public API reference.** Guidelines are scoped `global` or `ads / Social Ads`, so a rule cannot currently be scoped to a market at all.

Meanwhile the Localization Agent *"translates ad copy and creatives for global markets while maintaining brand safety."* **Translation without a market node is precisely the failure mode this journey is about.** That is not a criticism of the agent. It is an argument that the agent is being asked to do a job the data model does not support yet.

---

## 2. The nine dimensions of market context

A market is not a language. Nine dimensions, because they have different owners, different half-lives and different consequences:

| Dimension | Contains | Who owns it | If it is wrong |
|---|---|---|---|
| **Linguistic** | Script, direction, text expansion factor, line-breaking rules | Typeface platform | Layout breaks visibly |
| **Typographic** | Font glyph coverage, per-script minimum sizes, leading overrides | Typeface platform | Tofu, silent substitution, illegibility |
| **Regulatory** | Claim regime, prohibited patterns, mandatory disclaimers | Customer legal | Takedown, fine, pulled flight |
| **Formatting** | Date, currency, decimal, measurement, name order | Typeface platform | Small, invisible, embarrassing |
| **Cultural** | Colour symbolism, imagery taboos, gesture, numerology, national symbols | Customer local market lead | Public backlash |
| **Register** | Formality level, direct-address tolerance, humour tolerance | Customer brand plus market lead | Reads as a foreign brand |
| **Commercial** | Retailer landscape, price norms, promo conventions | Customer market lead | Irrelevance |
| **Competitive** | Market leader palettes, local private labels | Customer market lead | A rival's product in your own ad |
| **Seasonal** | Local calendar, demand windows, holiday meaning | Customer market lead | The concept does not translate at all |

Three of these nine are things Typeface can own and maintain centrally for every customer. Six of them belong to the customer and **almost certainly do not exist in their Arc Graph today.** That asymmetry is the whole design problem.

---

## 3. The journey

**Setup.** Halo Nutrition is launching "New Year Reset" in Japan. First time in market. The designer approved two concepts in November for the US and moved on. Typeface adapted them: 16 Japanese variants across Meta, Google and TikTok. The marketer running it has never launched in Japan, has no Japanese colleague on the team, and cannot read the output.

Her actual question is not *"is this translated."* It is **"would a Japanese person wince at this."**

She cannot answer that. **And neither can the agent.** Everything below follows from taking that honestly.

### Step 1. She opens the campaign and sees a coverage panel, not a verdict

This is the most important screen in the product and it is the one nobody builds, because it makes the product look weak.

> **Japan. First launch.**
> Market context: **3 of 9 dimensions present.**
> Present: linguistic, typographic, formatting.
> **Absent: cultural, register, commercial, competitive, seasonal.**
> Regulatory: partial, no named owner.
> **No local reviewer assigned.**
>
> I can check the objective layer. **I cannot assess cultural appropriateness for this market and I will not pretend to.**

Compare that against a green tick. The green tick is the worse product, and not by a small margin. It converts her uncertainty into false confidence and it transfers the blame to her when it goes wrong. The panel keeps the uncertainty where it belongs and tells her what to do about it.

This is the mechanic I would build the V1 around, and it is in the schema as `graduated_autonomy`: **the agent's permission to act is a function of how much context it holds.** Above 0.8 coverage it checks and auto-fixes. Between 0.5 and 0.8 it proposes and never applies. Below 0.5 it runs only the checks that do not depend on missing context, declares every dimension it cannot assess, and **refuses to issue a readiness verdict at all.**

The agent earns autonomy. Per market, per dimension.

### Step 2. It runs everything that is knowable, and finds real things

The objective layer is not thin. For Japan, with zero cultural data, it still catches:

- **4 variants will render tofu.** The brand face covers 13 of 44 required glyphs. The renderer substitutes silently. Nobody sees this until it is live. Fix: switch to the approved CJK face. One click, twelve variants, visible diff.
- **The headline box is now 40 percent empty.** Japanese contracts by 10 to 55 percent in character count. But contraction is not space saving: CJK needs taller line-height, and a layout that shrinks to fit the character count is illegible. Two findings from one cause, and the second is the one a non-designer would never reach.
- **The personalisation token produces a reversed name.** `{FirstName} {LastName}` is wrong in Japan, Korea, China and Hungary. Small, invisible, embarrassing.
- **The US DSHEA disclaimer is still in the footer.** It does not apply in Japan, and its presence is wrong rather than merely useless.
- **The date reads 01/31/2027.** Should be 2027年1月31日.

Five findings, all objective, all citable, all fixable, **none requiring any cultural knowledge whatsoever.** That is the honest V1 value proposition for a new market and it is already substantial.

### Step 3. It declares what it cannot assess, specifically

Not a generic disclaimer. A named list, with the known general risks marked clearly as **unverified for this brand**:

> **Cultural: not assessed.** No context for this market. Known general risks I have not adjudicated: white as a mourning colour, the number 4, direct second-person address, negative space as a quality signal. **These are prompts for a human, not findings.**
>
> **Register: not assessed.** Keigo level is a brand decision with no default. It cannot be inferred from the English source.
>
> **Seasonal: flagged.** The concept is timed to a 26 December to 31 January window. That window is a Western construct. **This may not be a creative defect. It may be that the concept does not adapt to this market, which is a strategy question and above my pay grade.**

That last one is the finding I would most want the product to surface, because it is the most expensive and the least likely to be caught. A translation pipeline will happily render "New Year Reset" into flawless Japanese and ship a concept built on a calendar assumption that does not hold. **The product should stop and say so, not translate its way through it.**

### Step 4. It routes the unknowable to someone who knows

Here is the reframe I would defend in a board meeting.

**The goal is not zero human review. It is precision-targeted human review.**

For a first launch in a new market, the marketer *should* get a local reviewer. That is correct practice, not a failure. What is wasteful is sending a local reviewer all 16 variants and asking "is this fine."

So the product does this instead:

> 11 of 16 variants are objectively clean and carry no market-specific risk. **5 variants carry the cultural risk**, because they are the ones with people, gesture, colour-dominant treatments and the seasonal framing. Route these 5 to a named reviewer with a specific question, not a general one.

One reviewer, one pass, five items, three specific questions. Not a designer, and not a creative review. A **market** review, which is a different and much rarer skill, correctly spent.

The efficiency win is real and it is defensible: **the review shrinks from 16 unfocused items to 5 focused ones, and it happens once instead of iteratively.** That is a number you can put in a business case.

### Step 5. The ship gate behaves differently in a low-coverage market

Blockers at zero, as usual. But additionally, below 0.5 coverage the gate will not clear without a **named human attestation** on the unassessed dimensions. Not a checkbox. A name, a date, and what they looked at.

The Ship Report then reads honestly:

> 31 checks run, 26 passed, 5 fixed.
> **4 dimensions unassessed:** cultural, register, commercial, competitive.
> **Cultural sign-off:** [named reviewer], 19 Nov, reviewed 5 variants.
> **Seasonal concern raised and accepted** by [marketer], reason recorded.
> Coverage at launch: 0.33. **Flagged for enrichment.**

She can defend every line of that. That is the product.

### Step 6. The loop closes on the context, not just the creative

This is the part that compounds. Whatever the local reviewer says becomes **market context**, written back to the Arc Graph against Japan, attributed to them, dated.

Launch two is not a first launch any more. Coverage moves from 0.33 toward 0.6. The agent's autonomy increases because its context did. By the fourth campaign it is checking register automatically because a human taught it the register once.

**The moat is not the checking engine. It is the market context that accumulates underneath it**, and it accumulates fastest for the customer with the most markets, which is exactly the customer Typeface wants.

---

## 4. What an agent needs that your current questions do not yet ask for

Your questions are strong on **what data exists**. An agent needs four things beyond data, and these are the gaps I would close.

### 4.1 Coverage, and the ability to say "I do not know"
Nothing in the current question set asks what happens when the context is **absent**. This is the single biggest gap, and it is most dangerous exactly where you are pointing the journey, because a new market is by definition the case with no data. If the agent's failure mode on missing context is silence, then silence reads as safety and the product is actively harmful. Ask what it does when it has nothing.

### 4.2 Precedence when authorities conflict
Market law says the footer must be present. Meta's spec reserves the bottom 35 percent. The designer locked the logo. All three cannot hold on one canvas. **Somebody has to have decided the order in advance**, because the marketer cannot arbitrate between German food law and Meta's spec, and asking her to is the failure the brief describes.

Typeface has *Hierarchy Resolution* for brand hierarchies, which resolves rule inheritance across a house of brands. That is brand-versus-brand. It does not appear to cover brand versus channel versus law. I have proposed an explicit precedence order with override rights per rank in the schema.

### 4.3 Temporal validity
Claims expire. Promo prices expire. Cultural notes go stale. Channel specs change under you. **A checker that enforces an expired rule is worse than no checker**, because it blocks correct work and teaches people to ignore it. Nothing in the current model appears to carry an expiry or a staleness policy.

### 4.4 Decision rights, stated as a boundary
What may the agent change without asking, ever? This is where Meta burned this entire market, and the REI case is the cautionary tale: Meta auto-enrolled the advertiser, silently regenerated an approved vendor photograph into a bicycle with two sets of handlebars, ran it for a week, and stated on the record that *"it is the advertiser's responsibility to review the AI outputs."* **The boundary needs to be a product decision written down, not an emergent behaviour.**

### 4.5 Three smaller ones worth having
- **Blast radius on propagation.** Your assumption says the children know when the parent changes. What happens to a child that was individually edited? Last-write-wins, conflict, or fork? Typeface's docs note there is no real-time collaborative editing and simultaneous edits are last-save-wins, which suggests this has not been solved for the variant tree either.
- **Who is accountable in the audit trail.** If the agent passes a variant and the platform rejects it, what does the record say? That is the Meta accountability gap, and if we build the same shape we inherit the same problem.
- **Negative examples.** You now assume you have failed and rejected creatives. Ask whether they are actually **retained with a reason**. They are the only realistic training signal for craft-defect detection and the cheapest dataset the company already owns and probably discards.

---

## 5. Three of your new questions I can already partly answer

Saves you asking, and it is better to walk in knowing.

**"What does the Agent currently return when it evaluates a variant? A score, a list, structured rule references with sources, highlighting deviations?"**
From the product directly: a rubric evaluation returns a **table of `Rubric objective | score | Verdict`** with pass ticks. At generation time, *"when a rule fires, Brand Graph names which rule and why"*, so structured rule references with an explanation already exist. A **Visual Brand Evaluator** shipped in May 2026 that *"evaluates images against guidelines."* What I could **not** find anywhere: **any numeric brand-compliance score, confidence value or severity ranking.** The product does binary blocking plus flagging with explanations. So the answer is probably "a list with cited rules, no score, no severity", and severity is the thing worth adding.

**"Arc Graph already surfaces frequently broken brand guidelines. Which ones break most often, across customers?"**
Worth softening the premise before you ask it. Arc Graph flags and explains violations **at the moment of generation**, and it lints the rules themselves for contradictions and schema violations. I found **no evidence of aggregate frequency reporting** across variants or across customers. So the honest version is: *"do you have any aggregate data on which guidelines break most often, or is flagging per-generation only?"* If the answer is no, that is a cheap, high-value thing to build, because it tells you which rules to encode first.

**"What is your actual first pass acceptance rate on adapted variants today?"**
This is the best question in your document and I could not answer it from outside. No published figure exists for anyone. For context on how thin the public data is: **Meta publishes no ad-specific rejection statistics at all**, and the best available proxy is their enforcement precision of roughly 91 to 92 percent in H1 2026, implying an 8 to 9 percent error rate on enforcement decisions. Google's 2024 report gives 5.1 billion ads removed and 9.1 billion restricted, but the top categories are network abuse and trademark, which no creative checker can touch. **If Typeface has an internal first-pass acceptance number, it is more valuable than anything published anywhere**, and it is the baseline your entire 90-day measurement plan needs. Ask for it first.

---

## 6. If I ran product here, the uncomfortable version

The market-entry case is the strongest wedge in this brief and the weakest part of the current platform, and those two facts are the same fact.

A Localization Agent that translates without a market node will produce fluent, grammatical, correctly-rendered creative that is wrong in ways no one on the team can see. That is worse than an obvious failure, because it ships.

So I would sequence it this way, and I would resist pressure to reorder:

1. **Build the market node and the coverage model first.** Unglamorous. It is the thing.
2. **Ship the objective layer only**, and ship it honestly, including the refusal to give a verdict below 0.5 coverage.
3. **Make routing a first-class feature**, not a fallback. Getting the right five items to the right reviewer is the product, not an admission of defeat.
4. **Close the loop on context.** Every human judgement becomes market context. This is what compounds, and it is what a competitor cannot copy by shipping a feature.
5. **Only then** consider automated cultural assessment, and only per-dimension where a customer's own accumulated data supports it.

The thing I would not do is claim cultural judgement in V1. We would be wrong in public, in a market where we have no standing, on behalf of a customer who trusted us. The Tourism Malaysia case is the whole warning in one line: an AI promo video shipped with the national flag rendered mirrored, and a Malaysian comedian's response was the sharpest critique of this entire category I found in months of research:

> *"What concerns me most is not that maybe this was a cost-saving measure. It's scary because the decision makers sat around, looked at this AI ad and said to themselves, 'That's good enough.'"*

A room full of people looked at a mirrored national flag and said yes. **Our job is not to be the room. It is to be the thing that says "I cannot check this, and here is who can."**

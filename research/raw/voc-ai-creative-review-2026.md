# NEW voice-of-customer material: reviewing, approving and shipping AI creative at scale (2025-2026)

Nothing on your exclusion list is repeated. Labels: **[VERBATIM]** exact text, **[PARA]** paraphrase, **[SYNTH]** my inference. Every Reddit quote came from the Arctic Shift archive API (raw comment bodies, so text is exact); Reddit blocks direct browser fetching from this environment, so permalinks are canonical-form constructions from archive IDs and were not visually re-opened. Flagged as needed.

**Read this caveat first.** 2026 Reddit marketing subs are heavily astroturfed. In my harvest I found three separate accounts (u/Zealousideal_Leg5615, u/Tall-Rooster-7112, u/SecretJob1727) posting near-identical copy promoting the same video tool, and a large volume of LLM-written "helpful expert" replies with a tool plug in paragraph four. I have marked vendor-affiliated and suspected-astroturf sources inline. The high-karma organic threads (scores 20 to 516) are the trustworthy spine.

---

## 1. The moment of deciding "is this ready to ship"

**The single best framing of the decision problem, from a named practitioner:**

**[VERBATIM]** Craig Elimeliah, Chief Creative Officer, Code & Theory, in Digiday, 24 Dec 2025 (Sam Bradley):
> "A single prompt can give you 200 like, pretty good options. But someone has to sift through and judge and refine. That decision work used to be invisible; now it is the job."

Same interview:
> "Client approvals are the new bottleneck. AI collapses the time it takes to make content but it does nothing to collapse the time it takes to approve the content"
> "The gap is becoming the most expensive part of the pipeline; AI moves in minutes and clients move in weeks and months"
> "The real cost isn't generating assets, it's generating *your* assets"
https://digiday.com/marketing/marketers-are-keen-to-use-generative-ai-in-ad-campaigns-but-hidden-costs-lurk/

**[VERBATIM]** Ellen Utrecht, Founder, MikeTeevee, Brand Perspectives 2026 (interviews with senior in-house creative leads at HelloFresh, Wayfair, DoorDash, Canva, Intuit, O2, Verizon; no sample size or fieldwork dates published), via MediaNews4U, 19 Sep 2026:
> "The question for creative teams is no longer how many options they can produce. It's how they decide which ideas deserve to exist."
> "Speed and volume cannot replace taste, judgement or the confidence to make a choice."
https://www.medianews4u.com/ai-is-driving-creative-volume-but-human-judgement-remains-the-filter-miketeevees-brand-perspectives-2026/

### The question asked directly, by a practitioner, on Reddit

**[VERBATIM]** u/hippohaul, r/advertising, 12 Feb 2026, post titled "How do you validate AI-generated ads/images before publishing?":
> "I'm seeing brands post AI content with obvious artifacts (weird hands, unnatural lighting, off compositions), and I'm curious if it's because: a) they don't see the issues b) They see them but ship anyway due to speed c) They don't have a good QC process."
https://www.reddit.com/r/advertising/comments/1r33ju5/how_do_you_validate_aigenerated_adsimages_before/

### Described rituals and checklists

**[VERBATIM]** u/SimonBuildsStuff, r/advertising, 13 Feb 2026, answering the above (agency side):
> "Mostly (c). QC processes were built for human-made creative. AI outputs break differently.
> The artifacts you mentioned are obvious ones. The harder problem is brand drift. AI generates something that looks fine on its own but put it next to your last 10 ads and it clearly does not belong.
> What we do now:
> * Hard rules first. Colours, fonts, logo placement, if these can be validated programmatically, do that before anyone looks at it.
> * Side-by-side comparison. Every AI output goes next to 3 recent approved pieces. Does it feel like the same brand made it?
> * Human gut check for the subtle stuff. Lighting, composition, vibe. Still no replacement for trained eyes."
https://www.reddit.com/comments/1r33ju5/_/o53qejy/

**[VERBATIM]** u/MulberryLost2889, agency lead, r/content_marketing, 24 Apr 2026 (the zoom-in checklist, with a stated cost):
> "the exact same thing happened to us about a year ago with a beverage brand, AI generated lifestyle shot, label text that looked correct at thumbnail size but was garbled when zoomed, made it through three rounds of internal review because everyone was looking at composition and lighting and nobody zoomed in on the label. Client caught it. We almost lost them. The fix we landed on was a mandatory checklist for any AI generated asset that includes specific zoom-in checks on text, hands, logos, product details, and small repeating patterns. Slows production down maybe 15 percent but the variance in QA outcomes dropped to almost zero. The time savings from AI production are real but they get partially eaten by the new QA layer, and any agency claiming otherwise is either lying or about to lose a client."
https://www.reddit.com/comments/1s6w3sy/_/ohxdm30/
*[FLAG] This comment reads partly LLM-assisted and the account has low karma. The substance matches the OP it replies to, which is organic (score 40).*

**[VERBATIM]** u/Middle-Wafer4480, 12-person agency with 15 clients, r/content_marketing, 29 Mar 2026 (OP, score 40):
> "A client for a premium skincare brand spotted AI artifacts in product images we delivered. Warped text on a bottle label, slightly wrong color on a cap. We missed it in review. Client was pissed, questioned our QC process, we almost lost the account. Had to add a dedicated manual review step for every AI-generated asset which eats into the time savings."
Also: *"Another client explicitly banned AI-generated content in their updated brand guidelines mid-project. Had to redo two weeks of work. Now we ask upfront."*
https://www.reddit.com/r/content_marketing/comments/1s6w3sy/we_brought_ai_tools_into_our_agency_workflow_6/
*[FLAG] Soft-promotional: the post also praises consolidating to "one platform." Treat the incident as real, the tooling narrative as sponsored-adjacent.*

**[VERBATIM]** u/dmdbGroup, r/FacebookAds, 17 Sep 2026 (two concrete pre-ship rules; discloses working on hermoso.ai):
> "The product should be your real photo composited in, not redrawn. Tools that 'reimagine' the product shift the label, the cap or the proportions a little, and people read that as fake instantly... **check the label against the original before you run it.**"
> "Keep headline text and prices out of the generated image. Models still mangle small text. Generate the scene clean, then add copy in a layout step."
https://www.reddit.com/comments/1wir34o/_/padsc6z/

**[VERBATIM]** u/bradfilm, agency, r/advertising, 13 Feb 2026 (the markup ritual, and a new role pairing):
> "When our agency creatives work with prompt engineers it is their responsibility to give feedback/mark up images with their comments to have it regenerated before shipping. Other places may not have as stringent controls or may just not care is it is so much cheaper for them to put out."
https://www.reddit.com/comments/1r33ju5/_/o530enj/

**[VERBATIM]** u/Interesting-Read-212, large international industrial company, r/graphic_design, 20 Sep 2026 (an actual written rule):
> "We never let AI near our logo, because it's very likely it will distort it, or break our business guide rules. Photos that feature people, products or locations must always be real footage. Only really generic imagery can be AI generated."
https://www.reddit.com/comments/1whym2n/_/pb1iugb/

### The honest admission about how review actually goes

**[VERBATIM]** u/TTFV, long-standing r/PPC agency contributor, 6 Sep 2026:
> "And I'm saying you shouldn't be using AI to generate assets yet. **Even if you review them human nature is to say 'I guess that's okay' and run with it rather than rewrite the 70% that are pedestrian at best.**"
https://www.reddit.com/comments/1w7ucq8/_/p84ws95/

**[VERBATIM]** u/Unhappy_Finding_874, r/marketing, 19 Jun 2026, on a thread about an IT leader bypassing regulated-content review:
> "the scary part isnt even the ai imo, its that theyre treating review as a vibes based obstacle instead of a control."
https://www.reddit.com/comments/1u9vflw/_/osnl8lq/

**[VERBATIM]** u/rocketstart1, r/content_marketing, 5 Apr 2026:
> "AI output gets treated as 'done' instead of 'first draft,' but the errors are subtler than human errors. The review step didn't disappear, it just got harder."
https://www.reddit.com/comments/1s6w3sy/_/oeco8j2/

**[VERBATIM]** u/hardikrspl, r/content_marketing, 16 Apr 2026:
> "AI didn't remove work, it just shifted it from production to validation. If that layer isn't built in, things break fast."
https://www.reddit.com/comments/1s6w3sy/_/ogh4915/

**[VERBATIM]** u/Er_Valdi, r/PPC, 20 May 2026 (home-services lead gen, on the invisible cost of shipping something slightly off):
> "the second the ad feels fake or 'off', you create friction you may never see inside Ads Manager"
https://www.reddit.com/comments/1tileok/_/omxbo1g/

### Survey backing

- **[VERBATIM]** Optimizely 2026 Global AI Marketing Study, n=2,003 marketing leaders, US/UK/DE/SE/NL/AU/UAE, fieldwork May-June 2026, conducted by Savanta: "25% admit they frequently or always publish AI-generated content they know is not fully on-brand when under deadline pressure." Also "Only 30% of marketers believe their brand voice is genuinely unmistakable." https://www.optimizely.com/company/press/2026-global-data-study/ *(verified firsthand)*
- **[PARA]** Smartly 2026 Digital Trends, n=450 marketers at orgs spending $5M+ annually, fieldwork Aug 2025: only **28% use AI to quality-assure campaign setups before launch**; 24% run campaigns through AI pre-testing before full deployment. https://ppc.land/smartly-research-reveals-92-of-marketers-say-ai-reshapes-customer-engagement/
- **[PARA]** Meta has a creative approval workflow "in testing" allowing teams to get feedback and alignment on creative modifications inside Ads Manager itself (announced Cannes Lions, 23 Jun 2026). **[SYNTH]** The platform that caused the control problem in theme 3 is now building the review layer. https://ppc.land/meta-ad-spend-returns-4-13-per-dollar-as-ai-creative-tools-roll-out-at-cannes/

### A fresh 2026 brand-safety incident (not on your list)

**[PARA]** **MAMEE** (Malaysian snack manufacturer) recalled a Selangor-themed tote bag in September 2026 after its AI-generated illustration of Lord Murugan at Batu Caves depicted the deity holding a three-pointed trident instead of the *vel*, the correct divine spear. CEO Pierre Pang's team apologised to Malaysia Hindu Sangam on 20 Sep 2026. **[VERBATIM]** brand statement: "We sincerely apologise to the entire Hindu community for the offence, disappointment and concern that have been caused"; the team "should have been more alert to the sensitivities of this country." CMO How Yuan Yi said there were "no remaining unsold units in the market." https://www.marketing-interactive.com/mamee-recalls-bags-after-ai-artwork-of-lord-murugan-sparks-backlash
**[SYNTH]** This is the cleanest 2026 example of an error no generic QC checklist catches: not an artifact, not brand drift, but a religious-iconography detail that required a specific reviewer to be in the room. It is also a different failure class from the Tourism Malaysia flag case.

---

## 2. Reviewing volume: what it is like to look at 20, 50, 100 variants

**[VERBATIM]** James Hurst, Executive Creative Director, HelloFresh, in MikeTeevee Brand Perspectives 2026:
> "Some teams are suffering from **real decision paralysis**, because they can now create an almost infinite number of variations at almost zero cost and in zero time."

**[VERBATIM]** Mike Pearson, Head of Creative & Promotions, Wayfair, same report:
> "In a world where everyone can create more with the same tools, and often with the same inputs, how do you stop everything looking the same?"
https://www.medianews4u.com/ai-is-driving-creative-volume-but-human-judgement-remains-the-filter-miketeevees-brand-perspectives-2026/ *(both verified firsthand via MediaNews4U; the primary MikeTeevee report page returned near-empty via r.jina.ai)*

### The only quantified "variants reviewed per hour" figure I found anywhere

**[VERBATIM]** u/brownelijah, r/FacebookAds, 17 Jul 2026:
> "turnaround per variation dropped a lot once we stopped briefing each one individually... we pick what to iterate from there. **the deciding part is still maybe 20% of the time, rest is just generation and QA. probably 4-5 variations reviewed per hour once you're in a rhythm.**"
https://www.reddit.com/comments/1mx99bi/_/oy654qy/
**[SYNTH]** At 4 to 5 an hour, a 50-variant batch is a 10 to 12 hour review job. That is the number that makes the volume problem concrete.

**[VERBATIM]** u/RealMuseAI, r/graphic_design, 17 Sep 2026, pricing the human selection step at volume:
> "So, yes, 500 a week is possible. Won't be pretty though. The API cost will be pretty high, probably around $250 per week **since you would need to create 2-3 images and select one visually which takes time.** Now if needing quality images, carefully curated and prompted personally and possibly editted in photoshop, you could do about 1-2 a day"
https://www.reddit.com/comments/1wieke2/_/paespmc/

### Named practitioners saying the volume was a mistake

From The Current (The Trade Desk), "AI made creative abundant. Marketers are rediscovering quality", John McDermott, published 18 Aug 2026, edited 20 Aug: https://www.thecurrent.com/innovation/ai-made-creative-abundant-marketers-rediscovering-quality

- **[VERBATIM]** Mike Margolin, former EVP at RPA, now Margolin + Systems: "pumping out fifty near-identical variants solves a problem the platforms have already solved"
- **[VERBATIM]** Andrew Lipsman, independent media analyst, Media, Ads + Commerce: "This whole idea of creating a million variants of an ad is bad for brand building". He recommends **a dozen assets or less per ad set**.
- **[VERBATIM]** Kevin Simonson, CEO, adMixt: "Brands do need lots of ads, but the pendulum swung way too far". **[PARA]** A beauty client cut from 1,000+ ads per month to 200 and reduced CAC by 25%; performance was "way better".
- **[VERBATIM]** Adam Ortman, Founder/CEO, Kinetic319: "AI does a very good job of meeting in the middle, which means it does a great job of just providing the average"
- **[VERBATIM]** Jack Johnston, VP Social Innovation and Growth, Tinuiti: "In today's environment, if content pieces are viewed as similar, the algorithm will consolidate them"

### The practitioner argument that reviewing all of them is wasted work

**[VERBATIM]** u/Zayncarter777, r/FacebookAds, 16 Mar 2026:
> "in one campaign I ran with 18 creatives in a single ad set, after the first week Meta spent about 75% of the budget on just 3 ads."
https://www.reddit.com/comments/1rv3303/_/oaqe1yd/
**[SYNTH]** If the platform concentrates 75% of spend on 3 of 18 within a week, the marginal value of carefully reviewing variants 4 through 18 is close to zero, but the brand-safety risk of any one of them is not. That asymmetry is the core of the review problem.

**[VERBATIM]** u/leading-a-swarm, r/FacebookAds, 14 Aug 2026 (the explicit "human on selection only" model):
> "Creative used to be about 20% of our monthly spend and it absolutely capped how many angles we tested. We flipped it: generate statics and variants in-house, **keep a human on selection only.** Cost per concept dropped enough that testing volume stopped being a budget decision."
https://www.reddit.com/comments/1vmtjsu/_/p3n4hjx/

**[VERBATIM]** u/WontonBogeyman, e-commerce advertiser, r/FacebookAds, 20 May 2026, describing the surface area he had to hand-audit:
> "we run the same creative in like 12 campaigns if it works as a seaonal because they're geographically segmented... **There's like 40 seasonal ads per ad set which are turned off because they're out of season and 3 or 4 ad sets per campaign, this is such a mess.** I'm having to scrape through every aspect of ads now."
https://www.reddit.com/comments/1ti023s/_/omu19ah/

### The volume-versus-eyeballs line

**[VERBATIM]** A pharmaceutical compliance lead, quoted in Marketing Dive, 14 Sep 2026:
> "The volume just keeps climbing. AI made it easy for our teams to create content and now there's more going out than we could ever put eyes on."
https://www.marketingdive.com/spons/the-ai-content-tsunami-creation-is-the-easy-part/830184/
**[FLAG] This is sponsored content (sponsor: Blee, an AI content governance vendor). The speaker is unnamed. Quote it as a vendor-sourced practitioner voice, not as journalism.**

### Volume statistics

- **[VERBATIM]** WARC for TikTok, "The New Creative Advantage", n=400 marketers directly involved in creative/content production decisions, UK/US/AU/BR, fieldwork May 2026, published 14 Jul 2026: "88% report higher creative volume since adopting the technology" but "only 45% report a significant improvement in quality." Limitations cited: "excessive human editing requirements 21%", "inconsistency across assets in the same campaign 23%", "Difficulty maintaining brand voice or visual identity registered 26%". https://ppc.land/only-45-of-marketers-gain-quality-from-ai-warc-and-tiktok-find/ *(verified firsthand)*
- **[VERBATIM]** Bannerflow platform analysis, 300+ brands, 1 Jan to 31 Aug 2026, 2.33 million creative assets: "78% of brands made video ads in 2026, only 46% ran them." **[SYNTH]** Roughly a third of brands that produced video never served any of it. That is a direct measure of produced-but-never-approved waste. https://ppc.land/bannerflow-78-of-brands-made-video-ads-in-2026-only-46-ran-them/
- **[VERBATIM]** Dash Social, State of Creative AI Marketing Report: "95% of AI-generated assets never make it into production." Also "85% of marketers said producing assets at scale and adapting assets across channels remains the biggest bottleneck". https://www.dashsocial.com/resources/creative-ai-report
  **[FLAG] I verified the sentence is on the page. The methodology is "in-depth interviews with global enterprise brands... 30 standardized questions" with no sample size and no fieldwork date. A percentage from an undisclosed qualitative interview base. Hedge heavily or do not use.**
- **[PARA]** u/datagekko, r/PPC agency, 26 Aug 2026: went "from shipping maybe 5-8 new creative concepts a week per client to 20-30" after automating prompt/headline/copy variation generation. https://www.reddit.com/comments/1vy8ksb/_/p5z1j1i/

---

## 3. Trust in AI creative tools over time, and turning features off

This is the richest new vein I found, and it is almost entirely about **Meta Advantage+ creative enhancements silently re-enabling themselves**. It is a 2026 trust story with a clear arc: the tool was wrong once, then repeatedly, and marketers now run a standing manual audit ritual because they no longer believe the off switch.

### The anchor thread: "Turning off 'Related Media' doesn't turn off 'Related Media'?"

**[VERBATIM]** u/WontonBogeyman, r/FacebookAds, 19 May 2026 (OP, score 32):
> "Related Media is an option i've been turning off every few days for the past 3 weeks for over 50 ads across 12 campaigns. It's still officially, in the ads dashboard, turned off now. **Yet I've just seen our f'ing Christmas ad in my news feed.** I think this might just be the final straw and we turn off meta ads to move fully over to google. This is absolutely insane that we're spending money showing old, seasonal ads 6 months after we stopped showing them after I've had to tell meta to stop showing them multiple times a week and now they're just doing it anyway."
https://www.reddit.com/r/FacebookAds/comments/1ti023s/turning_off_related_media_doesnt_turn_off_related/

Later in the same thread:
> "I've just seen our halloween ad from last year too FUCK MEEEEEEEEE. Opening it in the ad library it says the ad's inactive, obviously it is it's a fucking halloween ad so WHY IS IT BEING SHOWN. Related media, website media and every AI bullshit option is turned off HOW IS THIS HAPPENING" https://www.reddit.com/comments/1ti023s/_/omvafh0/
> "I've been on support chat for an hour and all they can tell me is that when they look at the ad, they see the ad, not the xmas ad it transitioned to... **apparently there isn't a way to see these test ads meta creates of our ads where it'll turn on the advantage+ options I've turned off**" https://www.reddit.com/comments/1ti023s/_/omr9wu1/
> "We've also had video ads being cut to a random frame that's still Reels aspect ratio, then have that being turned into a slide show with square images afterwards from a webpage the ads don't land on. **Like I couldn't even design a worse looking ad if I tried to.**" https://www.reddit.com/comments/1ti023s/_/omu1g91/

**[VERBATIM]** u/LouisVanHoof, agency managing multiple client accounts, same thread, 26 May 2026:
> "Any solutions here? Having the same issues with multiple client account since last week. **Since two years our job has been dodging their AI enhancement bullets, turning off toggles that we turned off in the first place. It's insanity.**"
https://www.reddit.com/comments/1ti023s/_/onxqv2x/

**[VERBATIM]** u/Either_Channel9230, same thread, 22 May 2026:
> "Meta building a system where your 'off' toggle spawns invisible ad copies that ignore your settings and resurrect deleted seasonal creative tells you exactly how much control they think advertisers actually deserve."
https://www.reddit.com/comments/1ti023s/_/onbten4/

**[VERBATIM]** u/HawthornWardrobe, same thread, 19 May 2026 (a customer-visible failure plus a time cost):
> "I had the same problem with a Black Friday ad last month, and **an ad that showed old pricing (that a customer ended up emailing the brand about, which was greaaat). Spent 4 hours on a support chat where they kept denying it happened, despite, my screenshots.**"
https://www.reddit.com/comments/1ti023s/_/omrcd41/

**[VERBATIM]** u/Consistent_Share_940, agency of 10+ years, same thread, 27 May 2026:
> "Our Agency (10+ years) are experiencing this issue since the 17th May. We have had multiple case escalations and **most of each day is taken up with client complaints on the issue or us writing up details for META Support. The case has transferred 7 times.**... We found creating fresh new ad accounts provided some small window to keep the customer happy but after 7 days or so, the learning/memory kicks in and META decides to swap out campaign images for something completely related."
https://www.reddit.com/comments/1ti023s/_/oo4i8kd/

**[VERBATIM]** u/Naive_Ad1644, same thread, 20 May 2026:
> "They will just gaslight you and say they don't see it on their end. Every time I reach out for similar issues I get 'we cannot replicate the issue.'"
https://www.reddit.com/comments/1ti023s/_/omumoqk/

**[VERBATIM]** u/uGoTaCHaNCe, same thread, 19 May 2026, on Meta's own AI assistant:
> "Their AI is REALLY BAD. It just regurgitates their docs and is super gated. **If you tell it that performance sucks it tells you to turn on Advantage+ Creative Enhancements.**"
https://www.reddit.com/comments/1ti023s/_/omrc4v6/

### The January 2026 mass re-enablement

**[VERBATIM]** u/duducaca, r/FacebookAds, 6 Jan 2026 (OP):
> "Here it goes again.. I recommend everyone to go and check their ads for more auto-enabled AI slop. Driven by today's underperformance, **I checked ad by ad and all AI optimisations that were disabled (and stayed disabled during Nov-thanks to code freeze period) is enabled again.** Some of them (like product tags) stay enabled even after I toggled them off. And after I turned that shit off, my campaign rolled back to learning.. Welcome to new year where **Meta dev team is your worst enemy.**"
https://www.reddit.com/r/FacebookAds/comments/1q5e0vi/autoenabling_of_advanced_creatives_enhancements/

**[VERBATIM]** u/DonSalaam, large advertising agency, same thread, 7 Jan 2026:
> "Meta turning on creative enhancements without our permission and without any notice is a serious issue. **I work for a large advertising agency, and we have had clients complaining to us after seeing their own ads with enhancements they never approved turned on. We have to manually now check ads every week to ensure nothing is turned on. It's a huge headache because we have many clients and tons of campaigns.**"
https://www.reddit.com/comments/1q5e0vi/_/ny5wqre/

**[VERBATIM]** u/Jose-CP, same thread, 6 Jan 2026 (the per-edit ritual):
> "in my accs, is that they are disabled, but if I edit some ad, they will automatically turn on. **So every time I want some edit, I have to 'untoggle' all optimizations**"
https://www.reddit.com/comments/1q5e0vi/_/nxznjdq/

**[VERBATIM]** u/FewPhotograph7209, same thread, 6 Jan 2026 (the UI lies to you):
> "In my settings 6/12 of the ai shite is turned on. When i click on it it says its turned off, but when i go into the ad settings its showing 6/12 turned on."
https://www.reddit.com/comments/1q5e0vi/_/nxzee0s/

**[VERBATIM]** u/supergox123, same thread, 6 Jan 2026:
> "some of them are now 'essential enhancements' which you can't turn off from the switch directly, some of them you can with a checkmark (?!) but you have to go below and open an additional pane and not all of them."
https://www.reddit.com/comments/1q5e0vi/_/ny1v9rg/

**[VERBATIM]** u/anassBLD, r/PPC, 2 Sep 2026 (the toggle count):
> "**If you aren't manually unchecking all 6+ enhancement sub-toggles on every single ad upload,** spend ends up leaking into bizarre AI-cropped assets and random generic audio. Daily alerting is genuinely useful for catching those silent resets **before the client notices.**"
https://www.reddit.com/comments/1w5808y/_/p7dctro/

**[VERBATIM]** u/WhatMattersHere, r/FacebookAds, 10 Sep 2026 (enhancements invalidate your test):
> "I would disable AI enhancements during that controlled creative test **because otherwise you may not be testing the asset you uploaded.**"
https://www.reddit.com/comments/1wc7lag/_/p8wulgq/

### "Wrong once" changes everything

**[VERBATIM]** u/Just_Use8502, r/content_marketing, 6 Apr 2026:
> "ai artifacts in client deliverables is a trust problem way more than a production problem, **one bad image and suddenly every asset is under a microscope.**"
https://www.reddit.com/comments/1s6w3sy/_/oejxx0v/

**[VERBATIM]** u/velvet-night_want, r/content_marketing, 16 Apr 2026:
> "I've seen the same thing with warped text on labels and **it's a nightmare to explain to a client why a bottle looks melted.** Having a human 'finisher' for every asset is the only way to keep from losing accounts."
https://www.reddit.com/comments/1s6w3sy/_/oglqjad/

### Trust in AI *scoring* and prediction specifically

From r/PPC, "are ai tools for ad creative research actually useful or just overhyped marketing claims", u/StrainBetter2490, 9 Jan 2026: https://www.reddit.com/r/PPC/comments/1q85rr8/are_ai_tools_for_ad_creative_research_actually/

- **[VERBATIM]** u/Away_You9725: "The accuracy issue is crucial; **if an AI tool provides you with a score that doesn't match your actual performance, it's worse than useless because you're now using faulty data to make decisions.**" https://www.reddit.com/comments/1q85rr8/_/nyl953k/
- **[VERBATIM]** u/trainmindfully: "**the danger is people treating the output as truth instead of a starting hypothesis. if a tool claims it can tell you what will win before spend, I get very skeptical fast.**" https://www.reddit.com/comments/1q85rr8/_/nyr4usc/
- **[VERBATIM]** u/Rich-Editor-8165: "AI can help with ideas, but **traffic tells the truth.**" https://www.reddit.com/comments/1q85rr8/_/o1r3nhz/
- **[VERBATIM]** u/Single-Sea-7804: "99% of AI Ads tools are BS because the technology is not advanced enough for it. **The best tool will always be your own analysis and judgement.**" https://www.reddit.com/comments/1q85rr8/_/nyn7x9s/
- **[VERBATIM]** u/stealthagents: "Sometimes you think you have a winner based on data, but then a totally random idea outperforms it. **It's all about that gut check too, right?**" https://www.reddit.com/comments/1q85rr8/_/nzynnx6/

### Named-practitioner and survey backing

- **[VERBATIM]** Jessica Gleim, ads consultant, on Meta's AI creative recommendation tools, eMarketer, 14 Jul 2026 (author Marisa Jones): they are "[are] not usable to help my clients grow their business." https://www.emarketer.com/content/meta-s-ai-ad-tools-creating-new-risks-marketers
- **[VERBATIM]** Ómar Thor Ómarsson, CEO and Co-Founder, Optise, Digiday 24 Dec 2025: "AI content can be awesome and it can be awful. **We're all learning to trust... what's coming out of the LLMs**"
- **[VERBATIM]** TripleLift, n=200 advertising professionals (US 113, UK 34, FR 31, CA 17, DE 3, AU 2), fieldwork April 2026: reasons for keeping human oversight, "67% cited lack of trust in AI output as the primary reason. Technical errors and hallucinations came second at 61%. The need for brand safety checks registered at 41%". Creative production adoption sits at only 25%. https://ppc.land/most-advertisers-use-ai-for-optimization-but-not-creative-triplelift-finds/ *(verified firsthand)*
- **[PARA]** StackAdapt with NewtonX, n=500 marketing/advertising professionals plus 187 StackAdapt clients, fieldwork 19 May to 8 Jun 2026: **only 6% act on in-platform AI recommendations "almost always"; 42% ignore them as generic or irrelevant.** 89% accept AI preparing actions for approval; only 50% accept autonomous AI even with proven performance. **78% reported at least some unreviewed automation running.** 17% report no clear accountability structure for poor AI decisions. https://ppc.land/only-6-of-marketers-act-on-in-platform-ai-recommendations-stackadapt-finds/
- **[PARA]** ARF (Advertising Research Foundation), two waves Nov 2025 and May 2026: **confidence in AI outputs among marketers using AI rose from 82% to 93%.** Formal training programs grew from 50% to 70% between waves. **[FLAG] sample size not disclosed in the accessible write-up; thearf.org gates the full report.** **[SYNTH]** This is the counter-trend to everything above: aggregate stated confidence is rising even as the practitioner complaints get sharper. Both can be true if trust is rising in *generation* and falling in *platform-side automation*.

---

## 4. Marketers who are not designers: "I can tell something is off"

**The strongest single quote in the entire harvest for this theme.**

**[VERBATIM]** u/Objective-Feed7250, r/marketing, 14 Jan 2026, post "Gen Z can spot lazy AI images and it's hurting conversion rates" (**score 410, 110 comments**), running ads for an apparel brand:
> "Been running ads for an apparel brand targeting 18 to 25 year olds. Our CTR dropped 40% after we switched to AI generated lifestyle shots. **The images looked fine to me. Models wearing the clothes, decent lighting, no obvious errors. But apparently Gen Z can tell.**... The report mentioned things like lighting inconsistencies and unnatural shadows. **Stuff that's not obvious unless you're looking for it.**"
https://www.reddit.com/r/marketing/comments/1qch0v1/gen_z_can_spot_lazy_ai_images_and_its_hurting/
**[FLAG]** The post opens with "New consumer trust report came out. 78% of Gen Z can identify AI generated images and will scroll past them." **I could not identify that report.** u/Reasonable-Wait6858 asked the OP for the link on 19 Jan 2026 and **never received an answer** (https://www.reddit.com/comments/1qch0v1/_/o0iezpq/). Treat the 78% as unverified. The first-person experience is the usable part.

### The vocabulary problem, from both sides

**[VERBATIM]** u/rxza_a, in-house designer, r/graphic_design, 19 Sep 2026 (the purest version of the phenomenon):
> "I can relate, my boss does the same. whenever i create **she was like there is something missing, she put same design in ai multiple times and then come up with see like i am saying.**"
https://www.reddit.com/comments/1wit9qb/_/papwlcg/
**[SYNTH]** The non-designer manager uses repeated AI generation as a substitute for the feedback vocabulary she does not have. She cannot write the note, so she generates until she can point at one.

**[VERBATIM]** u/eternally_bound_, copywriter, r/marketing, 22 Aug 2026:
> "all I get at the end is '**mmmm this doesn't feel right**' or 'can we do [very ridiculous thing] instead?' WHAT DO YOU MEAN 'FEEL?'"
https://www.reddit.com/comments/1vv8ln4/

**[VERBATIM]** u/AdRepresentative2514, copywriter of 12+ years, same thread, 25 Aug 2026:
> "If the manager/exec really knew what they wanted they'd do it. The issue is **they think they'll 'know it when they see it,'** or they are operating in a blind leading the blind situation and have no idea what actually works."
https://www.reddit.com/comments/1vv8ln4/_/p5pzdyp/

**[VERBATIM]** u/somse86, designer, r/graphic_design, 18 Sep 2026, listing exactly the words a marketer lacks:
> "You know that these contrast ist not good? You know these fonts dont fit each other? You know this lineheight is wrong? You know that this design hast the same styling like most ai designs and ppl would see that it is clearly ai? You know how that these Elements dont fit each other? You know that the spacing and the weighting of elements ist wrong?"
https://www.reddit.com/comments/1wit9qb/_/pakdwkd/

**[VERBATIM]** u/Eastern_Enthusiasm93, r/graphic_design, 2 Sep 2026:
> "I know designers have a superpower of noticing bad design that other people think looks fine (I'm haunted by bad kerning on packaging and papyrus being used for signage) but this AI slop looks crazy and it all looks the same to me."
https://www.reddit.com/comments/1w1xve1/_/p7e2bye/

**[VERBATIM]** u/seamore555, r/graphic_design, 3 Sep 2026, on the stakeholder gap:
> "AI slop sucks because NON DESIGNERS use it to make designs... **A non designer doesn't understand the value of the hook of a design.** The issue is with non designers (stakeholder) not understanding this concept. They think the value is the asset itself, when instead it's the result of the asset."
https://www.reddit.com/comments/1w61dqv/_/p7jrf9x/

### The marketer's own gut check, articulated

**[VERBATIM]** u/Saidhain, long-time marketer, r/marketing, 9 Dec 2025:
> "Maybe it's because I've been in marketing for a long time but **I get a very negative visceral gut reaction when I see the brushed sheeny shine of AI images.**"
https://www.reddit.com/comments/1pied29/_/nt5noam/

**[VERBATIM]** u/cancer_dragon, r/marketing, 14 Jan 2026 (28 upvotes):
> "You don't need AI to detect it, you can see it with your human eyes. **It looks wrong, unnatural, impossible.**... it also informs your audience that you don't actually care enough about what you're marketing... And if you don't care, why should they?"
https://www.reddit.com/comments/1qch0v1/_/nzk5ms2/

### Imposter feelings and the taste accusation

**[VERBATIM]** u/ThrowbackGaming, r/marketing, 14 Jan 2026 (downvoted to -6, which is itself the finding):
> "usually it's a skill issue where **someone that doesn't actually have any creativity or taste (*cough* the marketing team)** is creating images that look bad, don't follow brand standards, etc. The key is having the same bar of quality regardless of AI or not. You don't lower your standard for quality just because the AI made it in under 10 seconds."
https://www.reddit.com/comments/1qch0v1/_/nzk1fu4/

**[VERBATIM]** u/variousthings1776, marketer, r/marketing, 12 Sep 2025:
> "**As someone who sucks at design,** how much easier it is to get a professional looking image or deck."
https://www.reddit.com/comments/1neupxp/_/ndrm6ek/

**[VERBATIM]** u/Fabulous_Sun6669, r/PPC, 17 Apr 2026:
> "**I'm terrible at design,** so I started using an AI platform where I just screenshot a competitor's high-performing ad and upload it... **it completely bypasses the design learning curve for non-marketers.**" (Also: "text overlays still render a bit wonky sometimes, ngl, so I usually keep them minimal")
https://www.reddit.com/comments/1snvzrt/_/ogqcxxr/
*[FLAG] Probable tool promotion; the same template appears under u/Negative_Onion_9197. Use only as evidence of how the non-designer marketer positions themselves.*

**[VERBATIM]** u/Reasonable-Wait6858, in-house marketer, r/marketing, 19 Jan 2026 (the marketer who needs external evidence because they cannot win the argument on judgement alone):
> "Would you possibly be able to link the report about 78% of Gen Z scrolling past Ai generated images? **I've been in an on-going battle with my 60+ year old CEO's about Ai (they are extremely cheap and want to use it in place of photography to save a few $$$) and counter me everytime I push back against doing Ai photos** would love to have this to show them"
https://www.reddit.com/comments/1qch0v1/_/o0iezpq/

**[VERBATIM]** u/Arya_kidding_me, in-house marketer at an engineering firm, r/marketing, 22 Aug 2026 (the mirror image, a marketer on *their* stakeholders):
> "I HATE asking for their input because they don't know what they're talking about and make suggestions as if we're idiots... but when we are given the chance to answer their questions they ALWAYS end up saying 'wow, yeah that does make sense' or 'huh, I didn't know that'"
https://www.reddit.com/comments/1vv8ln4/_/p5b14mq/

### The judgement misfires in both directions

**[VERBATIM]** u/jaimequin, designer turned marketer, r/marketing, 13 Aug 2026:
> "my artwork has always been high end polished and **clients started telling me not to use AI on things that had no AI at all.** People can't tell the difference and that made me change the process to incorporate AI in my art. If my efforts now look AI then why not just use AI and save time"
https://www.reddit.com/comments/1vn2za2/_/p3guoim/

**[VERBATIM]** u/psyche74, r/marketing, 21 Jan 2026:
> "**Everyone \*thinks\* they can identify AI images.** I'm seeing the accusations everywhere these days, including on videos that predate AI's ability to create them."
https://www.reddit.com/comments/1qch0v1/_/o0s8buk/

### Survey backing

- **[VERBATIM]** DoubleVerify, n=2,020 marketers/advertisers across 21 markets plus 22,000 consumers across 22 markets, published 29 Jul 2026: "**56% [of consumers] say they cannot consistently identify AI-generated content**"; "Nearly half (48%) of marketers are concerned about using AI to build ad creative, peaking at 63% in North America." https://globenewswire.com/news-release/2026/07/29/3335149/0/en/global-study-poor-quality-ai-content-puts-brand-trust-at-risk.html
- **[VERBATIM]** IAB, "The AI Ad Gap Widens", n=505 US Gen Z/Millennial consumers + 104 US ad executives, fieldwork Oct 2025 to Jan 2026, published 15 Jan 2026: "82% of ad executives believe Gen Z/Millennial consumers feel very or somewhat positive about AI-generated ads, **nearly double the 45% of consumers who actually feel that way**." Gap widened from 32 points in 2024 to 37 points. https://www.iab.com/insights/the-ai-gap-widens/ *(verified firsthand; note this is a different IAB study from the Aymara governance one you already have)*

---

## 5. What marketers ask AI tools

### The only rigorous study of actual marketer prompt quality

**Adobe (Acrobat and Firefly) prompting study**, n=1,008 US AI users across finance, healthcare, retail, education, transportation and creative arts; researchers scored **1,000 text-to-image prompts against a 10-category rubric**; 95% confidence, 3% margin of error; published 21 May 2026. https://ppc.land/adobe-study-91-of-marketers-abandon-ai-tasks-due-to-bad-prompts/ *(verified firsthand)*

- **[VERBATIM]** "The average prompt scored 57 out of 100, equivalent to a C grade, and **not a single respondent achieved an A.**"
- **[VERBATIM]** "The three most frequently cited mistakes were: failing to define the soft elements of the output, such as tone or personality; neglecting to provide a clear example of the desired output style; and omitting a specific role or persona."
- **[VERBATIM]** "**91 percent of AI users surveyed have abandoned a generative AI task and reverted to manual work.**" For image tasks users expected usable results after roughly 4 attempts.
- **[VERBATIM]** "**One in seven respondents does not fact-check their AI outputs at all.**" Business professionals highest skip rate at 24%.
- **[PARA]** Gen Z reported the highest self-confidence (54% rating themselves 4 or 5 of 5) but scored **56/100 versus Millennials' 58/100**. **[SYNTH]** Confidence is inversely related to measured prompt skill in the group most likely to be given the tools.

### Practitioner complaints about prompting as a skill

**[VERBATIM]** u/Middle-Wafer4480, 12-person agency, r/content_marketing, 29 Mar 2026:
> "The learning curve hit team members at wildly different speeds. Two people picked it up in days. **One person still cant write a prompt that produces anything usable after 6 months. Theres no good training material for 'how to prompt for marketing-specific outputs.'**"
https://www.reddit.com/r/content_marketing/comments/1s6w3sy/

**[VERBATIM]** u/MulberryLost2889 on the prompt-library solution, 24 Apr 2026:
> "We stopped trying to make universal prompt training work and instead **built a prompt library specific to our common deliverables, social asset for B2B SaaS, blog header for finance vertical, product shot variation for ecommerce, etc. The people who couldn't write prompts from scratch could still execute well by adapting templates.**"
https://www.reddit.com/comments/1s6w3sy/_/ohxdm30/

**[VERBATIM]** u/Just_Use8502, r/content_marketing, 6 Apr 2026:
> "The prompt skill gap is probably the longest term problem you listed. It's not going away and **there's no good solution yet besides pairing strong and weak prompters on the same projects until it transfers.**"
https://www.reddit.com/comments/1s6w3sy/_/oejxx0v/

**[VERBATIM]** u/sylvant_ph, designer, r/graphic_design, 4 Aug 2026 (what bad marketer prompting looks like downstream):
> "Id get managers sending me tickets and ideas created with AI, **with almost no critical thinking and review, simply taking it as clear coin and not accounting for the 'sycophancy' factor.**"
https://www.reddit.com/comments/1vepuqq/_/p1mdiu3/

### Observed intent patterns: what marketers actually ask for

**[VERBATIM]** u/No-Egg7514, r/FacebookAds, 27 Oct 2025, giving the literal prompt he recommends:
> "Prompt it with: '**Generate 20 ad headline variations for [product] targeting [audience] with [pain point].**'"
https://www.reddit.com/comments/1ohlqnb/_/nlp6f3k/

**[VERBATIM]** u/FunStretch7412, r/FacebookAds, 12 Jun 2026, describing the prompt-then-cull pattern:
> "**Most people type something like 'sunglasses on a white background' and then complain the output looks fake.** The people getting decent results are putting in very detailed prompts, specific lighting, mood, angle, style references, and then **generating 20 to 30 variations and picking the best ones.** Sometimes doing light editing on top to fix the small tells."
https://www.reddit.com/comments/1u215y0/_/or6w24n/

**[VERBATIM]** u/Major_Fill_670, r/PPC, 6 Apr 2026 (prompts as creative version control, which is a genuinely new workflow pattern):
> "**the real unlock is that it outputs a file with the raw prompt for every single scene. if an ad dies after a week, I just tweak the prompt for scene 1 to test a new hook instead of re-rolling the whole damn video.**"
https://www.reddit.com/comments/1sdtejf/_/oema3ky/

**[VERBATIM]** u/Negative_Onion_9197, r/PPC, 13 May 2026 (the competitor-screenshot-to-prompt-template pattern; probable tool promotion, flagged):
> "I just upload a screenshot of a high-performing competitor ad or a proven local service layout. **It reverse-engineers the composition, lighting, and structure into a reusable prompt template. I just swap the variables** and it spits out new creatives in that exact proven aesthetic."
https://www.reddit.com/comments/1tbkhfr/_/oliaafe/

**[VERBATIM]** u/parrottvision, brand marketer building an AI marketing platform, r/marketing, 16 Dec 2025 (where prompting still fails, in the marketer's own words):
> "**Nano banana is insane but it still can't get the labels on product right unless they are really simple. We have lots of text on our labels. The other think it fails at is scale. Sometimes our product is the right size, other times it's huge in relation to the rest of the image objects.** Lifestyle images etc though, it's amazing."
https://www.reddit.com/comments/1pnwy1o/_/nud5591/

### The prompt role is being institutionalised

- **[PARA]** Jasper, State of AI in Marketing 2026, n=1,400 marketing professionals, fieldwork end of 2025: **36% are now responsible for designing prompts, templates or workflows**; 31% of organisations plan to hire AI prompt engineers or trainers, but only 28% intend to hire AI compliance and ethics leads. 65% of marketing teams now have designated AI roles. https://www.jasper.ai/state-of-ai-marketing-2026
- **[PARA]** Envato, n=1,780 creative professionals, published 12 Nov 2025: emerging roles respondents expect to formalize include **prompt engineer/strategist, AI creative director/orchestrator, AI curator/QA specialists, AI governance specialists.** https://elements.envato.com/learn/ai-trend-report *(verified firsthand)*
- **[VERBATIM]** u/sudipbiswas, founder of CreativeLens.ai, HN Ask HN Who is Hiring, 17 Aug 2026: "Marketing teams still spend a surprising amount of time manually reviewing campaigns, ads, social posts, emails, and other creative for brand guidelines, compliance requirements, and internal policies. CreativeLens lets companies upload their guidelines, turns them into review rules, and uses AI to review content before it goes live." https://news.ycombinator.com/item?id=49326458 **[FLAG] Vendor self-description. Useful only as evidence that "AI reviews the AI creative" is now a funded category.**

---

## 6. The handoff with designers in 2026

### Designers describing the new job: cleanup crew for marketer-generated AI

**[VERBATIM]** u/mushruined444, sole in-house designer at a product company, r/graphic_design, 17 Sep 2026, post "boss is using AI & comparing my design to it":
> "my boss now thinks it's fun to type stuff into ChatGPT and have it do our product label design, THEN assign me, the graphic designer the task of making it. **what's even worse is she isn't having me recreate the AI design but using it as the best result and judging my work based on how different it is from it.**... i have a four year design degree from a private institution and multiple years of work experience. she has a two year marketing degree and thinks she is on the same level as me. **she continues to make jokes that ChatGPT is our new designer.**"
https://www.reddit.com/comments/1wit9qb/

**[VERBATIM]** u/thepartypoison, in-house designer at a founder-led brand, r/graphic_design, 4 Aug 2026:
> "**I have to photoshop AI generated images to make them 'match' our other content/look real and it's hell on earth.**"
https://www.reddit.com/comments/1vepuqq/_/p1o0a2s/
Same user, same day: "My boss is having full on conversations with Claude, getting it to make marketing strategy bs/delegate money for ad spending... **it's like he can't make any decision on his own anymore.** So much of the content that the customer sees is AI generated, and I don't get how it's not obvious to him that it makes us look so shady as hell since were selling real products." https://www.reddit.com/comments/1vepuqq/_/p1nzz95/

**[VERBATIM]** u/ZippoS, r/graphic_design, 4 Aug 2026 (the workflow got killed by shame, not policy):
> "For a while there, I had **concepts generated with Meta AI being dropped on my plate to try and recreate. Low-res and both too complicated and too awful to work with. The public shaming really helped in nixing that workflow.**"
https://www.reddit.com/comments/1vepuqq/_/p1ppwrq/

**[VERBATIM]** u/Reddog8it, r/graphic_design, 19 Sep 2026 (the accommodation):
> "I don't fight if a client brings in AI... **I recreate the slop so it's usable and fix the thing where AI has obvious mistakes.** The reason is the client who brings in AI wants to use that design and doesn't care about design work or the thoughtfulness behind your design."
https://www.reddit.com/comments/1wit9qb/_/paus0en/

**[VERBATIM]** u/murkadees, freelance designer, r/graphic_design, 27 Dec 2025 (score 15) (the refusal):
> "**I would also mention that I do not work with AI-generated assets, so if they need to hire someone to 'fix' their generated logo they will need to look elsewhere.**"
https://www.reddit.com/comments/1px0pb6/_/nw7jyhq/

**[VERBATIM]** u/HearingFar7, designer at a sign company, r/graphic_design, 18 Sep 2026:
> "People don't understand why they are still getting charged a design fee when 'they designed it themselves'. **No, I can't take your AI design and make it a 4ft tall sign and it look good....without recreating it.**"
https://www.reddit.com/comments/1wjqwgw/_/pam3i69/

**[VERBATIM]** u/Historical_Air2790, print shop, r/graphic_design, 18 Sep 2026 (a hard ratio):
> "I work for a print shop and **almost half of what we get is AI slop at this point.** I just point out what is bad and see if they want to fix it. Most of the time they do."
https://www.reddit.com/comments/1wjqwgw/_/pal9xq2/

**[VERBATIM]** u/FontMasterFlex, print/production, r/graphic_design, 18 Sep 2026 (the most damning ratio in the harvest):
> "we've done samples for customers of EXACTLY what they sent. looks like utter dogshit. they don't care. **i'd say 1 out of 10 actually look at it and are surprised and want us to fix it.**"
https://www.reddit.com/comments/1wjqwgw/_/pamlatb/

### AI created the work rather than saving it

**[VERBATIM]** u/Embarrassed-Arm-6315, r/graphic_design, 19 Aug 2026:
> "the logo was AI-generated with no source file and no font name. You had to reverse-engineer a usable substitute. **On this job AI didn't save you time, it created the work.**"
https://www.reddit.com/comments/1vqve7w/_/p4k3luq/

**[VERBATIM]** u/MaskedManiac92, designer inside a data-analytics company's marketing team, r/graphic_design, 17 Aug 2026:
> "for the last few months, us designers are forced to use AI tools to 'optimize' our design so that we can churn out more stuff, **which leads to more work**... when I use AI, **I end up doing more work because I have to redo most of the work.** Despite all these meetings, where we are told that we are basically useless and replaceable if we don't 'get on with the times', the same clowns come to me when it's a print job."
https://www.reddit.com/comments/1vqve7w/_/p4a2xqh/

**[VERBATIM]** u/Rusty99Arabian, r/graphic_design, 3 Aug 2026 (the manager's mis-estimate, with a customer-visible consequence):
> "**My boss insisted that he was certain AI would make a complicated project 'super easy' and so we could get it done within the next half hour.** When we explained that we, the people who actually do the work, were certain the task was going to take longer than he thought, we were assured we were wrong. **Surprise, it has taken hours, and now the president is asking why the marketing team suggested so many wrong social media statements about the company.**"
https://www.reddit.com/comments/1vepuqq/_/p1jtw1n/

### Marketers losing designer access

**[VERBATIM]** u/Intrepid-Law-7728, r/graphic_design, 18 Sep 2026 (headcount arithmetic):
> "**I've witnessed a marketing team go from 3 marketers, and 5 graphic designers slowly dwindle into 2 marketers who use Canva and Adobe.** The demand is high, and those platforms allow for the fastest turnaround time."
https://www.reddit.com/comments/1wjqwgw/_/pakqf3k/

**[VERBATIM]** u/Sgreaat, ex-UX designer, r/graphic_design, 18 Sep 2026:
> "I worked at a company that went from a marketing department of four, including a graphic designer, to zero. **The marketing design work started being picked up by anyone who fancied having a go.**... because it's seen as a fun, creative, thing to do, **all kinds was going out.**"
https://www.reddit.com/comments/1wjqwgw/_/pansw88/

**[VERBATIM]** u/dudeoverderr, 100+ person marketing agency, r/marketing, 13 Aug 2026, post "How can we convince leadership that creative (brand/strategy/design) is still valuable?":
> "my 100+ employee marketing agency just let go of several leaders on our creative team, our creative director, two design directors, and brand manager. **But they kept the 'Performance Creative' team, separate from ours, who are 99% production design for performance marketing who use AI to do quick, average-quality work.**... They don't think we're a huge selling point because they see market data, and **they don't know how to measure quality.**"
https://www.reddit.com/comments/1vn2za2/

**[VERBATIM]** u/mr-goond, PPC manager, r/PPC, 11 Sep 2026:
> "A few weeks ago we found out that **half of the creative studio (graphic designers, copywriters etc) had been made redundant becuase of 'ai related productivity streamlining'** so now I'm genuinely a bit worried that the paid team might be next..."
https://www.reddit.com/comments/1wdjquk/

**[VERBATIM]** u/Religion_Of_Speed, r/graphic_design, 8 Sep 2026:
> "I was just let go because of marketing budget. It's a pretty big chain restaurant and I was THE in-house designer, now they just won't have one... **We're currently being replaced by AI and Canva templates.**"
https://www.reddit.com/comments/1wamawp/_/p8m3g0z/

### What the review handoff looks like in practice now

**[VERBATIM]** u/MemeHermetic, works with large and mid-size B2B clients, r/graphic_design, 17 Sep 2026 (the cost of the executive AI drop-in, timed):
> "we have a very firm standing policy that we do not knowingly use any AI generated assets. Clients seem to love it, until of course **one of their C-suite cowboys rolls up with some amazing shit he ran out in GPT and we now have to spend half an hour explaining why it's bad, while their internal marketing team WHO TOLD US NOT TO DO IT will quietly sit there and act like it's the first time they've ever heard this policy.**"
https://www.reddit.com/comments/1whym2n/_/pae5wnv/

**[VERBATIM]** u/Fun-Imagination-7008, in-house designer, r/graphic_design, 22 Sep 2026 (the workflow being routed around):
> "We also keep coming across designed items that were given to them behind our backs, without going through our workflow. So, they are hiding things on purpose. **I've found my final, approved projects with changes made to them after the fact.**"
https://www.reddit.com/comments/1wixxi8/_/pbcunla/

**[VERBATIM]** u/fifty8th, sole marketing person at a manufacturing company, r/graphic_design, 19 Sep 2026 (the new approval chain, with marketing outside it):
> "Just this week **one of our sales people designed their own flyer getting it approved but head of sales and the owner,** though I think it was more approved for concept than design."
https://www.reddit.com/comments/1wj4ur4/_/parvkfv/

**[VERBATIM]** u/chatterwrack, r/graphic_design, 18 Sep 2026, on Photoshop's Firefly panel (one line, and the best joke in the corpus):
> "**Our stakeholders will soon get to shout their desires straight to the document.**"
https://www.reddit.com/comments/1wjqwgw/_/pamdr09/

**[VERBATIM]** u/Usual-Problem6002, freelance content writer, r/marketing, 23 Jun 2026:
> "Someone with no marketing training using AI to produce 'marketing materials' and leadership thinks it's fine because it looks polished. **The problem isn't just that it's bad work, it's that it resets expectations.** Now everyone thinks marketing is just 'tell AI to make a thing' and the bar drops for everyone."
https://www.reddit.com/comments/1u9vflw/_/otbh6rz/

### The marketer-side view of the same shift

**[VERBATIM]** u/ctvu12, "senior marketing leader here for a multi billion dollar company", r/PPC, 10 Jun 2026:
> "I'm having to reskill my PPC folks as automation has created a situation where **1-2 strong operator with strong judgement is more productive than 4 average ones**, which creates rework and too many cooks in a kitchen... I am in no hurry to hire more PPC marketers but I highly value a great one."
https://www.reddit.com/comments/1u1uedy/_/oqsk83e/

**[VERBATIM]** u/Collossal_Yarn, Creative Director, r/advertising, 5 May 2026 (where the time actually goes):
> "Due to staff shortage and a wave of pitches, I've stepped in to help with the entirety of the creative process, including using AI image gen for mocks/comps in decks. I've actually quite enjoyed using it for that... But outside of that? **My other 6+ hours a day? I have no idea how the AI revolution gets me off of a client call, out of a creative briefing or allows me to miss a concept review.**"
https://www.reddit.com/comments/1t3yk6j/_/ok0ceka/

**[VERBATIM]** u/Reeelfantasy, r/marketing, 10 Aug 2026 (predicting the job title):
> "AI is assisting in a lot of creative marketing tasks... **But it does also increase the workload in terms of quality auditing, coordination and discussion between teams and clients, and the overall trust in the work produced. AI works as an extra employee that needs managing and nurturing and the future may see new jobs such as AI content coordinator, moderator, and auditor.**"
https://www.reddit.com/comments/1vjz5a4/_/p2udfq9/

**[VERBATIM]** u/QuantumModulus, r/graphic_design, 25 Aug 2026:
> "That's why all these employers are desperately seeking AI-loving designers. **They want quantity, speed, and cheapness. Taste is dead, because they never cared about craft.**"
https://www.reddit.com/comments/1vy3bov/_/p5tr9py/

### Survey backing on the role split

- **[VERBATIM]** Envato, n=1,780 creative professionals globally, published 12 Nov 2025: daily AI use is **marketers 60% versus graphic designers 40% and illustrators 40%.** Most frustrated by AI: **graphic designers and illustrators at 14%, versus 8-9% for marketers and content creators.** Most energized: content creators 53%, marketers 50%. "One in three expect design roles to transform this year." "**58% have used AI without disclosing to a client**"; only 31% always disclose. https://elements.envato.com/learn/ai-trend-report *(verified firsthand)*
  **[SYNTH]** A 20-point gap in daily use and a near-2x gap in frustration is the handoff problem in two numbers: marketers generate, designers receive and fix.
- **[VERBATIM]** Nicole Greene, Gartner analyst, Digiday 24 Dec 2025: "Most of my clients are now using gen AI specifically to develop higher quality, strategic creative groups **to pass to their agencies**."
- **[PARA]** Forrester, "Predictions 2026: Marketing Agencies Resign Their Agency", 1 Oct 2025: a **15% reduction in agency jobs in 2026**, after average 8% headcount cuts in 2025. **[VERBATIM]** an agency CEO quoted in the post: "By 2028, we'll double profits and halve the people." https://www.forrester.com/blogs/predictions-2026-marketing-agencies-resign-their-agency/
- **[PARA]** Forrester with the 4A's, "The State Of AI Inside US Marketing Agencies, 2026", press release 24 Jun 2026 (**sample size not disclosed, report paywalled**): 90% of US marketing agencies use generative AI. Forrester's own headline framing is that nine in ten agencies use AI **to cut costs at the expense of creativity.** https://investor.forrester.com/news-releases/news-release-details/forrester-nine-10-us-marketing-agencies-use-ai-cut-costs-expense

---

## 7. Retail media and multi-market creative pain from practitioners

This was thin for you before and is still the thinnest section. Here is what is genuinely new. **I found essentially nothing usable in r/AmazonSeller or r/FulfillmentByAmazon**; those searches returned zero on-theme results. Flagging that as a real gap, not a lack of effort.

**The best single quote on multi-market creative economics:**

**[VERBATIM]** u/highqualityugc, r/FacebookAds, 3 Aug 2026, on a thread about state-level campaign splitting:
> "the state level thing is the part most people won't be able to copy, and it's not the targeting that stops them. **it's supply. the second you split by state you need a separate creative per segment, and now you're producing 10x the assets for the same campaign. most teams hit that wall and quietly go back to one national ad.**
> what makes it survivable is **locking what stays fixed before anything gets briefed. product name, core benefit, the objection you're handling, the cta, the offer. those never move. only the hook and the setting change per state.**
> then you get 10 variants that are the same ad wearing different weather, and when new york beats texas you actually know it was the angle and not that someone reworded the cta halfway through.
> worth naming which variable each batch is testing too. **if you can't say what the variable is you're producing, not testing, and the read at the end is just spend.**"
https://www.reddit.com/comments/1vebxd2/_/p1gsudu/

**[VERBATIM]** u/DazzlingCaramel5661, 12-market advertiser, r/PPC, 22 Sep 2026 (**discloses working at Bannerflow**):
> "What actually works at that scale (12 markets) is building one master template per format where the brand elements are locked, and the things that need to vary per market are the only things that change...
> **It's also worth separating translation versus localization. A translation service gives you the words. What takes the time is fitting those words into the layout correctly, for ex: German copy is longer, Arabic runs right to left, some markets need more disclaimer space.**"
https://www.reddit.com/comments/1nhl4e0/_/pbbxsif/

**[VERBATIM]** u/Confident_Pin584, r/PPC, 28 May 2026, on cross-market UGC:
> "Native language, references, filming style, even how people talk about skincare on camera changes market to market. A US creator trying to sound 'European' usually sticks out immediately in paid social, especially in Germany and Poland...
> Your point about 'localization in reverse' is dead on. **Brands think they're buying creator sourcing, but they're often buying US creative with subtitles.**"
https://www.reddit.com/comments/1tpkcxs/_/ooaayd2/

**[VERBATIM]** u/WhiskeyVagabond, insurance marketing, r/marketing, 19 Jun 2026 (regulated multi-jurisdiction creative, the closest analogue to retail media's spec fragmentation):
> "Pretty much all sales and marketing collateral had to be approved by each insurance jurisdiction... some states like NY and CA were on an island. It was a giant pain to make changes and a long process. **Sales wanted to edit collateral to focus on certain product aspects for different customers/industries and it was impossible to do those customizations at scale with the regulations.**"
https://www.reddit.com/comments/1u9vflw/_/osn8871/

**[VERBATIM]** u/Er_Valdi, r/PPC, 20 May 2026, on category-dependent AI tolerance (relevant to multi-vertical retail media):
> "In remodeling specifically, trust is doing like 70% of the work. People are about to spend $20k-$100k letting actual strangers into their house... **If I see an AI-generated hoodie ad, whatever. If I see an AI-generated kitchen remodel, my first thought is 'wait... did these guys even do this project?'**"
https://www.reddit.com/comments/1tileok/_/omxbo1g/

**[VERBATIM]** u/BlueGridMedia, r/PPC, 3 Jun 2026 (where the human edit pass is mandatory versus optional):
> "**anything trust-dependent, home services, legal, medical, high-ticket, needs a human edit pass so it doesn't look generic. For product images and straightforward ecomm creative, AI-assisted is fine and nobody notices.**"
https://www.reddit.com/comments/1tvok1l/_/opjrb9q/

**[VERBATIM]** u/AfternoonMuch6824, r/PPC (on platform self-contradiction):
> "Google rejecting its own AI generated copy for breaking Google's rules is pretty funny lol."

### Coordinated vendor astroturf as evidence of how this is being sold

**[FLAG]** Three separate r/FacebookAds and r/PPC accounts (u/Zealousideal_Leg5615 7 Jun 2026, u/Tall-Rooster-7112 4 Jun 2026, u/SecretJob1727 8 Jun 2026) posted near-identical copy about the same video tool, each including a version of: *"the localization feature translates one winning creative into 30 plus languages so you can test multiple markets from the same base"* and *"we went from producing 4 creatives per week to 20."* Do not cite these as practitioner voice. They are useful as evidence of **the exact promise the category is being sold on in 2026**: one winner, 30 languages, no rebuild, and no mention of who reviews the 30.

### Supply-side statistics

- **[PARA]** Celtra Creative Insights Report, 9th edition: **[VERBATIM]** "95% year-over-year growth in CTV ads that automatically adapt headlines, images, and offers". Sample size and per-campaign variant data are gated. https://celtra.com/resource/the-celtra-creative-insights-report-9th-edition/
- **[PARA]** Smartly 2026 Digital Trends, n=450, fieldwork Aug 2025: **42% deploy AI specifically to scale creative production for different audience segments.**
- **[PARA]** Relevant unmined 2026 coverage surfaced but not fetched: "AI is scaling retail media creative, but community signals may determine whether it actually works" (InternetRetailing, 20 Jul 2026); "How Diageo automated commerce media at scale with 15x faster launches" (The Drum, 12 May 2026); Adobe GenStudio for Commerce Media Networks launch (1 Jul 2026). These are the best remaining retail-media leads.

---

## 8. 2026 surveys and studies you may have missed

**Structural finding first. [SYNTH]** The review-burden question is being asked almost exclusively by **vendors** (Optimizely, Knak, TripleLift, Filestage, Ziflow, Screendragon, Typeface, Canto, Dash Social). Forrester, Gartner, Deloitte, McKinsey, Nielsen, Kantar, the ANA and The CMO Survey publish adoption, budget, trust and capability-gap numbers and stop there. **None of them publishes approval rounds per asset, hours spent reviewing AI creative, or the percentage of brands that have had an AI creative incident.** That asymmetry is itself a defensible claim: the industry measures AI creative output volume and does not measure the human review cost it creates.

### The strongest single source

**Optimizely 2026 Global AI Marketing Study.** n=2,003 marketing leaders, US/UK/DE/SE/NL/AU/UAE, fieldwork May-June 2026, conducted by Savanta. https://www.optimizely.com/company/press/2026-global-data-study/ *(all verified firsthand)*
- **[VERBATIM]** "More than three quarters (76%) of marketers spend at least three hours each week editing, fact-checking or correcting AI-generated output."
- **[VERBATIM]** "25% admit they frequently or always publish AI-generated content they know is not fully on-brand when under deadline pressure"
- **[VERBATIM]** "More than half (54%) of marketers say leadership underestimates the human effort required to make AI-generated work usable."
- **[VERBATIM]** "Only 30% of marketers believe their brand voice is genuinely unmistakable."
- **[VERBATIM]** "30% say they frequently or always pass off AI-generated work as their own, human-created original work"
- **[PARA]** Only **4%** report AI saves time at every process stage. 69% of C-suite report full AI alignment; only 27% of analysts agree. 65% would pause or adjust their AI rollout to strengthen governance.

### Best approval-rounds data anywhere

**Knak, "Marketing Production in the Age of AI" / State of Marketing Production 2026.** n=333 enterprise marketing decision-makers, US/UK/Canada, companies $50M to $1B+ revenue, published 28 Jul 2026. https://knak.com/state-of-marketing-production/ Coverage verified firsthand at https://martech.org/why-ai-hasnt-solved-marketings-time-problem/ (8 Sep 2026, Kath Pay)
- **[VERBATIM]** "69% go through two or three rounds of revisions before receiving approval"
- **[VERBATIM]** "Sixty percent of teams need at least four people to produce a single email"
- **[VERBATIM]** "88% say its output still requires moderate or substantial human editing"
- **[PARA]** Biggest delay: **securing approvals and sign-offs, 47%.** Design and creative production 38%. Coordination 36%.
- **[VERBATIM]** "82% of enterprise marketing teams spend at least half their time on production, building, reviewing, approving, and sending, instead of strategy or planning."
- **[VERBATIM]** "85% of marketing teams missed at least one campaign launch date in the past 12 months because of workflow constraints. Getting approvals and sign-off is the single biggest reason why."

### The "review tax", quantified

**TripleLift.** n=200 advertising professionals, fieldwork April 2026, published 19 May 2026. https://ppc.land/most-advertisers-use-ai-for-optimization-but-not-creative-triplelift-finds/ *(verified firsthand)*
- **[VERBATIM]** "45% of respondents spend between one and four hours per week reviewing AI outputs. A further 22% spend between four and eight hours on the same activity." **6% dedicate 12+ hours weekly.**
- **[PARA]** AI adoption by function: campaign optimization 73%, audience targeting 59%, **creative production only 25%**, full campaign execution automation 19%.

### Governance becomes the top blocker

- **[PARA]** **Jasper, State of AI in Marketing 2026**, n=1,400, fieldwork end 2025, published Feb 2026: **27% cite governance as the top barrier to scaling AI, up from 8% the prior year.** Ranked barriers: (1) brand, legal and compliance reviews, (2) lack of output quality, (3) data and privacy risks. **Review is the number-one scaling constraint.** 91% of teams now use AI, up from 63%. Only 41% can demonstrate AI ROI, down from 49%. https://www.jasper.ai/state-of-ai-marketing-2026
- **[VERBATIM]** **Screendragon, "The State of AI in Content & Creative Operations 2026"**, n=500 marketing/creative/content/ops leaders, US and UK, released 21 Jul 2026: "only 24% of organizations have fully integrated AI into everyday workflows"; only **18% of work enters organizations through structured workflow systems**; **82% do not have fully connected DAM and workflow environments**; only 21% feel very confident meeting future content demand. https://www.prnewswire.com/news-releases/why-marketings-ai-progress-is-stalling-at-scale---new-research-from-screendragon-302831070.html
  **This is the most promising un-mined source for your exact thesis. The full report is form-gated and promises "10 evidence-based research chapters" with cohort cuts by role and team size. Worth a manual download.**
- **[PARA]** **ProGEO.ai**, n=112 marketing professionals surveyed at RSAC, March 2026: **76.8% have formal corporate genAI usage policies but only 43.8% enforce them with technical controls.** 12.5% rely on the honour system. 57.1% maintain personal genAI subscriptions outside organisational visibility. **[FLAG] small n, recruited at a cybersecurity conference, skews security-aware.** https://ppc.land/76-of-marketing-pros-use-genai-daily-but-governance-lags-behind/
- **[PARA]** **NP Digital**, n=565 US digital marketers (Sept 2025) plus a 600-prompt accuracy test, published early Feb 2026: **36.5% admit hallucinated content has been published publicly.** Of those published errors, **53.9% involved brand-unsafe content.** 47.1% encounter inaccuracies several times weekly. **Only 23% felt confident using AI without review.** https://ppc.land/nearly-half-of-marketers-encounter-ai-errors-weekly-as-study-exposes-trust-gap/
- **[PARA]** **Mediaocean 2026 outlook**, n=320 marketing professionals, fieldwork Nov 2025: top AI deployment concerns are **balancing adoption with brand safety, accuracy and creative control 43%; managing AI automation without losing oversight 42%; governance and compliance uncertainty 38%.** https://ppc.land/marketers-bet-on-ai-media-despite-struggling-with-generative-ai-adoption/
- **[VERBATIM]** **Integral Ad Science with YouGov**, n=220 UK digital media experts, fieldwork Oct 2025, released 8 Dec 2025: 56% identified "ad adjacency to AI-generated content as a major digital media challenge for 2026". https://ppc.land/uk-advertisers-brace-for-ai-content-chaos-as-brand-safety-concerns-surge/
- **[VERBATIM]** **Canto, 2026 State of Digital Content Report**, n=434 US and UK professionals, fieldwork Nov 2025: "88% of teams struggle to keep product content consistent across channels"; "**Only 35% of respondents feel very confident employees are always using the most up to date, approved version**". https://www.canto.com/press-releases/cantos-state-of-digital-content-report-new-research-reveals-key-digital-content-trends-for-2026/
- **[VERBATIM]** **The CMO Survey** (Duke Fuqua / Christine Moorman with AMA and Deloitte), 35th edition, fielded 7-29 Jan 2026, 308 respondents from 2,111 contacted (14.6% response rate), 97% VP-level or above. On a 7-point scale, "Ensuring that the marketing strategy that generative AI produces is a good fit **for your brand**" scored **4.5, up from 4.3 in 2025.** "Understanding how content or decisions are being made" 4.1 to 4.4. https://cmosurvey.org/wp-content/uploads/2026/04/The_CMO_Survey-Highlights_and_Insights_Report-2026.pdf
  **[SYNTH]** This is the best analyst-grade proxy for brand-consistency risk. After three years of genAI, senior US marketers rate their own ability to keep genAI output on-brand at barely above the midpoint, improved by 0.2 points in a year.
- **[VERBATIM]** **Typeface Signal Report, "The AI Speed Paradox"**, n=200+ VP-level marketing leaders: "In 2025, 85% of leaders shipped a campaign in one to two weeks. By 2026, only 50% do, and 34% now need one to two months." "93% of marketing leaders say AI raised the pressure to move faster"; "Only 20% have the documented workflows to scale"; "66% name compliance, legal, and privacy as the top barrier to scaling AI." https://www.typeface.ai/resources/reports/typeface-signal-report
  **[FLAG]** The most on-point figures (92% say a campaign now requires 10+ stakeholders; **44% require 20 or more people for a single launch, up from 10% in 2025**) are **secondhand only**, via https://ppc.land/murphycobb-adds-amplify-unit-to-vet-ai-production-tech-for-advertisers/ and agencyreporter.com. They are in the gated PDF, not the landing page. **Your working directory is /Users/vikas/pallavi/Typeface, so you may be able to cite these firsthand from the internal PDF.**

### Regulatory, which is now part of the ship decision

**[VERBATIM]** u/ksplat_, r/PPC, 10 Jul 2026 (score 12), post "EU AI Act starts August 2026, matters if you're running AI generated ad creative":
> "Article 50 of the EU AI Act enforces Aug 2, 2026, requires actual machine readable disclosure on AI content, not just a caption. Applies regardless of where you're based if you've got EU traffic. **The part that actually matters for ad creative specifically: anything AI generated that could pass as a real photo/video gets treated like a deepfake under this, doesn't matter that it's just a product shot or campaign asset, no 'it's just marketing' exemption for images/video like there is for text.** Fines up to 15M or 3% of global turnover, worldwide revenue not just EU."
https://www.reddit.com/r/PPC/comments/1uskxjo/eu_ai_act_starts_august_2026_matters_if_youre/
Corroborated by a separately-surfaced legal summary: **[VERBATIM]** "meaningful human review and editorial responsibility eliminates the need for disclosure" for AI-generated *text* on matters of public interest, but images and video require labelling regardless. https://www.legal500.com/intelligence/european-union/media-telecoms-it-entertainment/eu-ai-act-guidance-expands-ai-disclosure-rules-for-advertisers-and-pr-teams
**[SYNTH]** As of 2 Aug 2026, "did a human meaningfully review this" is not just a quality question in the EU, it is a disclosure-liability question. That materially changes the value of a provable review step.

### The review-as-a-product market forming

**[PARA]** **Blee raised $27M** on 8 Sep 2026 to build AI content governance for legal, compliance and brand teams. **MurphyCobb launched an "Amplify" unit** on 21 Sep 2026 specifically to vet AI production tech for advertisers. **PerformLine launched a pre-publication scanner** bringing AI-powered compliance review to marketing creative on 13 Jul 2026.

---

## 9. Quantified time costs

### Rounds and versions

| Figure | Source | Notes |
|---|---|---|
| **69% go through 2 or 3 rounds of revisions before approval** | Knak, n=333 enterprise marketers, Jul 2026 | Marketing production generally, not AI-specific |
| **60% need at least 4 people to produce a single email** | Knak, same | |
| **Approvals and sign-offs = 47%**, the single biggest delay | Knak, same | Ahead of design/production at 38% |
| Review averages **8 days and 3+ versions**; brands 10 days, startups 9, agencies 7+, freelancers 4 | Filestage, n=366 | **2023 vintage. Pre-AI. No 2025/2026 edition exists.** This is the original source of the widely-laundered "8 days" figure. https://filestage.io/blog/creative-collaboration-report/ |
| "57% of creatives, three to five versions of a project typically occur before it can be dubbed 'done'"; "48% said that they spend at least five hours per month chasing feedback"; "60% frequently have to spend time simply explaining to external stakeholders how to give feedback" | Ziflow 2023 State of Creative Workflow | **2023, sample size not published** |
| **Practitioner contract norms: 2 or 3 rounds included, hourly after** | Consistent across seven independent r/graphic_design, r/videography and r/GraphicDesignPH practitioners, Sept 2026 | See below |

The 2 to 3 round norm, stated independently:
- **[VERBATIM]** u/Melodic-Excitement-9: "Three round revision max. Else pay more or go elsewhere." https://www.reddit.com/comments/1wovm4l/_/pbqn2cy/
- **[VERBATIM]** u/Diligent-Educator409: "I include 3 in the quote... **Usually more than 3 rounds of revisions is either that they are communicating poorly, they're being indecisive, or the project has evolved / changed.**" https://www.reddit.com/comments/1wovm4l/_/pbqbqjh/
- **[VERBATIM]** u/Designer_Sea_6652: "Did you have a 'contract' stating number of revisions included (usually about 3) and then state $ for each additional round of changes. **Makes clients really check the work when they know they're going to get charged more**" https://www.reddit.com/comments/1wovm4l/_/pbq6t1c/
- **[VERBATIM]** u/Recordeal7, 25 years in video: "I tell clients '2 rounds of revisions' then all hourly rates apply... **I'll be on the lookout for AI revisions now. I think it's a spectacular idea to incorporate some AI review limitation in the production agreement.**" https://www.reddit.com/comments/1wmai8r/_/pb5psk9/

### What actually happens versus the contract

**[VERBATIM]** u/emotionalthroatpunch, freelance designer, r/graphic_design, 24 Sep 2026 (the densest single data point in the harvest):
> "I usually include two rounds of revisions in projects where I charge a flat fee... **Got a project on at the moment with about ~30 discrete deliverables, some of which are currently sitting at draft 10, as the client decided to suddenly involve a bunch of other stakeholders in the feedback process.** It's a punish for sure, but **I'm gonna make about three times what I originally quoted on the job**"
https://www.reddit.com/comments/1wovm4l/_/pbqdifs/
**[SYNTH]** 30 deliverables, draft 10, 3x the quote, cause: a late stakeholder addition. That is the whole failure mode in one comment.

**[VERBATIM]** u/uckfu, agency/in-house comms group, r/graphic_design, 24 Sep 2026:
> "Our clients typical review process involves a team, so they want each member of the team to have their own comments and edits documented. **Not just on round one, but also on round 10.**... At the moment, we are slightly behind our growth projections, so every client is considered 'at risk'. So our account teams are bending over backwards."
https://www.reddit.com/comments/1wp1bdx/_/pbrxdzu/
Same user on the round multiplier: **[VERBATIM]** "There is also a tendency of clients pulling in a **last minute reviewer that has not been part of the process sooner.** Which can cause major speed bumps as a new voice wants to get involved." https://www.reddit.com/comments/1wp1bdx/_/pbs8mt5/

**[VERBATIM]** u/Specialist-Ear-761, r/managers, 13 Sep 2026 (rounds before the client ever sees anything):
> "At ad agencies, it's not uncommon for teams working to present their initial ideas to group creative directors and executive creative directors at the same time, then **receiving feedback and doing a few more rounds of revisions before it gets to the client**"
https://www.reddit.com/comments/1we0zna/_/p9aig7y/

**[VERBATIM]** u/TheWolfAndRaven, video editor, r/editors, 18 Sep 2026: "**It took 37 rounds of revisions**, that was round 20 something." https://www.reddit.com/comments/1wifh57/_/pab7m8m/

### Why the round count is unmeasurable today (the sharpest creative-ops observation found)

**[VERBATIM]** u/LouieValkhof, r/graphic_design, 24 Sep 2026:
> "Agree with putting a number in the contract, but **it only held up for us once we also wrote down what one round is.** For a long time feedback came in over chat, email and comments in a shared folder, a bit at a time, and **'3 rounds' meant nothing because nobody could say which round a message belonged to.** Now a round is one batch of feedback, collected in one place and sent back together. Anything after that batch starts the next round. And every time we deliver, the mail says how many rounds are left, so when an extra one gets charged it's not news to anyone."
https://www.reddit.com/comments/1wovm4l/_/pbq7lur/

### Hours

- **76% spend at least 3 hours per week** editing, fact-checking or correcting AI output (Optimizely, n=2,003)
- **45% spend 1-4 hrs/wk, 22% spend 4-8 hrs/wk, 6% spend 12+ hrs/wk reviewing AI outputs** (TripleLift, n=200)
- **70%+ spend hours weekly fact-checking AI outputs** (NP Digital, n=565)
- **[VERBATIM]** "60% of agency creative teams report spending over 25% of their time on non-creative tasks" (Monotype, "over 1,000 creative professionals", fieldwork dates not published) https://www.monotype.com/agency-scaling-operations-report
- **[PARA]** Ad strategists spend an average of **39.75 hours monthly** on routine campaign tasks, roughly 25% of annual working time; **71% of ad ops teams report manual processes put client campaigns at risk** (Fluency 2026 Agency AdOps Benchmark, n=170+ US agencies and in-house teams, published 26 Mar 2026) https://ppc.land/71-of-ad-agencies-say-manual-work-is-putting-campaigns-at-risk/
- **[VERBATIM, SECONDHAND, SPONSORED]** "nearly half of respondents reported that creating, reviewing, approving and activating a single piece of content can involve **between 51 and 200 people**". Attributed to Adobe by a **sponsored** Marketing Dive post, 14 Sep 2026. **[FLAG] business.adobe.com is unreachable; the Adobe primary, report name and sample size could not be confirmed.** https://www.marketingdive.com/spons/the-ai-content-tsunami-creation-is-the-easy-part/830184/

### AI-specific time observations from practitioners

- **4 to 5 variations reviewed per hour** once in rhythm; deciding is ~20% of total time (u/brownelijah, r/FacebookAds, above)
- A mandatory AI zoom-in checklist **slows production by about 15%** but nearly eliminates QA variance (u/MulberryLost2889, above)
- **2 to 3 generations reviewed per usable asset** at volume, versus 1 to 2 finished assets per day when a human actually completes them (u/RealMuseAI, above)
- **Half an hour per executive AI drop-in** spent explaining why it is bad (u/MemeHermetic, above)
- **4 hours** and **5 hours to 3am** on Meta support chats over AI-swapped creative (u/HawthornWardrobe and u/WontonBogeyman, above)
- **2-3 hours per client every Monday down to ~10 minutes of review** for automated reporting (u/datagekko, r/PPC, 26 Aug 2026) https://www.reddit.com/comments/1vy8ksb/_/p5z1j1i/
- **[VERBATIM]** u/anton-zazerski, HN, 14 Sep 2026, on an AI-generated launch video: "It came back with this in 1 pass with **5 rounds of feedback**." https://news.ycombinator.com/item?id=49697382 **[FLAG] vendor demo, directional only.**

**[GAP]** Neither I nor my sub-agent found a clean first-person "we spend X hours a week QA-ing AI variants" statement from a named marketer. The TripleLift bands are the best available. This looks like a genuine hole in the public record and therefore a defensible thing to claim nobody has measured.

### More reviewers does not mean fewer errors

**[VERBATIM]** u/SoftballGuy, r/graphic_design, 27 Aug 2026:
> "And then someone checked the QR code. IT WAS STILL THE QR JABBERWOCKY. My dumb ass had personally put that code in, wrote down a reminder to get a real code when the site went up, and then just forgot. **Three people proofed it, including our legal counsel, and not a single person on the team checked the QR before it went up. We sent this to local business! We sent this to media!**"
https://www.reddit.com/comments/1vzxbvz/_/p68hx6p/

### The 2026 proofing stack, named by practitioners not vendors

From r/graphic_design, "Are your clients dropping Acrobat and PDFs as the proofing standard?", u/uckfu, 24 Sep 2026: https://www.reddit.com/comments/1wp1bdx/
Named in use: **Workfront, Ziflow, PageProof, Veeva** (life sciences), **frame.io, usepastel.com**, and Acrobat online with manually named rounds (r1, r2).
- **[VERBATIM]** u/twitchykittystudio: "If you utter the words '**high risk of in-market error**' regarding the current 'process', you just might catch the attention of the people who can help you remedy this." https://www.reddit.com/comments/1wp1bdx/_/pbsgf25/
- **[VERBATIM]** u/uckfu, OP: "This year, our team has run into quite a few clients that either can't accept a PDF or they can't work with a PDF... **We have clients converting PDFs to PPT, or having us convert our INDD files back to word, so they can use track changes.** Unfortunately we are not in any position to push back (management)."
- **[VERBATIM]** u/uckfu on tool adoption friction: "But, unfortunately, **getting a green light to use new software at our company is tough. Everything has to go through corporate IT.**" https://www.reddit.com/comments/1wp1bdx/_/pbrxxrn/

---

## 10. Counter-evidence: marketers who say this is not a problem

This side is real and I looked for it hard. It clusters into four arguments.

### Argument 1: the numbers say it is fine, and the outrage is marketer-to-marketer

**[VERBATIM]** u/RegisterConscious993, performance marketer, 18 years in business, r/marketing, 14-16 Jan 2026 (the fullest counter-case in the corpus; note he was **downvoted to -103, -34 and -25** across the thread, which is itself the finding):
> "**I'm not talking out of my ass here. I'm a performance marketer, I look at numbers every single day. The numbers show my costs go down and profits up.**" https://www.reddit.com/comments/1qch0v1/_/nzkeb5p/
> "**Of course if you zoom in and analyze the image you may be able to tell, but 99% of consumers don't. They scroll, like, and move on.**" https://www.reddit.com/comments/1qch0v1/_/nzkctx9/
> "I actually just needed a custom hero image made for my landing page. I could either spend 45 minutes in Photoshop, spend money and time to hire someone, or spend 5 minutes prompting an llm to get it. An AI image made sense here. **It didn't hurt conversion rates and I highly doubt anyone noticed. Even if they did, I'm a numbers guy and the numbers said sales still come in regardless.**"
> "Most people here aren't performance marketers and aren't tech savvy. Why should I listen to you or anyone in this sub if they aren't in my field? **I listen to people in my field and most importantly I listen to the numbers.**" https://www.reddit.com/comments/1qch0v1/_/nznqkyf/

**[VERBATIM]** u/BlueGridMedia, agency, r/PPC, 3 Jun 2026 (the cleanest, least-heated version):
> "**Clients generally don't ask or care how the creative was made, they care whether it performs. The sensitivity is more of a marketer-to-marketer conversation than a real consumer concern.**... For product images and straightforward ecomm creative, AI-assisted is fine and nobody notices."
https://www.reddit.com/comments/1tvok1l/_/opjrb9q/

### Argument 2: the perceived quality bar is a confound, not a finding

**[VERBATIM]** u/ThrowbackGaming, r/marketing, 14 Jan 2026:
> "**there are too many variables at play to blindly attribute a drop in CTR directly to the use of ai-generated images. You could have just as easily had the same drop with a stock image.** It could have been the wrong audience, it could be bad copywriting, bad offer, etc. Unless you are running surveys to get user feedback on your ads it's hard in general to determine exactly what could be causing a dip in performance."
https://www.reddit.com/comments/1qch0v1/_/nzk1fu4/

**[VERBATIM]** u/danque, r/marketing, 15 Jan 2026:
> "I wouldn't say that this makes a conclusive study. **To really make sure that it's the ai influencing your campaign try doing a/b sample with both ai and non ai images.**"
https://www.reddit.com/comments/1qch0v1/_/nzp7ikg/

**[VERBATIM]** u/psyche74: "Everyone \*thinks\* they can identify AI images." (full quote in theme 4)

### Argument 3: perfection per asset is the wrong goal

**[VERBATIM]** u/Latter-Law5336, r/FacebookAds, 9 Jan 2026:
> "**also stop trying to make every creative perfect. better to test 20 decent ones than spend a week on 3 polished ones**"
https://www.reddit.com/comments/1q4jfk3/_/nyj6k38/

**[VERBATIM]** u/BashFunky, r/FacebookAds, 19 Feb 2026:
> "The brands winning with AI video ads aren't making one 'perfect' video. They're producing 15-20 variations (different hooks, same body) and letting Advantage+ pick the winners. **Even if each individual AI ad is 80% as good as a hand-crafted one**, [the volume wins]"
https://www.reddit.com/comments/1r4wcb5/_/o69nbiy/

**[VERBATIM]** u/DKsnap, 15 years in performance marketing, 10 in search arbitrage, r/marketing, 11 Aug 2026:
> "**I use to build teams of 20+ buyers to run my feed partnerships and now I built LLMs to do all that 24/7 and all I needed to do was build in the baseline ROI and train the agents to do their task in the workflow. I see a lot of top spenders across all paid media running a ton of AI automation and crushing it.**"
https://www.reddit.com/comments/1vjz5a4/_/p2yye7o/

### Argument 4: AI output is more consistent than human output, which is a QA advantage

**[VERBATIM]** u/Educational-Idea-439, agency, r/content_marketing, 6 May 2026:
> "The fix was using a purpose-built avatar tool rather than a general generator. HeyGen gave us predictable output: same presenter, same lighting, same quality bar across every asset. No off days, no re-shoots. **That consistency is actually a QA advantage over filmed content, which helped get client buy-in.**"
https://www.reddit.com/comments/1s6w3sy/_/ok9qj0b/

**[VERBATIM]** u/CanklankerThom, working designer, r/graphic_design, 22 Jun 2026 (downvoted to -3):
> "**People complaining it's taking their jobs are dumb. It's an incredible tool and I've found the more creative you are, the more you can get out of it. It has actually produced MORE work opportunities** [for me]"
https://www.reddit.com/comments/1ucqcgg/_/ot5zhee/

**[VERBATIM]** u/jaimequin, r/marketing, 13 Aug 2026: "If my efforts now look AI then why not just use AI and save time and get me 90% there." (full quote in theme 4)

### Survey-side counter-evidence

- **[PARA]** ARF: marketer confidence in AI outputs rose **82% to 93%** between Nov 2025 and May 2026 waves. **[FLAG] n not disclosed.**
- **[PARA]** Kantar: **over 40% of ads with seamless AI integration landed in the top tier for branded cut-through.** Ads with obvious or distracting AI visuals performed worse. https://www.kantar.com/inspiration/advertising-media/rethinking-ai-generated-advertising
- **[VERBATIM]** DoubleVerify: "**40% [of consumers] view polished, professional AI ads positively**"; "56% say they cannot consistently identify AI-generated content"
- **[VERBATIM]** Ipsos, n=3,000 US consumers, 20 ads (10 human, 10 AI): "**Only 25% of AI ad viewers were at least somewhat confident the spot was AI-made**"; 40% of all viewers were uncertain either way. (Their headline finding cuts the other way: human ads scored 14% stronger on short-term and 17% stronger on long-term effectiveness.) https://www.ipsos.com/en-us/ai-ads-are-good-enough-and-thats-problem
- **[PARA]** Impression, n=1,000 UK marketing professionals, fieldwork Oct 2025: **54% anticipate larger marketing teams; only 6.7% expect team size decreases.** **[VERBATIM]** Mikey Emery: "AI job scaremongering could still be a bit premature." https://ppc.land/77-of-uk-marketers-predict-growth-while-ai-stays-out-of-creative-roles/

### Internal review itself judged worthless by marketers

This is a distinct counter-argument: not "AI is fine" but "review theatre was always the problem." From r/marketing, "How do you get feedback on ads?", u/UchihAckerman7, 14 Jul 2026: https://www.reddit.com/comments/1uw48nz/
- **[VERBATIM]** u/FisherTeps2001: "**we used to do team feedback rounds and they were useless because teammates picked apart copy and colors no real customer would ever notice.** now i just dm 3 or 4 people who look like our buyers and ask them what stops them from clicking, and that's been the only feedback that's ever moved anything." https://www.reddit.com/comments/1uw48nz/_/oxgw14k/
- **[VERBATIM]** u/FarRub2855: "**Internal group feedback usually just turns into people trying to sound smart in front of thier boss instead of looking at the actual message.**" https://www.reddit.com/comments/1uw48nz/_/oxhra09/
- **[VERBATIM]** u/TieForeign8827, an actual structured protocol: "Don't ask 'what do you think?', give colleagues a five-second view, then ask three fixed questions: **what is being sold, who is it for, and what should you do next?** Use their answers to catch comprehension gaps" https://www.reddit.com/comments/1uw48nz/_/oxhuon3/

---

## Flagged, unverified or explicitly do-not-use

1. **"78% of Gen Z can identify AI generated images and will scroll past them"** (u/Objective-Feed7250's opening line). Source never produced despite a direct request in-thread. **Unverified.**
2. **Dash Social "95% of AI-generated assets never make it into production."** Sentence confirmed on the page; methodology is undisclosed-n qualitative interviews.
3. **Adobe "51 to 200 people" per content item** and **"demand for content will grow 5x by 2027."** Both secondhand; business.adobe.com unreachable.
4. **Typeface Signal Report stakeholder counts (92% / 44% / 20+ people).** Secondhand, in the gated PDF. You likely have internal access.
5. **Ziflow blog cluster** claiming "62% of marketers have seen content demand rise fivefold", "90% of teams still require three or more approval layers", "30% of teams have published off-brand content", "average creative review runs eight days across three rounds". **DO NOT CITE.** All traced to an unsourced Medium post or laundered from Filestage's 2023 survey through two intermediaries.
6. **Lytho's "only 26% use AI to support governance"** attributed to Jasper 2026. Figure not on the Jasper landing page.
7. **Kantar Media Reactions 41% / 29%** and **all Gartner figures**: sample sizes not disclosed in accessible sources.
8. **Statistics farms to avoid entirely** (numbers appear invented, no traceable methodology): amraandelma.com, influencers-time.com, digitalapplied.com, omnibound.ai, averi.ai, sqmagazine.co.uk, memeburn.com, technologychecker.io, klover.ai, contentgrip.com, metaintro.com. The last two **mis-attribute Forrester**.
9. **Reddit astroturf**: the Arcads cluster (theme 7), the competitor-screenshot-to-prompt-template cluster (theme 5), and most single-score comments in r/FacebookAds that mention a tool by name.
10. **Genuine measurement gaps in the public record**: percentage of marketers who review every AI asset versus a sample; approval rounds specifically for AI creative; variants per campaign as a benchmark; off-brand rate from AI creative as a measured number; and a first-person "hours per week QA-ing AI variants" quote.

---

## Retrieval routes

**Worked**
- **Arctic Shift Reddit archive API** (`arctic-shift.photon-reddit.com`). The single most productive route by a wide margin and the only Reddit route that worked at all. Modes: `/api/comments/tree?link_id=<id>&limit=200`, `/api/comments/search?subreddit=X&body=<terms>&sort=desc`, `/api/posts/search?subreddit=X&title=<terms>`, `/api/posts/ids?ids=a,b,c`. Requires a browser User-Agent or it 403s. **Gotchas that cost real time:** `body=` requires one of subreddit/author/link_id alongside it; `limit=100` on a `body=` search often times out while `limit=20-30` works; multi-word queries with common words return HTTP 422 far more often than short rare terms; single-word title searches return 422; it throttles hard after roughly 15 to 20 queries and then returns 422 for everything for several minutes. **Productive loop:** `posts/search` by subreddit and date window to get titles, eyeball for on-theme titles, then `comments/tree?link_id=` to pull the whole thread.
- **PullPush** (`api.pullpush.io`). Worked for roughly the first 15 comment searches, then hard 429 for the rest of the session and never recovered. Good while it lasted for broad keyword discovery. Note `subreddit=` combined with `q=` returns zero rows.
- **Google News RSS via curl** (`news.google.com/rss/search?q=...&hl=en-US&gl=US&ceid=US:en`). Unblocked, batchable, returns dated headlines plus publisher. Best discovery tool for trade press. This is how I found the MAMEE incident, the MikeTeevee coverage and the retail media leads. Its `<link>`s are opaque JS redirects, so it gives titles and dates but not URLs.
- **Bing News RSS via curl** (`bing.com/news/search?q=...&format=RSS`) returns **real publisher URLs** inside the apiclick `url=` parameter. Pair the two: Google News RSS to find the story, Bing News RSS to resolve the URL. This pairing is the best WebSearch substitute currently available.
- **WebFetch direct on known URLs.** Worked cleanly on digiday.com, ppc.land, martech.org, medianews4u.com, marketing-interactive.com, thecurrent.com, emarketer.com, optimizely.com, iab.com, elements.envato.com, dashsocial.com, ipsos.com, kantar.com, mediapost.com, globenewswire.com, filestage.io, screendragon.com.
- **Sitemap mining plus slug guessing**, then WebFetch the exact URL. ppc.land (12,162 posts) is the single richest vein for dated survey coverage.
- **curl plus browser UA on cmosurvey.org, then `pdftotext -layout`.** Highest-yield route for analyst-grade data: full question wording and 7-point scales.
- **`https://r.jina.ai/<url>` as a 403 bypass.** Worked for investor.forrester.com and canva.com/newsroom.
- **HN Algolia API** (`hn.algolia.com/api/v1/search`). Worked, no auth, but **very low yield**: Show HN and Ask HN spam dominates every marketing-adjacent query. Use `advancedSyntax=true` with a single quoted phrase; multiple ANDed terms return zero.

**Failed**
- **Every general web search engine.** DuckDuckGo html/ and lite/ (captcha, and WebFetch on it returns the duck-selection challenge page), Mojeek (captcha), Brave (Tor-block interstitial), Ecosia (403), Startpage (WebFetch allowlist block), Marginalia (302 to a non-commercial index, useless for trade press), all public SearXNG instances (searx.be, priv.au, opnxng.com, search.inetol.net, searxng.site: Anubis or custom bot challenges).
- **Bing web search via r.jina.ai** returns HTTP 200 but **ignores the query entirely** and serves generic AI-company results. Bing *News* RSS is fine; Bing *web* is not. Do not be fooled by a 200.
- **r.jina.ai against search engine endpoints** hits Cloudflare on r.jina.ai itself. `s.jina.ai` now requires an API key (401).
- **Reddit direct.** www.reddit.com/*.json and old.reddit.com return 403 or an SPA shell for every User-Agent tried. WebFetch refuses www.reddit.com. r.jina.ai passes through Reddit's 403.
- **Redlib/Libreddit mirrors.** redlib.catsarch.com, safereddit.com, redlib.privacyredirect.com, redlib.freedit.eu, redlib.nadeko.net all behind Anubis/Cloudflare challenges. The Anubis page leaks `og:title`, which produces false "it worked" greps.
- **Other Reddit archives:** api.pushshift.io, api.reveddit.com, teddit.net all empty or dead.
- **Hard 403 or unreachable:** gartner.com, mckinsey.com, business.adobe.com, canva.com, cnet.com, forbes.com, businesswire.com, demandgenreport.com. Adweek soft-404s every URL guess to its homepage.
- **JS-rendered site search pages return only nav chrome** to WebFetch: marketingbrew.com/search, thedrum.com/search, adexchanger.com/?s=.
- **Registration or paywall gated:** IAB full reports, Celtra, Screendragon, Dash Social, Canva, Digiday+.
- **Python `xml.etree` is broken in this environment** (no expat module); RSS and sitemaps must be parsed with regex.

---

## The 5 quotes I would put on a slide

1. **Craig Elimeliah, Chief Creative Officer, Code & Theory** (Digiday, 24 Dec 2025):
   > "A single prompt can give you 200 like, pretty good options. But someone has to sift through and judge and refine. **That decision work used to be invisible; now it is the job.**"
   *The thesis sentence. Named, senior, on the record, and it reframes review from cost centre to the actual work.*

2. **u/Objective-Feed7250, running paid social for an apparel brand** (r/marketing, 14 Jan 2026, score 410):
   > "**The images looked fine to me.** Models wearing the clothes, decent lighting, no obvious errors. But apparently Gen Z can tell... **Stuff that's not obvious unless you're looking for it.**"
   *The non-designer's blind spot, self-reported, with a 40% CTR drop attached. Nobody says this about themselves in a survey.*

3. **u/LouisVanHoof, agency running multiple client accounts** (r/FacebookAds, 26 May 2026):
   > "**Since two years our job has been dodging their AI enhancement bullets, turning off toggles that we turned off in the first place. It's insanity.**"
   *Trust collapse in one line, and it names the specific failure: the control surface lies.*

4. **u/TTFV, r/PPC agency practitioner** (6 Sep 2026):
   > "**Even if you review them human nature is to say 'I guess that's okay' and run with it** rather than rewrite the 70% that are pedestrian at best."
   *The most honest thing anyone said about what review actually is at volume. Pairs with brownelijah's 4 to 5 variants per hour.*

5. **u/highqualityugc, performance creative** (r/FacebookAds, 3 Aug 2026):
   > "the second you split by state you need a separate creative per segment, and now **you're producing 10x the assets for the same campaign. most teams hit that wall and quietly go back to one national ad.**"
   *The multi-market section's missing quote. "Quietly go back" is the tell: the capability exists, the review capacity does not.*

**Runners-up worth holding in reserve:** u/Just_Use8502, "one bad image and suddenly every asset is under a microscope." u/SimonBuildsStuff, "QC processes were built for human-made creative. AI outputs break differently." Ellen Utrecht (MikeTeevee), "The question for creative teams is no longer how many options they can produce. It's how they decide which ideas deserve to exist." And u/Serious-ISFJ-T (r/FacebookAds, 8 Aug 2026), "Creative production has never been cheaper yet ads quality has never been worse." https://www.reddit.com/comments/1vj3sz8/_/p2j87bf/
# Voice of Customer: Enterprise Performance / Brand Marketers Shipping Ad Creative at Scale

**Method note:** This session's WebSearch quota was exhausted before I started, so I built my own retrieval path (Startpage via a proof-of-work solver, Reddit via redlib mirrors, direct HTTP + reader-proxy fetches). That worked well for Reddit, trade press, and vendor research. It worked poorly for LinkedIn (mostly blocked) and for G2/Trustpilot free-text (paywalled/JS-gated). Gaps are flagged explicitly at the end.

**Labels used throughout:** `[VERBATIM]` = exact quoted text. `[PARA]` = my paraphrase of a source. `[SYNTH]` = my own inference, not in any source.

---

## 1. The pain of reviewing large volumes of creative variants

### The phrases they actually use

`[VERBATIM]` "the whole game collapsed into a creative testing race"
u/No-Sprinkles-9955, r/FacebookAds, Jul 2026: "targeting is basically advantage+ deciding everything, bidding is automated, placements are automated. the only place i can actually still move the needle is how many creative angles i can put in front of the algo each week. feels like the whole game collapsed into a creative testing race. whoever can produce and iterate more concepts wins... curious how many new creatives you all are pushing per week and **how you keep up without burning out**"
https://www.reddit.com/r/FacebookAds/comments/1v9kpra/creative_is_the_only_lever_left_everything_else/

`[VERBATIM]` "the creative treadmill"
Same thread, u/No-Sprinkles-9955: "once targeting is dialed in its literally just creative volume from there. **thats the grind tho, pumping out enough variants to actually find winners.**" ... "game changer for **the creative treadmill** ngl"
(Note: this commenter is plugging a tool in the same breath, so treat as marketing-adjacent, but the phrase is in circulation.)

`[VERBATIM]` The volume benchmark, from a practitioner in that same thread (u/highqualityugc):
"tie the weekly number to spend instead of picking one: $5-15k/mo, 3 to 5 new creatives a week; $15-50k/mo, 8 to 15; $50k+, 20 to 30. **median DTC brand shipped 8 a week in 2026, up from about 4.5 in 2024. top quartile past 22.** ... roughly 1 to 3 in 10 become real winners, and the **top 2% of creatives eat 43-53% of total spend**. you cannot pick those in advance so at bats are the only mechanism."
https://www.reddit.com/r/FacebookAds/comments/1v9kpra/
`[SYNTH]` These numbers are unsourced practitioner assertion, not a study. But they are exactly the mental model your buyer carries around: volume is mandatory, hit rate is low, and nobody can pre-select winners. That framing is why per-variant human review does not scale.

`[VERBATIM]` "which version are we using?"
u/batsy_beats, r/SocialMediaMarketing, Jan 2026, post titled "The creative production bottleneck is killing campaign timelines":
"the back and forth between strategists, designers, copywriters, and approval chains creates these **insane delays** that make planning basically impossible. By the time final assets are ready **the market moment has often passed or the brief is outdated**, then there's feedback scattered across email, Slack, project management tools, random Google Docs... nobody can find anything when they need it and **everyone's asking 'which version are we using?'**"
https://www.reddit.com/r/SocialMediaMarketing/comments/1qcv8x5/the_creative_production_bottleneck_is_killing/

`[VERBATIM]` "permission theater"
u/Late_Sun_8834, same thread: "speed beats polish every time and most teams are still pretending it's 2015. Once you remove handoffs and let creatives ship fast **without permission theater**, everything else starts working again."

`[VERBATIM]` "Approving is not reviewing"
Inam Khan, Senior Creative Strategist, comment on a LinkedIn post by Antonio Ventre: "**Approving is not reviewing**, and three questions decide which one just happened."
https://www.linkedin.com/posts/antonioventre_hot-take-the-meta-ad-library-is-where-creative-activity-7506242882027208704-FMS6
`[SYNTH]` This is the single sharpest phrase I found for the core insight: at volume, the human "review" step silently degrades into a rubber stamp. That is the wedge.

### Quantified review burden

`[VERBATIM]` Superside "Overcommitted" report (n=206 enterprise creative and marketing leaders):
- "**78% said creative demand exceeds the team's capacity to deliver.**"
- "76% personally felt burned out by the amount of work in the past year." Around 80% reported burnout across their teams.
- "**70% said their most talented creatives spend their time on tasks below their skill level.**"
- "85% said they have had to focus on day-to-day admin over creative work."
- "55% of creative projects in large organizations are labeled high priority" and "35% of delivery pressure comes directly from executives."
https://www.superside.com/blog/creative-bottlenecks

`[VERBATIM]` Superside "Breakpoint" (AI follow-up): "More than 4 in 5 (85%) leaders say their executive team's expectations have shifted because of AI, with **92% saying executives are asking for higher quality work, and 94% adding that they expect it faster**." And "86% of respondents say their team is either at or over capacity."
https://www.superside.com/blog/breakpoint

`[VERBATIM]` "Only 28% of creative professionals spend more than half their day on actual creative work, according to the Ziflow State of Creative Workflow"
https://www.usewonderful.com/blog/best-creative-operations-tools
`[PARA]` I could not reach Ziflow's primary report; treat this as **secondhand, primary source unverified.**

`[VERBATIM]` Forrester Total Economic Impact study of Superside: composite enterprise customer saw "**60% fewer review rounds**" and "30% fewer feedback loops."
https://www.superside.com/blog/creative-bottlenecks
`[SYNTH]` Vendor-commissioned, so directionally useful only. But "review rounds" being the headline metric a vendor chooses to sell against tells you it is the felt pain.

---

## 2. AI-generated creative quality problems, in practitioners' own words

### The specific defect vocabulary

`[VERBATIM]` **Brand drift is the named failure mode.** u/WillIndependent7466, r/FacebookAds, Jul 2026:
"when an ad is generated rather than built, **the brand usually comes out slightly wrong. colours that are near your palette but not actually it, or a logo that's been redrawn.** for software it's worse, half the time there's a **screenshot of a dashboard that doesn't exist in the product.** none of that registers as fake to someone scrolling, so the click still happens. then they land on the site and it doesn't look like the ad they clicked, and **that gap is where you lose them.** ... which is why i think your static vs video split is real... **statics survive because there's less surface area to get wrong.**"
https://www.reddit.com/r/FacebookAds/comments/1v8m5vi/i_uncovered_the_truth_about_facebooks_ai_ads/
`[SYNTH]` This is the best single quote in the entire corpus for your product. It names the exact failure class (near-miss palette, redrawn logo, fabricated product render), explains why it survives review (it does not read as "fake"), and ties it to a revenue mechanism (ad-to-landing-page mismatch).

`[VERBATIM]` Same thread, u/Upper_Difference4189 on a 50-creative test (30 static / 20 video, fashion and home decor):
"the statics held up okay but the videos were a mess. **weird hand movements, products that warped mid-frame, uncanny valley smiles that creeped people out once they looked closely**"
"the dashboard thing in particular, i swear half the saas ads i see have screenshots that look like they came from a completely different app than what you actually get"

`[VERBATIM]` Same thread, u/highqualityugc on what viewers actually detect:
"when animoto asked people who spotted an AI video what gave it away, it was **robotic gestures 67%, unnatural voice 55%, flat emotional tone 51%.** nobody said rendering quality. so it's motion and audio, not pixels, which is why the stills look fine and the video still dies."
"the one that gets missed is **the face drifting between clips. jawline or skin tone shifts slightly when two generations get stitched together.** viewers cannot name it but they stop trusting the person, and it only shows up after you cut."
`[PARA]` The Animoto percentages are cited by a Reddit user; I did not verify against Animoto's primary research. **Flag as unverified.**

`[VERBATIM]` Six fingers as the canonical tell. Travis Moh, LinkedIn post on Meta's AI ad labels:
"**Small mistakes can hurt the whole ad. A product looks off. A screenshot feels fake. A hand has six fingers lol. One weird detail can make the buyer question everything else.**" ... "Here's what I'd do: **Review every AI edit before launch.** ... **Are you reviewing Meta's AI edits before they go live?**"
Commenter Anjeanette Carter: "**Exactly. If one detail feels fake, people start questioning the whole message.**"
Commenter Abdo Mazloum: "The label itself probably won't kill performance. **A product that suddenly looks different from the landing page will damage trust much faster.**"
https://www.linkedin.com/posts/travis-moh_an-analysis-of-metas-ai-ad-labels-and-what-activity-7484925458892091393-4Pn0

`[VERBATIM]` Distorted logo shipping from an agency. u/vocalyouth, r/graphic_design, Jul 2025 (604 upvotes):
"my agency made a stupid video in ai for social media this week, but couldn't get the ai to spit out exactly what they wanted and got incredulous with our motion graphics person bc they said the only way to do it would take days of work to fix by hand and reanimate. so **then they posted an ai generated image instead of a video and the company logo looks distorted and there are all kinds of weird visual inconsistencies with the image. it immediately reads as AI. it's embarrassing to me as a designer who gives a shit about doing good work.**"
https://www.reddit.com/r/graphic_design/comments/1m9w4ig/client_put_my_design_in_chatgpt_to_tell_me_what/

`[VERBATIM]` Brand governance as the missing layer. u/peter_salvato, r/branding, Jun 2026:
"**most people don't have brand guidelines that are actually usable by an AI tool. They have a mood board and a color palette. That's not governance. Governance is: here's what we sound like, here's what we never sound like, here's how to check if something drifted.** Without that, the model just does whatever sounds plausible."
He describes building "40 rules that constrain generation during production, not after... **Mechanical stuff you can check before anything ships.** The output got noticeably better once the constraints were specific enough that **I could catch violations before they went out.**"
https://www.reddit.com/r/branding/comments/1twfnkf/shipping_ai_slop_is_slowly_killing_your_personal_brand/
`[SYNTH]` This user independently invented a hand-rolled version of the product you are researching. Strong signal.

`[VERBATIM]` Practitioner consensus on AI as acceleration, not replacement. u/LubanMedia2024, r/FacebookAds (after 50+ AI creative tests):
"AI creatives can deliver competitive CTR and CPC... **However, the difference becomes obvious after the click.** Many AI ads receive impressions and traffic but struggle to generate strong conversion rates because they lack authenticity. AI videos are especially sensitive. **Small issues with facial expressions, movement, or product presentation can reduce trust and shorten the creative's lifespan**, even if the algorithm continues to deliver impressions."

### Platform auto-resize and auto-crop as a defect source

This is a distinct and very hot vein. Marketers are furious that platforms silently alter their creative.

`[VERBATIM]` u/Prinnykin, r/FacebookAds, Jan 2026, "Meta keeps re-applying AI image adjustments to my ads even after I turn them off":
"**A customer actually reached out to me to say my Instagram ad looked strangely cropped and blurred.** ... It's blurring edges, auto-cropping, and **cutting off text in some placements.** In Ads Manager my creative looks fine, but **in real Instagram placements the image is clearly altered.** ... But it keeps reverting to its own shitty AI version anyway."
Follow-up from the same user: "**I was so embarrassed when a potential customer sent me a screenshot of my ad. It was a total mess, with half of the text cut off, and the other half of the image was just blurred. Not only have I been losing money from this AI crap, but it's also affecting my reputation. It makes my business look so unprofessional.**"
https://www.reddit.com/r/FacebookAds/comments/1qd3vpz/meta_keeps_reapplying_ai_image_adjustments_to_my/
`[SYNTH]` Note the discovery mechanism: **a customer caught it, not the marketer.** The in-tool preview lied. That is the single most product-relevant anecdote in this whole report.

`[VERBATIM]` Same thread, u/QuantumWolf99: "This is Meta forcing Advantage+ creative enhancements now even when you toggle them off... been seeing this across multiple accounts I manage and **it's driving performance down when text gets cut off or blurred.**"
u/Carey251: "They apply almost all their AI bullshit to my ads after opting out at the account level and campaign level. **NO ONE wants the AI slop.**"

`[VERBATIM]` u/mygatito, r/FacebookAds, Mar 2026: "I noticed performance drop since last week, turns out the images are getting stretched automatically which **causes text to get chopped off.** CTR has increased ten fold for some campaigns and **conversions are almost next to 0.**"
https://www.reddit.com/r/FacebookAds/comments/1ryah3j/new_auto_image_auto_stretch_is_destroying_sales/

`[VERBATIM]` u/TinyPlotTwist, same thread: "meta rolls these out silently and **they break text-heavy creatives.** while you're there, check if auto-placed assets are overriding your original creative dimensions, that's another silent culprit."

`[VERBATIM]` u/digitaladguide, r/FacebookAds, Nov 2024, a widely upvoted teardown "11 Adv+ Creative 'Enhancements' & Why I Turn Them Off":
On Add Overlays: "**If you spent time and effort doing market research and designing your ad, why would you throw some sloppy looking text over the top of it?**"
On Visual touch-ups: "This enhancement basically modifies your creative to fit more placements and may adjust the colors/brightness of it. **Verdict: If you spent time and effort making professional creatives to fit all placements (1:1, 9:16 and 1.91:1) and keeping in mind safe zones, then I would keep this off.**"
On Music, a story he relays: "**a spin instructor posting an ad for spin class with the music enhancement on. She saw her own ad and the ad had horror film background music.** LOL Obviously not the tone."
https://www.reddit.com/r/FacebookAds/comments/1gvueuz/11_adv_creative_enhancements_why_i_turn_them_off/

`[VERBATIM]` The settings-revert problem, same thread:
u/DubbersAnonymous: "Anyone had the issue before where you turn them off but then **a week later they have magically been turned on**…"
u/Fabulous_Rich8974: "**Yes it happens when you publish. So after i publish i wait until approved and then double check** sometimes these features flip back on"
u/CypherElite: "They annoy me so much because **I have to constantly manually turn them off** 😭"
u/ConsiderationOk9099: "Go into ad account's advertising settings > advantage+ creative and uncheck the 'Test new enhancements' box. **It allows Meta to serve ads with the tools enabled without you knowing.** It says 5% of your impressions, but I wouldn't be surprised if it was more."
`[SYNTH]` There is a durable manual QA ritual here that people describe doing by hand every single publish: ship, wait for approval, go back in, re-check that the platform did not re-enable its own creative mutations. That is an unautomated recurring check.

`[VERBATIM]` u/Open-Pipe5301, r/PPC, Feb 2025: "My carousel ads are being cut off and **it looks super unprofessional.** ... I've spent a week back and forth with the Meta Marketing Pro team trying to resolve this and they are just passing me around... **The campaign is now over** but I would love to learn why this may have been happening."
u/meegee, replying: "if you must ship one file, **build a 4:5 with a 1:1 safe zone and keep all text/logos inside the center square** ... separate ad sets by placement family (feeds vs explore vs marketplace vs profile) so **the crop logic can't surprise you.**"
u/RobertBobbertJr, same thread: "We've had issues where our **product feed kept showing a nutritional label instead of the product image** on facebook. Support couldn't figure it out at all. Only duplicating the campaign ever fixed it."
https://www.reddit.com/r/PPC/comments/1igmlpv/meta_ads_are_being_cut_off_formatting_is_wrong/

### Google's automatically created assets

`[VERBATIM]` u/LucidWebMarketing, r/PPC: "I've seen them when taking over active accounts. More than a few times, **I've shaken my head and thought 'what the hell is this?' Turns out most times, it's automatically created assets that didn't make much sense. What would be nicer is the same feature but given as recommendations that you can alter. Not pure AI but more computer assisted help.**"
u/TTFV: "Still not ready for prime time as **many of the creatives are nonsensical.** My strong recommendation is don't use this feature."
u/TheTalentedMrTorres: "still a long ways off from being something that I'd trust, **too much potential for the system to come up with something wildly irrelevant** or otherwise dull & ineffective."
u/snoozer39, on SKU/category mismatch: "you are a hardware and garden store, it'll be possible **the garden ads will have a headline of 'power tools on sale'** now or your ad group advertising the latest fruit tree selection will offer 'brilliant shades of paint' in the ad. Not exactly matching."
https://www.reddit.com/r/PPC/comments/11f1spv/whats_your_opinion_on_google_ads_automatically/
`[SYNTH]` "Recommendations you can alter, not pure AI" is a near-verbatim statement of the flag-versus-auto-fix preference you asked about in section 8. It came unprompted from a practitioner in 2023.

---

## 3. Ads that shipped with a visible mistake

### Named public incidents

**Google, Super Bowl LIX (Feb 2025), Gemini ad with a hallucinated statistic.** The ad showed Gemini claiming Gouda accounts for "50 to 60 percent" of global cheese consumption. Google **quietly re-edited the YouTube version of the ad before the game** after online users flagged it. Covered by Ars Technica, Fortune, Futurism, Mashable, NY Post, SFGate.
https://arstechnica.com/ai/2025/02/not-gouda-nough-google-removes-ai-generated-cheese-error-from-super-bowl-ad/
https://fortune.com/2025/02/09/google-gemini-ai-super-bowl-ad-cheese-gouda/
`[SYNTH]` The perfect "factual claim in creative" incident: it was caught by the public, not by internal review, on the most expensive media buy of the year.

**Coca-Cola "Holidays Are Coming," 2025 AI remake.** Business Insider, Lara O'Reilly, Nov 5 2025:
`[VERBATIM]` "Look closely, and you'll see the famous Coca-Cola trucks **appear to change shape as they roll through the festive village. The trucks also appear to gain or lose wheels in each scene.** Other viewers also noticed... a concerning moment at the 50-second mark when a truck appears to be on a collision course with a crowd of onlookers."
`[VERBATIM]` Production scale: "**just five AI specialists refined 70,000 video clips to create the ad in 30 days**, using tools such as OpenAI's Sora, Google's Veo 3, and Luma AI."
`[VERBATIM]` Pratik Thakar, Coca-Cola global VP and head of generative AI: "**There will be people who criticize, we cannot keep everyone 100% happy. But if the majority of consumers see it in a positive way, it's worth going forward.**"
`[VERBATIM]` On the 2024 version, Thakar told Ad Age: "**Consumers were not concerned about AI versus non-AI**" and consumers do not look at AI campaigns the way creative directors do.
`[VERBATIM]` Dino Burbidge, independent innovation specialist who documented the wheel errors, to Business Insider: the production issues were **"inexcusable"** and Coca-Cola **"risks damage to its brand."** "Is this the slippery slope that previously trusted media and production values will go down because 'consumers don't care'? **Craft, creativity, and quality should hold true. As soon as we let that go, who's going to fight for it?**"
`[VERBATIM]` Counterpoint, PJ Pereira (Pereira O'Dell / Silverside AI): "once they recognized AI as the future, **they stopped debating whether it's perfect or not** and instead focused on how to use it in the best, most creative way possible."
`[VERBATIM]` Measurement split: System1 gave the ad its top score of 5.9 stars. DAIVID found it "slightly less likely (2.1%) to generate positive emotions and more likely to evoke feelings of distrust (2%) than the industry norms."
https://www.businessinsider.com/coca-cola-ai-holiday-ad-glitches-highlight-ai-shortcomings-2025-11
2024 defect detail, same piece: "the wheels gliding across the floor instead of spinning and the eerie-looking AI 'humans' smiling creepily."
`[SYNTH]` This is the definitive case study for your positioning: the artifacts (object inconsistency across shots, wheel count, brand asset geometry) are exactly the class a machine checker catches and a human reviewer scanning 70,000 clips cannot.

**McDonald's pulled an AI-generated Christmas ad, Dec 2025.** Guardian headline quotes a consumer: `[VERBATIM]` **"Ruined my Christmas spirit."** The replacement "avoids close-ups of humans and mostly features AI-generated images of cute animals."
https://www.theguardian.com/business/2025/dec/11/mcdonalds-removes-ai-generated-christmas-ad-advert-backlash

**Toys R Us / Sora (2024)**, "widely panned online as soulless."
https://www.businessinsider.com/brands-reject-ai-aerie-heineken-polaroid-marketing-2025-10 (citing marketing-interactive.com)

**H&M, Skechers, Guess** all "taken heat for using AI brand ambassadors instead of human models." Same BI source.

**Callaway / Good Good Golf (Aug 2026)**, ad pulled after backlash; the CEO publicly apologized and said the company approved the ad and "apologized for that mistake."
https://www.cnn.com/2026/08/25/sport/good-good-callaway-ad-golf

**Converse (Sep 2026)**, pulled an ad after users said the lighting created a silhouette resembling a KKK hood. Brand statement: "We will do better."
https://kfor.com/news/converse-apologizes-pulls-ad-after-online-controversy-we-will-do-better/
`[SYNTH]` Worth noting as the category of defect nobody has a checklist for: unintended silhouettes and negative space. This is a real limit on what automated checking can promise.

### Practitioner war stories, with costs and discovery mechanisms

From r/graphic_design, "What's the biggest screw up you've ever made as a designer?" (Sep 2024). This thread is a goldmine.
https://www.reddit.com/r/graphic_design/comments/1fnnd24/whats_the_biggest_screw_up_youve_ever_made_as_a/

`[VERBATIM]` **The CMO catches it.** u/Patricio_Guapo: "**Misspelled the name of the company, in 72 point headline type, on a full-page ad that ran in Newsweek magazine. The whole agency signed off on it, three people in the client company signed off on it. No one caught it and it went out the door. Who saw it first? The CEO. That was not a fun day around the ol' ad agency.**"
`[SYNTH]` Eight human approvers, 72pt type, still shipped. This directly answers "would more human review have caught it": no.

`[VERBATIM]` **Wrong Pantone in a brand style guide, $14,000.** u/sunfizz18: "I was fairly new in my career and creating a brand style guide for a logo and decided to work off of one that I had just created for another client since we always followed the same template. **I successfully swapped everything out except for one Pantone color number.** The client ordered some bags to be printed with their new logo using that Pantone number and was not very happy when they saw an entirely different color printed on the bags. My company reimbursed the client... **which I believe was $14,000.** They threatened to make me (who was only making $29k a year) cover the cost but opted not to since my creative director also failed to notice the error when he approved the style guide. **They did proceed to remind me and the entire team about my error at every Monday morning standup we had for 6 months until I eventually quit.**"
`[SYNTH]` Note the exact defect: a single token copied from a prior brand's template into a new brand's asset. That is precisely a machine-checkable brand-token mismatch, and it was invisible to two humans.

`[VERBATIM]` **The template-inheritance typo, 5,000 units.** u/Ultragorgeous: on a brochure for a proofreading company, "CMYK + 2 spots, typeset to death, retouched to hell, and proofread to the hilt. Every department spent their free time fine-tuning this thing. I prepped the files for press, and introduced the letter 's' in this sentence: 'we pride ourselves in taking the utmost care in typesetting and proofreading for our clients.' Guess where the 's' went. **We printed 5,000 before it was discovered.** Here is the answer: **sour clients.**"

`[VERBATIM]` **The RGB-to-CMYK conversion error.** u/jojothekoolkitty: "Was just starting in design and used an online tool for converting RGB to CMYK values. **A handful of brand books ended up having the wrong colour codes. Horrified and humiliated when a client asked about the odd colours.**"

`[VERBATIM]` **The version race condition.** u/Gibbie42: "Not five minutes after I hit send I noticed that one of layers was out of order... fixed it up, swapped the files and figured it was 6:30 at night, no one would have pulled down the files yet... Nope. **In that small amount of time the files were downloaded.** Weeks later when the sign was installed I went to go see it and yep, there was my incorrect file. **But no one has ever noticed it's slightly wrong and it's been 12 years. But I see it every time I'm there.**"

`[VERBATIM]` **The production director's catalog of 30 years.** u/WinkyNurdo: "**Large format billboards in the wrong colours, signage spelt wrong, brochures with wonky foiled stamps on the FC, hoarding with incorrect QR codes, business cards with no contact details, a logo with outlined fonts but spelt wrong** ... I could go on forever. The fact is, fuckups WILL happen. ... **no sign off should really depend on one person.**"

`[VERBATIM]` **Where blame actually lands.** u/fastinggrl: "Tbh, places put too many jobs on a designer... **we are one of the gatekeepers to be able to spot issues like this** but tbh, the more experienced I get in my career as a designer, the less responsibilities I have because I work at places that actually staff appropriately and understand that **there needs to be a process to avoid these sorts of hiccups.**"
u/design_studio-zip: "**If the work is signed off, it's never really the fault of the designer** unless mistakes are somehow introduced after that or a previous version is sent to print."
u/Dracmageel describes a defensive ritual: "**That's why i make sure it's at least 5 other people to make sure all the information is correct at my job, i refuse to take the blame, at least alone.**"

`[VERBATIM]` **Over-review causes errors.** u/InfiniteDuckling, r/marketing: "Small mistakes like this often happen because of over micro management. **People get burned out following too many instructions and more mistakes happen. People also start to rely on the micro-manager to catch mistakes because they're so involved anyway, surely someone else will catch the mistake.**"
https://www.reddit.com/r/marketing/comments/jcw1dv/what_is_your_biggest_screwup_youve_ever_made_at/
`[SYNTH]` Diffusion of responsibility across a long approval chain is itself a defect source. More reviewers can mean fewer catches.

`[VERBATIM]` **50 iterations, 15,000 copies, wrong phone number.** u/ScreamingDizzBuster, r/marketing: "**There were 50 iterations, everything had to be checked by every single person in the client company including the janitor, everything was proofread by us again 30 times. Nobody proofread the fucking phone number on the back.** We printed 15,000 copies at a very high cost (embossed, gold highlights, recycled fiber paper, tissue paper between photo pages). ... We had to print little custom-made stickers the right size, commandeer every single person in the company, who just sat there for **two days** sticking them on the back."

`[VERBATIM]` **The untested CTA.** u/mcm215, r/marketing: "We proofread everything three or four times... but **no one thought to actually dial the phone number** to be sure it routed properly. And, so, for about a week, **customers calling to order medical textbooks were routed to an adult phone chat line.** ... I now ALWAYS verify my CTAs personally."
(Two independent people in the same thread report the sex-line phone number failure mode.)

`[VERBATIM]` **"Sender's remorse."** u/chuff80, r/marketing: "**10 years in marketing. I still get the sweats when I am about to hit send, even after the team has looked over the final (final) draft.**"
u/Useful-ldiot named it: "**I call it senders remorse. That feeling of dread when you hit go.**"
`[SYNTH]` This is the emotional core of your product. The pre-launch dread is real, persistent, and survives seniority. Reducing that dread is the felt benefit, not "saving time."

---

## 4. Marketers versus designers, and the design bottleneck

### How designers feel about marketers editing their work

`[VERBATIM]` u/smilesmiley, r/graphic_design, Jun 2024, 274 upvotes, "Everybody thinks they can do our job":
"The marketing person making designs when you have already made multiple ones... They think their design is better so they post it on the company's linkedin for everyone to see. Even the HR posts job posts with neon colors. They asked us for designs and we gave them designs but they totally ignored it... **I get ashamed because I think everyone thought I made those horrible designs when my designs just get ignored.** The graphic they made is awful but what can I do? **I have been called snippy for voicing my opinion on their horrible design.**"
https://www.reddit.com/r/graphic_design/comments/1dpw3rx/everybody_thinks_they_can_do_our_job/
`[SYNTH]` The reputational asymmetry is the key dynamic: the designer's name is attached to output they did not approve and cannot veto. Speaking up costs social capital ("snippy").

`[VERBATIM]` u/pineapplepredator, same thread: "a lot of the contention is due to **the number of people who get into marketing because they see it as a way to be creative while lacking a creative skill set.** A designer or any commercial artist typically gets fulfillment in their craft in other places so they are more flexible and professional at work. But when someone uses their job as their sole creative outlet, **their emotions are involved.** Especially if they don't have skill. And then you get the Dunning Krueger effect on top of that."

`[VERBATIM]` u/[deleted], same thread, on why marketers and designers argue past each other: "**a giant red button will always perform better than a brand color normal size button, but that doesn't mean it's the right choice. Can't go solely by short term metrics.**"
`[SYNTH]` This is the compressed version of the whole marketer-versus-brand-team conflict. Performance metrics and brand guidelines optimize different objectives, and no shared artifact adjudicates between them.

`[VERBATIM]` Designers on non-designer AI use. u/HyperSculptor, r/graphic_design: "**To me the real damage is how AI creates a massive loss of appreciation for what it takes to make great design**, for most people. In other words it creates a culture where people are clueless and go wOhaaAaaAa when you show them an ugly AI potatoe with a Ferrari badge."
u/JamesTheBadRager: "Yea always the same shit, it's as if the ai tools we designers used is totally different from those clients or managers. **Always claimed that they had great results but when prompted they always couldn't answer.**"
u/Gertie7779: "I ended up asking him if it was so easy and efficient to make these AI generated videos, **why don't you make them yourself?**"

### How marketers feel about waiting on design, with turnaround times

`[VERBATIM]` **The disproportion, stated plainly.** u/Intelligent-Panda495, r/SocialMediaMarketing: "**Campaign structure setup might take an hour but creative approval can take two weeks minimum, it's wild how disproportionate that is.**"
https://www.reddit.com/r/SocialMediaMarketing/comments/1qcv8x5/
`[SYNTH]` One hour of media ops versus two weeks of creative approval. If you need one number to anchor a pitch deck, this is it, with the caveat that it is one practitioner's estimate.

`[VERBATIM]` u/carebear7077, same thread: "**the approval process itself is just slow by nature when multiple people are involved, the tools help with organization but they can't force people to give feedback faster. The bottleneck is usually human decision-making speed, not the tech.**"
`[SYNTH]` This is the strongest objection you will face. Anyone selling creative QA automation has to answer it: you are not speeding up human judgment, you are removing the mechanical checks from the human's queue so the judgment can happen faster.

`[VERBATIM]` u/PeterJPeter, same thread, a former in-house marketing lead: "From my experience **it's exactly the tools that causes the most issues: briefs, reviews, etc are scattered across so many places separate from the asset that context just gets lost and it's just way too slow.** In my previous role I had in-house creative people and a couple of agencies and **coordinating all of the production and approval was a pain.**"

`[VERBATIM]` **Why teams go around their agency.** Superside Overcommitted: "**51% of leaders have lost faith in traditional agencies**, and among teams still working with them, **only 13% say the partnership works well.** The reasons are familiar: **37% say agencies move too slowly, 34% point to quality and 31% say briefing the agency takes longer than briefing the internal team.**"
https://www.superside.com/blog/creative-bottlenecks

`[VERBATIM]` u/Ian_J_Miller, r/marketing, on the designer's side of the same dynamic: "As a designer I call jobs like this **'monkey jobs'**, where you're basically just acting as a stylus/mouse for a client who can't use the software on their own but thinks they know how to do your job better than you. **After the 50th revision you realize they're not going to budge on their opinions, so you just give up and do whatever they say** since they're the ultimate authority. **These projects usually end up being disasters** because... you're relying on other people to catch mistakes."
Same user: "**As the last in the chain of a creative product, designers usually have to rely on the content that's given to us** to do our jobs effectively and **we have the tightest deadlines because the schedule won't move for us.** ... **it's not our job to proofread content.**"
`[SYNTH]` Both sides describe the same failure: the last person in the chain is compressed, disempowered, and implicitly expected to catch everyone's errors. Nobody thinks it is their job to proofread.

### Political cost of asking for a re-review

`[PARA]` **This is my thinnest area.** I did not find clean verbatim quotes of a marketer saying "I don't want to bug the designer again." The closest evidence is indirect but consistent:
- The "snippy" quote above shows designers are penalized for pushing back, which implies the reverse also carries cost.
- u/Late_Sun_8834's "**permission theater**" implies the approval ask is experienced as a social ritual rather than a quality gate.
- u/Dracmageel's "**I refuse to take the blame, at least alone**" shows people add reviewers defensively, not because the reviewers add value.
`[SYNTH]` The mechanism is real and well-supported but under-quoted in public text. This is likely because admitting you avoided a review is an admission of negligence, so people do not post it. **I would recommend getting this one from customer interviews rather than from public sources.**

---

## 5. Quantitative signals

### The "creative drives X% of ad effectiveness" stat, traced

**The real source is Nielsen Catalina Solutions (NCS) plus Nielsen, 2017.** The study analyzed roughly 500 CPG campaigns from 2016 and Q1 2017.

The number is reported two ways and this is the source of most misquoting:
- **47% = creative alone.** `[VERBATIM]` Inside Radio, Nov 2017, reporting NCS: "**Creative currently represents 47% of a campaign's effectiveness, while context is 2% and brand 15%.**"
https://www.insideradio.com/free/nielsen-creative-still-rules-ad-outcomes/article_abae3542-c395-11e7-a0ad-0b99ef23cc5d.html
- **49% = creative (47%) plus context (2%).** MarketingCharts reported it as "49% of a brand's sales lift from advertising is due to the creative, with 47% attributable to the quality and messaging of the creative and 2% to the context in which the ad is placed." Media planning and buying = 36%. Brand factors = 15%.
https://www.marketingcharts.com/advertising-trends-80662

Channel splits from the same study: for TV (linear and addressable), media contributes 50% and creative 37%. **For digital (video, display, mobile), creative accounts for 56% of sales lift.**

`[VERBATIM]` Nielsen's own framing, Carl Marci, Chief Neuroscientist, Oct 2017: "**creative quality contributes as much to a brand's in-market success as all other factors combined.** Further, the study found that **when creative is strong, it's the overwhelming driver of in-market success: up to 80% for traditional TV and 89% for digital advertising.** Conversely, when creative is weak, the sales lift is weak across TV and digital, and other media factors are the main drivers."
https://www.nielsen.com/insights/2017/perspectives-want-a-successful-ad-get-creative/

`[VERBATIM]` **A useful critique to know about.** Recast (MMM vendor) on why the stat rarely shows up in models: "**a remarkable 47% of the campaign's contribution to sales was attributable to Creative.** ... Despite the importance of Creative, most Marketing Mix Models (MMMs) do not account for creative performance. **Even Facebook's Robyn MMM tool only recommends including the format of creative** (static, video, in-stream) rather than a granular view of which ad worked." They also raise a genuine methodological caution: "**Whenever a creative performs poorly, if the CMO is doing their job that ad gets turned off... because the marketer is affecting control of the system, the impact of creative isn't correlated with sales.**"
https://getrecast.com/creative-performance/

`[SYNTH]` **Guidance for your team:** cite "47%" with "Nielsen Catalina Solutions, 2017, ~500 CPG campaigns" and note the 56% digital figure, which is the more relevant one for your buyer. Avoid the free-floating "creative drives 70% of effectiveness" numbers that circulate without provenance. The 2017 date is now a liability; expect pushback that it predates algorithmic creative selection.

### AI incidents and governance: the strongest single dataset

**IAB in partnership with Aymara, survey of 125 US advertising executives at companies with 50+ employees, fielded July 2024, published Aug 2025.** This is the most directly on-point research I found for your product.

`[VERBATIM]` "**Over 70% of marketers have encountered an AI-related incident in their advertising efforts, including hallucinations, bias, or off-brand content, yet less than 35% plan to increase investment in AI governance or brand integrity oversight over the next 12 months.**"

`[VERBATIM]` Consequences of those incidents: "**40% had to pause or pull ads, over a third dealt with brand damage or PR issues, and nearly 30% had to conduct internal audits.** Some saw wasted budgets, client complaints, or legal concerns. **Only 6% said the impact was minimal.**"

`[VERBATIM]` **The overconfidence finding, which is your whole thesis:** "Most teams rely on **human review and brand integrity checklists**, which are important but basic steps. More advanced practices are far less common such as consulting external AI ethics experts, running red team testing, and **using automated evaluation tools.** Alarmingly, 10% of respondents either do nothing or aren't sure how they manage AI risks. Yet confidence remains high. **Nearly 90% say they feel prepared to catch AI issues before launch.** This may reflect trust in existing workflows, but **given that 70% have already had incidents, it also suggests a false sense of security.**"

`[VERBATIM]` "only one-third of brands, agencies, and publishers have adopted or plan to adopt any formal governance tools."
`[VERBATIM]` "**over 90% said yes**" to considering a third-party solution to evaluate risks like hallucinations, bias, or off-brand content. "One marketer said it would offer '**peace of mind**,' while another noted it would '**reduce risk to our brand and business.**'"
`[VERBATIM]` "**14% say no one owns AI governance**, and others aren't sure who does."
`[VERBATIM]` "**Only 6% believe current safeguards are enough.**"
`[VERBATIM]` "over 60% support labeling AI-generated ads, with only 15% opposed" and "37% fearing audiences will distrust ads made by AI."
`[VERBATIM]` "58% plan to increase AI for creative generation in the next year."
https://www.iab.com/insights/ai-adoption-is-surging-in-advertising-but-is-the-industry-prepared-for-responsible-ai/
`[SYNTH]` The 90%-feel-prepared versus 70%-already-had-an-incident gap is the most quotable tension in this entire report. It is a validated, named-source version of the "approving is not reviewing" insight.

### Creative production volume and AI adoption

`[VERBATIM]` Superside Overcommitted and Breakpoint (n=206 enterprise creative/marketing leaders):
- "62% of creative teams now handle twice as many" projects (from the "Overcommitted" report, via https://www.superside.com/blog/creative-content-velocity)
- "**96% say AI can help teams move faster and handle more projects**" and "93% anticipate that it will improve the quality of their work"
- "**about 39% of leaders say they worry about AI quality, 33% expressed concern about legal and/or IP risk, and 32% cited lack of training as an issue**"
- "9 in 10 leaders say they'll use AI more frequently this year, and 52% say they'll use it much more"
- "about 4 in 5 creative professionals say they want to create bolder work, but they're always racing against the clock, and 77% say they feel bogged down with too many lower-priority tasks"
- "**Creative quality is vital to marketing results, in fact, 80% of marketers see it as key to marketing success.**"
https://www.superside.com/blog/breakpoint and https://www.superside.com/blog/creative-bottlenecks
`[SYNTH]` Superside is a creative services vendor, so treat as advocacy research. But n=206 enterprise leaders is a real sample and the internal tension (96% believe AI helps, 39% worry about AI quality) is credible and useful.

`[VERBATIM]` **Deloitte / Duke Fuqua CMO Survey, April 2026:** "**AI use in marketing has nearly doubled in two years, rising from 13.1% of marketing activities in 2024 to 24.2% in 2026.**"
Reported via https://www.swordandthescript.com/2026/04/economic-outlook-marketing/ citing https://cmosurvey.org/
`[PARA]` I could not retrieve the CMO Survey PDF directly; **verify against the primary report before external use.**

`[VERBATIM]` **Salesforce Generative AI Snapshot Series**, n=1,000+ marketers, Jun 2023:
- "**66% percent of marketers say human oversight is needed to successfully use generative AI in their role.**"
- "71% of marketers believe generative AI's **lack of human creativity and contextual knowledge is a potential barrier**"
- "over a third (39%) also say they **don't know how to safely use generative AI**"
- "51% are currently using generative AI"
https://www.salesforce.com/news/stories/generative-ai-for-marketing-research/

`[VERBATIM]` **Gartner**, Nov 2025 press release: "**65% of CMOs say advances in AI will dramatically change their role in the next two years**," and a separate Gartner survey of 426 business leaders (Sep-Oct 2025) found "82% of leaders say their company's..." (the sentence is truncated in the snippet I retrieved).
https://www.gartner.com/en/newsroom/press-releases/2024-11-17-gartner-survey-finds-65-percent-of-cmos-say-advances-in-ai-will-dramatically-change-their-role-in-the-next-two-years
`[VERBATIM]` Gartner, Dec 2023: "**By 2026, 60% of CMOs will adopt content authenticity technology, enhanced monitoring, and brand-endorsed user-generated content (UGC) to protect** [their brands from deceptive content]."
https://www.gartner.com/en/newsroom/press-releases/2023-12-14-gartner-predicts-fifty-percent-of-consumers-will-significantly-limit-their-interactions-with-social-media-by-2025
`[SYNTH]` The "content authenticity technology" prediction is the closest Gartner language to an automated brand-integrity checking category.

### Stats I recommend you do NOT use without verification

`[VERBATIM]` "According to IAB Tech Lab, **nearly 1 in 3 display ads contain serious quality issues**, from file size problems to rendering bugs."
https://magicbrief.com/post/ad-creative-qa-checklist-catch-mistakes-before-your-ads-go-live
`[PARA]` **I could not find any IAB Tech Lab source for this.** Searching the exact phrasing returns only this MagicBrief article and unrelated IAB documents. Treat as a **probable zombie stat.** It is attractive for your positioning, which is exactly why it needs verification before you put it on a slide.

`[PARA]` The "creative drives 70% / 75% / 80% of ad effectiveness" variants that circulate are usually misreadings of Nielsen's conditional figure ("**up to 80% for traditional TV and 89% for digital** *when creative is strong*"), which is a very different claim from an unconditional attribution share.

---

## 6. How marketers decide "is this good enough to ship"

### Published QA checklists

**MagicBrief, "Ad Creative QA Checklist" (Mar 2025)** is the most complete published practitioner checklist I found. It is structured in three passes:
`[VERBATIM]` **Step 1, Technical:** watch start to finish for glitches, missing frames, awkward cuts; check audio/video, confirm duration matches platform requirements; "**Verify aspect ratio (9:16, 1:1, 4:5, etc.) and test how it renders across devices**"; test interactive elements; "**Make sure key visuals and text aren't too close to the edges or too small for mobile screens**"; view on mobile; check load speed.
`[VERBATIM]` Pro tip: "**Instagram, TikTok, and YouTube Shorts each have different overlays and UI elements that can block or crop parts of your creative. Always preview your ad on the actual platform** to ensure your text, logos, and CTAs appear where they should."
`[VERBATIM]` **Step 2, Content accuracy:** "Double-check all text for typos, spelling errors, and grammar, **including overlays, subtitles, and captions**"; "Ensure all stats, claims, and bold messaging are accurate and backed by reliable sources"; "**Follow your brand guidelines for fonts, colours, logos, and tone**"; cultural sensitivity; UGC permissions and credit.
`[VERBATIM]` Pro tip: "**Don't just review your ad creative in edit mode. Play it through in full screen, on a phone, and with fresh eyes.**"
`[VERBATIM]` **Step 3, Performance:** hook strength, message order, pacing, emotional response, CTA clarity.
`[VERBATIM]` **On who reviews, and this is important:** "It's totally fine to have a small team, in fact, it's often better. While Creative QA is a shared responsibility, **too many cooks can spoil the broth. Passing the baton between departments often leads to confusion and delays.** To avoid that, **limit the final QA process to just one or two reviewers.** ... Getting early input from multiple team members is valuable, but **final sign-off should rest with one person.**"
https://magicbrief.com/post/ad-creative-qa-checklist-catch-mistakes-before-your-ads-go-live
`[SYNTH]` Two things to note. First, essentially every item in Steps 1 and 2 is mechanically checkable; only Step 3 is genuinely judgment. That is a clean product boundary. Second, the industry's own best-practice advice is to *reduce* the number of reviewers, which means the safety net is deliberately thin. A machine layer is the only way to have both fewer reviewers and more coverage.

### Heuristics in the wild

`[VERBATIM]` **"Mute it and watch three seconds."** u/highqualityugc, r/FacebookAds: "**quickest check is muting the ad and watching seconds 0 to 3. centered framing, even light with no shadows, a room with nothing personal in it. that reads as a set and it kills the thing.**"

`[VERBATIM]` **"The safe zone."** u/meegee, r/PPC: "build a 4:5 with a 1:1 safe zone and **keep all text/logos inside the center square.**"

`[VERBATIM]` **"Ship, then re-check after approval."** u/Fabulous_Rich8974, r/FacebookAds: "after i publish i wait until approved and then **double check** sometimes these features flip back on."

`[VERBATIM]` **"Volume over polish" as an explicit shipping philosophy.** Hernan Vazquez, Facebook post, Jul 2026: "**Creative volume > Creative perfection. 3 polished ads you 'hope' will work vs 30 good-enough ads you TEST to find winners.**"
https://www.facebook.com/hernanvazquezim/posts/your-winning-ad-just-died-after-48-hours-againwelcome-to-running-meta-ads-in-202/1535857254854793/
`[SYNTH]` This is the doctrine your product has to work with, not against. The bar is not "is this beautiful," it is "**is this good enough that it will not embarrass us**." Those are completely different checks, and the second one is far more automatable.

`[VERBATIM]` **Defensive review as a social strategy, not a quality strategy.** u/Dracmageel, r/graphic_design: "i make sure it's at least 5 other people to make sure all the information is correct at my job, **i refuse to take the blame, at least alone.** And the final review of information is done by the owner, and **he approves without actually looking at things**, so it's always 'hey, is this piece as you wanted it to be?...' and he just goes yep, everything is absolutely right, **so he doesn't get mad when something goes wrong.**"
`[SYNTH]` A perfect description of a sign-off that provides legal cover but zero quality assurance. Everyone in the chain knows it.

---

## 7. What marketers fear

`[VERBATIM]` **Reputation and professionalism, from the person who ships it.** u/Prinnykin, r/FacebookAds: "**It makes my business look so unprofessional.**" And: "I was so embarrassed when a potential customer sent me a screenshot of my ad."

`[VERBATIM]` **The CMO seeing it.** u/Patricio_Guapo: "**Who saw it first? The CEO.**"

`[VERBATIM]` **Being named in public for months.** u/sunfizz18: "They did proceed to remind me and the entire team about my error at every Monday morning standup we had for 6 months **until I eventually quit.**"

`[VERBATIM]` **The dread itself.** u/chuff80: "10 years in marketing. **I still get the sweats when I am about to hit send**, even after the team has looked over the final (final) draft."

`[VERBATIM]` **Pulled ads and wasted flight days, quantified.** IAB/Aymara: of the 70% who had an AI incident, "**40% had to pause or pull ads, over a third dealt with brand damage or PR issues, and nearly 30% had to conduct internal audits.** Some saw wasted budgets, client complaints, or legal concerns."

`[VERBATIM]` **Legal and IP.** Superside Breakpoint: "**33% expressed concern about legal and/or IP risk.**"

`[VERBATIM]` **Being forced to publish the AI label.** u/lizalove91, r/FacebookAds: "if you use the 'Add Animation' feature **you might get slapped with a 'created with AI' label on your ad which I definitely DO NOT want. The community I am advertising to primarily hates AI.**"
`[SYNTH]` Underrated fear: using a platform's own creative automation can trigger an AI disclosure label on your ad, which for some audiences is itself the reputational damage. Meta and TikTok label automatically, so the marketer does not control this.

`[VERBATIM]` **Consumer-side risk, measured.** DAIVID CEO Ian Forrester on AI ads: "they are **a little cold; a little too bloodless to really move people in any way.**" DAIVID evaluated 21 fully or partly AI-generated ads from Volvo, Microsoft, Puma and others: they were "**3% less likely to generate intense positive emotions than the industry norm and 12% more likely to generate feelings of distrust.**"
`[VERBATIM]` Megan Belden, global practice lead for ad effectiveness at NielsenIQ: "**Brains have a prototype or a blueprint for everything we experience. If there's something slightly different in that blueprint, it sends a signal to us that something's just off.**" Most sensitive areas: "ads that featured human faces, human motion, and human connection."
`[VERBATIM]` Pew Research, Sep 2025: 50% of Americans more concerned than excited about AI in daily life, up from 37% in 2021; 57% rate societal risks as "high"; only 12% are confident they can tell AI from human content.
https://www.businessinsider.com/brands-reject-ai-aerie-heineken-polaroid-marketing-2025-10
`[SYNTH]` "Something's just off" is the consumer-side name for the same defect class your product catches. That is a strong narrative bridge: the artifact is small, the trust penalty is not.

`[VERBATIM]` **The anti-AI brand positioning as a competitive fear.** Stacey McCormick, CMO of Aerie, on committing publicly to "real people only" in ads; the announcement was Aerie's most-liked Instagram post of the past year. Polaroid, Heineken, Cadbury 5 Star and DC Comics have run comparable anti-AI positioning. Same BI source.

---

## 8. Trust and control: flag it or fix it?

### Direct practitioner statements of the preference

`[VERBATIM]` **The clearest one, unprompted, from 2023.** u/LucidWebMarketing, r/PPC, on Google's automatically created assets: "**What would be nicer is the same feature but given as recommendations that you can alter. Not pure AI but more computer assisted help.**"
https://www.reddit.com/r/PPC/comments/11f1spv/

`[VERBATIM]` **Control as the stated reason to opt out.** u/Not-Reading, r/PPC: "**Turned this off right away. If you want to be fully in control of your messaging then this should be turned off.**"
u/MediaNinjaLtd, r/googleads: "I turn them off too, honestly **anything that is 'let google use this automated thing instead of you manually doing/building it' I leave it off**"

`[VERBATIM]` **Revoked consent is the trust-killer, not the AI itself.** The Meta threads are unambiguous on this. u/Live-Tumbleweed-916: "**By default meta has turned on letting them experiment with AI that will always override your ad settings. Exasperating, I know!**" u/Prinnykin: "I have it turned off at the ad manager settings level, but **Meta keeps turning them back on at the ad level**, even after I switch them off. It's incredibly frustrating." u/digitaladguide, on whether the re-enabling is a bug: "**They are definitely aware they are doing this. I highly doubt it's a glitch.**"
`[SYNTH]` The pattern across every auto-enhancement thread I read: practitioners are not hostile to AI assistance in principle. They are hostile to **AI changes applied without consent, silently, after approval, and invisibly in the preview.** Your product's posture should be flag-by-default, fix-on-explicit-approval, with a visible diff and a durable opt-out that actually persists. Auto-fix that silently mutates approved creative is the exact behavior this market has learned to hate about Meta and Google.

`[VERBATIM]` **A nuanced pro-automation counterpoint**, for balance. u/Quiet_Replacement215, r/FacebookAds: "I agreed on this in the past. **But now, I actually turn on most of them.** There were some weird combinations for sure. And, a few features actually give you some control like site links." And: "I remembered **AI background used to give really weird suggestions that didn't match the products at all.** Now they keep it to a solid color background which is more universal. However, this feature still doesn't look good for my feed, so this one is turned off."

### Human-in-the-loop as stated policy

`[VERBATIM]` Salesforce: "**66% percent of marketers say human oversight is needed to successfully use generative AI in their role.**"
`[VERBATIM]` IAB's own recommendation: "Start with foundational checks like human review, policy guidelines, bias testing, and build toward structured evaluations, **automated audits (with human-in-the-loop oversight where appropriate)**, and continuous monitoring that can **scale with content volume and model complexity.**"
`[VERBATIM]` IAB: "**over 90% said yes**" to a third-party solution evaluating hallucinations, bias, or off-brand content, with "peace of mind" and "reduce risk to our brand and business" as the stated motives.

### Academic grounding

**Dietvorst, Simmons & Massey (2015), "Algorithm Aversion: People Erroneously Avoid Algorithms After Seeing Them Err," *Journal of Experimental Psychology: General*.** Core finding: people **lose confidence in algorithmic forecasters faster than in human forecasters after observing the same magnitude of error**, and will choose an inferior human forecaster as a result.
PDF: https://marketing.wharton.upenn.edu/wp-content/uploads/2016/10/Dietvorst-Simmons-Massey-2014.pdf
PubMed: https://pubmed.ncbi.nlm.nih.gov/25401381/
`[SYNTH]` The direct product implication: **your false positives are much more expensive than your false negatives.** One wrong "this logo is warped" flag will cost you more trust than one missed defect. Precision over recall, and make every flag inspectable so the user can verify rather than just believe.

**Follow-up worth knowing:** Dietvorst, Simmons & Massey's later work on **"algorithm aversion is reduced when people can modify the algorithm's output, even slightly."** Chicago Booth Review coverage of Dietvorst and Bharti on "diminishing sensitivity to forecasting error": https://www.chicagobooth.edu/review/even-when-algorithms-outperform-humans-people-often-reject-them
`[SYNTH]` This is the single most actionable academic finding for your design: **let the user adjust the fix before accepting it.** Even trivial adjustability materially increases adoption. That is an argument for "suggest a fix, let them tune it, they apply it" over both pure flagging and pure auto-fix.

`[VERBATIM]` **MIT Center for Collective Intelligence**, via MIT Sloan: "**on average, AI-human combinations do not outperform** the best of either humans or AI alone" across a meta-analysis, though the picture differs by task type.
https://mitsloan.mit.edu/ideas-made-to-matter/when-humans-and-ai-work-best-together-and-when-each-better-alone
`[SYNTH]` Useful to know because it is the counter-citation a skeptical enterprise buyer may raise. The escape hatch: that meta-analysis is about *joint decision quality*, not about *mechanical verification offload*, which is the task class you are in.

`[VERBATIM]` **Automation-aversion in marketing specifically:** "54% of marketing decision-makers worry that overreliance on AI could erode the human creativity that helps ads" perform.
https://www.stackadapt.com/resources/blog/ai-advertising
`[PARA]` Cited as "a global survey" without attribution in that post. **Primary source unverified.**

---

## 9. Retail media specifics

`[PARA]` **This is my weakest section and I want to be honest about it.** I found very little authentic practitioner voice on retail media creative adaptation pain. Reddit's retail media discussion (r/PPC, r/FulfillmentByAmazon, r/AmazonSeller) is overwhelmingly about bids, ACOS and keywords, not creative specs or rejections. Trade press coverage of the topic is mostly vendor-sponsored. Here is what I did confirm.

### The fragmentation complaint, documented

`[VERBATIM]` Xenoss, on retail media growing pains: "**the lack of standardization across retailers (ad formats, how to buy...)**"
https://xenoss.io/blog/dsp-advertising-market

`[VERBATIM]` Osmos, on in-store and offsite retail media: "**fragmentation: every retailer's screens, every signage vendor, every attribution methodology different. Standardization is what makes brand** [investment possible]."
https://www.osmos.ai/blog/future-of-retail-media-retailers-becoming-media-networks
Same source, on the creative workload specifically: "**retail media requires matching creative assets to format specifications**" per retailer.
https://www.osmos.ai/blog/retail-media-evolution-the-complete-guide

`[VERBATIM]` Marketing Week, Sep 2025, quoting the advertiser complaint about commerce media: "**Advertisers were telling us, 'Every retailer says it's raining cash...'**" (the quote is truncated in my retrieval; the piece is "'Significant appetite': Creativity and measurement's role in the next [era of commerce media]")
https://www.marketingweek.com/creativity-measurement-commerce-media/

`[VERBATIM]` LinkedIn editorial on Amazon retail media challenges: "**every retailer speaks a different language**" and the market needs "standardization, and more brand-friendly innovation."
https://www.linkedin.com/top-content/retail-merchandising/retail-industry-challenges/common-challenges-in-amazon-retail-media/

`[VERBATIM]` **The best single articulation of the pain, though it comes from a vendor pitch.** Cape.io, profiled in IAB UK's "AI in Ad Tech Ecosystem," describes its value proposition as: "**Zero Platform Rejections: Ensures creative assets meet the completely divergent specifications of Linear TV, CTV, and social media from a single upload point, virtually eliminating failed uploads and missed SLAs due to creative.**" They maintain "**a Global Spec Database: thousands of living technical specifications for every broadcaster, streamer, and social platform globally**" and run an "AI Compliance Check: Reviews creatives against market and publisher guidelines / codes."
https://www.iabuk.com/ai-ad-tech-ecosystem
`[SYNTH]` "Missed SLAs due to creative" and "failed uploads" are the vendor-side names for what you called wasted flight days. IAB UK publishing this is a signal the category is being recognized. Also note: **a direct competitor is already positioning on exactly this,** including the regulatory-compliance angle (their models are trained by ex-Clearcast, ex-Ofcom, ex-ARPP people).

`[VERBATIM]` IAB standards work is live: IAB is producing "**(Retail) Media Standards & Flexi Ad Sizes Guidelines for Retail Media Networks**" aimed at easing "creative production, and operational strain for publishers and buyers."
https://www.relevant-digital.com/weeklywrap
`[PARA]` I could not retrieve the primary IAB document. **Worth chasing directly at iab.com; it is likely the most citable industry acknowledgment that retail media creative fragmentation is a named problem.**

`[VERBATIM]` Retailer-side AI creative tooling is already shipping: "**Through their AI Creative Studio, Amazon is helping brands create 30-**[second video ads]..."
https://www.marinsoftware.com/blog
`[VERBATIM]` "Walmart Connect enlists creative partners to help brands craft better ads" (Marketing Dive headline).
https://www.marketingdive.com/editors/padams/
`[SYNTH]` Both major RMNs are moving into creative generation themselves. That is both a threat (they may bundle QA) and a tailwind (more machine-generated retail media creative means more defects to catch, and brands will not trust the retailer to grade its own homework).

---

## Where the evidence is thin, and what I would do next

1. **The political cost of asking a designer to re-review.** Real but not publicly quotable. People do not post "I skipped review because I didn't want to bother anyone." **Get this from customer interviews.**
2. **Retail media practitioner voice.** Almost absent from public forums. I would go to the Path to Purchase Institute community, the r/AmazonSeller Discord, or agency contacts at Tinuiti / Skai / Pacvue directly.
3. **G2 / Trustpilot / Capterra free-text.** These are JS-gated and I could not extract review bodies. This is likely your richest untapped vein for section 2 and section 4 complaints about AdCreative.ai, Creatopy, Celtra, Smartly.io, Bynder and Frontify. Worth a manual pass or a paid review-data source.
4. **LinkedIn at scale.** Mostly blocked to me. The two posts I did get (Travis Moh, Antonio Ventre) were both high-signal, which suggests the channel is worth working manually.
5. **Two stats need verification before external use:** the "IAB Tech Lab, 1 in 3 display ads have serious quality issues" claim (I believe this may be a zombie stat) and the April 2026 CMO Survey AI-usage figures (I retrieved them secondhand).

## Three quotes I would put on a slide

1. u/WillIndependent7466, r/FacebookAds: "**when an ad is generated rather than built, the brand usually comes out slightly wrong. colours that are near your palette but not actually it, or a logo that's been redrawn... none of that registers as fake to someone scrolling, so the click still happens. then they land on the site and it doesn't look like the ad they clicked, and that gap is where you lose them.**"
2. IAB / Aymara, 2025: "**Nearly 90% say they feel prepared to catch AI issues before launch... given that 70% have already had incidents, it also suggests a false sense of security.**"
3. u/Prinnykin, r/FacebookAds: "**A customer actually reached out to me to say my Instagram ad looked strangely cropped and blurred.**"
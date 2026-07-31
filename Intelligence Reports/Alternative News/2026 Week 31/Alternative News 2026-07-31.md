---
title: Daily Intelligence Report - Alternative News - 2026-07-31
tags: [intelligence, daily-report, alternative-news, investigations]
updated: 2026-07-31
---

# Daily Intelligence Report - Alternative News
**Date:** Friday, 31 July 2026
**Sources checked:** The Intercept (feed + homepage), ProPublica (homepage), The Dissenter (author index), Responsible Statecraft (homepage), openDemocracy (homepage), Byline Times (special investigation index), OCCRP (homepage), Bellingcat (homepage), Investigate Europe (homepage), The Markup (homepage), Drop Site News (search-based discovery, per handling note)
**Sources failed:** Declassified UK (homepage and /feed/ both returned HTTP 403 — eleventh blocked occurrence, following 18, 20, 22, 23, 24, 25, 26, 27, 28 and 30 July; no run occurred 29 July)

---

## Editor's note

Nothing carrying today's date landed at any T1 or T2 source. The substance in this report is two genuine misses surfacing only now: a significant Drop Site News investigation into an Israeli-funded operation to shape what AI chatbots say about Gaza, and two openDemocracy pieces on UK press-freedom and regulatory-accountability stories, all dated 28-29 July and never written up because the 29 July run didn't happen and the 30 July run's searches came up empty. The Drop Site story is the one with real teeth, both editorially and for Orwell's own AI work.

---

## No stories today

No investigation, analysis, or documents-based piece publishing on 31 July 2026 was found across The Intercept, ProPublica, The Dissenter, Responsible Statecraft, openDemocracy, Byline Times, OCCRP, Bellingcat, Investigate Europe, The Markup, or Drop Site News.

The Intercept's feed is current through 30 July (a piece on Germany deporting the Bob Vylan frontman over anti-Israel chants), nothing dated today. ProPublica's homepage shows no item with an explicit 31 July date. The Dissenter's author index still tops out at 24 July. Responsible Statecraft is current through 30 July (Houthi/Saudi Arabia round two, and Trump's Lebanon strategy), nothing today. openDemocracy's most recent dated item is 30 July (a Venezuela earthquake piece, outside this register's scope). Byline Times' special investigation index still tops out at 23 July. OCCRP is current through 30 July (a Pentagon fuel-subcontractor investigation, EU sanctions on the Prince Group). Bellingcat's most recent piece is 30 July (a World Cup prediction-markets piece, not accountability journalism) with its last investigation proper on 24 July (Mali drones). Investigate Europe's most recent item remains 27 July. The Markup has nothing newer than 28 July. Drop Site News was searched per its handling note; nothing from today surfaced.

Declassified UK could not be checked directly: the homepage and /feed/ both returned HTTP 403, the same failure mode as every check since 18 July.

---

## Story 1: Israel paid $46.5 million to shape what AI chatbots say about Gaza

**Source:** Drop Site News | https://www.dropsitenews.com/p/israel-brad-parscale-ai-chatbots-gaza (direct fetch returned HTTP 403; reconstructed from Middle East Monitor's detailed republication and corroborating coverage)
**Author:** Byline not confirmed — Drop Site News's own site is blocked to direct fetch and none of the syndicating outlets checked name the reporter. **Published:** approximately 28-29 July 2026 (Middle East Monitor and Pakistan Today both carry it dated 29 July; one secondary source cites 28 July) | **Read time:** ~7 min
**Related vault notes:** [[Agent Org]], [[Priority System]]

Per the granularity rule this is written up as a catch-up, not today's story: no report ran on 29 July, and the 30 July report's Drop Site search came up empty, so this is the first time it appears in this category despite being one of the more consequential stories of the week.

Drop Site News reports that Brad Parscale, Donald Trump's former 2020 campaign manager, has since October 2025 been running a covert operation on behalf of the Israeli government aimed at shaping how AI systems such as ChatGPT, Gemini, Copilot and Perplexity answer questions about Israel and Gaza. The contract, held by Parscale's firm Clock Tower X, is worth $46.5 million in total and currently runs at $4.5 million a month, having tripled from an initial $1.5 million monthly rate.

The mechanism is not direct lobbying of the AI companies but content seeding: Clock Tower X built a network of ten websites, each pushing a specific narrative. Paxpoint.org presents Israel as committed to peace, Allyvia.org promotes US-Israel military cooperation, and FactSignal.org poses as a neutral fact-checking outlet while publishing material that discredits Palestinian journalists and denies genocide allegations in Gaza. The sites carry Foreign Agents Registration Act notices identifying Clock Tower X as an agent of the Israeli government, though the report found some AI platforms drop that disclosure when citing the material as a source.

The evidentiary basis is a Common Crawl analysis: the ten sites were crawled 912 times between January and June 2026, rising from twice in January to 376 times in May, tracking the period the AI-targeting strategy intensified. Drop Site says it manually verified a sample of 50 archived links. Researchers then tested five AI systems directly. Gemini, Copilot and Perplexity cited the Clock Tower network in their answers; when asked whether the US should deepen military cooperation with Israel, Perplexity answered "Yes" and cited Allyvia.org as its top source. ChatGPT and Claude showed no evidence of having trained on the network's content, though both can still surface the sites through live web search.

The report leans on a joint study by Anthropic, the UK AI Security Institute and the Alan Turing Institute, which found that as few as 250 planted documents can compromise a language model's outputs regardless of the model's overall training-data volume — the technical claim that makes a ten-website, low-traffic operation a viable influence vector against systems trained on billions of documents. Named experts quoted include Check First CEO Hervé Letoqueux, who cautioned that measuring the material's actual influence on any specific model is difficult, and NewsGuard analyst Alice Lee, who noted the propaganda is hard to flag because it mixes real information with a slanted framing rather than fabricating facts outright. The Digital Forensic Research Lab is cited stressing that appearing in Common Crawl doesn't guarantee a model actually trained on the content, a caveat the report itself carries rather than glosses over.

The story matters beyond the Gaza framing fight. It is a documented, funded case of a state actor treating AI training-data pipelines as a lobbying surface, using content-marketing tactics (clean summaries, bullet points, heavy internal linking) that are indistinguishable in form from legitimate SEO best practice. That is the detail worth sitting with: the same structural signals that make a page rank well and read as trustworthy to a crawler are exactly what this operation industrialised.

---

## Story 2: UK medical regulator leaked a sexual-abuse complainant's confidential file to an unrelated doctor

**Source:** openDemocracy | https://www.opendemocracy.net/uk-doctors-watchdog-shared-sexual-abuse-victims-confidential-file/
**Author:** Sian Norris | **Published:** 28 July 2026 | **Read time:** ~5 min
**Related vault notes:** none directly relevant.

Per the granularity rule this is a catch-up, not today's story: it was missed because no report ran 29 July and the 30 July report only logged openDemocracy's date range without checking individual stories.

openDemocracy reports that a doctor, given the pseudonym Diana, complained to the General Medical Council (GMC) that a consultant had sexually assaulted her during a medical examination. When the GMC emailed her its investigation findings, the message contained the confidential file of a different woman entirely — full name, home address and a summary of alleged offences relating to an unrelated domestic and sexual abuse complaint against another doctor. A second data failure surfaced when Diana received her own case summary: the GMC had not redacted the name of a nurse who witnessed the original examination and was quoted in the police report.

Hampshire Police had already closed Diana's case with no further action, citing insufficient evidence, despite not having interviewed either the suspect or available witnesses. openDemocracy cites Labour MP Josh Fenton-Glynn's figures showing 94% of 997 sexual-assault complaints made to the GMC between January 2018 and August 2025 ended with no suspension or erasure of the doctor concerned. The outlet reviewed the email correspondence directly and put the breach to the GMC, which confirmed it had sent "the incorrect summary in error" and asked for the message to be deleted, while telling openDemocracy it takes data protection "very seriously" and has "robust processes" for reporting such incidents — a claim sitting awkwardly against the GMC's own record of five ICO notifications over five years and its apparent failure to self-report this one until asked.

The story's significance is structural rather than singular: a regulator responsible for handling some of the most sensitive complaints in the health system mishandled the data of two separate abuse complainants in the same case thread, on top of a body of evidence showing the GMC rarely acts against doctors accused of sexual misconduct in the first place.

---

## Story 3: Barrister prosecuted for defending Palestine Action activist sentenced as a "terrorist"

**Source:** openDemocracy | https://www.opendemocracy.net/palestine-action-filton-24-charlotte-head-rajiv-menon-kc-contempt-of-court-judge-johnson/
**Author:** Charlotte Head (first-person) | **Published:** 28 July 2026, updated 29 July 2026 | **Read time:** ~6 min
**Related vault notes:** none directly relevant.

Per the granularity rule this is a catch-up, missed for the same reason as Story 2.

Charlotte Head, sentenced to six years in prison over the August 2024 Palestine Action raid on the Elbit Systems weapons factory in Filton, Bristol, writes that her barrister, Rajiv Menon KC, is now himself facing a criminal contempt-of-court prosecution over his closing speech in her trial — the first prosecution of a barrister for defending a client in English legal history, according to the piece. Head and her co-defendants were charged with ordinary offences (criminal damage, violent disorder, aggravated burglary), not terrorism. Judge Johnson granted himself the authority to apply a "terrorism connection" at sentencing regardless, imposed reporting restrictions that stopped media naming that possibility during the trial, withheld the point from the jury, restricted the evidence the defence could put before jurors on retrial, and ultimately sentenced Head as a terrorist on 12 June, adding a 15-year post-release notification regime on top of the six-year term.

Menon's closing speech cited the Penn and Mead case of 1670, the foundational English precedent for jury independence from judicial direction. Johnson referred him for contempt prosecution over it. The Criminal Bar Association has warned the prosecution risks a chilling effect on defence advocacy generally. Head's account also names then-Home Secretary Yvette Cooper as having discussed the case and Palestine Action publicly in Parliament and the media before the trial concluded, without consequence. Menon received a last-minute stay on the contempt matter; it is now due to be heard in September 2026.

This runs on the same track as the Burnley/Barclays Palestine Action sentencing story carried in the 28 July report (five defendants, guilty of criminal damage, facing a post-conviction terrorism-connection application ahead of 4 September sentencing): a second, harsher instance of English courts applying terrorism findings to Palestine Action property-damage cases without a terrorism charge ever being laid, this time reaching as far as prosecuting the defence barrister himself.

---

## Sourcing quality

- **Drop Site News / Clock Tower X story:** could not be fetched directly (403); reconstructed from Middle East Monitor's detailed republication, cross-checked against Pakistan Today, The Express Tribune and Democracy Now's independent summary, all consistent on the core figures ($46.5m, ten sites, Common Crawl numbers). No byline confirmed anywhere in secondary coverage — flag this explicitly rather than guess. The underlying claim that Gemini/Copilot/Perplexity "cited" the network rests on Drop Site's own testing methodology, not independently reproduced here; treat the specific AI-response example (Perplexity's "Yes" answer) as Drop Site's test result, not a general finding about model behaviour.
- **GMC data-breach story:** openDemocracy reviewed the email correspondence directly and got an on-record response from the GMC confirming the error, which is solid primary-document sourcing. The 94% no-action statistic is attributed to an MP's figures, not openDemocracy's own analysis; the complainant is pseudonymised, standard for this kind of reporting but worth noting.
- **Menon/Palestine Action story:** first-person account from the defendant herself, published on her own outlet's platform, so read it as advocacy journalism rather than neutral reporting — the framing throughout is Head's own. The core facts (charges laid, sentence length, contempt referral, CBA statement) are checkable against public court record and are consistent with Declassified UK's separate 27 July reporting on the same wider Palestine Action sentencing pattern, which lends some independent corroboration to the general shape of events even though the specific quotes and framing here are one-sided.

---

## Research pipeline

- **Declassified UK, eleventh blocked occurrence (18, 20, 22, 23, 24, 25, 26, 27, 28, 30, 31 July; no check possible 29 July).** No change in failure mode across six weeks. The 20 July flag to Gareth remains unanswered. Recommend a direct decision (extend, downgrade to T2, or retire alongside Consortium News) rather than another rollover.
- **Clock Tower X / AI training-data seeding, worth its own Research note.** The technique (low-traffic content farms optimised for crawler pickup rather than human readers, riding the "as few as 250 documents can bias a model" finding) is a template that isn't unique to Israel/Gaza and is directly relevant to how Orwell should think about its own SEO portfolio's exposure to and defences against this kind of seeding, and to any AI-facing content Orwell itself produces.

---

## Threads

Two threads worth holding together. First, AI-training-data manipulation as a live lobbying tactic (the Clock Tower X story) sits next to Orwell's own SEO and content work as a cautionary case study rather than a coincidence — worth a look at whether portfolio sites carry any of the same crawler-facing signals this operation exploited. Second, the Menon/Filton story and the Burnley/Barclays sentencing story (28 July report) are the same emerging pattern from two different courts: English judges applying terrorism findings to Palestine Action property-damage convictions without a terrorism charge ever being brought, now extending to prosecuting defence counsel. Worth tracking as a single developing story if a third instance appears.

---

## Open loops from yesterday

- **Declassified UK access failure**, carried from 20 July, now on its eleventh occurrence (see Research pipeline). Unresolved, still needs Gareth's call.
- No story-level open loops from 30 July — that report had no stories of its own to carry forward.

---

## What this means for Orwell

The Clock Tower X story is the one item this week with a direct Orwell angle: it's a working, funded example of an actor deliberately seeding low-traffic websites with crawler-optimised, clean-summary content specifically to bias what large language models say, exploiting the same signals (clear structure, bullet points, internal linking) that legitimate SEO also optimises for. Worth five minutes at some point to sanity-check whether anything in the SEO portfolio could read as an unintentional version of this to a suspicious crawler, and whether it changes how Orwell should think about AI-facing content quality generally. The two openDemocracy stories (GMC data breach, Menon contempt prosecution) sit outside Orwell's commercial lines and are logged for the register's own sake.

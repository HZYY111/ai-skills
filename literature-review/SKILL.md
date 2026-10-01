---
name: literature-review
description: Find, verify, screen, organize, compare, and synthesize research papers into evidence-grounded literature reviews. Use for literature searches, top-conference or top-journal paper lists, research surveys, related-work overviews, method taxonomies, evidence tables, research-trend analyses, or careful comparisons of published results across multiple papers. Ask targeted scope questions before broad searches when a missing topic, date range, publication scope, paper type, or desired depth would materially change the result.
---

# Literature Review

## Operating objective

Turn a defined research question into a traceable set of real, relevant, high-quality papers and a review whose important claims can be checked against reliable sources.

Treat verification as a publication requirement. Never present an unverified paper, author, venue, dataset, metric, result, code repository, or conclusion as established fact. Mark missing or conflicting evidence instead of guessing.

## Clarify the scope

Before a broad search, check whether the user has specified:

- research topic or question;
- explicit start and end years;
- venue or publication-quality scope;
- paper types to include;
- expected output and review depth.

If any choice would materially change the search, ask 1–3 targeted questions and wait for the answers. Do not launch a broad search first.

Convert relative periods into explicit inclusive years. State the interpretation before searching. For example, interpret “the last three years” using the current date and report the exact year range.

## Select the minimum sufficient mode

- **Paper discovery**: return a verified, structured paper list and the search record.
- **Evidence review**: add per-paper research questions, innovations, methods, datasets, metrics, results, and limitations.
- **Literature survey**: classify the field, compare commensurable evidence, and write the review in the structure and depth requested by the user.

Use the least extensive mode that fully answers the request.

## Evidence rules

1. Verify bibliographic identity before including a paper in the confirmed set.
2. Prefer the conference or journal site, publisher page, and the paper itself. Use DBLP, arXiv, Semantic Scholar, project pages, and official repositories as complementary evidence.
3. Cross-check important metadata across multiple reliable sources when available. If a conflict remains, report it and do not silently choose a value.
4. Read the paper or an authoritative full-text version before reporting methods, datasets, metrics, numerical results, ablations, or limitations.
5. Treat search snippets, generated summaries, citation exports, and third-party descriptions as discovery aids, not as evidence for paper content.
6. Attach a reliable source or paper link to every important fact, numerical result, and comparative conclusion.
7. Separate author claims, directly demonstrated evidence, external verification, and review-level inference.
8. Use `not reported`, `not found`, `not verified`, or `not comparable` when evidence is insufficient. Never reconstruct missing details from memory or expectation.

## Relevance and quality gate

Include a paper only when it matches the user's topic, time range, venue or quality criteria, and requested paper type.

Judge quality with evidence appropriate to the request, such as publication venue, peer-review status, methodological completeness, experimental rigor, relevance, and source reliability. Do not substitute citation count or venue reputation for topical fit. Explain borderline inclusions and exclusions.

When the user asks for papers from “top conferences and top journals” without naming venues, cover all conferences and journals broadly recognized as top-tier within the specified research direction. Do not reduce the search to one ranking system. Build a field-specific venue set from authoritative ranking lists, relevant scholarly societies, official venue information, and established community consensus. Record the basis for the set. Include a disputed venue only with a clear qualification. Ask about the ranking system only when the user's request or institution makes that distinction material.

## Core workflow

1. **Define** the research question, scope, and output contract. Finish when all material search choices are explicit.
2. **Expand** keywords, abbreviations, related terms, and method names. Finish when each major concept has searchable variants.
3. **Search** multiple reliable sources and keep a search log. Finish when the planned sources and query families have been covered or documented as inaccessible.
4. **Deduplicate** records by title, authors, year, DOI, and version relationships. Finish when preprints and published versions are linked rather than double-counted.
5. **Screen** titles and abstracts against explicit inclusion and exclusion criteria. Finish when every candidate has a recorded decision.
6. **Verify** bibliographic identity and publication status. Finish when every included paper has sufficient source support or an explicit verification warning.
7. **Extract** evidence from the full text or authoritative supplementary material. Finish when every requested field is supported or marked unavailable.
8. **Classify and compare** methods and experiments only on compatible evidence. Finish when comparison boundaries are explicit.
9. **Write** the paper list or survey in the user's requested structure. Finish when every requested section is present and traceable to evidence.
10. **Audit** citations, factual claims, numbers, and uncertainty labels. Finish when no unsupported important claim remains.

## Search record

Keep at least:

- search date;
- platform or database;
- exact query or keyword group;
- explicit time range;
- venue or quality scope;
- inclusion and exclusion criteria;
- candidate, excluded, and included counts;
- access or coverage limitations.

## Comparability and best-result rules

Identify the dataset and version, split, metric definition, evaluation protocol, training data, pretraining, model scale, and other material conditions before comparing results.

Use topical relevance to decide whether a paper belongs in the review. Use experimental comparability to decide what role it can play in result comparison.

- Treat direction-matched, high-quality papers with sufficiently compatible metrics and settings as **primary comparison papers**. They may support quantitative comparisons and best-result judgments.
- Treat direction-matched, high-quality papers with different metrics, datasets, protocols, or other incompatible settings as **secondary papers**. Keep them in the paper list and literature review, explain their relevance and contributions, and state the source of incomparability. Do not include them in a shared numerical ranking or use them to support a cross-setting best-result claim.
- Exclude papers that do not match the specified research direction, regardless of venue prestige.

Group results by compatible setting. Compare numbers directly only within those groups. Use narrative comparison across incompatible groups and state why a fair numerical ranking is not possible.

Distinguish:

- a paper's own state-of-the-art claim;
- the best result within the verified and comparable evidence set;
- a result corroborated by multiple reliable sources.

Never describe a result as the current best without naming the dataset, metric, experimental setting, evidence cutoff date, and verification level.

## Required outputs

Match the user's requested format. When the user requests a full review, support at least:

- research background and problem definition;
- method taxonomy and representative papers;
- per-paper or per-category problems, innovations, and method descriptions;
- datasets, metrics, and experimental settings;
- major results and fair comparisons;
- carefully qualified best results;
- primary and secondary paper roles, with reasons for non-comparability where applicable;
- limitations, open problems, trends, and future directions;
- linked citations and the search record.

Do not replace the user's requested structure with a default template. Ask for clarification when two requested requirements conflict.

## Reference routing

Load only the reference needed for the current stage:

- Read `references/search-strategy.md` when planning or executing searches and recording coverage.
- Read `references/screening-and-verification.md` when screening, deduplicating, or verifying papers and publication status.
- Read `references/evidence-extraction.md` when extracting paper-level claims, methods, experiments, results, and limitations.
- Read `references/survey-writing.md` when classifying literature, comparing evidence, or writing a review.
- Read `references/output-templates.md` when the user needs a paper table, search log, evidence matrix, comparison table, or full-review format.

## Response style

Answer the user's actual question first. Keep the response concise unless the requested review requires depth. Use process diagrams, classification tables, and comparison tables when they make relationships clearer. If repeated questions show that an explanation did not work, change the explanation method rather than repeating it.

For commands or research tools, give the next concrete action first, then briefly explain why. Explain unfamiliar English command terms in the user's language.

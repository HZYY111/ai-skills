# Survey Writing

Use this reference to turn a verified evidence matrix into a literature review. Follow the user's requested structure, emphasis, terminology, length, and language. Do not replace an explicit user requirement with this default organization.

## 1. Confirm the writing contract

Before drafting, record:

- the review question and intended audience;
- required sections and their order;
- desired depth and length;
- time and venue scope;
- whether the output is a narrative review, structured review, systematic review, or another form;
- required citation and table format;
- evidence cutoff date.

Ask for clarification only when requirements conflict or a missing choice would materially change the review. If the user has already specified the structure, follow it directly.

**Completion criterion:** every explicit user requirement has a planned location in the review.

## 2. Check the evidence base

Write from the verified paper set and evidence matrix. Keep the search log, screening record, source locators, comparison groups, and unresolved conflicts available during drafting.

Do not use a search snippet, generated summary, or unverified secondary description as evidence for a paper's method, result, or conclusion. Do not fill a requested section with guesses when evidence is missing.

State the review's scope, evidence cutoff date, number of included papers, and important coverage limitations. Do not call the review exhaustive or systematic unless the search and screening process supports that claim.

**Completion criterion:** every paper used in the review is verified, and every known evidence limitation has a visible treatment plan.

## 3. Build the central synthesis

Organize the review around the research problem and the relationships among methods, not as a sequence of isolated paper summaries.

Use this reasoning chain:

```text
research problem
-> limitations of prior approaches
-> method families and design choices
-> changes in information, supervision, objective, or system structure
-> experimental evidence
-> supported conclusions, limitations, and open questions
```

Identify the few claims that the whole review must establish. Connect each claim to papers and evidence before drafting prose.

**Completion criterion:** the review has a clear central argument, and each major section advances it.

## 4. Write the background and problem definition

Explain:

- the research problem and why it matters;
- inputs, outputs, assumptions, and operating conditions;
- the principal technical difficulties;
- the scope covered and excluded by the review;
- the main historical or methodological transition relevant to the selected period.

Define ambiguous terms and distinguish adjacent research directions. Keep background proportional to the user's requested depth.

Support important factual or historical statements with reliable citations.

**Completion criterion:** a reader can tell exactly which problem the review covers and which nearby problems it does not cover.

## 5. Construct the method taxonomy

Choose classification dimensions that explain technical differences, such as:

- learning or supervision regime;
- model architecture;
- representation or information flow;
- optimization objective;
- use of external data, retrieval, tools, or prior knowledge;
- training or inference strategy;
- application or data modality.

Prefer one primary taxonomy. Add a secondary view only when it reveals a different important relationship.

For every category, provide:

- defining criterion;
- research problem addressed;
- core idea;
- representative papers;
- main innovations;
- common method structure;
- strengths, assumptions, and limitations;
- evidence showing when the category works.

Categories need not be mutually exclusive, but overlaps must be explicit. Do not create categories only to give every paper a unique label.

**Completion criterion:** every included paper has a justified place in the taxonomy or an explained cross-category role.

## 6. Select representative papers

Select representative papers using transparent reasons:

- direct relevance to the review question;
- foundational or method-defining contribution;
- strong experimental evidence;
- importance to a method category;
- influence on later work;
- unusually informative positive or negative result;
- relevance to an emerging trend.

Do not choose representatives only by citation count, venue prestige, or recency. A representative paper must illustrate a claim made by the review.

For each representative paper, report at the depth requested by the user:

- title, authors, year, and venue;
- direct paper link and code link when available;
- research problem;
- claimed and demonstrated innovations;
- method description;
- datasets and metrics;
- main results under their exact settings;
- comparison role;
- limitations.

**Completion criterion:** every highlighted paper has a stated reason for being representative and evidence for every reported field.

## 7. Synthesize problems, innovations, and methods

Within each method category, compare papers along the same questions:

1. What problem or prior limitation does the paper target?
2. What concrete technical change does it introduce?
3. How does that change affect data, representations, supervision, objectives, or inference?
4. Which experiment supports the claimed benefit?
5. Under which assumptions or conditions does the benefit hold?

Separate author-stated novelty from demonstrated differences and review-level interpretation. Avoid promotional descriptions that are not supported by methods or experiments.

Use a comparison table when several papers share fields. Keep necessary explanations in prose when a table would hide assumptions or causal relationships.

**Completion criterion:** similarities and differences are stated on common dimensions rather than as disconnected summaries.

## 8. Synthesize datasets and metrics

Explain:

- which datasets dominate the field and what they measure;
- dataset versions, splits, populations, modalities, languages, or domains;
- which datasets serve training, validation, testing, or pretraining roles;
- common evaluation metrics and their definitions;
- metric direction, scale, and aggregation method;
- known dataset or metric limitations;
- gaps between benchmark evaluation and real-world use.

Do not merge results across different dataset versions, splits, or metric definitions. Use separate table groups when necessary.

**Completion criterion:** every experimental comparison in the review maps to an explicit dataset, split, metric, and protocol.

## 9. Compare results fairly

Start from the comparison roles assigned during evidence extraction.

### Primary comparison papers

Use these for numerical comparison only within groups that share sufficiently compatible:

- datasets and versions;
- train, validation, and test splits;
- metric definitions;
- evaluation protocols;
- training and external data;
- pretraining, backbone, and model scale when material;
- supervision and inference regimes.

### Secondary papers

Keep direction-matched, high-quality papers in the review when their metrics or settings differ. Explain their methods, innovations, qualitative evidence, and relevance. State the exact incompatibility and exclude them from a shared numerical ranking.

Use narrative comparison across incompatible groups. Never describe a secondary paper as weaker merely because its reported number is on a different metric or setting.

**Completion criterion:** every direct numerical comparison belongs to a compatible group, and every secondary paper has a visible reason for its role.

## 10. Report current best results

Treat “current best” as a bounded evidence statement, not a universal property of a method.

For each best-result statement, name:

- dataset and version;
- split;
- metric and definition;
- experimental protocol;
- training and external data;
- model scale or backbone when material;
- comparison set;
- evidence cutoff date;
- verification level.

Distinguish:

- a paper's own state-of-the-art claim;
- the best verified result within one paper's comparable baselines;
- the best result among the review's compatible evidence set;
- a result corroborated by an authoritative external benchmark.

If settings are not sufficiently compatible, state that no fair overall ranking is available. Report separate best results by setting when supported.

**Completion criterion:** no best-result statement lacks a setting, comparison boundary, date, or verification label.

## 11. Write limitations and open problems

Synthesize limitations at several levels:

- method assumptions and failure cases;
- dataset bias, leakage, scale, or coverage;
- metric validity and benchmark saturation;
- weak baselines or incomplete ablations;
- reproducibility and unavailable resources;
- efficiency, compute, latency, or deployment constraints;
- robustness, generalization, privacy, fairness, or safety;
- gaps between claimed scope and tested scope.

Distinguish limitations acknowledged by authors, directly demonstrated failures, and review-level analysis. Do not invent criticism to make the section appear complete.

Turn recurring limitations into well-defined open problems rather than generic statements such as “more research is needed.”

**Completion criterion:** every open problem follows from repeated or important evidence in the reviewed literature.

## 12. Identify trends

Describe a research trend only when multiple verified papers or a clear sequence of evidence supports it.

For each trend, state:

- what changed;
- when the change appears in the review period;
- which papers demonstrate it;
- what evidence motivates it;
- whether it is established, emerging, or speculative.

Separate publication-frequency observations from technical progress. More papers on a topic do not by themselves prove that the method is better.

**Completion criterion:** every trend has a time boundary, supporting papers, and an evidence-strength label.

## 13. Propose future research directions

Derive future directions from identified evidence gaps. For each direction, specify:

- unresolved problem;
- why current methods do not solve it;
- promising technical route;
- required dataset, benchmark, or evaluation change;
- testable research question or hypothesis;
- likely risks or constraints.

Label proposals as review synthesis rather than claims made by the cited papers. Avoid vague predictions and unsupported certainty.

**Completion criterion:** every proposed direction is connected to a documented limitation or open problem and can be investigated empirically.

## 14. Use citations and links

Attach citations close to the facts they support. Provide a direct canonical paper link for every paper in the structured list and for every representative paper on first mention. Add DOI, open full text, project, code, and data links when available and useful.

Use the original paper for methods and experimental claims. Use official venue or publisher pages for publication facts. Label external benchmark or repository evidence separately.

Do not cite one paper for a statement that combines unsupported claims from several papers. Do not cite a survey as a substitute for checking the primary paper when reporting exact methods or numbers.

**Completion criterion:** every important factual claim and number has a nearby, appropriate source, and every listed paper has a working direct link.

## 15. Choose the clearest presentation

Use the smallest format that makes the evidence clear:

- a process diagram for the search or method sequence;
- a taxonomy table for method categories;
- an evidence table for paper-level fields;
- separate result tables for compatible experimental groups;
- prose for reasoning, qualifications, and cross-category synthesis.

Lead with the answer or conclusion the user requested. Keep background, repeated definitions, and paper-by-paper narration under control. Explain technical ideas for a research beginner without removing necessary precision.

## 16. Final audit

Before delivery, confirm that:

- the review follows every explicit user requirement and requested section order;
- all included papers match the specified research direction;
- paper identities, venues, links, and code claims are verified;
- problems, innovations, methods, datasets, metrics, results, and limitations are supported;
- primary and secondary papers are distinguished;
- incompatible results are not forced into one ranking;
- every current-best statement is bounded and qualified;
- author claims, direct evidence, external verification, and review inference are separated;
- important claims and numbers have citations;
- search scope, cutoff date, and limitations are visible;
- missing evidence is stated rather than guessed.

If any check fails, revise the affected section before delivering the review.

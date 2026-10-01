# Evidence Extraction

Use this reference after screening and verification to extract paper-level evidence for a structured paper list, comparison, or literature review. Extract only the depth required by the user's output contract.

## 1. Establish the evidence packet

For each paper, gather the best available version of:

- canonical publication page;
- published or author-provided full text;
- supplementary material;
- correction or erratum;
- official project page;
- official code and data repositories.

Record the exact version read. Prefer the published version. When using an author manuscript or arXiv version, check whether its content differs from the published paper.

Use the paper and its supplement as primary evidence for research content. Use official repositories to clarify implementation, configuration, preprocessing, or released resources. Use external sources only for metadata checks, background, or independent result verification, and label them separately.

**Completion criterion:** every extracted claim names the source version from which it was taken.

## 2. Preserve evidence locations

For every important fact or number, record a locator:

- section or subsection;
- page number when stable;
- figure, table, equation, algorithm, or appendix identifier;
- supplementary-material location;
- repository file or configuration path when relevant;
- direct paper or resource URL.

Prefer a precise locator such as `Table 2, row “Method X,” column “Accuracy”` over a general note such as `Experiments section`.

Do not cite an abstract, search snippet, generated summary, or repository README for a claim that should be checked in the method or experiments.

**Completion criterion:** another reader can locate every important extracted item without repeating the entire search.

## 3. Extract bibliographic and access information

Carry forward the verified identity rather than re-creating it:

- title;
- authors;
- publication year and date convention;
- conference or journal and paper type;
- DOI or persistent identifier;
- canonical paper page;
- open-access full text;
- arXiv page and version when applicable;
- project, code, and data links;
- evidence-access status.

Mark unavailable links as `not found` or `not verified`. Do not infer them from similar titles or repository names.

## 4. Extract the research problem

State:

- the task or question addressed;
- why it matters in the paper's setting;
- the input and expected output;
- the population, domain, modality, or operating conditions;
- the limitation of prior approaches that motivates the work;
- the scope the paper actually evaluates.

Keep the problem statement narrower than the paper's promotional language when the experiments support only a limited setting.

**Completion criterion:** the problem statement explains what is solved, under which conditions, and against which prior limitation.

## 5. Extract contributions and innovation

Separate three layers:

1. **Author-stated contribution**: what the paper explicitly claims is new.
2. **Demonstrated contribution**: what the method and experiments directly support.
3. **Review inference**: how the contribution differs from nearby work according to the evidence set.

For each claimed innovation, identify:

- the changed component, objective, data flow, supervision, representation, or evaluation design;
- the nearest baseline or prior approach;
- the concrete difference;
- the evidence that the difference matters;
- whether the novelty is methodological, empirical, resource-oriented, analytical, or applicative.

Do not repeat adjectives such as `novel`, `effective`, or `robust` without specifying the technical change and supporting evidence.

**Completion criterion:** every innovation is tied to both a concrete technical difference and an evidence source.

## 6. Extract the method

Describe the method at the depth required by the user. Cover:

- inputs and outputs;
- preprocessing or data construction;
- overall pipeline or architecture;
- purpose of each major component;
- information or tensor flow between components;
- training objectives and important losses;
- training and inference procedures;
- assumptions, constraints, and required external resources;
- implementation details that materially affect reproduction or comparison.

For each major component, use this frame:

```text
purpose -> input -> operation -> output -> connection -> expected benefit -> supporting evidence
```

Do not reconstruct missing equations, hyperparameters, or implementation choices. Mark them as unreported.

**Completion criterion:** the description is sufficient to distinguish the method from its closest alternatives without adding unsupported detail.

## 7. Extract datasets and data conditions

For every dataset or benchmark, record when reported:

- exact name and version;
- role: training, validation, test, pretraining, or external data;
- domain, modality, population, or language;
- sample count and class distribution;
- official or custom split;
- preprocessing, filtering, augmentation, and leakage controls;
- label source and annotation process;
- access or licensing constraints;
- dataset citation and official link.

Distinguish benchmark data from additional training data. Record synthetic, private, proprietary, or unreleased data because they affect reproducibility and fair comparison.

**Completion criterion:** every reported result can be connected to a defined dataset, split, and data-use role.

## 8. Extract metrics and evaluation protocols

For every metric, record:

- exact name and variant;
- definition or formula when ambiguity is possible;
- unit or scale;
- direction of improvement;
- averaging method, threshold, or aggregation rule;
- evaluation protocol and test split;
- whether the metric is directly comparable across papers.

Do not treat metrics with similar names as identical without checking their definitions. Examples include macro versus micro F1, top-1 versus top-5 accuracy, and dataset-specific versions of mAP, BLEU, ROUGE, or success rate.

**Completion criterion:** each result value has an unambiguous metric and evaluation protocol.

## 9. Extract experimental settings

Record conditions that can change the meaning of a comparison:

- model and parameter scale;
- backbone or foundation model;
- initialization and pretraining data;
- training data and additional supervision;
- prompt, retrieval, tool, or test-time resources;
- baseline implementations;
- hyperparameters that materially affect results;
- number of runs, random seeds, and variance reporting;
- compute or hardware when relevant;
- zero-shot, few-shot, fine-tuned, transductive, or other evaluation regime.

Do not describe two results as comparable merely because they use the same dataset and metric.

**Completion criterion:** all material comparison conditions are recorded or explicitly marked as unreported.

## 10. Extract numerical and qualitative results

For each result used in the review, record:

- exact value and unit;
- dataset, split, and metric;
- model or method variant;
- comparison baseline;
- absolute and relative improvement only when correctly calculable;
- uncertainty, confidence interval, variance, or significance test when reported;
- table, figure, or text location;
- qualifications stated by the authors.

Copy values from the paper table or text, not from a chart estimate, search snippet, or secondary summary. Preserve arrows, percentages, decimal scales, and whether higher or lower is better.

Use qualitative findings only with their tested context, examples, or evaluation method. Do not generalize a case study into a universal result.

**Completion criterion:** every result in the evidence matrix can be traced to an exact source location and experimental setting.

## 11. Evaluate best-result claims

Record a best-result or state-of-the-art claim as one of:

- **author claimed**: stated by the paper but not independently checked;
- **verified within paper**: supported against the comparable baselines reported in that paper;
- **verified within review set**: best among the review's independently checked, compatible results;
- **externally corroborated**: supported by another reliable benchmark or authoritative source;
- **not comparable**: settings differ enough to prevent a fair ranking.

For every such claim, record:

- dataset and version;
- test split;
- metric and definition;
- experimental regime;
- training and external data;
- evidence cutoff date;
- comparison set;
- verification level.

Never convert an `author claimed` result into an unqualified current-best statement.

**Completion criterion:** every best-result statement has a bounded setting, comparison set, date, and verification label.

## 12. Extract limitations and risks

Separate:

- limitations acknowledged by the authors;
- failure cases demonstrated by experiments;
- missing evidence or weak controls;
- reproducibility limitations;
- generalization and external-validity risks;
- efficiency, compute, data, privacy, fairness, or safety constraints;
- review-level concerns inferred from comparison with other papers.

Label review-level concerns as analysis, not as statements made by the authors. Do not invent a limitation merely to fill the field; use `not discussed` when appropriate.

**Completion criterion:** each limitation is attributed to the paper, direct evidence, or review analysis.

## 13. Assign comparison roles

After extraction, classify each direction-matched paper:

- **primary comparison paper**: quality is sufficient and the relevant dataset, metric, protocol, and material settings are compatible with a comparison group;
- **secondary paper**: direction and quality are sufficient, but metrics, datasets, protocols, scale, data, or other settings prevent direct numerical comparison.

Keep secondary papers in the structured list and review. Use them for method classification, innovations, qualitative evidence, limitations, and trends. State the exact reason they are not in a shared ranking.

Do not classify an off-topic paper as secondary; exclude it during screening.

**Completion criterion:** every included paper has a role and an explicit comparability reason.

## 14. Build the evidence matrix

Use one row per canonical paper and preserve source locators:

| Field | Required content |
|---|---|
| Identity | Title, authors, year, venue, paper type |
| Links | Canonical paper, DOI, full text, arXiv, project, code, data |
| Research problem | Task, setting, input, output, prior limitation |
| Contributions | Author claim, demonstrated contribution, review inference |
| Method | Pipeline, components, objectives, assumptions |
| Data | Dataset, version, split, role, preprocessing, added data |
| Evaluation | Metrics, definitions, protocols, baselines |
| Results | Exact values, variants, uncertainty, source locations |
| Best-result status | Setting, comparison set, cutoff date, verification level |
| Limitations | Author-stated, demonstrated, and review-inferred |
| Comparison role | Primary or secondary, with reason |
| Evidence status | Verified, partially verified, not reported, or disputed |

Keep concise summaries in the matrix and preserve detailed notes separately when needed.

## 15. Audit and hand off

Before survey writing, confirm that:

- every paper and resource link points to the correct work;
- every important fact and number has a source locator;
- author claims and review inferences are separated;
- datasets, metrics, splits, and settings are explicit;
- missing information is marked rather than reconstructed;
- primary and secondary roles follow the comparability evidence;
- best-result claims have bounded settings and verification labels;
- limitations are attributed correctly.

Pass the completed evidence matrix, detailed notes, source links, comparison groups, and unresolved conflicts to `survey-writing.md`.

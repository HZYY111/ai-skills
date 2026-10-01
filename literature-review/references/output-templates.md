# Output Templates

Use only the templates required by the user's requested output. Remove unused sections and fields. Preserve explicit user formatting requirements over these defaults.

Use `not reported`, `not found`, `not verified`, `disputed`, or `not comparable` instead of leaving an ambiguous blank or inventing content.

## 1. Scope confirmation

Use this compact block before searching when assumptions need to be made:

```markdown
## Search scope

- Research topic:
- Research question:
- Time range: <start year>–<end year>, inclusive
- Date convention: <conference year / journal issue year / online publication year>
- Venue scope:
- Paper types:
- Output mode: <paper discovery / evidence review / literature survey>
- Review depth:
- Evidence cutoff date:
- Confirmed assumptions:
```

When material information is missing, ask 1–3 targeted questions instead of filling this block with guesses.

## 2. Top-venue set record

Use this when the user requests all top conferences and journals in a research direction:

```markdown
## Venue set

| Venue | Type | Subfield | Top-tier basis | Ranking labels | Status or dispute | Official link |
|---|---|---|---|---|---|---|
| <full name (abbreviation)> | Conference/Journal | <subfield> | <authoritative list, society, and/or field consensus> | <labels if applicable> | Confirmed/Qualified | <URL> |

Coverage note: <how the set was built, what years it applies to, and any unresolved omissions>
```

Do not present one ranking list as the complete venue set unless the user explicitly requests that list.

## 3. Search log

```markdown
## Search record

**Search date:** <YYYY-MM-DD>  
**Time range:** <start year>–<end year>, inclusive  
**Date convention:** <...>  
**Inclusion criteria:** <...>  
**Exclusion criteria:** <...>  

| Platform or source | Exact query or navigation path | Filters | Results reviewed | Candidates retained | Notes |
|---|---|---|---:|---:|---|
| <source> | `<exact query>` | <years, venue, type> | <number/not available> | <number> | <coverage issue or terminology found> |

### Search accounting

- Raw candidate records:
- Duplicate or related versions grouped:
- Records excluded:
- Records unresolved:
- Canonical papers included:
- Coverage limitations:
```

Ensure the counts reconcile after version grouping. Do not invent a platform result count.

## 4. Screening decision log

```markdown
## Screening decisions

| ID | Candidate title | Decision | Reason code | Canonical work or version family | Verification status | Notes |
|---|---|---|---|---|---|---|
| P001 | <title> | Include/Uncertain/Exclude | <wrong-topic, duplicate-version, etc.> | <ID or relationship> | <full text/metadata/partial/unverified> | <brief reason> |
```

Keep excluded and unresolved records separate from the confirmed paper list.

## 5. Compact paper list

Use this when the user mainly wants discoverable papers:

```markdown
## Paper list

| # | Paper | Authors | Year | Venue | Role | Paper link | Open full text | Code |
|---:|---|---|---:|---|---|---|---|---|
| 1 | <verified title> | <verified authors> | <year> | <venue and paper type> | Core/Supporting/Background | [Official page](<URL>) | [PDF/arXiv](<URL>) or Not found | [Code](<URL>) or Not verified |
```

Add a one-sentence relevance note when the title alone does not show why the paper belongs.

## 6. Detailed paper evidence card

Use one card per canonical paper for an evidence review:

```markdown
## <ID>. <Verified paper title>

- **Authors:**
- **Year:**
- **Venue and paper type:**
- **Canonical paper page:**
- **DOI:**
- **Open full text / arXiv:**
- **Project page:**
- **Official code:**
- **Data:**
- **Evidence version read:**
- **Review role:** <core / supporting / background>
- **Comparison role:** <primary / secondary>

### Research problem

<Task, setting, input, output, and targeted prior limitation.>

### Innovations

- **Author-stated:** <claim with source locator>
- **Demonstrated:** <supported difference with evidence>
- **Review interpretation:** <clearly labeled synthesis>

### Method

<Pipeline, major components, objectives, training, inference, and assumptions.>

### Data and evaluation

| Dataset | Version and split | Role | Metric and definition | Protocol | Source locator |
|---|---|---|---|---|---|
| <dataset> | <version/split> | Train/Validation/Test/Pretraining | <metric> | <setting> | <section/table/page> |

### Main results

| Method variant | Dataset and split | Metric | Result | Baseline or comparison | Setting qualifications | Source locator |
|---|---|---|---:|---|---|---|
| <variant> | <dataset/split> | <metric> | <exact value and unit> | <baseline> | <pretraining, scale, data, regime> | <table/row/column/page> |

### Best-result status

- **Claim:**
- **Dataset, metric, and setting:**
- **Comparison set:**
- **Evidence cutoff date:**
- **Verification:** <author claimed / verified within paper / verified within review set / externally corroborated / not comparable>

### Limitations

- **Author acknowledged:**
- **Directly demonstrated:**
- **Review analysis:**

### Comparability note

<Why the paper is primary or secondary, and which comparison group it may enter.>
```

Do not force a field to contain prose when the paper does not report the information.

## 7. Evidence matrix

Use this for cross-paper synthesis:

```markdown
| ID | Problem | Innovation | Method family | Dataset and split | Metrics | Main supported result | Limitations | Comparison role | Evidence status |
|---|---|---|---|---|---|---|---|---|---|
| P001 | <...> | <...> | <...> | <...> | <...> | <result with locator> | <...> | Primary/Secondary | Verified/Partial/Disputed |
```

Keep cells concise. Put detailed settings and source locations in the paper evidence cards.

## 8. Comparable-result table

Create one table for each compatible experimental group:

```markdown
## Results: <dataset, version, split, metric, and evaluation regime>

**Compatibility boundary:** <shared conditions required for this table>  
**Evidence cutoff date:** <YYYY-MM-DD>

| Paper and method | Year | Training and external data | Backbone or scale | Metric | Result | Uncertainty | Verification | Source |
|---|---:|---|---|---|---:|---|---|---|
| <paper/method> | <year> | <data> | <scale> | <metric> | <value> | <reported value or not reported> | <level> | <table locator and link> |
```

Place incompatible results in separate tables or in the secondary-paper table below.

## 9. Secondary-paper table

```markdown
## Relevant papers outside the shared numerical comparison

| Paper | Why it is relevant | Method or innovation | Evidence contributed | Reason not directly comparable | Paper link |
|---|---|---|---|---|---|
| <paper> | <direction match> | <method> | <qualitative or setting-specific finding> | <different metric, dataset, protocol, scale, or data> | [Paper](<URL>) |
```

Do not describe a secondary paper as inferior solely because it does not enter the main result table.

## 10. Current-best statement

Use this bounded form:

```markdown
As of <evidence cutoff date>, <paper/method> reports <result> on <dataset and version>, using <split>, <metric definition>, and <evaluation regime>. Within <explicit compatible comparison set>, this is <verification level>. This statement does not cover <excluded or incompatible settings>.
```

Allowed verification labels:

- `author claimed`;
- `verified within paper`;
- `verified within review set`;
- `externally corroborated`;
- `not comparable`.

If no fair ranking is possible, use:

```markdown
No single current-best result is reported because the included papers use incompatible <datasets/metrics/protocols/settings>. The review therefore reports separate results by experimental group without an overall ranking.
```

## 11. Full literature-review structure

Use this default only when the user has not supplied a different structure:

```markdown
# <Review title>

## 1. Scope and search record
- Research question
- Explicit time and venue scope
- Search sources and queries
- Inclusion and exclusion criteria
- Included-paper count
- Evidence cutoff date and limitations

## 2. Research background
- Motivation
- Problem definition
- Inputs, outputs, assumptions, and technical challenges

## 3. Method taxonomy
- Classification rationale
- Category definitions
- Representative papers and links

## 4. Problems, innovations, and methods
- Per-category research problems
- Core ideas and technical differences
- Evidence supporting claimed benefits

## 5. Datasets and evaluation
- Dataset roles, versions, and splits
- Metrics and protocols
- Dataset and metric limitations

## 6. Experimental comparison
- Compatible comparison groups
- Primary-paper result tables
- Secondary-paper discussion
- Fairness and reproducibility qualifications

## 7. Current best results
- Bounded result statements by setting
- Author claims versus independently verified findings
- Cases where no fair ranking is available

## 8. Limitations and open problems
- Method, data, evaluation, and reproducibility limitations
- Repeated evidence gaps

## 9. Research trends
- Established and emerging trends
- Supporting papers and time boundaries

## 10. Future research directions
- Evidence-derived questions
- Testable technical routes and evaluation needs

## References
- Verified citations with direct paper links
```

## 12. Uncertainty and conflict notes

Use visible labels:

```markdown
- **Not reported:** the paper does not provide the information.
- **Not found:** the information or link was not located in the searched sources.
- **Not verified:** a claim or resource was found but lacks sufficient authoritative support.
- **Disputed:** reliable sources conflict; list the values and sources.
- **Not comparable:** experimental conditions do not support direct numerical comparison.
- **Review inference:** the statement is a synthesis by the reviewer, not a claim made by the paper.
```

Never hide uncertainty in a footnote when it changes the interpretation of a result.

## 13. Delivery checklist

Before returning any template-based output, confirm that:

- every listed paper matches the research direction;
- every paper identity, venue, and link is verified;
- every requested field is present or explicitly marked unavailable;
- important facts and numbers have nearby sources;
- paper links are direct and working;
- primary and secondary papers are distinguished when results are compared;
- incompatible settings are not placed in one numerical ranking;
- current-best statements use bounded settings and verification labels;
- the user's requested structure takes precedence over the default template.

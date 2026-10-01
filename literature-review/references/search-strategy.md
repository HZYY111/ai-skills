# Search Strategy

Use this reference to plan and execute a literature search, define coverage, and preserve a reproducible search record. Stop before final inclusion decisions; use `screening-and-verification.md` for screening, deduplication, and confirmation.

## 1. Freeze the search contract

Record the following before searching:

- research topic or question;
- explicit inclusive start and end years;
- publication and venue scope;
- paper types;
- language or access constraints;
- required outputs and depth.

Ask 1–3 targeted questions only when missing information would materially change the result. If the topic is already clear, do not ask the user to restate it.

Convert relative dates into explicit years and state the interpretation. Also record which date controls eligibility: conference year, journal issue year, official online-publication year, or another user-specified date. Do not silently mix date conventions.

**Completion criterion:** every material boundary is explicit, or the user has approved a documented assumption.

## 2. Build a concept map

Split the research question into concept blocks:

| Block | Typical content |
|---|---|
| Core problem | The task, phenomenon, or research question |
| Method family | Established and emerging approach names |
| Application or domain | Population, modality, environment, or use case |
| Evidence terms | Dataset, benchmark, evaluation, comparison, survey |
| Exclusions | Adjacent meanings that produce false positives |

For each block, collect:

- canonical terms;
- abbreviations and expanded forms;
- spelling, hyphenation, and naming variants;
- older and newer terminology;
- closely related methods or predecessor terms;
- field-specific dataset or benchmark names when useful.

Use paper titles, venue taxonomies, and terminology from verified seed papers to refine the vocabulary. Do not assume that one fashionable keyword covers the whole field.

**Completion criterion:** every major concept has enough variants to retrieve papers that use different terminology without expanding into a different research direction.

## 3. Define the venue set

When the user names venues, use that list exactly and report access limitations.

When the user asks for “top conferences and top journals” without naming venues, construct a field-specific set that covers all venues broadly recognized as top-tier in the specified research direction. Do not restrict the set to one ranking system.

Build the set from:

1. authoritative disciplinary ranking or recommendation lists;
2. relevant scholarly societies and professional associations;
3. official conference and journal information;
4. stable community consensus within the specific subfield.

Use the union of supported venues, then annotate each venue with:

- full name and standard abbreviation;
- conference or journal;
- relevant subfield;
- evidence for top-tier status;
- ranking-system labels when applicable;
- disputed or borderline status.

Do not treat one global list as authoritative for every subfield. Do not infer top-tier status from citation metrics alone. If a venue's status is disputed, keep it separate or label it clearly rather than silently treating it as undisputed.

**Completion criterion:** the search record contains a justified venue set for every relevant subfield, with disagreements and omissions visible.

## 4. Use complementary search paths

Use at least two search paths for non-trivial reviews:

### Topic-first search

Search the concept combinations across broad scholarly indexes. Use this path to discover terminology, venues, and papers outside the initial venue assumptions.

### Venue-first search

Search each venue in the defined venue set by year and topic. Use this path to detect relevant papers missed by ranking or keyword behavior in general indexes.

### Citation chaining

Use backward references and forward citations from verified seed papers when the topic has established terminology or a clear research lineage. Treat citation chaining as a supplement, not a replacement for database and venue searches.

### Author or project search

Use author pages, project pages, and official repositories only to find associated papers, code, datasets, or corrected links. Verify discovered papers through authoritative publication sources before confirming them.

**Completion criterion:** both topic-first and venue-first coverage are complete, or the search log explains why one path was not applicable; useful seed papers have received citation chaining where appropriate.

## 5. Assign each source a role

Use sources for the evidence they are suited to provide:

| Source | Primary role |
|---|---|
| Conference or journal site | Official acceptance, track, year, and publication identity |
| Publisher or proceedings page | Canonical metadata, DOI, publication version, and full text |
| DBLP | Computer-science bibliographic discovery and metadata cross-checking |
| arXiv | Preprint discovery, version history, and accessible author manuscripts |
| Semantic Scholar | Broad discovery, citation links, and related-paper exploration |
| Official project page or repository | Code, data, models, configurations, and paper-associated resources |

Add field-specific databases when they materially improve coverage. Record the database name and purpose.

Do not use a search snippet, generated answer, repository README, or third-party summary as evidence for paper content. At the search stage, label records as candidates rather than verified inclusions.

## 6. Capture usable paper links

Give every retained candidate a direct paper link that lets the user identify and reach the work without repeating the search.

Prefer links in this order:

1. official conference, journal, proceedings, or publisher landing page;
2. DOI URL;
3. official open-access proceedings page;
4. author-posted or repository full text;
5. arXiv abstract page and versioned PDF.

When both a published version and a preprint exist, retain both and label them clearly. Use the published landing page as the canonical paper link and the preprint as an accessible full-text alternative when appropriate.

Keep separate fields for:

- canonical paper page;
- DOI URL;
- open-access full text or PDF;
- arXiv page and version;
- project page;
- official code repository.

Do not return search-result URLs, temporary download URLs, tracking links, or a repository URL as a substitute for the paper link. Confirm that each saved link resolves to the same title and authors before it reaches the final paper list.

**Completion criterion:** every retained candidate has a stable paper-identification link; missing full-text or code links are marked as unavailable rather than invented.

## 7. Construct and run queries

Combine terms within a concept block with `OR`; combine different blocks with `AND`. Use exclusions only when false positives are persistent and clearly unrelated.

Example pattern:

```text
("few-shot learning" OR "few shot classification" OR meta-learning)
AND
(benchmark OR evaluation OR dataset)
AND
(2024 OR 2025 OR 2026)
```

Adapt syntax to each platform. Preserve the exact query actually used, not only a cleaned-up description.

Run queries in small families:

1. broad core-topic query;
2. major method-family queries;
3. dataset or benchmark queries where relevant;
4. venue-by-year queries;
5. terminology discovered during searching.

Inspect early results before multiplying queries. Add a term only when it retrieves a missing branch or removes a documented false-positive pattern.

**Completion criterion:** every concept and venue branch has at least one recorded query, and new queries no longer reveal an unsearched relevant branch.

## 8. Capture candidate records

For every candidate, retain enough information for later deduplication and verification:

- title as displayed;
- authors as displayed;
- year and date convention;
- claimed venue and paper type;
- DOI, arXiv identifier, or other persistent identifier;
- discovery source and URL;
- canonical paper page and DOI URL when available;
- open-access full-text URL when available;
- arXiv page and version when applicable;
- project page and official code URL when discovered;
- query or citation path that found it;
- provisional relevance note;
- verification status.

Keep preprints and published versions as separate raw records at this stage, but record suspected relationships. Resolve them during deduplication.

## 9. Maintain the search log

Record each search session:

| Field | Required value |
|---|---|
| Search date | ISO date |
| Platform | Database, venue site, or other source |
| Query | Exact query or navigation method |
| Time range | Explicit inclusive years and date convention |
| Venue scope | Named venues or the justified top-tier set |
| Filters | Paper type, language, subject, access, or track filters |
| Results reviewed | Number inspected when available |
| Candidates retained | Number sent to screening |
| Notes | Coverage gaps, errors, or newly discovered terminology |

Never report an exact total result count when the platform does not expose a stable count. Use `not available` or describe the review depth instead.

## 10. Check coverage and stop

Do not stop only because the first page looks sufficient. Stop when all of the following hold:

- every planned platform or source has been searched or marked inaccessible;
- every major keyword and method branch has been searched;
- every venue in scope has received venue-first coverage for the target years;
- citation chaining no longer reveals a new relevant branch;
- recent query iterations produce mostly duplicates or clearly out-of-scope records;
- remaining coverage limitations are documented.

This is a coverage stop, not proof that no other paper exists. State the evidence cutoff date and limitations in the final output.

## 11. Hand off to screening

Pass the raw candidate set, venue-set record, concept map, exact search log, and known version relationships to `screening-and-verification.md`.

Do not label candidates as included, high quality, or verified until that workflow is complete.

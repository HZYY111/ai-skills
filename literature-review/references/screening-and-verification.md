# Screening and Verification

Use this reference to turn a raw candidate set into a deduplicated, verified set of papers that matches the user's research direction and scope. Use `evidence-extraction.md` later for detailed method and experiment extraction.

## 1. Freeze the decision criteria

Copy the approved search contract and convert it into explicit inclusion and exclusion rules before screening.

Include a paper only when it satisfies all mandatory conditions:

- directly addresses the specified research direction or a user-approved subproblem;
- falls within the explicit time convention and year range;
- matches the requested venue, quality, and paper-type scope;
- has a verifiable bibliographic identity;
- provides enough accessible evidence for the output in which it will be used.

Exclude or separately label:

- papers from an adjacent but different research direction;
- records outside the time range;
- editorials, abstracts, posters, demos, tutorials, workshop papers, or short papers when the requested scope excludes them;
- duplicate versions of the same work;
- withdrawn or retracted work, unless the user explicitly asks to study it;
- records whose identity or publication status cannot be verified.

Do not include an off-topic paper because it is highly cited or appears in a prestigious venue. When a paper is relevant but its experiments may not be comparable, retain it and mark comparison eligibility as pending rather than excluding it.

**Completion criterion:** every mandatory rule has a written yes/no test that can be applied consistently.

## 2. Screen for direct relevance

Screen titles and abstracts against the research question, not only against keyword overlap.

For each candidate, identify:

- the problem actually studied;
- the input, output, population, or application setting;
- the central method or intervention;
- whether the claimed contribution answers the user's question.

Assign one relevance decision:

- **include**: directly addresses the requested direction;
- **uncertain**: abstract evidence is insufficient; inspect the full text;
- **exclude**: addresses a different problem or only mentions the topic incidentally.

Use a short reason code for every exclusion, such as `wrong-topic`, `wrong-period`, `wrong-venue`, `wrong-paper-type`, `insufficient-evidence`, or `duplicate-version`.

**Completion criterion:** every candidate has a relevance decision and a recorded reason; every `uncertain` record has received full-text inspection or remains explicitly unresolved.

## 3. Group duplicate and related versions

Detect duplicates using several signals:

- normalized title;
- author overlap and order;
- DOI or other persistent identifier;
- arXiv identifier;
- identical abstract or method description;
- explicit “extended version of” or “published as” statements.

Build one version family for each work. Distinguish:

- preprint versions;
- conference versions;
- extended journal versions;
- corrections or errata;
- supplementary material.

Use the final peer-reviewed publication as the canonical record when it exists, but retain links to useful preprints and earlier versions. Do not merge a journal extension with the conference paper when it contains a materially different method, dataset, experiment, or claim; instead, link the records and explain the relationship.

Count one work once unless the user's unit of analysis is publication versions.

**Completion criterion:** no included work is double-counted, and every related version has an explicit relationship to the canonical record.

## 4. Verify bibliographic identity

Verify each included paper against an authoritative source such as the official venue, proceedings, journal, or publisher page. Cross-check with an independent bibliographic source when available.

Confirm:

- exact title;
- complete author list or the authoritative displayed form;
- publication year under the chosen date convention;
- full venue name and standard abbreviation;
- conference track or journal article type when relevant;
- volume, issue, and pages or article number when applicable;
- DOI, arXiv identifier, or other persistent identifier;
- publication, withdrawal, correction, or retraction status.

Do not infer venue publication from an arXiv manuscript that merely says “submitted to” or “under review.” Do not treat an accepted workshop, short, findings, demo, or companion-track paper as a main-track full paper without explicit evidence.

If authoritative sources conflict, record the conflicting values and their sources. Resolve the conflict only with stronger evidence; otherwise mark the field as disputed.

**Completion criterion:** every included paper has an authoritative identity source, and every unresolved metadata conflict is visible.

## 5. Verify top-venue eligibility

When the user requests top conferences or top journals, compare the claimed venue with the justified, field-specific venue set created during search planning.

Confirm:

- the venue belongs to the paper's actual research subfield;
- the relevant publication year and venue name are correct;
- the paper belongs to an eligible track and paper type;
- the basis for top-tier status is recorded;
- disputed venues are explicitly qualified.

Use all broadly recognized top-tier venues in the specified direction rather than silently selecting one ranking list. Do not upgrade a venue because a particular paper is influential, and do not downgrade a direction-matched paper solely because two ranking systems disagree; report the disagreement and apply the user's stated scope.

**Completion criterion:** every paper included under a top-venue requirement has a recorded and checkable venue-eligibility basis.

## 6. Verify paper and resource links

Open each saved link and confirm that it resolves to the same title and authors.

Verify separately:

- canonical official or publisher paper page;
- DOI URL;
- open-access full text or PDF;
- arXiv abstract page and version;
- official project page;
- official code repository.

Prefer stable landing pages over temporary PDF, redirect, search-result, or tracking URLs. Label links by type. Do not use a code repository, blog post, citation page, or generated summary as the paper link.

Treat a repository as official only when the paper, authors, project page, or verified organization links to it. If code existence cannot be confirmed, report `not verified` rather than selecting a similarly named repository.

**Completion criterion:** every included paper has a working canonical identification link; every additional link has the correct type and relationship.

## 7. Check evidence access

Determine how much evidence is available for each paper:

- **full-text verified**: authoritative or author-provided full text is accessible;
- **metadata verified**: identity is verified, but the full text is unavailable;
- **partially verified**: only some authoritative evidence is accessible;
- **unverified**: identity or publication status remains unsupported.

Use metadata-verified papers in a bibliographic list when they otherwise meet scope, but do not report detailed methods, datasets, metrics, results, or limitations without full-text evidence. Exclude unverified records from the confirmed paper set; place them in an unresolved appendix only when useful to the user.

**Completion criterion:** every retained paper has an evidence-access label that limits what later stages may claim.

## 8. Apply the quality gate

Assess quality only after direct relevance and identity verification.

Consider:

- peer-review and publication status;
- venue quality under the agreed scope;
- clarity of the research question and contribution;
- methodological completeness;
- experimental design and baseline adequacy;
- dataset and metric suitability;
- robustness, ablation, statistical support, or repeated trials where applicable;
- reproducibility evidence, including supplementary material, code, and configurations;
- disclosed limitations, conflicts, corrections, or retractions.

Do not use citation count, author reputation, venue name, or a paper's own novelty claim as sufficient evidence of quality. For recent papers, treat low citation counts as inconclusive.

Assign a transparent status such as `core`, `supporting`, `background`, or `exclude`, with a one-sentence reason. This status describes the paper's role in the review, not its numerical comparison eligibility.

**Completion criterion:** every included paper has a quality-and-role decision supported by recorded evidence.

## 9. Preserve non-comparable but relevant papers

Do not exclude a direction-matched, high-quality paper only because it uses a different dataset, metric, protocol, model scale, or experimental setting.

Retain it as a potential secondary paper and record the suspected source of non-comparability. Confirm its final primary or secondary comparison role after detailed evidence extraction.

Exclude it from a shared numerical ranking until comparability is demonstrated. It may still support method classification, innovation analysis, qualitative findings, limitations, and research-trend discussion.

**Completion criterion:** relevant papers are preserved without implying that incompatible results are directly comparable.

## 10. Maintain the decision record

Keep one row per canonical work:

| Field | Required content |
|---|---|
| Record ID | Stable local identifier |
| Canonical title | Verified title |
| Version family | Preprint, conference, journal, correction, supplement |
| Scope decision | Include, uncertain, or exclude |
| Reason | Short reason code and explanation |
| Venue status | Verified venue, track, year, and top-tier basis if required |
| Evidence access | Full text, metadata only, partial, or unverified |
| Quality role | Core, supporting, background, or exclude |
| Comparison status | Pending, potentially primary, or potentially secondary |
| Paper links | Canonical, DOI, full text, and arXiv as applicable |
| Resource links | Project, code, and data as applicable |
| Verification sources | Sources used to confirm the record |
| Conflict notes | Unresolved discrepancies or warnings |

Report candidate, excluded, unresolved, and included counts. Ensure the counts reconcile after version grouping.

## 11. Audit and hand off

Before evidence extraction, confirm that:

- every included paper directly matches the specified direction;
- every included identity and venue is supported by an authoritative source;
- duplicate versions are grouped correctly;
- every paper link reaches the correct work;
- unavailable information is marked rather than guessed;
- non-comparable but relevant papers remain available as secondary evidence;
- all exclusions and unresolved cases have reasons;
- the final counts reconcile with the decision record.

Pass the verified paper set, version families, links, quality roles, comparison-status notes, and source evidence to `evidence-extraction.md`.

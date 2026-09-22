# Facebook Ads Performance Analytics — Guided Project Campaign

**Campaign ID:** FBADS-PBI-01  
**Plan date:** 22 September 2026  
**Assignment deadline shown in the supplied brief:** Sunday, 27 September 2026, 11:59 PM  
**Status:** Planning only. Dataset, report, and GitHub repository have not yet been inspected or created for this campaign.

## 1. Project objective

Build a defensible Power BI report that compares advertising spend, engagement, and recorded approved conversions across campaigns and audience categories. Package the work as a reproducible GitHub portfolio project, while separately preparing the instructor's required PBIX and screenshot submission.

The working title is **Facebook Ads Campaign Performance Analysis**. Suggested repository name: `facebook-ads-powerbi`.

A successful project answers which campaigns generated more recorded outcomes, which had lower cost per outcome, and which warrant further investigation. It does not claim that observational comparisons prove causation, profitability, or future performance.

## 2. Decisions that must precede implementation

### 2.1 Instructor approval

The supplied assignment brief mentions class datasets or a dummy dataset. It does not explicitly approve an external Kaggle dataset. Ask the instructor whether this dataset is acceptable before treating the Facebook analysis as the final submission. The previously started financial dashboard remains a fallback submission until this is resolved.

### 2.2 Dataset selection and verification

Candidate: **Sales Conversion Optimization**, published on Kaggle under `loveall/clicks-conversion-tracking` [1]. The publisher describes 1,143 observations and 11 variables covering ad and campaign identifiers, audience categories, impressions, clicks, spend, enquiries, and approved conversions. Its documented columns contain no dates or revenue. The licence is displayed as “Other (specified in description).”

These are publisher descriptions, not results from inspection of the user's actual CSV. Record the actual filename, version/access date, row count, columns, and any differences when the file arrives.

Do not add invented campaign dates, revenue, product prices, interest-category names, or currency symbols. Keep interest values as codes unless a reliable mapping is supplied. Treat the publisher's conversion terminology as provisional metadata to verify, not as a complete attribution specification.

### 2.3 Public-sharing decision

Do not commit the raw dataset or publish a data-bearing report until reuse and redistribution terms are clarified. Attribution is part of documentation, not our substitute for checking the terms. A public source-only project is the planned fallback: reviewed project definitions or a template, source-download instructions, and approved screenshots/documentation.

A PBIT omits imported model data, but its metadata can retain filter selections and other literal values [8]. PBIP definitions and templates still need inspection before publication.

## 3. Scope and releases

### Release A — Assignment-ready core

One complete overview page that satisfies every visual requirement, with correct totals, working filters, and a clean layout. Save a working PBIX and a readable screenshot before attempting optional enhancements.

### Release B — Advanced analytical report

Add a diagnostic page and a campaign-detail drillthrough page. Improve filter-aware calculations, navigation, conditional formatting, explanatory labels, and evidence-based findings.

### Release C — Reproducible portfolio

Publish a reviewed GitHub repository containing source or a template, documentation, screenshots, source attribution, reproducible refresh instructions, and a tested release. Submit the instructor's PBIX and screenshot separately.

**Out of scope before the deadline:** live Facebook API integration, cloud data warehousing, scheduled refresh, forecasting without time data, actual ROAS without revenue, machine-learning predictions, and automated budget allocation. Add none of these merely to make the project sound advanced.

## 4. Assignment traceability

| Supplied requirement | Planned implementation | Acceptance evidence |
|---|---|---|
| Dashboard title created using a DAX measure | Filter-aware title with all/single/multiple selection states | Change campaign selections and verify title updates |
| 3–4 slicers; extra points mentioned above 3 | Four data slicers: company campaign, age group, gender, interest code | All four visible on the overview and tested |
| 3–5 card visuals; extra points mentioned above 3 | Five separate KPI cards | Each card uses an explicit DAX measure |
| One pie/donut with DAX measures | Campaign share of total advertising spend | Values reconcile to filtered spend |
| One column/bar chart with DAX measures | Approved conversions by company campaign | Values reconcile to the campaign table |
| One table with DAX measures | Campaign, spend, impressions, clicks, enquiries, approved conversions, CTR, and cost per approved conversion | Totals and formatting verified |
| Colour/design/grid bonus | Consistent typography, spacing, alignment, number formatting, and restrained colours | Screenshot review at normal reading size |
| Required submission | PBIX file plus dashboard screenshot | PBIX reopens and screenshot matches the saved default view |

Use the company campaign field for the main campaign slicer after checking its actual cardinality and meaning. Do not assume that the company's campaign ID and Facebook tracking campaign ID are interchangeable.

Microsoft documents DAX expression-based visual titles that respond to filters and selections [5]. The exact title-binding clicks will be taught against the installed Desktop interface.

## 5. Proposed report pages

### Page 1 — Executive Overview

Purpose: satisfy the assignment and communicate the overall picture immediately.

Five KPI cards: total spend, impressions, clicks, approved conversions, and cost per approved conversion. The conversion card may use clearer wording only after its definition is recorded in the metric dictionary.

Four slicers: company campaign, age group, gender, and interest code. Place them together, followed by the KPI row, the spend-share donut and campaign comparison bar, then the campaign table. Provide a clear reset control and a short source/limitations note. Do not add a date slicer to an undated dataset.

### Page 2 — Campaign and Audience Diagnostics

Purpose: investigate differences hidden by overall totals.

Plan an age-by-gender comparison, an interest-code comparison with a documented Top N rule when necessary, a spend-versus-approved-conversions scatter chart, and a compact ad table. Show both performance ratios and their denominators so that low-volume results are not presented as equally reliable to larger samples.

A metric selector is a stretch feature, not a replacement for the four required overview slicers. Field parameters can switch the measures or dimensions used by visuals [6]. Correctly label and format each selected metric rather than mixing currencies, counts, and percentages on an unchanged axis.

### Page 3 — Campaign Detail (drillthrough target)

Purpose: select one campaign and inspect its ads, spending, and recorded outcomes.

Include the selected campaign title, its KPI summary, a detailed ad table, and a back button. Test which filters carry through and clearly define whether audience filters should be preserved. Microsoft describes drillthrough as navigation to a detail page filtered for the selected context [7].

Keep this page hidden from normal navigation only after the navigation path works. A custom tooltip page is optional and is not another required visible page.

## 6. Guided working method

Work on one small task at a time. Each lesson contains the task ID, objective, exact actions, a brief explanation, expected result, and evidence to share. Review the result before continuing to the next task. UI instructions should match the installed version and the screenshot, not assume an older interface.

A normal checkpoint is a screenshot, a short count/total, or a saved documentation change. Do not ask for credentials, tokens, or private account details. Do not claim a task is complete from a screenshot that does not show the relevant evidence.

## 7. Detailed campaign backlog

All tasks below are initially **Not started**.

### Phase 0 — Confirm feasibility and inspect the source

**Goal:** establish a permitted, suitable dataset and a bounded business question.

- **T00:** Confirm external-dataset acceptance with the instructor.
- **T01:** Download the selected CSV and record its source/access date.
- **T02:** Inspect the actual columns, row count, candidate row identifier, and missing data.
- **T03:** Record the dataset's limitations and public-sharing decision.

**Gate:** dataset accepted for the assignment; actual file inspected; unsupported metrics excluded. Public publication may remain blocked while local analysis proceeds with an accepted dataset.

### Phase 1 — Create the project workspace

**Goal:** organise the project before building visuals.

- **T04:** Record the installed Power BI Desktop version and available project-save options.
- **T05:** Create a short local project path and the planned folders.
- **T06:** Initialise local Git and draft a README plus `.gitignore`; review staged files.
- **T07:** Set up a private GitHub repository once the account, repository owner, name, and visibility are confirmed. Push only reviewed project scaffolding initially.

**Gate:** local structure is correct; no dataset, cache, token, or personal machine configuration is accidentally tracked.

### Phase 2 — Import and clean with Power Query

**Goal:** make transformations explicit and repeatable.

- **T08:** Import CSV through Power Query without editing the original file.
- **T09:** Set data types: identifiers and categorical codes as categories; counts as whole numbers; spend as an appropriate numeric type.
- **T10:** Profile the full dataset, not just the default preview. Inspect nulls, errors, duplicate keys, unusual values, and whitespace.
- **T11:** Record each cleaning decision. Investigate unusual conversion/click relationships instead of silently deleting rows.
- **T12:** Establish a portable data-source parameter and a repeatable refresh process.

**Gate:** no unexplained type errors; all row exclusions documented; before/after counts reconcile; refresh works from the intended source path.

### Phase 3 — Model the data

**Goal:** make aggregations and filters correct before drawing conclusions.

- **T13:** Define the grain: write exactly what one fact row represents after checking uniqueness and repeated identifiers.
- **T14:** Build a small fact-and-dimension model where it is useful; start with campaign and audience lookup needs rather than manufacturing extra tables.
- **T15:** Configure and verify one-to-many, single-direction relationships where appropriate. Confirm that dimension keys are unique and fact keys match.
- **T16:** Set category sorting and summarisation behaviour; hide technical keys not intended for report users.
- **T17:** Compare row counts and additive totals before and after modelling.

**Gate:** dimension selections filter facts correctly; no duplicate-key fan-out or unexplained blank categories; the model has a consistent grain. Microsoft's star-schema guidance distinguishes dimensions for grouping/filtering and facts for summarisation [2].

For this small CSV, learning the model is the purpose. Do not claim that many tiny lookup tables automatically improve performance.

### Phase 4 — Build and validate DAX measures

**Goal:** use explicit, reusable definitions rather than visual-specific arithmetic.

- **T18:** Create base measures for spend, impressions, clicks, enquiries, and approved conversions.
- **T19:** Add CTR, CPC, CPM, and cost per approved conversion.
- **T20:** Define blank-versus-zero behaviour and consistent number formats.
- **T21:** Add a filter-aware title and document all/single/multiple/no-data states.
- **T22:** Add selected-context spend share and optional ranking only after base measures pass verification.

**Gate:** at least one manually checked campaign and one combined filter selection reconcile to the source. Ratio totals are recomputed from aggregate numerators and denominators, not averages of row ratios.

### Phase 5 — Complete the assignment-ready overview

**Goal:** secure the required submission before advanced work.

- **T23:** Set the page canvas, grid, spacing, and visual hierarchy.
- **T24:** Add the four required slicers and five individual KPI cards.
- **T25:** Add the donut, campaign bar chart, and campaign table using DAX measures.
- **T26:** Bind the title measure and verify visual interactions.
- **T27:** Save a working PBIX and capture a readable overview screenshot.

**Gate:** every assignment row in Section 4 is evidenced. This is Release A. Do not begin optional features while the core page is incorrect.

### Phase 6 — Add advanced analysis and interaction

**Goal:** improve investigation, not visual clutter.

- **T28:** Build the diagnostic page and show volume alongside efficiency.
- **T29:** Add campaign drillthrough and test filter carryover plus the back button.
- **T30:** Add useful conditional formatting, reset behaviour, and page navigation.
- **T31:** Add a metric selector or custom tooltip only after the required advanced page works.

**Gate:** every additional feature answers an identified question and works under combined filtering. Remove confusing or unfinished extras before submission.

### Phase 7 — Validate and write findings

**Goal:** make the analysis defensible.

- **T32:** Run the functional and data-quality test matrix in Section 9.
- **T33:** Write three findings, each with the metric, comparison, selection context, and supporting evidence.
- **T34:** Write two investigation or test recommendations and explain what additional evidence would be needed for a business decision.
- **T35:** Finish visual formatting and freeze the submission scope.

**Gate:** there are no invented findings, unsupported causal claims, or undocumented benchmark thresholds. This is Release B.

### Phase 8 — Publish and submit

**Goal:** deliver reproducible source and a working assessed artefact.

- **T36:** Complete README, data dictionary, metric definitions, data-quality notes, findings, and test results.
- **T37:** Save reviewed PBIP project definitions when supported, or export a reviewed PBIT fallback. Preserve a working PBIX for the instructor [3,8].
- **T38:** Check data-sharing permissions and inspect all staged files, metadata, screenshots, and release attachments.
- **T39:** Test a fresh-clone workflow using the documented source download and data-path parameter. Reopen the final PBIX separately.
- **T40:** Push the reviewed repository and create a `v1.0.0` release. Attach a data-bearing PBIX only when publication terms permit it.
- **T41:** Submit the PBIX and screenshot through the instructor's specified channel; confirm receipt.

**Gate:** GitHub is understandable and reproducible; the assessed PBIX opens; the screenshot reflects the submitted file. This is Release C.

## 8. Metric specification

| Proposed measure | Definition | Important behaviour |
|---|---|---|
| Total Spend | Sum of validated spend values | Do not assume currency is USD |
| Total Impressions | Sum of impressions | Not unique people reached |
| Total Clicks | Sum of clicks | Do not describe as unique visitors without evidence |
| Total Enquiries | Sum of the publisher's total-conversion field | Keep separate from approved conversions |
| Approved Conversions | Sum of the approved-conversion field | Document publisher meaning and attribution uncertainty |
| CTR | Total Clicks / Total Impressions | Format the ratio as a percentage; do not multiply by 100 again in a percentage-formatted measure |
| CPC | Total Spend / Total Clicks | Undefined when clicks are zero |
| CPM | 1,000 × Total Spend / Total Impressions | Undefined when impressions are zero |
| Cost per Approved Conversion | Total Spend / Approved Conversions | Undefined when approved conversions are zero |
| Spend Share | Selected group's spend / explicitly defined comparison total | State which campaign/audience filters the denominator retains |

Use `DIVIDE` for denominator-sensitive DAX calculations; it returns blank on zero division by default [4]. A blank or clearly labelled “Not available” is not the same as a zero cost. Zero spend with positive outcomes must also be reviewed before ranking.

Do not force impressions, clicks, enquiries, and purchases into a strict funnel unless the dataset's definitions support that interpretation. Do not treat summed ad-level conversion counts as deduplicated unique customers.

## 9. Validation matrix

| Test area | Required evidence |
|---|---|
| Source integrity | Actual filename, rows, column types, row grain, candidate-key uniqueness, and issue log |
| Transformation audit | Before/after counts; justified row exclusions; no unexplained changes to additive totals |
| Relationships | Unique dimension keys, matching fact keys, correct filter direction, and preserved totals |
| Measures | Independent reconciliation for base totals and ratio calculations |
| Empty states | Zero clicks, zero approved conversions, missing values, and filter selections returning no rows |
| Filters | Single and combined selections; all versus multiple campaign selections; clearing and reset |
| Advanced navigation | Drillthrough context, back navigation, and intentional cross-page filter behaviour |
| Visual integrity | Readable labels, correct units, correct sort order, no clipped content, no misleading shared axes |
| Findings | Each finding includes a denominator or volume context and a clear limitation |
| Reproducibility | Source instructions and data-path parameter work in a separate checkout/location |
| Publication safety | No unapproved source data, caches, credentials, private paths, or hard-coded confidential values |
| Submission | Reopened PBIX matches screenshot; required files submitted before the stated deadline |

Only report performance timings after measuring them on the user's machine. Prioritise unnecessary visual removal and correct modelling over unmeasured optimisation claims.

## 10. GitHub structure and publication rules

```text
facebook-ads-powerbi/
├── README.md
├── .gitignore
├── docs/
│   ├── PROJECT_CAMPAIGN.md
│   ├── data-dictionary.md
│   ├── data-quality.md
│   ├── metrics.md
│   ├── findings.md
│   └── testing.md
├── data/
│   ├── README.md
│   └── raw/                         # Local only until sharing is cleared
├── powerbi/
│   ├── FacebookAds.pbip             # When PBIP is supported/enabled
│   ├── FacebookAds.Report/
│   └── FacebookAds.SemanticModel/
├── screenshots/                    # Reviewed before publication
└── exports/                        # Local submission artefacts; ignored initially
    └── FacebookAds.pbix
```

PBIP stores report/model definitions in text files and is currently documented as a preview feature. Keep one working source of truth and generate the instructor's PBIX from it; do not independently edit two divergent versions [3]. Desktop-generated `.pbi` cache and local settings must not be committed. A PBIT is the fallback when PBIP would disrupt the deadline.

Suggested milestone commits:

```text
chore: initialise project structure and source documentation
data: add documented cleaning and model definitions
feat: add validated advertising performance measures
feat: complete assignment overview
feat: add diagnostics and campaign drillthrough
docs: record findings validation and reproduction steps
release: prepare v1.0.0 submission
```

The proposed public README should show the question, screenshot, source and limitations, model summary, metric definitions, evidence-based findings, refresh instructions, tested Desktop version, and publication scope. Distinguish licensing for original project work from third-party data.

GitHub blocks ordinary repository files above 100 MiB and recommends Releases or Git LFS for appropriate large-file workflows [9]. Check actual output size rather than assume the PBIX needs LFS. A GitHub release does not remove the dataset-permission check.

## 11. Deadline-aware schedule

This is a proposed working schedule, not a guarantee of effort or completion.

| Date | Target |
|---|---|
| 22 September | Dataset/instructor decision, source inspection, workspace |
| 23 September | Power Query cleanup, documentation, model |
| 24 September | DAX validation and complete assignment-ready overview |
| 25 September | Diagnostic page, drillthrough, selected polish |
| 26 September | QA, findings, documentation, GitHub publication, final PBIX and screenshot |
| 27 September | Reopen and verify deliverables, practise explanation, submit with time to spare |

When time is tight, remove custom tooltips, metric selectors, and extra chart variations first. Preserve correct measures, all assessed visuals, readable design, and the required submission files. Keep the previous financial report available until the new dataset is approved and Release A works.

## 12. First checkpoint

**Active task:** T00–T02, dataset readiness.

Supply the actual downloaded CSV and confirm whether the instructor accepts an external Kaggle dataset. The first working lesson is inspection of that file, followed by the precise import steps. Do not start building visuals from assumed columns.

## References

The assignment requirements and deadline are transcribed/paraphrased from the image supplied in this conversation. The remaining sources are the dataset publisher and official product documentation, accessed 22 September 2026.

[1] Kaggle, Sales Conversion Optimization: https://www.kaggle.com/datasets/loveall/clicks-conversion-tracking

[2] Microsoft, Understand star schema and the importance for Power BI: https://learn.microsoft.com/en-us/power-bi/guidance/star-schema

[3] Microsoft, Power BI Desktop projects: https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview

[4] Microsoft, DIVIDE function: https://learn.microsoft.com/en-us/dax/divide-function-dax

[5] Microsoft, Create expression-based titles and subtitles: https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-conditional-format-visual-titles

[6] Microsoft, Use field parameters in Power BI reports: https://learn.microsoft.com/en-us/power-bi/create-reports/power-bi-field-parameters

[7] Microsoft, Drillthrough in Power BI reports: https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-drillthrough

[8] Microsoft, Create and use report templates: https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-templates

[9] GitHub, About large files on GitHub: https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github

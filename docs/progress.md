# Project progress

Last updated: 22 September 2026

## Task status

| Task | Status | Evidence and limitations |
|---|---|---|
| T00 | Pending | External-dataset acceptance and the instructor's AI-assistance conditions have not been confirmed. |
| T02 | Completed (read-only inspection) | The local source was inspected as 1,143 data rows and 11 columns; `ad_id` was unique across all rows, and the source SHA-256 was recorded. |
| T04 | Completed (readiness verification) | The About dialog confirmed Microsoft Power BI Desktop version `2.157.1354.0` 64-bit (August 2026). User screenshots confirmed that the PBIP, project PBIR, and TMDL project-format options are present and enabled. No settings were changed and no restart was required. |
| T05 | Completed | The project was non-destructively relocated to a short Windows-local directory exposed to WSL through the mounted local drive. The original directory is retained as an inactive rollback copy, and Codex was reopened with the selected directory as its working and Git root. |
| T06 | Completed — limited approved scope | Added targeted Git exclusions plus minimal root, data, and progress documentation. The existing repository was used; repository initialization and remote operations were not performed. |
| T07 | Partial — source-only repository published | The reviewed source and documentation were pushed to the existing public GitHub repository on `main`. This differs from the campaign's originally planned private repository. Raw/processed data, PBIX/PBIT files, cache data, and local Power BI settings were excluded. |
| T08 | Completed | Power BI Desktop created the `FacebookAds` PBIP baseline and imported `KAG_conversion_data.csv` through Power Query. The saved project uses PBIR report definitions and a TMDL semantic model. Refresh, save, close, reopen, and the loaded 1,143-row result were verified through user evidence and read-only file inspection. |
| T09 | Completed | Identifier/category columns remain text, count fields use whole numbers, and spend uses a decimal number. All 1,143 rows converted without errors; Desktop loaded and rendered aggregates from the edited model. |
| T18–T22 | Completed for Release A | Eleven explicit DAX measures were added, including additive totals, CTR, CPC, CPM, cost per approved conversion, selected-context spend share, and a filter-aware title. Unfiltered rendered results reconcile to independent source calculations. |
| T23–T25 | Completed for Release A | The 1920×1080 Executive Overview rendered with four slicers, five KPI cards, a spend donut, an approved-conversion bar chart, and a campaign detail table. |
| T26 | Partial | The title and unfiltered visuals rendered correctly. PBIR structure and field bindings passed schema and reference checks, but a live slicer interaction test was not completed before publication preparation. |

T01, T03, T10–T17, and T27–T41 remain incomplete except for the Release A work explicitly recorded above. T07 remains partial because repository visibility differs from its original acceptance condition. T00 remains pending external confirmation.

## GitHub publication

The source-only project is published at `https://github.com/Cheng-Chan/facebook-ads-powerbi` on branch `main`. Anonymous access confirmed that the repository is public. Publication does not resolve instructor acceptance, AI-assistance/disclosure requirements, or dataset redistribution permission. No raw dataset or data-bearing Power BI deliverable was published.

## Release A implementation and validation

Power BI Desktop successfully opened the edited project and rendered the Executive Overview without a reported warning. The visible unfiltered results matched independent calculations from the unchanged local CSV:

| Metric | Verified result |
|---|---:|
| Source rows | 1,143 |
| Total spend | 58,705.23 |
| Total impressions | 213,434,828 |
| Total clicks | 38,165 |
| Total enquiries | 3,264 |
| Approved conversions | 1,079 |
| CTR | 0.02% at the displayed two-decimal precision |
| Cost per approved conversion | 54.41 |

Before the Desktop render test, all report, page, and 13 visual JSON files conformed to their declared Microsoft PBIR schemas. After Desktop loaded and saved the report, it upgraded seven accepted visual definitions from schema `2.9.0` to `2.12.0`; Microsoft currently returns HTTP 404 for that declared `2.12.0` schema URL, so those seven files could not be revalidated online. Their JSON syntax remains valid and Desktop itself rendered and saved them. The unchanged `2.9.0` visual definitions and report/page metadata still pass their published schemas. All 23 visual field references resolve to an existing column or measure; visual identifiers are unique; and all visual bounds fit the page canvas.

The rendered screenshot verified report loading, DAX execution, visual rendering, and overall reconciliation. It did not verify a post-build refresh, combined filter selections, title single/multiple-selection states, clearing filters, a second close/reopen cycle, PBIX export, or screenshot-file delivery. Those checks remain outstanding and must not be inferred from source validation.

## T06 validation

- The raw CSV remained present with SHA-256 `2ee88488b5229562e8814b08e95e09e675aa939f69fc16f124eefe2bfdfa7cf8`.
- `data/raw/KAG_conversion_data.csv` was ignored by the targeted `data/raw/` rule and was neither tracked nor staged.
- `.gitignore`, `README.md`, `data/README.md`, and `docs/progress.md` remained eligible for Git tracking.
- Representative PBIP, PBIR, and TMDL source paths were not excluded.
- Only the four authorized files were created or modified. Nothing was staged, committed, pushed, fetched, or remotely changed.

## T04 Power BI Desktop readiness

Evidence was supplied through user screenshots of the Power BI Desktop About dialog and **Global > Preview features**. The displayed application version agrees with the independently detected Microsoft Store package version `2.157.1354.0`.

| Setting displayed in Power BI Desktop | Final state | Verification and action |
|---|---|---|
| `Power BI Project (.pbip) save option` | Enabled | A checked box was visible in the user screenshot. It was already enabled, so no change was applied. |
| `Store semantic model using TMDL format` | Enabled | A checked box was visible in the user screenshot. It was already enabled, so no change was applied. |
| `Store reports using enhanced metadata format (PBIR)` | Enabled | A checked box was visible in the user screenshot. It was already enabled, so no change was applied. |

The separate `Store PBIX reports using enhanced metadata format (PBIR)` option was visible but disabled. It was intentionally left unchanged because it is outside the approved project-format settings. Since no setting was changed, Power BI Desktop did not require a restart for this task.

At completion of T04, this readiness check did not yet prove that a PBIP could be saved or reopened, which project formats Desktop would actually emit, or whether refresh, DAX execution, report rendering, and visual interactions worked. T08 subsequently verified the baseline, emitted formats, initial refresh, and reopen behavior; the other behaviors remain untested.

## T05 authoritative workspace

The authoritative workspace is now a short Windows-local project directory that is also accessible from WSL through the mounted local drive. A non-destructive copy preserved the complete repository, hidden Git metadata, ignored raw data, and untracked documentation. The former WSL-native directory remains unchanged as an inactive rollback copy and must not receive further project edits.

The destination contains the existing project files plus empty `powerbi/` and `screenshots/` directories. No placeholder, report, or semantic-model files were created.

Validation evidence:

- Source file and directory manifests remained unchanged during copying, showing no concurrent source edit during the operation.
- Every copied file hash and directory entry matched the source before the two approved empty directories were added.
- Windows and WSL both read the same existing README and reported the same raw CSV SHA-256.
- A uniquely named temporary probe was written and read in both directions, then removed.
- A user screenshot confirmed that Power BI Desktop's file dialog could browse to the empty `powerbi/` directory; the dialog was canceled without saving a report.
- The reopened Codex session reported the selected directory as both its physical working directory and Git root.
- Branch, remote configuration, Git configuration, and HEAD were preserved; the Git index remained empty.
- The raw CSV remained ignored, untracked, and unstaged with SHA-256 `2ee88488b5229562e8814b08e95e09e675aa939f69fc16f124eefe2bfdfa7cf8`.

At completion of T05, filesystem access alone did not prove that Power BI could save or reopen a PBIP, emit PBIR and TMDL definitions, refresh data, execute DAX, render visuals, or preserve interactions. T08 subsequently verified the baseline, emitted formats, initial refresh, and reopen behavior; the other behaviors remain untested.

## T08 Desktop-generated baseline and CSV import

Power BI Desktop created the editable project under `powerbi/` rather than through manual construction or renaming. The baseline includes:

- `FacebookAds.pbip` as the project pointer;
- a PBIR report folder with `definition.pbir` version 4.0 and a `definition/` tree; and
- a semantic-model folder using TMDL, including `model.tmdl` and the generated table definition.

The CSV was imported as the `KAG_conversion_data` query in Import mode. The automatic `Changed Type` step was removed so that type decisions remain scoped to T09. Read-only inspection of the saved TMDL confirmed 11 string columns and an M expression containing only the CSV source and promoted-header operations; no `Table.TransformColumnTypes` call was present.

Validation evidence:

- The initial user screenshot showed Desktop's title bar identifying `FacebookAds` as a Power BI Project.
- After loading, a user screenshot showed the query and all 11 fields in the Data pane.
- The user performed the requested refresh, save, close, and reopen sequence without reporting an error.
- A Data view screenshot from the reopened project showed `KAG_conversion_data` with 1,143 rows.
- The raw CSV remained unchanged with SHA-256 `2ee88488b5229562e8814b08e95e09e675aa939f69fc16f124eefe2bfdfa7cf8`; it remained ignored, untracked, and unstaged.
- The Git index remained empty, and no PBIP definition was edited outside Power BI Desktop.

The generated query currently contains a local absolute source path. Portability remains deferred to T12. Column types are intentionally provisional pending T09. No DAX measure, relationship, visual, screenshot deliverable, or interaction test was created under T08.

## Validation boundary

Power Query refresh and PBIP save/reopen were verified under T08. No DAX execution, analytical visual rendering, or interaction tests have occurred.

Future checks, not yet implemented:

- Assign and validate deliberate Power Query and model data types under T09.
- Replace or parameterize the local absolute source path under T12.

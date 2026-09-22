# Facebook Ads Campaign Performance Analysis

This project contains an editable Power BI Project (PBIP) for analysing advertising spend, engagement, and recorded approved conversions across campaigns and audience categories.

## Dashboard

The assignment-ready **Executive Overview** is implemented in PBIR/TMDL source and has rendered successfully in Power BI Desktop. It includes:

- a filter-aware DAX title;
- campaign, age-group, gender, and interest-code slicers;
- five KPI cards for spend, impressions, clicks, approved conversions, and cost per approved conversion;
- campaign spend distribution and approved-conversion comparison charts; and
- a campaign performance table based on explicit measures.

The unfiltered dashboard reconciles to 1,143 source rows: total spend `58,705.23`, impressions `213,434,828`, clicks `38,165`, enquiries `3,264`, and approved conversions `1,079`. Cost per approved conversion is `54.41`.

The project was created and tested with Microsoft Power BI Desktop `2.157.1354.0` 64-bit (August 2026). The report definition uses PBIR and the semantic model uses TMDL.

## Open and refresh

1. Download `KAG_conversion_data.csv` as described in [data/README.md](data/README.md).
2. Open `powerbi/FacebookAds.pbip` in Power BI Desktop.
3. If your checkout is not at `C:\Projects\facebook-ads-powerbi`, update the CSV source path in **Transform data → Data source settings**.
4. Refresh the model and verify the reconciliation totals above.

The current source path is intentionally documented rather than presented as portable. A reusable data-path parameter remains future work.

See the [guided project campaign](Facebook_Ads_PowerBI_Project_Campaign.md) for the backlog, analytical rules, and acceptance criteria.

## Data and permissions

Raw and processed data are intentionally excluded from Git. Local data remains on the developer's machine; ignoring it does not delete it.

The following decisions are still pending:

- instructor acceptance of the external Kaggle dataset;
- instructor requirements for AI assistance and disclosure; and
- permission to redistribute the source dataset.

Until those questions are resolved, this repository must not be treated as approval to publish the raw dataset or a data-bearing Power BI file. This source-only repository excludes the raw CSV, PBIX/PBIT files, and local Power BI cache data.

## Analytical limitations

The source has no dates, revenue, profit, or documented currency. Results describe recorded campaign observations and do not establish causation, profitability, unique-customer counts, or future performance. Interest values remain category codes because no authoritative label mapping was supplied.

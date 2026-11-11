# Merchant Acquisition & Activation Performance Analysis

## Project Overview

This project analyzes merchant acquisition performance across different lead sources using a synthetic dataset of 120 prospective merchants.

The objective is to understand how effectively different acquisition channels generate leads and convert them into acquired merchants.

The analysis was conducted using Microsoft Excel, utilizing PivotTables, Excel formulas, and data visualizations.

> **Disclaimer:** All data used in this project is synthetic and created exclusively for portfolio and analytical demonstration purposes. It does not represent actual company or business records.

## Business Context

Merchant acquisition is an important operational activity for marketplaces and digital platforms.

Businesses can identify and acquire prospective merchants through various channels, such as:

- Social media sellers
- Google Search and top-up websites
- Paid advertising campaigns
- Gaming communities
- Competitor marketplaces

Each acquisition channel may produce different lead volumes and conversion outcomes.

Understanding these differences can help businesses evaluate their acquisition strategy and identify potentially effective channels.

## Project Objectives

1. Analyze monthly lead generation and merchant acquisition trends.
2. Compare lead volume across different acquisition sources.
3. Measure acquisition conversion rates by source.
4. Identify differences in acquisition channel performance.
5. Evaluate an initial hypothesis regarding merchants with previous marketplace experience.

## Dataset Overview

The dataset contains 120 synthetic merchant leads identified between January and June 2026.

| Attribute | Description |
|---|---|
| Lead ID | Unique identifier for each lead |
| Merchant Name | Synthetic merchant name |
| Lead Identified Date | Date the lead was identified |
| Lead Source | Acquisition channel |
| Source Detail | More specific source information |
| City | Merchant location |
| Product Category | Merchant product category |
| Previous Marketplace Experience | Whether the merchant has previous marketplace experience |
| First Contact Date | Date of first contact |
| Contact Status | Contact progress |
| Acquisition Date | Date the merchant was acquired |
| Onboarding Status | Onboarding progress |
| Onboarding Completed Date | Date onboarding was completed |
| Merchant Status | Current merchant status |
| First Transaction Date | Date of the first transaction |
| Activation Status | Whether the merchant has completed a first transaction |

## Analysis & Visualizations

This version focuses on two areas of merchant acquisition performance.

### 1. Monthly Lead Generation vs. Merchant Acquisition

**Business Question:** Are monthly lead volumes translating into successful merchant acquisitions?

This visualization compares:

- Monthly leads identified.
- Monthly merchants acquired.

![Monthly Lead Generation vs. Merchant Acquisition](visualizations/monthly-lead-acquisition.png)

**Key Observations:**

- Lead generation remained consistent at 20 leads per month from January to June.
- Monthly merchant acquisitions ranged from 8 to 10 during January–June.
- Four additional merchants were acquired in July from leads identified in previous months.
- Lead generation and merchant acquisition are measured using different date fields.

**Business Interpretation:**

Consistent lead generation does not necessarily result in acquisitions within the same month. Tracking both lead identification and acquisition dates provides a clearer view of the acquisition process over time.

### 2. Lead Generation vs. Merchant Acquisition by Source

**Business Question:** Which acquisition channels generate the highest number of acquired merchants?

This visualization compares lead volume and acquired merchants across five acquisition sources.

![Lead Generation vs. Merchant Acquisition by Source](visualizations/acquisition-by-source.png)

**Acquisition Performance:**

| Lead Source | Leads Identified | Merchants Acquired | Acquisition Rate |
|---|---:|---:|---:|
| Competitor Marketplace | 20 | 10 | 50.0% |
| Gaming Community | 25 | 10 | 40.0% |
| Google Search | 25 | 13 | 52.0% |
| Paid Advertising | 20 | 10 | 50.0% |
| Social Media | 30 | 14 | 46.7% |
| **Total** | **120** | **57** | **47.5%** |

**Key Observations:**

- Social Media generated the highest lead volume, with 30 leads and 14 acquired merchants.
- Google Search achieved the highest acquisition rate at 52%.
- Competitor Marketplace and Paid Advertising both achieved a 50% acquisition rate.
- Gaming Community recorded the lowest acquisition rate at 40%.

**Hypothesis Evaluation:**

An initial hypothesis suggested that merchants sourced from competitor marketplaces might be easier to acquire because they are already familiar with marketplace workflows.

However, the synthetic dataset shows that Google Search achieved a slightly higher acquisition rate (52%) compared to Competitor Marketplace (50%).

Therefore, the initial hypothesis is not supported by the current dataset.

Further analysis would be required to understand whether previous marketplace experience influences acquisition outcomes.

## Key Metrics

**Total Leads Identified:** 120

**Total Merchants Acquired:** 57

**Overall Acquisition Rate:** 47.5%

Acquisition Rate is calculated using:

`Acquisition Rate = Merchants Acquired / Total Leads Identified × 100%`

## Methodology

The analysis was performed using Microsoft Excel.

1. Organized the source data into an Excel Table.
2. Created helper columns to group lead identification and acquisition dates by month.
3. Built PivotTables to aggregate lead and acquisition counts.
4. Created summary tables for the visualizations.
5. Used combination charts to compare lead volume and merchant acquisition.
6. Calculated acquisition rates for each lead source.

## Tools & Techniques

- Microsoft Excel
- PivotTables
- Excel Tables
- Excel Formulas
- Combo Charts
- Data Aggregation
- Conversion Rate Analysis

## Limitations

- The dataset is synthetic and does not represent actual business performance.
- Findings describe the generated dataset and should not be interpreted as evidence of real-world channel effectiveness.
- Lead generation and merchant acquisition are measured using different date fields.
- The analysis currently focuses on lead generation and merchant acquisition.
- Onboarding completion and first-transaction activation have not yet been analyzed.

## Future Analysis

Potential extensions for this case study include:

- Merchant onboarding completion analysis.
- First-transaction activation analysis.
- Time to first transaction by acquisition source.
- Comparison of acquisition and activation performance across channels.
- Evaluation of the relationship between previous marketplace experience and merchant activation.

These topics are intentionally outside the scope of the current version.

## Project Structure

```text
merchant-acquisition-analysis/
├── README.md
├── data/
│   └── merchant-acquisition-dataset.csv
├── workbook/
│   └── merchant-acquisition-dataset.xlsx
└── visualizations/
    ├── monthly-lead-acquisition.png
    └── acquisition-by-source.png

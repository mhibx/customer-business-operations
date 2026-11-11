# Merchant Acquisition & Activation Performance Analysis

## Project Overview

This project analyzes merchant acquisition performance across different lead sources using a synthetic dataset of 120 prospective merchants.

The analysis focuses on understanding how effectively each acquisition channel generates leads and converts them into acquired merchants.

The project uses Microsoft Excel to organize data, build PivotTables, calculate acquisition metrics, and create visualizations.

> **Note:** All data used in this project is synthetic and created for portfolio and analytical demonstration purposes. It does not represent actual company or business records.

## Business Context

Merchant acquisition is an important part of marketplace and digital platform operations.

Businesses may acquire prospective merchants through multiple channels, including:

- Social media sellers
- Google Search
- Paid advertising
- Gaming communities
- Competitor marketplaces

Each channel may produce different lead volumes and acquisition outcomes.

This analysis aims to provide an initial understanding of channel performance and identify which sources generate the most acquired merchants.

## Project Objectives

1. Analyze monthly lead generation and merchant acquisition trends.
2. Compare lead volume across different acquisition sources.
3. Measure acquisition conversion rates by source.
4. Identify potential differences in acquisition channel performance.

## Dataset Overview

The dataset contains 120 synthetic merchant leads covering January–June 2026.

Key fields include:

| Field | Description |
|---|---|
| Lead ID | Unique identifier for each lead |
| Merchant Name | Synthetic merchant name |
| Lead Identified Date | Date the lead was identified |
| Lead Source | Acquisition channel |
| Source Detail | More specific source information |
| City | Merchant location |
| Product Category | Merchant product category |
| Previous Marketplace Experience | Whether the merchant has prior marketplace experience |
| First Contact Date | Date of first contact |
| Contact Status | Contact progress |
| Acquisition Date | Date the merchant was acquired |
| Onboarding Status | Onboarding progress |
| Onboarding Completed Date | Date onboarding was completed |
| Merchant Status | Current merchant status |
| First Transaction Date | Date of the first transaction |
| Activation Status | Whether the merchant has completed a first transaction |

## Analysis Scope

This version focuses on two visualizations.

### 1. Monthly Lead Generation vs. Merchant Acquisition

**Business question:** Are monthly lead volumes translating into successful merchant acquisitions?

The analysis compares:

- Leads identified by month.
- Merchants acquired by acquisition month.

| Month | Leads Identified | Merchants Acquired |
|---|---:|---:|
| Jan 2026 | 20 | 10 |
| Feb 2026 | 20 | 8 |
| Mar 2026 | 20 | 9 |
| Apr 2026 | 20 | 10 |
| May 2026 | 20 | 8 |
| Jun 2026 | 20 | 8 |
| Jul 2026 | 0 | 4 |

**Key observations:**

- Lead generation remained consistent at 20 leads per month from January to June.
- Merchant acquisitions ranged from 8 to 10 per month during January–June.
- Four additional merchants were acquired in July from leads identified in earlier periods.

The different date fields are used intentionally: lead generation is measured by Lead Identified Date, while acquisition is measured by Acquisition Date.

### 2. Lead Generation vs. Merchant Acquisition by Source

**Business question:** Which acquisition channels generate the highest number of acquired merchants?

| Lead Source | Leads | Acquired | Acquisition Rate |
|---|---:|---:|---:|
| Competitor Marketplace | 20 | 10 | 50.0% |
| Gaming Community | 25 | 10 | 40.0% |
| Google Search | 25 | 13 | 52.0% |
| Paid Advertising | 20 | 10 | 50.0% |
| Social Media | 30 | 14 | 46.7% |
| **Total** | **120** | **57** | **47.5%** |

**Key observations:**

- Social Media generated the highest lead volume, with 30 leads and 14 acquired merchants.
- Google Search achieved the highest acquisition rate at 52%.
- Competitor Marketplace and Paid Advertising both achieved 50%.
- Gaming Community had the lowest acquisition rate at 40%.

Google Search performed slightly better than Competitor Marketplace in acquisition conversion, so the initial hypothesis that competitor marketplace leads would convert more effectively is not supported by this dataset.

## Methodology

The analysis was conducted using Microsoft Excel.

1. Organized the source data into an Excel Table.
2. Created helper fields for monthly lead and acquisition grouping.
3. Built PivotTables to aggregate lead and acquisition counts.
4. Created summary tables for visualization.
5. Used combination charts to compare lead volume and merchant acquisition.
6. Calculated acquisition rate using:

`Acquisition Rate = Acquired Merchants / Total Leads × 100%`

## Tools Used

- Microsoft Excel
- PivotTables
- Combo Charts
- Excel formulas
- CSV dataset

## Limitations

- The dataset is synthetic and does not represent actual business performance.
- The analysis describes the generated dataset and should not be interpreted as evidence of real-world channel effectiveness.
- Acquisition and lead generation are measured using different date fields.
- This version does not yet analyze onboarding completion or first-transaction activation performance.

## Future Analysis

Potential next steps include:

- Merchant onboarding completion analysis.
- First-transaction activation analysis.
- Time to first transaction by acquisition source.
- Comparison of acquisition and activation performance across channels.

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

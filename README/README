# 📱 Mobile Phone Sales Analytics
### A Data Analytics Project — Python · SQL · Power BI

---

> **This is a guided project brief.** Every phase includes a business context, questions to guide your thinking, and step-by-step instructions on how to build it. Read each section completely before writing any code. This is how real-world analytics systems are built.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Phase 1 — Data Discovery & Business Understanding](#phase-1--data-discovery--business-understanding)
- [Phase 2 — Data Cleaning & Preparation](#phase-2--data-cleaning--preparation)
- [Phase 3 — Data Modelling & Metric Computation](#phase-3--data-modelling--metric-computation)
- [Phase 4 — Dashboard Design & Visualisation](#phase-4--dashboard-design--visualisation)
- [Phase 5 — Documentation & Presentation](#phase-5--documentation--presentation)
- [Timeline](#timeline)
- [Dashboard Colour Reference](#dashboard-colour-reference)
- [A Final Note](#a-final-note)

---

## Project Overview

Every mobile phone retailer — from a single-store operator on Lagos Island to a national distributor supplying chains across West Africa — faces the same fundamental commercial question: **which products are driving our revenue, which markets are growing, and where are we losing ground?**

Sales data is one of the richest sources of business intelligence available to any organisation. It tells you which brands are performing, which price segments customers are gravitating toward, which payment methods they prefer, and how revenue is trending over time. Yet in most retail businesses, this data sits in point-of-sale systems or unstructured spreadsheets and is never properly interrogated. Commercial decisions get made on instinct rather than evidence.

In larger retail and distribution organisations, commercial analytics teams exist specifically to turn raw transaction and product data into strategic decisions. They answer questions like:

- Which brands and models are generating the most revenue this quarter?
- Is the business growing month-on-month, and which product tier is driving that growth?
- What is the average selling price across the portfolio, and is it moving up or down?
- Which customer segments — by age, gender, or geography — buy the most, and what do they buy?
- Where is revenue concentrated, and does that concentration represent an opportunity or a risk?

This project places you in the role of a **Commercial Data Analyst** at a mobile phone retail company. You have been handed a dataset of sales transactions and product records and asked to build an analytics pipeline that produces a management dashboard. That pipeline — from raw data to a clean, decision-ready report — is exactly what you will build here.

By the end of this project, you will have built a working solution that mirrors how commercial analytics teams in retail and consumer electronics businesses operate. Every phase maps to a real workflow that exists inside a properly run retail organisation.

**Dataset:** Mobile Sales Dataset — Kaggle
👉 https://www.kaggle.com/datasets/waqi786/mobile-sales-dataset

---

## Dataset

**Mobile Sales Dataset**
📥 [Download from Kaggle](https://www.kaggle.com/datasets/waqi786/mobile-sales-dataset)

> You will need a free Kaggle account to download the file. Once downloaded, place the raw file in `data/raw/` and do not modify it under any circumstances. This is your source of truth — treat it exactly as you would treat a live export from a point-of-sale or ERP system.

The dataset contains information about mobile phone sales transactions including brand, model, price, units sold, customer demographics, payment method, and date. Your job is to build a pipeline that transforms this raw data into a commercial performance dashboard.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| **Python** (`pandas`, `sqlite3`) | Data ingestion, cleaning, transformation, feature engineering |
| **SQL** (SQLite) | Data storage, schema design, aggregation queries, metric computation |
| **Power BI** | Sales performance dashboard — design, layout, and visualisation |

---

## Project Structure

```
mobile-sales-analytics/
├── data/
│   ├── raw/                            ← Original Kaggle download. Never modify this.
│   └── processed/                      ← Cleaned outputs from Python scripts
├── scripts/
│   ├── clean_data.py                   ← Phase 2: all cleaning and transformation logic
│   ├── load_to_sql.py                  ← Phase 3: database creation and data loading
│   └── queries.sql                     ← Phase 3: all metric queries
├── exports/                            ← CSVs exported from SQL, used as Power BI inputs
├── dashboard/
│   └── mobile_sales_dashboard.pbix     ← Phase 4: full Power BI report (2 pages + overlay)
├── findings_summary.md                 ← Phase 5: key findings and business recommendation
└── README.md
```

> Build this folder structure before writing a single line of code. Folder discipline is a professional habit — it also makes your project reproducible by anyone who picks it up after you.

---

## Phase 1 — Data Discovery & Business Understanding
**Duration: Week 1 | Tool: Excel or any CSV viewer**

### Business Context

Before any analyst opens a code editor, they must understand the data they are working with. In commercial environments, this phase is called *data discovery* or *data profiling*. It involves sitting with the raw data and asking hard questions — what does each field actually represent, how clean is it, and is it reliable enough to build business decisions on?

This step is not glamorous. It has no code, no charts, and nothing to show a manager. But it is the single most important phase of any analytics project. Analysts who skip it routinely build pipelines that produce wrong answers — confidently and at scale.

In this project, the dataset is your source system. Treat it as if it came from a live point-of-sale terminal in a retail store. You did not design the system, you cannot change how it captures data, and you must work with whatever is there.

### Questions to Guide Your Thinking

Open the dataset in Excel first — not Python. Read it before you process it.

- What does each row represent? Is it one row per transaction, per product, per day, or per customer? This is the most fundamental question and everything else depends on getting it right.
- What is the date range covered? Is the data continuous — every day or month accounted for — or are there gaps? What might explain those gaps in a real retail context?
- What fields does the dataset contain? Before looking at values, group the columns mentally: which ones describe the product, which describe the customer, which describe the transaction itself, and which describe time?
- How is revenue captured? Is there a direct revenue or sales amount column, or do you need to derive it from price and quantity? What is the difference between those two approaches and when does it matter?
- Look at the brand and model columns carefully. Are values consistent? Is "Samsung" always spelled the same way, or do variations exist? What happens to your brand-level revenue analysis if inconsistencies are not resolved before aggregation?
- Look at the date column. Is it stored as a proper date, or as a string? Try sorting by date in Excel — does it sort chronologically or alphabetically? The answer tells you everything about how it is stored.
- Are there missing values in fields you will need for analysis? Are they scattered randomly or concentrated in specific columns? What business explanation might account for systematic nulls in a field?
- Who will use this dashboard? A Sales Director wants headline growth numbers. A Commercial Manager wants brand and model breakdowns. A Marketing team wants customer segment insights. How does the intended audience shape what you build?

### How to Build This Phase

Open the raw CSV in Excel. Do not sort, filter, or edit anything. You are observing, not intervening.

Scroll through every column. For each one, write a plain-English description in a separate notes document — not what the column name says, but what the actual values tell you it means. A column named `price` could be unit price, total price, selling price, or recommended retail price. Only the values will reveal which.

Pay close attention to:
- The brand field — count unique values and look for near-duplicates or inconsistent capitalisation
- The date field — confirm the format and check the full date range
- Any numeric field that should never be zero or negative — are there violations?
- Whether a revenue column already exists or must be calculated

Write a **Data Overview document** — one page maximum — that covers: what the dataset contains, the time period it spans, the five most important columns for commercial analysis, and any data quality issues you have already spotted. This document is the foundation for every decision you make in the phases that follow.

### ✅ Milestone

You can explain the dataset clearly without referring to notes — what it contains, what each key column represents, how revenue should be calculated, and what data quality issues you expect to encounter. Your written Data Overview document exists and is specific, not vague.

---

## Phase 2 — Data Cleaning & Preparation
**Duration: Week 2 | Tool: Python**

### Business Context

Raw transactional data from any source system is almost never analysis-ready. In retail environments this is especially true — point-of-sale systems are optimised for capturing transactions quickly, not for producing clean analytical outputs. Values are inconsistent. Categories are misspelled. Date fields are formatted incorrectly. Numeric fields store values as text.

This phase — called *data wrangling* or *ETL preparation* — is where you take responsibility for the quality of every number that will eventually appear on a management dashboard. In production environments this runs automatically on a schedule. You are building it manually so you understand every transformation being made and why.

A critical professional principle applies here: **every transformation is a business decision, and every business decision must be documented.** If you drop rows, you must explain what data is now excluded. If you fill a null with a default, you must justify that assumption. If you standardise a category name, you must explain the rule you applied. Undocumented transformations are the single most common cause of analytical errors that damage trust in data teams.

### Questions to Guide Your Thinking

- Which columns are genuinely necessary for a commercial sales dashboard? Which can be dropped without affecting any output?
- Where there are missing values in columns you need, what is the right treatment for each? Dropping removes that transaction entirely. Filling with a default makes an assumption. Flagging as "Unknown" preserves the row while being transparent. Each choice has consequences — what are they?
- The brand and model columns likely have inconsistent capitalisation or spacing. What Python method handles this, and why must it be applied before any grouping or aggregation?
- If a revenue column does not exist in the raw data, you must calculate it. Write the formula in plain English before writing it in code. Is it simply price multiplied by quantity, or are there other factors?
- How will you define price tiers? Budget, Mid-Range, Premium, and Flagship are standard retail categories — but the thresholds are a business decision, not a technical one. What does the distribution of prices in this dataset suggest about where those boundaries should sit?
- After cleaning, how will you verify the output is correct? What specific checks will confirm the cleaning worked and introduced no new errors?

### How to Build This Phase

Write a **Python script** — not a Jupyter notebook. Notebooks are the right tool for exploration. Scripts are what get deployed in production. Structure your script with clearly labelled sections:

```python
# ── 1. IMPORTS ──────────────────────────────────────────────────
# ── 2. CONFIGURATION (column lists, mappings, thresholds) ───────
# ── 3. LOAD RAW DATA ────────────────────────────────────────────
# ── 4. INITIAL PROFILING ────────────────────────────────────────
# ── 5. SELECT COLUMNS ───────────────────────────────────────────
# ── 6. FIX DATA TYPES ───────────────────────────────────────────
# ── 7. STANDARDISE CATEGORIES ───────────────────────────────────
# ── 8. HANDLE NULLS ─────────────────────────────────────────────
# ── 9. CREATE DERIVED COLUMNS ───────────────────────────────────
# ── 10. VALIDATE & EXPORT ───────────────────────────────────────
```

Load the CSV with `pd.read_csv()`. Before doing anything else, run `.info()`, `.describe()`, and `.value_counts()` on every categorical column. Print the outputs and read them. This is your data quality baseline.

Define a `COLUMNS_TO_KEEP` list at the top of the configuration section and filter down to those columns early. For all categorical columns, apply `.str.strip().str.title()` before any aggregation — a single inconsistent value silently fragments your brand totals.

Create the following derived columns. Write the business rule as a code comment before writing each transformation:

- `revenue` — total transaction value. Derive from price × quantity if not already present.
- `month_year` — formatted as "Jan 2023". Used for trend chart x-axis labels.
- `month_num` — numeric month. Used for correct chronological sorting.
- `year` — calendar year. Used for year-over-year analysis.
- `price_tier` — Budget / Mid-Range / Premium / Flagship. Define thresholds based on the price distribution you observed in Phase 1. Document your thresholds and reasoning as a comment.

```python
# PRICE TIER THRESHOLDS
# Based on observed price distribution in this dataset:
# Review the quartiles from .describe() and set boundaries that create
# meaningful commercial segments — not arbitrary equal splits.
# Budget:    prices below [your threshold]
# Mid-Range: [threshold] to [threshold]
# Premium:   [threshold] to [threshold]
# Flagship:  above [threshold]
# Rationale: [write your reasoning here before coding it]
```

Export to `data/processed/clean_sales.csv`. Never overwrite the raw file.

Add a comment block at the very top of the script: what it does, what input it expects, what output it produces, and the date it was last modified.

### ✅ Milestone

A clean CSV exists in `data/processed/` with correct data types, no nulls in critical columns, consistent category capitalisation, and all four derived columns present and correctly populated. You can explain every transformation in the script — including the business justification — without referring to notes.

---

## Phase 3 — Data Modelling & Metric Computation
**Duration: Week 3 | Tool: SQL (SQLite)**

### Business Context

Clean data needs a home with structure. In real organisations, transformed data lives in a database — not in flat files. A database enforces schema, makes data queryable, and creates a single source of truth. Multiple systems and users can read from it simultaneously. It is also where the definitions of your metrics become concrete and consistent.

This phase introduces one of the most important concepts in analytics engineering: the difference between *storing data* and *modelling data*. Storing means putting rows in a table. Modelling means designing how those rows are structured and typed so the right questions can be answered quickly, correctly, and consistently across the organisation.

Metrics are not just numbers — they are **business definitions encoded in SQL**. Once your query answers a question one way, that answer becomes the definition. If a Sales Director and a Finance Director calculate "Total Revenue" differently and arrive at different numbers, the business has a credibility problem. Your SQL is where that problem gets permanently solved.

### Questions to Guide Your Thinking

- What should your schema look like? Is one table sufficient, or would splitting into a transactions table and a products lookup table make the structure cleaner and more queryable?
- How do you define total revenue? Write the definition in plain English before writing any SQL.
- "Which brand is performing best?" — does best mean highest total revenue, highest units sold, or highest revenue per unit sold? These are three different queries that can produce three different answers. How do you handle that ambiguity in your documentation?
- Month-on-month growth is a standard commercial metric. What SQL logic produces it, and what does a negative result mean in a retail context?
- Average Selling Price (ASP) is one of the most watched metrics in electronics retail. How would you calculate it portfolio-wide, and then by brand? What does a declining ASP tell a commercial team?
- How should you name and organise your export files so that the `exports/` folder is self-explanatory to someone who has never seen the project?

### How to Build This Phase

Use Python's built-in `sqlite3` library. Write `load_to_sql.py` to create the database, define the schema explicitly with column names and types, and load the cleaned CSV using `.to_sql()`. Run this script **once**. Loading and querying are separate operations — never combine them.

Write `queries.sql` with clearly labelled, individually named queries. Every query must have a comment block above it: the business question it answers, the output columns it returns, and any assumptions in the calculation.

Build queries to answer these business questions — you define the exact calculation and document it:

- What is the total revenue, total units sold, and average selling price across the full dataset?
- Which brands generate the most revenue? Which generate the most units? Does the ranking change between the two, and what does that difference tell you?
- Which models are the top 10 by revenue? By units? Are the same models in both lists?
- How does monthly revenue trend across the full date range?
- How does revenue break down by price tier? What percentage does each tier represent?
- Which payment methods are most commonly used, and does the preference differ by price tier?
- Which customer segment by age group or gender generates the most revenue?
- What is the average selling price by brand?

Name your exports clearly and consistently:

```
exports/
├── metric_total_summary.csv
├── metric_revenue_by_brand.csv
├── metric_top10_by_revenue.csv
├── metric_top10_by_units.csv
├── metric_monthly_trend.csv
├── metric_revenue_by_price_tier.csv
├── metric_payment_method.csv
├── metric_customer_segment.csv
└── metric_asp_by_brand.csv
```

### ✅ Milestone

All queries execute without error and return logically sound results. At least two metrics have been manually verified against the raw CSV in Excel. `queries.sql` is clean, fully commented, and organised. The `exports/` folder is populated with correctly named files.

---

## Phase 4 — Dashboard Design & Visualisation
**Duration: Week 4–5 | Tool: Power BI**

### Business Context

The dashboard is where everything you have built becomes visible to the people who make decisions. But a dashboard is not a data dump — it is a **communication product**. Every visual, every colour, every label, and every layout decision is a communication choice. Information that is hard to find or visually overwhelming does not get used, no matter how technically correct it is.

This dashboard has two pages and two audiences:

- **Home Page:** For the Commercial Director and Sales Manager. Headline KPIs, trends, brand and tier performance. Answers: *"How are we performing and are we growing?"*
- **Table View:** For the Analyst and Commercial Manager. Full model-level detail, sortable, filterable. Answers: *"Which specific products and segments do I need to look at more closely?"*

### Canvas Setup

Go to **View → Page Size → Custom**. Set:
- Width: **1280**
- Height: **720**

This fits a standard corporate laptop (1366×768) without requiring the user to zoom out. Set the view to **Fit to Page** in Power BI Service — it will scale cleanly to any screen size.

### Sidebar (Both Pages)

Width: 58 | Background: `#B00600` | Position: left edge

The sidebar contains navigation and global actions only. Data filters stay on the canvas.

| Element | Position | Action |
|---------|----------|--------|
| SUMMIT BANK logo text | Top, vertical | Static label |
| Home icon | y: 80 | Bookmark → Home page |
| Table icon | y: 130 | Bookmark → Table page |
| Divider line | y: 185 | Rectangle, 1px, `rgba(198,177,125,0.25)` |
| ✦ AI button | y: 195 | Bookmark → AI Overlay |
| Settings icon | y: 260 | Optional |
| User avatar | Bottom | Static initials circle |

### Page 1 — Home Dashboard

**Header (y: 14, height: 28)**

| Element | Width | x | Content |
|---------|-------|---|---------|
| Dashboard title | 450 | 72 | "Mobile Sales Dashboard" — white, 12pt bold |
| Date subtitle | 250 | 72 | "As at [Month Year]" — muted, 9pt |
| Refresh tag | 110 | 960 | "● Live · Last refresh [time]" — teal pill |
| Logo pill | 90 | 1078 | "SUMMIT BANK" — red background, gold text |

**KPI Row 1 — Executive Overview**

| Property | Value |
|----------|-------|
| y position | 66 |
| Height | 58 |
| Card width | 189 |
| Gap between cards | 6 |
| Starting x (after sidebar) | 72 |

| Card | Measure | Top Border |
|------|---------|-----------|
| Total Revenue | SUM(revenue) | `#B00600` |
| Total Units Sold | SUM(units_sold) | `#B00600` |
| Number of Brands | DISTINCTCOUNT(brand) | `#B00600` |
| Number of Models | DISTINCTCOUNT(model) | `#B00600` |
| Best Selling Brand | TOPN brand by revenue | `#C6B17D` |
| Avg Selling Price | [Total Revenue] / [Total Units] | `#00A9A5` |

**Divider line:** y: 130, height: 1, width: 1192, x: 72, colour: `#E8EAED`

**KPI Row 2 — Movement & Growth**

| Property | Value |
|----------|-------|
| y position | 150 |
| Height | 58 |
| Card width | 189 (same as Row 1) |

| Card | Measure | Conditional Colour |
|------|---------|-------------------|
| MoM Revenue (₦) | Current minus prior month | Positive: `#00A9A5` / Negative: `#D64040` |
| MoM Revenue (%) | % movement | Same rule |
| Top Growth Brand | Highest MoM brand | Gold text `#9A7D3A` |
| Biggest Decline | Lowest MoM brand | Red text `#D64040` |
| Premium Tier Share | Premium + Flagship % of revenue | Teal text |
| Budget Tier Share | Budget % of revenue | Neutral |

**Left Panel — Slicers**

| Element | Width | Height | x | y |
|---------|-------|--------|---|---|
| Slicer container | 120 | 126 | 72 | 224 |
| Brand slicer | 108 | 56 | 78 | 232 |
| Price tier slicer | 108 | 56 | 78 | 294 |

Slicer tile style. Selected: `#B00600` fill, white text. Unselected: `#F4F5F7` fill, `#8A9BB0` text.

**Line Chart — Monthly Revenue Trend**

| Property | Value |
|----------|-------|
| Width | 870 |
| Height | 156 |
| x | 200 |
| y | 224 |

- X-axis: `month_year` field, sorted by `month_num`
- Primary line: Total Revenue — `#B00600`, 2.5px, smooth
- Secondary line: Units Sold on secondary axis — `#C6B17D`, 1.5px, dashed
- Data labels: last point only
- Grid lines: off
- Title: "Monthly Revenue Trend" — white, 10pt bold, left-aligned

**Donut Chart — Revenue by Price Tier**

| Property | Value |
|----------|-------|
| Width | 148 |
| Height | 156 |
| x | 1078 |
| y | 224 |

Segments: Budget `#C6B17D` · Mid-Range `#00A9A5` · Premium `#B00600` · Flagship `#424B54`

Centre label: total revenue value. Two stat cards below — Premium % and Budget %.

**Combo Chart — Top 10 Brands**

| Property | Value |
|----------|-------|
| Width | 1036 |
| Height | 106 |
| x | 200 |
| y | 388 |

- Bars: Revenue per brand — `#B00600`, sorted descending
- Line overlay: MoM change % — `#00A9A5`
- Constant line at 0% for MoM axis
- No grid lines

**Clustered Bar Chart — Revenue by Brand & Price Tier (Full Width Bottom)**

| Property | Value |
|----------|-------|
| Width | 1192 |
| Height | 190 |
| x | 72 |
| y | 502 |

Each brand as a cluster, one bar per price tier. Corporate colour `#B00600`, individual colour `#C6B17D`. Sorted by total brand revenue descending.

---

### Page 2 — Table View

**Summary Strip (y: 66, height: 48)**

Four cards across full width: Total Revenue · Total Units · Avg Selling Price · MoM Change %. Same styling as homepage KPI cards.

**Filter Row (y: 122, height: 28)**

Chip-style filters: All Brands / Top 10 / Bottom 10 · All Tiers / Budget / Mid-Range / Premium / Flagship · Search box right-aligned.

**Table Visual**

| Property | Value |
|----------|-------|
| Width | 1192 |
| x | 72 |
| y | 158 |
| Height | 490 |

**Exact columns in this order:**

| Column | Source | Format |
|--------|--------|--------|
| Rank | RANKX measure | Number — medal icons top 3 |
| Brand & Model | Concatenated field | Bold, 9pt |
| Price Tier | price_tier column | Coloured pill per tier |
| Units Sold | SUM(units_sold) | Number, thousands separator |
| Total Revenue | SUM(revenue) | Currency ₦, 2 decimals |
| Avg Selling Price | Revenue ÷ Units | Currency ₦ |
| Revenue Bar | Data bar — revenue | `#B00600` fill, show value beside bar |
| MoM Change % | MoM measure | Conditional font colour |
| Payment Method | Most common per model | Text |
| Status | Status DAX measure | Coloured pill |

**Table Formatting:**

- Header: background `#424B54`, text `#FFFFFF`, bold, 9pt, uppercase
- Alternating rows: `#FFFFFF` and `#FAFBFC`
- Row height: 36
- Font: Segoe UI, 9pt, `#424B54`
- Hover row: `#FEF5F5`
- Column borders: 1px `#F0F2F4`
- No outer table border — let the container rectangle frame it

**DAX Measures for the Table:**

```
Rank =
RANKX(ALL(Sales[Model]), [Total Revenue],, DESC, Dense)

MoM Revenue Change % =
VAR CurrentMonth = CALCULATE([Total Revenue], LASTDATE(Sales[Date]))
VAR PrevMonth = CALCULATE([Total Revenue], PREVIOUSMONTH(Sales[Date]))
RETURN DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0)

Product Status =
IF([MoM Revenue Change %] > 0.02, "Growing",
  IF([MoM Revenue Change %] < -0.05, "Declining", "Watch"))

Avg Selling Price =
DIVIDE([Total Revenue], [Total Units Sold], 0)
```

**Status conditional formatting:**

- Growing → background `#EAF7F7`, text `#00A9A5`
- Watch → background `#FEF9EC`, text `#E8A020`
- Declining → background `#FEF0F0`, text `#D64040`

**Price Tier pill colours:**

- Budget → background `#FBF6EC`, text `#9A7D3A`
- Mid-Range → background `#EAF7F7`, text `#00A9A5`
- Premium → background `#FEF0F0`, text `#B00600`
- Flagship → background `#ECEEF0`, text `#424B54`

**Table Footer:**

Rectangle below table — `#F9F9FB` fill, `#E8EAED` top border, height 32. Record count card left-aligned. Export to Excel button right-aligned.

---

### AI Summary Overlay

Create a bookmark page called `AI_Overlay`. Triggered from the ✦ AI button in the sidebar.

**Structure:**
- Full-canvas dimming rectangle: `#424B54`, 85% opacity
- White panel: 340px wide, right-aligned, 10px border radius
- Red header: `#B00600` — AI badge + "Sales Performance — Executive Summary" + close ✕ button
- Body: three metric mini-cards + three text sections + three flag boxes
- Footer: timestamp + Export PDF button

**AI Summary Text to Paste into Smart Narrative:**

---

**Portfolio Health**

> The business recorded total revenue of **[Total Revenue]** across **[Total Units Sold]** units sold as at **[Latest Month]**, representing a month-on-month movement of **[MoM Revenue Value]** (**[MoM Revenue %]**) compared to **[Previous Month]**. The portfolio covers **[Number of Brands]** brands and **[Number of Models]** models, with an average selling price of **[Avg Selling Price]** across all transactions.

---

**Brand & Tier Performance**

> **[Best Selling Brand]** leads the portfolio by revenue, contributing **[Best Brand Revenue %]** of total sales. The premium and flagship tiers combined account for **[Premium Tier Share]** of total revenue, while the budget tier represents **[Budget Tier Share]**. **[Top Growth Brand]** recorded the strongest month-on-month growth at **[Top Growth Brand MoM %]**. **[Biggest Decline Brand]** recorded the steepest revenue contraction at **[Biggest Decline MoM %]** and warrants a commercial review.

---

**Customer & Payment Insights**

> The **[Top Customer Segment]** customer segment generates the highest revenue contribution at **[Top Segment Revenue %]** of total sales. **[Top Payment Method]** is the most preferred payment method, accounting for **[Top Payment Method %]** of transactions. Payment preferences show variation by price tier — customers purchasing flagship devices show a higher tendency toward **[Flagship Payment Method]**.

---

**Risk Flag**

> Revenue concentration in the top three brands represents **[Top 3 Brand Concentration %]** of total portfolio revenue. A decline in any one of these brands would have a material impact on overall performance. The commercial team should monitor brand-level trends closely and ensure no single brand represents an unmanaged concentration risk.

---

Every item in square brackets is a dynamic value — click **+ Value** in the Smart Narrative toolbar and select the corresponding measure. After pasting, format section titles in bold, key values in red (`#B00600`), and positive/negative movements in teal/red respectively using the format toolbar.

**Connecting the Overlay:**

1. Build the overlay page content
2. Create a bookmark called `AI_Summary_Open` with the overlay page active
3. Create a bookmark called `AI_Summary_Close` with the Home page active
4. Assign `AI_Summary_Open` to the ✦ AI sidebar button via Format → Action → Bookmark
5. Assign `AI_Summary_Close` to the ✕ close button on the overlay panel

### ✅ Milestone

A complete `.pbix` with two navigable pages and a functional AI overlay. All KPI cards are populated from DAX measures. All charts use correct fields. The table has conditional formatting on Status, MoM %, and Price Tier columns. The sidebar navigates correctly. Every number has a unit label. No visual floats outside its container rectangle.

---

## Phase 5 — Documentation & Presentation
**Duration: Week 6**

### Business Context

No analytics project is complete until it is documented and communicated. A pipeline that only the person who built it can maintain is a liability. A dashboard that requires a 10-minute explanation before the viewer understands it has failed its primary purpose.

Commercial stakeholders are not interested in how the pipeline was built. They want to know what the data says, why it matters, and what they should do about it. The ability to translate technical work into a clear business narrative is what separates an analyst who gets consulted from one who only gets commissioned.

### Questions to Guide Your Thinking

- If you handed this project folder to a colleague with no prior context, could they run the pipeline from scratch using only the README? What would break first?
- What are your two or three most significant findings? Not observations — findings. A finding has a subject, a fact, a context, and an implication.
- If the Commercial Director asked "what is the single most important thing this data is telling us?", what would your answer be in one sentence?
- What are the limitations of this dataset and analysis? What additional data would make it more accurate or more useful?

### How to Build This Phase

Write `findings_summary.md` with exactly three sections:

**1. What Was Built**
One paragraph describing the solution — data source, tools used, and what the output is. Written for a senior stakeholder, not a developer.

**2. Key Findings**
Two or three specific, evidence-backed findings structured as: observation → magnitude → business implication → suggested action.

Example structure:
> *"Samsung generates 38% of total revenue but only 22% of units sold, indicating a premium price position. This concentration means a single brand relationship carries significant portfolio risk — the commercial team should ensure contract terms and supply agreements with Samsung are reviewed before each quarter."*

**3. Recommendation**
One clear, specific, actionable recommendation. Not five suggestions — one recommendation you would confidently present to a Sales Director.

Clean your scripts. Remove all exploratory print statements and dead code. Add comments to every logical block. Update this README to reflect your actual implementation. Prepare a **15-minute walkthrough** in this order:

1. Business problem
2. Data and approach
3. Key findings
4. Dashboard demo — both pages and AI overlay
5. Limitations and next steps

Practice it once. The technical sections should require no notes.

### ✅ Milestone

Project folder is clean and reproducible. `findings_summary.md` reads like a business document. README reflects the actual implementation. You can present in 15 minutes without hesitation, and a colleague could reproduce your pipeline from the repository alone.

---

## Timeline

| Phase | Focus | Duration | Tool |
|-------|-------|----------|------|
| 1 | Data discovery & business understanding | Week 1 | Excel |
| 2 | Data cleaning & preparation | Week 2 | Python |
| 3 | Data modelling & metric computation | Week 3 | SQL |
| 4 | Dashboard design & visualisation | Week 4–5 | Power BI |
| 5 | Documentation & presentation | Week 6 | — |

---

## Dashboard Colour Reference

| Element | Hex | Usage |
|---------|-----|-------|
| Primary Red | `#B00600` | Main bars, KPI borders, sidebar, headers |
| Champagne Gold | `#C6B17D` | Secondary accents, second data series |
| Dark Slate | `#424B54` | Table header, sidebar, body text |
| Teal | `#00A9A5` | Growth indicators, positive MoM values |
| Sky Blue | `#30BCED` | Optional third series |
| Page Background | `#F4F5F7` | Canvas base |
| Card Background | `#FFFFFF` | All visual containers |
| Surface | `#FAFBFC` | Alternating rows, footers, strip backgrounds |
| Muted Text | `#8A9BB0` | Labels, subtitles, axis text |
| Border | `#E8EAED` | All dividers and container outlines |

---

## A Final Note

Real-world analytics systems are not built by people who know the most Python or write the most elegant SQL. They are built by people who ask the right questions before writing any code, who document every decision they make, and who communicate their findings in a way that drives action rather than generating more questions.

At every phase in this project, resist the instinct to move fast. Read the section. Think through the questions. Understand what you are building and why — before you build it. The code is the easy part. The thinking is the job.

---

*Project guided by [Your Name] · April 2026*

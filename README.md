# 📦 Predictive Demand Planning and Procurement Execution Analysis

### From inventory reporting to proactive replenishment decisions.

A Power BI supply chain analytics solution designed to separate **demand planning** from **day-to-day replenishment decisions**.

The project transforms retail inventory and demand data into a decision-support application that helps planners understand demand and inventory behavior while giving buyers a focused view of what needs to be reordered and how much to order.

---

## 🎯 The Business Problem

Supply chain teams often use the same reporting interface for two fundamentally different activities:

- Long-term demand planning
- Daily procurement and replenishment

Combining these workflows can create what I call a **"Dashboard Identity Crisis"** — too much information for planners, insufficient focus for buyers, and unnecessary cognitive load for operational teams.

This can contribute to:

- Delayed purchasing decisions
- Stockout risk
- Excess inventory
- Tied-up working capital
- Manual procurement calculations
- Difficulty identifying priority SKUs

The goal of this project was therefore not simply to build another dashboard.

It was to design a workflow that answers three increasingly important questions:

> **What is happening? → What is likely to happen? → What should we do next?**

---

# 💡 The Solution

I designed a **dual-module Power BI application** that separates strategic demand analysis from operational replenishment.

```text
                    SUPPLY CHAIN ANALYTICS
                            │
             ┌──────────────┴──────────────┐
             │                             │
       DEMAND PLANNING               REPLENISHMENT
             │                             │
      Understand demand               Take action
             │                             │
   Forecast • ABC • Trends       ROP • Safety Stock
                                 Suggested Order Qty
             │                             │
             └──────────────┬──────────────┘
                            ↓
                 BETTER INVENTORY DECISIONS
```

### Module 1 — Demand Planning

Focused on understanding demand behavior, inventory coverage, product priorities, and forecast performance.

### Module 2 — Replenishment Console

Focused on converting inventory conditions into actionable procurement decisions.

---

# 📊 Demand Planning

![Demand Analysis Overview](assets/demand-analysis-overview.png)

The Demand Planning module provides a focused view of:

- Current inventory
- Average daily sales
- Days of supply
- Forecast performance
- Sales and inventory trends
- Regional inventory coverage
- Forecast variance
- SKU-level demand classification

### Dynamic ABC Analysis

Products are dynamically classified according to their cumulative revenue contribution.

This helps prioritize high-value products and focus inventory management efforts where they have the greatest financial impact.

### Demand Forecasting

A lightweight forecasting approach provides a forward-looking demand signal while maintaining visibility into forecast variance.

### Forecast Guardrails

The analysis highlights deviations between forecasted and actual demand, helping identify products that may require additional attention.

### Inventory Coverage

Days of Supply provides visibility into how long current inventory can support expected demand.

---

# 🔄 Replenishment Console

![Replenishment Console](assets/replenishment-console.png)

The Replenishment Console translates inventory analysis into procurement actions.

### Key Decision Metrics

- Total Inventory Value
- SKUs to Reorder
- Critical SKUs
- Suggested Order Capital

### Reorder Point

The model calculates a reorder threshold based on expected demand during lead time and safety stock:

> **ROP = Demand During Lead Time + Safety Stock**

### Suggested Order Quantity

The model compares the current inventory position against the replenishment requirement and generates a suggested order quantity.

This provides buyers with an action-oriented view instead of requiring them to manually calculate replenishment quantities.

---

# 🧠 Data Model

![Power BI Data Model](assets/data-model.png)

The solution uses a structured analytical model connecting key retail and inventory entities.

### Core model components

| Component | Purpose |
|---|---|
| `dim_Product` | Product attributes and classification |
| `dim_Store` | Store and regional analysis |
| `dim_Calendar` | Time intelligence |
| Sales / Inventory fact data | Historical operational activity |
| Measures | Centralized analytical calculations |

The model was designed to support consistent filtering, reusable measures, and reliable analytical calculations across the application.

---

# ⚙️ Technical Implementation

## Power BI

Used as the primary analytical and visualization platform for the complete solution.

## DAX

Developed analytical logic for:

- Demand calculations
- Average daily sales
- Inventory metrics
- Forecasting
- ABC classification
- Reorder Point calculations
- Suggested Order Quantity
- Days of Supply
- Variance analysis

Key DAX techniques included:

`SWITCH(TRUE())` · `DATEADD()` · `COUNTROWS()`

## Power Query

Used for:

- Data cleaning
- Transformation
- Data preparation
- Handling inconsistent source values
- Preparing analytical tables

## Data Modeling

Designed relationships between dimensions and fact data to provide consistent filtering and reusable analytical logic.

---

# 🛡️ Data Quality & Reliability

Analytical models are only useful when the underlying calculations can be trusted.

The solution includes safeguards for problematic source values such as:

- Blank revenue
- Null values
- Negative revenue
- Missing demand
- Zero-demand scenarios

These safeguards help prevent misleading KPIs and calculation errors from flowing into decision-making.

---

# 📈 Business Value

The project shifts the workflow from:

### Reactive Reporting

> **"What happened?"**

to:

### Proactive Decision Support

> **"What should we do next?"**

The solution helps:

- Reduce manual purchasing guesswork
- Identify critical inventory risks
- Prioritize high-value SKUs
- Improve visibility into inventory coverage
- Balance stockout risk against excess inventory
- Support more disciplined procurement decisions
- Reduce cognitive load by separating planning from execution

---

# 🔍 Key Takeaway

The core idea behind this project is simple:

> **Good analytics should not only explain the business. It should help the business decide what to do next.**

The project demonstrates how Power BI can move beyond descriptive reporting and become an **operational decision-support tool**.

---

# 📁 Project Files

### Power BI Application

The complete Power BI project is available here:

**[Open the Power BI file](powerbi/Retail-Inventory-Demand-Planning.pbix)**

The PBIX file contains the data model, Power Query transformations, DAX measures, calculations, and dashboard experience presented in this case study.

### Documentation

- [Methodology](documentation/methodology.md)
- [Data Source & Attribution](documentation/data-source.md)

---

# 📚 Data Source

This project uses the **Retail Store Inventory and Demand Forecasting** dataset published on Kaggle by **Wavelet**.

The dataset is synthetically generated and was used for educational and portfolio purposes.

**License:** Apache License 2.0

[View the original dataset on Kaggle](https://www.kaggle.com/datasets/atomicd/retail-store-inventory-and-demand-forecasting/data)

For dataset details, attribution, and licensing information, see:

**[Data Source & Attribution](documentation/data-source.md)**

---

# 🧰 Tools & Technologies

**Analytics & BI**

`Power BI` `DAX` `Power Query` `Data Modeling`

**Data & Analysis**

`Excel` `SQL` `Python` `Pandas`

**Business Domain**

`Supply Chain Analytics` `Inventory Planning` `Demand Analysis` `Procurement Analytics`

---

# 👤 About Me

I'm **Omar Alkhulaidi**, a Data Analyst focused on **Business & Operations Analytics**.

I build practical analytics solutions that turn operational data into clear insights, reliable KPIs, and better business decisions.

My interests include Business Intelligence, Operations Analytics, Supply Chain Analytics, and decision-support solutions.

### Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Omar%20Alkhulaidi-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/omar-alkhulaidi/)

[![GitHub](https://img.shields.io/badge/GitHub-Omar--Alkhulaidi-black?style=flat-square&logo=github)](https://github.com/Omar-Alkhulaidi)

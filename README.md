# Fashion-Marketing-Sales-Analysis

## Table of Contents

- [📌 Introduction](-introduction)
- [📂 Dataset & Data Model](-dataset--data-model)
- [🧠 Design Thinking Process](-design-thinking-process)
- [📊 Key Insights & Visualizations  ](#-key-insight-visualizations)
- [6. Installation & Usage](#6-installation--usage)

---

## 📌 Introduction

### Project Overview
This project focuses on analyzing the business and marketing data of a multi-channel fashion retail and e-commerce enterprise.
It uses a tactical dashboard to link advertising spend with revenue at the SKU level.

### Problem Statement
The business currently lacks a unified view of its marketing effectiveness. 
Sales revenue and marketing costs (CPM, CPC, CTR) are stored in separate datasets, making it difficult for leadership:
* **Identify Profit Drivers:** Determine which specific campaigns or products (SKUs) are truly driving growth.
* **Evaluate ROI:** Measure the real Return on Investment across different marketing channels.
* **Optimize Budget:** Stop wasting resources on underperforming campaigns and reallocate funds to high-conversion areas.

### Core Business Questions
The project focuses on answering key tactical questions:
* **ROI/ROAS:** What is the Return on Ad Spend (ROAS) for each campaign and SKU? 
* **Correlation:** How do marketing metrics like CPM, CPC, and CTR impact net sales?
* **Budget Optimization:** How can we reallocate the budget to maximize total revenue based on KPIs?

---

## 📂 Dataset & Data Model
The dataset (`[DAC] Project 3 - Dataset.xlsx`) contains three core tables:

1. **`Order`**: Raw order-level data including Order ID, timestamp, source (organic/admin), product, category, price, quantity, COGS, and order status.
2. **`mkt_camp_cost`**: Campaign-level daily marketing spend with CPM, CPC, CTR, impressions, and click metrics per campaign.
3. **`mkt_camp_by_sku_cost`**: Campaign × SKU-level breakdown of ads spend, allocated orders, impressions, inbox/comment counts, and derived ROAS metrics.
Includes a `Sample Description` sheet explaining how each marketing KPI is calculated per SKU per campaign.

### Data Model
This project utilizes a Star Schema architecture to ensure performance and analytical flexibility in Power BI.
Two main Fact tables track sales orders and marketing costs per product. 
These connect to shared Dimension tables for dates, products, and campaigns.
<img width="1049" height="630" alt="image" src="https://github.com/user-attachments/assets/202e3415-7ed6-4eca-b10c-dfa926cf441c" />

## 🧠 Design Thinking Process

To ensure this dashboard delivers real business value rather than just displaying raw numbers, I applied a structured Design Thinking approach. This helped bridge the gap between technical data modeling and the actual needs of the business stakeholders (Marketing & Sales Managers).
## 1️⃣ Empathize
### 5W1H Problem Statement

| Dimension | Question | Core Finding |
| :--- | :--- | :--- |
| **WHO** | Who is experiencing the problem? | Marketing Managers & Performance Marketing Specialists. |
| **WHAT** | What is the exact issue? | Inability to track the conversion funnel (Click ➔ Inbox ➔ Sale) and calculate true **ROAS per SKU**. |
| **WHY** | Why does it matter? | To stop wasting budget on underperforming campaigns and scale profitable products. |
| **WHEN / WHERE** | When do they need this data? | During daily campaign performance reviews and real-time budget optimization. |
| **HOW** | How will this dashboard help? | By providing a centralized view of key metrics (Spend, Revenue, ROAS) to enable fast, data-driven decisions. |

### Empathy Map: Marketing Stakeholders


| Quadrant | User Insight (Based on Stakeholder Context) |
| :--- | :--- |
| **Thinking & Feeling** | Worried about marketing spend efficiency and afraid of wasting the ad budget. |
| **Seeing** | Multiple campaigns running simultaneously, fragmented costs, and performance fluctuating daily. |
| **Saying & Doing** | Constantly asking for key metrics: "What is the ROAS, CTR, CPC, and revenue for each campaign?" |
| **Pains** | Difficulty in evaluating the true effectiveness of individual campaigns. |
| **Gains** | The ability to easily see budget allocation by SKU and detailed ROAS. |
| **Stakeholder Need** | Needs to immediately answer: "Which campaign is the most effective?" and "Which SKU generates actual revenue?" |

## 2️⃣ Define Point of View (POV)

To solve the business problem, I established the core metrics and analytical perspectives required for the dashboard.

* **North Star Metrics:** **ROAS (Return on Ad Spend)** & **Profit Margin**. These metrics perfectly bridge the gap between marketing expenses and actual sales performance.
* **Key Analytical Perspectives (Dimensions):**
    * **Overview (Time Trends):** Evaluating the overall health of marketing campaigns and budget pacing over time.
    * **Campaign Level:** Analyzing ad efficiency (CTR, CPC, Cost per Inbox) to identify the most cost-effective campaigns.
    * **Product (SKU) Level:** Pinpointing exactly which SKUs generate the highest revenue so stakeholders can confidently reallocate the ad budget.
* **Growth Formula (Driving ROAS):**
    * ROAS improves when high-converting SKUs receive a larger share of the budget.
    * ROAS improves with higher ad engagement quality (higher CTR, lower Cost per Interaction).
    * ROAS improves when total revenue scales faster than the overall ad spend.
 
### 3️⃣ Ideate (Brainstorming & Dashboard Architecture)

In this stage, I translated the business requirements into actionable hypotheses and mapped out the information architecture for the dashboard to ensure a logical user flow (from macro to micro).

#### Part 1: Brainstorming Business Hypotheses
| Objective | Overview (Time Trends) | Campaign Efficiency | Product (SKU) Level | Traffic & Engagement |
| :--- | :--- | :--- | :--- | :--- |
| **Optimize Marketing Spend** | Daily ROAS fluctuates significantly, needing close monitoring. | Daily spend is unstable, leading to inconsistent revenue. | High spend on certain days yields disproportionately low revenue. | Monitor customer interaction frequency and cost (CPC). |
| **Maximize ROAS** | Identify macroeconomic trends affecting overall purchasing power. | Highlight campaigns that spend heavily but generate low revenue. | Top-spending campaigns consume the majority of the budget. | Shift budget from "cash-burning" campaigns to high-converting ones. |

<br>

#### Part 2: Dashboard Information Architecture
To avoid overwhelming the users, I structured the dashboard into three distinct pages based on the level of detail required for decision-making:

| Information Tier | Page 1: Overview | Page 2: Campaign Performance | Page 3: Product Performance |
| :--- | :--- | :--- | :--- |
| **Critical Info (Top KPIs)** | Total Budget, Total Spend, Total Revenue, Utilization %, Account ROAS | Campaign Spend, Campaign Revenue, Campaign ROAS, CTR, CPC, CPM | Cost Allocation by SKU, ROAS by SKU, Ads Sales by SKU |
| **Important Info (Trends & Breakdowns)** | Spend vs Revenue by Day, Total Spend & Budget Utilization by Campaign | CTR & CPC Trends by Week, Conversion Funnel (Impression ➔ Click ➔ Inbox) | Top Products by SKU, Ads Revenue by Category & Material |

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1 Preview  
<img width="1078" height="602" alt="image" src="https://github.com/user-attachments/assets/d51ce5e3-4f89-42a8-b6c0-294e78a203db" />

# 🚀 KickStarter Projects Dashboard

> An end-to-end Business Intelligence project analyzing **379K KickStarter crowdfunding campaigns** — uncovering funding patterns, category performance, and what drives campaign success or failure.

---

## 📁 Repository Structure

```
KickStarter/
│
├── 📂 dashboard/        # 2 dashboard pages
├── 📂 raw_data/         # Original KickStarter dataset before cleaning & transformation
└── 📄 README.md         # Project documentation
```

> **Note:** The data model file is not included in this repository due to file size constraints. The full data model (relationships, schema, and DAX measures) is embedded inside the `.pbix` file within the `dashboard/` folder.

---

## 🎯 Project Overview

This project delivers a comprehensive analysis of **KickStarter crowdfunding campaigns**, covering **379,000+ projects** across multiple countries and categories spanning from the platform's early days through 2018. The goal is to surface patterns in campaign funding, category dominance, and project status distribution — helping creators benchmark their campaigns and understand market dynamics.

---

## 🔄 Project Workflow

### 1. 🗃️ Data Collection & Exploration
- Sourced a real-world KickStarter dataset with campaign-level details: goal, pledged amount, backers, category, country, launch date, and outcome
- Performed initial profiling to understand data shape, distributions, and quality issues

### 2. 🧹 Data Cleaning & Transformation
- Removed duplicates and handled null/irrelevant records
- Standardized currency, date formats, and category labels
- Handled undefined and suspended campaign states
- All transformations applied using **Power Query (M Language)** in Power BI

### 3. 🔗 Data Modeling
- Designed a clean schema with fact and dimension tables
- Built DAX measures for all KPIs visible in the dashboard
- Established date intelligence for the time-series analysis (2009–2018)

### 4. 📊 Dashboard Development
- Built a **2-page interactive Power BI report**
- Page 1: Detailed category and funding breakdown
- Page 2: High-level overview with geographic and time analysis

---

## 📌 Key Metrics (From the Dashboard)

| KPI | Value |
|-----|-------|
| **Total Pledged** | $3.62 Billion |
| **Total Goal** | $19 Billion |
| **Total Projects** | 379K |
| **Total Backers** | 40 Million |

---

## 📊 Dashboard Pages & Features

### Page 1 — KS Projects Dashboard (Detailed View)
- **Project Status Distribution** — Donut chart showing campaign outcomes:
  - Failed: 195.13K (51.53%)
  - Canceled: 132.42K (34.97%)
  - Successful: 38.49K (10.17%)
  - Live / Suspended / Undefined: remainder
- **Projects Launched Over Time** — Line chart tracking campaign volume from 1970s to 2018, with peak activity around 2014–2015
- **Top Categories by Funding** — Bar chart of top funded categories:
  - Product Design — $0.70bn
  - Tabletop Games — $0.47bn
  - Video Games — $0.21bn
  - Hardware — $0.16bn
  - Technology — $0.15bn
  - Documentary — $0.14bn
- **Category Performance by Status** — Stacked bar showing success vs failure breakdown per category
- **Target vs Raised Funds by Category** — Clustered bar comparing sum of pledged vs sum of goal per category

### Page 2 — Ks Dashboard (Overview)
- **Projects Launched Over Time (2009–2018)** — Detailed line chart of yearly campaign growth and decline
- **Project Status Distribution** — Donut chart (same KPIs, cleaner layout)
- **Projects by Main Category** — Treemap showing category dominance:
  - Film & Video, Music, Publishing, Games, Technology, Design, Art, Food, Theater, Comics, and more
- **Projects by Country** — Horizontal bar chart showing US dominance, followed by GB, CA, AU, DE

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Data modeling, DAX, and dashboard development |
| **Power Query (M)** | Data cleaning and transformation |
| **DAX** | Calculated measures and KPIs |
| **CSV / Excel** | Source data format |
| **Git & GitHub** | Version control and project hosting |

---

## 💡 DAX Measures (Examples)

```dax
-- Total Pledged
Total Pledged = SUM(Campaigns[usd_pledged])

-- Total Goal
Total Goal = SUM(Campaigns[goal])

-- Total Projects
Total Projects = COUNTROWS(Campaigns)

-- Total Backers
Total Backers = SUM(Campaigns[backers])

-- Success Rate
Success Rate % =
DIVIDE(
    COUNTROWS(FILTER(Campaigns, Campaigns[state] = "successful")),
    COUNTROWS(Campaigns),
    0
)
```

---

## 🔍 Key Insights (From the Data)

- Only **~10% of campaigns** successfully reach their funding goal — the majority fail or get canceled
- **Product Design and Tabletop Games** lead in total funds raised, far ahead of other categories
- Campaign activity peaked in **2014–2015** with 68K–77K launches per year, then declined sharply
- The **US dominates** campaign volume by a wide margin; GB and CA follow at a fraction
- **Film & Video** is the largest category by number of projects, while **Product Design** leads in funding raised
- Total funding pledged ($3.62bn) is only **~19% of total goals set ($19bn)**, reflecting the high failure rate

---

## 🚀 Getting Started

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version recommended)

### Steps to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Salma-rar/KickStarter.git
   ```

2. **Open the report**
   - Navigate to the `dashboard/` folder
   - Open the `.pbix` file using **Power BI Desktop**

3. **Explore the raw data**
   - The original dataset is available in `raw_data/` for reference and reproducibility

4. **Interact with the Dashboard**
   - Switch between the two report pages for different views
   - Use slicers and filters to explore specific categories or countries

---

## 👩‍💻 Author

**Salma Rar**
- GitHub: [@Salma-rar](https://github.com/Salma-rar)
- Project Repository: [KickStarter Dashboard](https://github.com/Salma-rar/KickStarter.git)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Built with ❤️ using Power BI — turning crowdfunding data into actionable insights*

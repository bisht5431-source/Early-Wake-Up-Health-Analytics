<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=055E56&height=200&section=header&text=Early%20Wake-Up%20Health%20Analytics&fontSize=34&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Power%20BI%20Dashboard%20%7C%20VitaIndex%20Health%20Analytics&descAlignY=58&descSize=15"/>

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![DAX](https://img.shields.io/badge/DAX-055E56?style=for-the-badge&logo=microsoftazure&logoColor=white)](#)
[![Pages](https://img.shields.io/badge/Pages-2%20Report%20Pages-20B2AA?style=for-the-badge)](#)
[![Dataset](https://img.shields.io/badge/Dataset-10%2C000%20Individuals-055E56?style=for-the-badge)](#)
[![Domain](https://img.shields.io/badge/Domain-Health%20%26%20Wellness-20B2AA?style=for-the-badge)](#)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)](#)

</div>

---

## 🏥 Project Overview

> **Does waking up early actually make you healthier — and what does the data say?**

**Early Wake-Up Health Analytics** is a two-page, fully interactive Power BI dashboard built under the **VitaIndex Health Analytics** brand. It analyses **10,000 individuals** across sleep behaviour, fitness levels, wellness metrics, sugar levels, BMI, exercise patterns, and health risk indicators — giving recruiters, analysts, and health researchers instant, visual answers.

The dashboard connects real-world health data across **demographic, geographic, and lifestyle dimensions**, making it one of the most comprehensive personal health analytics projects in this portfolio.

---

## 🖼️ Dashboard Preview

### 📊 Page 1 — Home Page (Overview Analysis)
<img width="1308" height="730" alt="Screenshot 2026-06-16 122257" src="https://github.com/user-attachments/assets/e3036b23-4b9b-47ab-8f14-10881bbd9f00" />


### 📋 Page 2 — Overview Page (Drill-Down Detail Table)
<img width="1306" height="730" alt="Screenshot 2026-06-16 122338" src="https://github.com/user-attachments/assets/85961a3b-e9dd-4a3c-b347-86cbf05a3a91" />


> 📁 Save your screenshots into an `assets/` folder as `homepage.png` and `overviewpage.png`

---

## 🗂️ Report Pages

| Page | Name | Purpose |
|------|------|---------|
| 1️⃣ | **Home Page** | Executive KPI cards, sugar level trends, exercise distribution, life satisfaction, health score by age group |
| 2️⃣ | **Overview Page** | Individual-level drill-down table with Person ID, Country, BMI, Blood Sugar, Diabetes Risk, Exercise Minutes |

---

## 🎯 KPI Cards (Visible on Both Pages)

| KPI | Value | What It Measures |
|-----|-------|-----------------|
| 👥 **Total Participants** | 4,851 | Total individuals in the filtered dataset |
| 💚 **Avg Health Score** | 74.3 | Mean health score across all participants |
| ⏰ **Early Waker %** | 41.7% | Percentage of participants who wake up early |
| 🚶 **Avg Fitness Score** | 75.01 | Mean fitness score across all participants |
| 👣 **Avg Daily Steps** | 8,097 | Average number of steps per day |

> Two **benchmark comparison cards** sit at the top right — **Late Waker Health Score: 2830** vs **Early Waker Health Score: 2021** — giving instant comparison between the two groups.

---

## 📊 Page 1 — Home Page Visuals

| Visual | Chart Type | Key Insight |
|--------|-----------|-------------|
| **Avg Sugar Level by Age Group** | Clustered Column Chart | Sugar rises steadily with age — 103 at 18–25, reaching 112 at 65+ |
| **Life Satisfaction Score by Marital Status** | Donut Chart | Married leads at 45.6% (16.4K) · Single 34.2% · Divorced 13.3% · Widowed 6.9% |
| **Total Exercise Duration by Exercise Type** | Horizontal Bar Chart | Running #1 at 41K mins · Weight Training 40K · Walking 39K · None 18K |
| **Total Health Score by Age Group** | Area + Line Chart | Peaks at 26–35 (74K) then sharp decline after 46–55 down to 47K at 56–65 |

---

## 🔍 Page 2 — Overview Page (Drill-Down Table)

The overview page features a **row-level detail table** with full drill-down capability across every individual record.

### Columns in the Drill-Down Table

| Column | Source | Description |
|--------|--------|-------------|
| `Person_ID` | Dataset | Unique individual identifier (e.g. P00004) |
| `Country` | Dataset | Country of the participant (20+ countries) |
| `Height cm` | Dataset | Height in centimetres |
| `Weight kg` | Dataset | Weight in kilograms |
| `Occupation` | Dataset | Job type — Software Engineer, Manager, Laborer, etc. |
| `Gender` | Dataset | Male / Female |
| `Exercise in Minutes` | Dataset | Total weekly exercise duration |
| `Diabetes Risk` | Dataset | Low / Medium / High risk classification |
| `Age` | Dataset | Participant age |
| `Blood Sugar Level` | Dataset | Measured blood sugar value |
| `Total BMI` | Dataset | Calculated Body Mass Index |

### 🔎 Drill-Down Hierarchy

```
All Participants
    └── Country
            └── Person_ID
                    └── Individual Record Detail
```

Click any row to drill into that participant's full health profile across all dimensions.

---

## 🎛️ Interactive Slicers (Left Panel — Both Pages)

| Slicer | Field | What It Filters |
|--------|-------|----------------|
| 🚻 **Gender** | `gender` | Filter all visuals by Male / Female |
| 🚬 **Smoking Status** | `smoking_status` | Filter by smoker / non-smoker status |
| 💪 **Workout Intensity** | `workout_intensity` | Filter by Low / Medium / High intensity |
| 🌍 **Country** | `country` | Filter by any of the 20+ countries in dataset |

> All four slicers are **cross-filtering** — selecting one automatically narrows all other visuals on the page simultaneously.

---

## 🧮 DAX Measures Used

```dax
-- Total number of participants
Total Participants =
    COUNTROWS('health_data')

-- Average health score across all records
Avg Health Score =
    AVERAGE('health_data'[health_score])

-- Early Waker percentage
Early Waker % =
    DIVIDE(
        CALCULATE(COUNTROWS('health_data'),
                  'health_data'[early_waker] = "Yes"),
        [Total Participants],
        0
    ) * 100

-- Average fitness score
Avg Fitness Score =
    AVERAGE('health_data'[fitness_score])

-- Average daily steps
Avg Daily Steps =
    AVERAGE('health_data'[daily_steps])

-- Late Waker total health score (benchmark card)
Late Waker Health Score =
    CALCULATE(
        SUM('health_data'[health_score]),
        'health_data'[early_waker] = "No"
    )

-- Early Waker total health score (benchmark card)
Early Waker Health Score =
    CALCULATE(
        SUM('health_data'[health_score]),
        'health_data'[early_waker] = "Yes"
    )

-- Average blood sugar level by group
Avg Sugar Level =
    AVERAGE('health_data'[blood_sugar_level])

-- BMI calculation (if not pre-calculated in data)
Total BMI =
    DIVIDE(
        'health_data'[weight_kg],
        ('health_data'[height_cm] / 100) * ('health_data'[height_cm] / 100),
        0
    )

-- Health score difference: Early vs Late wakers
Health Score Gap =
    [Early Waker Health Score] - [Late Waker Health Score]

-- Age group classification (calculated column)
Age Group =
    SWITCH(TRUE(),
        'health_data'[age] <= 25, "18–25",
        'health_data'[age] <= 35, "26–35",
        'health_data'[age] <= 45, "36–45",
        'health_data'[age] <= 55, "46–55",
        'health_data'[age] <= 65, "56–65",
        "65+"
    )
```

---

## 💡 Key Business Insights

| # | Insight | Data Point |
|---|---------|-----------|
| 1 | **Blood sugar rises with age** — a clear linear trend from 103 (18–25) to 112 (65+) | Column chart |
| 2 | **Married individuals report highest life satisfaction** — 45.6% vs 34.2% for singles | Donut chart |
| 3 | **Running is the most popular exercise** — 41K minutes, followed closely by Weight Training (40K) | Bar chart |
| 4 | **Health score peaks at 26–35 years** (74K) and drops sharply after 46–55 (47K) | Area chart |
| 5 | **Filtered to Male only** — all visuals respond to the Gender slicer in real-time | Slicer |
| 6 | **Early wakers total health score (2021) is lower than late wakers (2830)** — because early wakers are fewer in count (41.7%) | Benchmark cards |

---

## 🗃️ Data Model

| Table | Type | Rows | Description |
|-------|------|------|-------------|
| `health_data` | Fact / Main Table | 10,000 | All individual health records |
| `Measures` | Measures Table | — | All DAX measures stored separately (best practice) |

---

## 🛠️ Tech Stack

| Tool | Usage |
|------|-------|
| **Power BI Desktop** | Dashboard design, data modeling, interactivity |
| **DAX** | All KPI measures, benchmark cards, age groups, BMI |
| **Power Query (M)** | Data cleaning, column typing, null handling |
| **VitaIndex Brand** | Custom logo, color palette `#055E56`, icons |

---

## 📁 Repository Structure

```
early-wakeup-health-analytics-powerbi/
│
├── 📊 Early_WakeUp_Health_Analytics.pbix    ← Main Power BI file
├── 📄 README.md                              ← You are here
│
├── 📁 assets/
│   ├── homepage.png                          ← Page 1 screenshot
│   ├── overviewpage.png                      ← Page 2 screenshot
│   └── vitaindex_logo.png                    ← Brand logo (transparent)
│
├── 📁 data/
│   └── early_wakeup_health_dataset.csv       ← Raw dataset (10,000 rows)
│
└── 📁 dax/
    └── measures.dax                          ← All DAX measures exported
```

---

## 🚀 How to Use

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/early-wakeup-health-analytics-powerbi.git
   ```

2. **Open the dashboard**
   - Open `Early_WakeUp_Health_Analytics.pbix` in **Power BI Desktop**
   - Free download → [powerbi.microsoft.com](https://powerbi.microsoft.com/desktop/)

3. **Connect data**
   - Go to **Home → Transform Data → Data Source Settings**
   - Point to `data/early_wakeup_health_dataset.csv`

4. **Explore**
   - Use **Gender, Smoking Status, Workout Intensity, Country** slicers to filter
   - Switch between **Home Page** and **Overview Page** via left navigation buttons
   - On the **Overview Page** — click rows to drill into individual records

---

## ⭐ Recommended Repository Name

```
early-wakeup-health-analytics-powerbi
```

---

---

<div align="center">

## 👨‍💻 Built by Manish Bisht

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=055E56&center=true&vCenter=true&width=500&lines=Data+Analyst+%7C+6%2B+Years+Experience;SQL+%7C+Power+BI+%7C+Python+%7C+Excel;Turning+Raw+Data+into+Real+Decisions" alt="Typing SVG" />

---

**Manish Bisht** is a Senior Data Analyst with 6+ years of experience in SQL, Power BI, Excel, Python, MIS Reporting, and Business Intelligence. This dashboard is part of a growing portfolio of real-world analytics projects covering Finance, Healthcare, HR, Supply Chain, and Wellness domains.

Every dashboard in this portfolio is built with one goal:

> *"Make data so clear that the insight is impossible to miss."*

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/dataanalyst-manish)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/bisht5431-source)
[![Email](https://img.shields.io/badge/Email-055E56?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alphainsights123@gmail.com)

---

> *If this project helped you or inspired your own work — please consider giving it a* ⭐ *— it genuinely means a lot and helps others find it too.*

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=055E56&height=100&section=footer"/>

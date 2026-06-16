# 🌅 Early Wake-Up Health Analytics Dashboard

## 📌 Project Overview

The Early Wake-Up Health Analytics Dashboard is an interactive Power BI project designed to analyze the relationship between sleep habits, fitness activities, wellness indicators, and overall health outcomes.

Using a dataset of 10,000 individuals, this dashboard provides actionable insights into health scores, exercise behavior, lifestyle patterns, and wellness categories through dynamic visualizations and KPI tracking.

---

## 🎯 Business Objective

The objective of this project is to identify how lifestyle habits such as:

* Sleep Duration
* Exercise Type
* Daily Physical Activity
* Smoking Status
* Wellness Category
* Marital Status

influence overall health and fitness outcomes.

---

## 📊 Dashboard Features

### Executive KPIs

* Total Participants
* Average Health Score
* Early Waker Percentage
* Average Fitness Score
* Average Daily Steps
* Early Waker vs Late Waker Health Score Comparison

### Interactive Filters

* Gender
* Smoking Status
* Workout Intensity
* Wellness Category

### Key Insights Visuals

#### Average Sugar Level by Age Group

Analyzes blood sugar trends across different age demographics.

#### Life Satisfaction Score by Marital Status

Compares life satisfaction among married, single, divorced, and widowed participants.

#### Exercise Duration by Exercise Type

Highlights which exercise activities contribute the most to physical activity levels.

#### Health Score by Age Group

Identifies health score patterns and trends across age categories.

---

## 🛠 Tools & Technologies

* Power BI Desktop
* Power Query
* DAX (Data Analysis Expressions)
* Data Modeling
* Data Visualization
* Interactive Dashboard Design

---

## 📈 Key Metrics

| Metric             | Description                               |
| ------------------ | ----------------------------------------- |
| Total Participants | Total individuals included in the dataset |
| Avg Health Score   | Average overall health rating             |
| Avg Fitness Score  | Average fitness performance score         |
| Early Waker %      | Percentage of early risers                |
| Avg Daily Steps    | Average daily physical activity           |

---

## 📚 DAX Measures Used

### Total Participants

```DAX
Total Participants =
COUNTROWS('Health Data')
```

### Average Health Score

```DAX
Avg Health Score =
AVERAGE('Health Data'[Health_Score])
```

### Average Fitness Score

```DAX
Avg Fitness Score =
AVERAGE('Health Data'[Fitness_Score])
```

### Average Daily Steps

```DAX
Avg Daily Steps =
AVERAGE('Health Data'[Daily_Steps])
```

### Early Waker Count

```DAX
Early Waker Count =
CALCULATE(
    COUNTROWS('Health Data'),
    'Health Data'[Early_Waker] = "Yes"
)
```

### Early Waker Percentage

```DAX
Early Waker % =
DIVIDE(
    [Early Waker Count],
    [Total Participants]
)
```

### Early Waker Health Score

```DAX
Early Waker Health Score =
CALCULATE(
    SUM('Health Data'[Health_Score]),
    'Health Data'[Early_Waker] = "Yes"
)
```

### Late Waker Health Score

```DAX
Late Waker Health Score =
CALCULATE(
    SUM('Health Data'[Health_Score]),
    'Health Data'[Early_Waker] = "No"
)
```

---

## 📊 Insights Generated

* Individuals who wake up early generally demonstrate higher health and fitness scores.
* Exercise type influences overall physical activity and wellness levels.
* Health scores vary significantly across age groups.
* Life satisfaction differs across marital status categories.
* Lifestyle habits show measurable impact on wellness outcomes.

---

## 🚀 Skills Demonstrated

* Data Cleaning
* Data Transformation
* Data Modeling
* DAX Calculations
* KPI Development
* Interactive Reporting
* Dashboard Design
* Business Storytelling

---

## 📷 Dashboard Preview

### Overview Dashboard

<img width="1306" height="730" alt="Screenshot 2026-06-16 115507" src="https://github.com/user-attachments/assets/01e24b6d-c0d7-4003-af7a-6c7b48673104" />


---

## 👨‍💻 Author

**Manish Bisht**

Aspiring Data Analyst passionate about transforming raw data into actionable business insights through Power BI, SQL, Excel, and Python.

---

⭐ If you found this project useful, feel free to star the repository and connect with me on LinkedIn.

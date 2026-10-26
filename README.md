# Marketing Funnel & Conversion Performance Analysis

## 📌 Project Overview

This project analyzes marketing campaign performance using Power BI and the UCI Bank Marketing dataset. It explores subscription outcomes, evaluates conversion rates across contact methods and education levels, and identifies opportunities to improve future marketing campaigns.

The dashboard presents key performance indicators (KPIs), campaign outcomes, customer segmentation, and actionable recommendations.

## 🎯 Objectives

* Measure overall marketing campaign conversion performance.
* Compare successful and unsuccessful subscription outcomes.
* Analyze conversion rates across different contact methods.
* Examine conversion rates across education categories.
* Identify opportunities to improve campaign targeting and effectiveness.

## 📊 Dataset

**Dataset:** Bank Marketing — UCI Machine Learning Repository

**Source:** [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing)

The analysis uses `bank-additional-full.csv`, which contains records from a Portuguese bank's direct marketing campaigns. The target variable `y` indicates whether a customer subscribed to a term deposit (`yes` or `no`).

## 🛠️ Tools & Technologies

* Microsoft Power BI
* Power Query for data preparation
* DAX for calculated measures
* Data visualization and exploratory analysis

## 📈 Key Performance Indicators

| KPI                      | Description                                        |
| ------------------------ | -------------------------------------------------- |
| Total Contacts           | Total marketing campaign contact records           |
| Successful Subscriptions | Contacts that resulted in a subscription           |
| Conversion Rate          | Successful subscriptions divided by total contacts |
| Unsuccessful Contacts    | Contacts that did not result in a subscription     |

### Measures Used

**Total Contacts**

```DAX
Total Contacts = COUNTROWS('Marketing_Campaigns')
```

**Successful Subscriptions**

```DAX
Successful Subscriptions =
CALCULATE(
    COUNTROWS('Marketing_Campaigns'),
    'Marketing_Campaigns'[y] = "yes"
)
```

**Conversion Rate**

```DAX
Conversion Rate =
DIVIDE(
    [Successful Subscriptions],
    [Total Contacts],
    0
)
```

**Unsuccessful Contacts**

```DAX
Unsuccessful Contacts =
[Total Contacts] - [Successful Subscriptions]
```

## 🔍 Dashboard Analysis

The Power BI report includes:

* **Campaign Subscription Outcomes:** Compares successful and unsuccessful campaign outcomes.
* **Conversion Rate by Contact Method:** Compares conversion performance for cellular and telephone contacts.
* **Conversion Rate by Education Level:** Examines differences in conversion performance across education categories.
* **KPI Cards:** Summarize campaign reach, subscriptions, conversion rate, and unsuccessful contacts.

## 💡 Key Findings

* The overall subscription conversion rate is approximately **11.27%**.
* Cellular contacts show a higher conversion rate than telephone contacts in the analyzed data.
* Conversion rates vary across education categories, highlighting differences in campaign response.
* Most contacts did not result in a subscription, indicating opportunities to evaluate campaign targeting and engagement strategies.

## 🚀 Recommendations

1. Investigate why conversion rates differ between contact methods.
2. Evaluate campaign timing, contact frequency, and customer engagement.
3. Analyze customer segments to identify characteristics associated with higher subscription rates.
4. Test targeted campaign strategies and compare their performance.
5. Track conversion rates over time to evaluate whether changes improve results.

These recommendations are hypotheses to test; the dashboard does not establish that any particular intervention will improve conversions.

## ⚠️ Scope & Limitations

This project analyzes marketing contacts and term-deposit subscription outcomes. The dataset does not provide separate website visitor, lead, and customer stages, so the analysis does not measure a full website-to-customer funnel.

The findings describe patterns in the available dataset and do not establish causation.

## 📁 Repository Contents

* `Marketing_Funnel_Conversion_Analysis.pbix` — Power BI report
* `dashboard_page1.png` — Marketing dashboard screenshot
* `dashboard_page2.png` — Insights and recommendations screenshot
* `README.md` — Project documentation

## 👩‍💻 Project Purpose

This project demonstrates practical skills in data preparation, DAX measures, KPI development, conversion analysis, and business-focused data visualization using Power BI.

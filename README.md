# RANKLENS — Global University Rankings Analysis

### Data-Driven Exploration of University Performance, Rankings & Global Trends

---

## 📌 Project Overview

**RankLens** is a data analysis project focused on exploring global university rankings between **2012 and 2015**.

The project analyzes university performance across multiple dimensions, including:

* Quality of Education
* Quality of Faculty
* Alumni Employment
* Publications
* Citations
* Influence
* Patents
* Overall University Score
* World Ranking

Instead of focusing only on the highest-ranked universities, RankLens investigates **ranking movements, country-level patterns, research performance, university consistency, and the relationship between research performance and overall ranking position**.

---

## 🎯 Objectives

The main objectives of this project are to:

* Identify consistently high-performing universities.
* Analyze factors associated with overall world ranking.
* Examine university ranking movements between 2012 and 2015.
* Compare university performance across countries.
* Analyze India's representation and performance.
* Identify the strongest research-related indicators.
* Develop a custom **Research Performance Index**.
* Compare research performance with overall ranking position.
* Identify universities whose research profile differs substantially from their overall ranking position.
* Build interactive visualizations for exploring university rankings.

---

## 📊 Dataset

The dataset contains university ranking information from **2012 to 2015**.

### Dataset Size

* **2,200 university-year records**
* **1,000 unique universities**
* **14 columns**
* **4 years of ranking data**

### Dataset Columns

| Column                 | Description                                 |
| ---------------------- | ------------------------------------------- |
| `world_rank`           | Global ranking position of the university   |
| `institution`          | University name                             |
| `country`              | Country of the university                   |
| `national_rank`        | University ranking within its country       |
| `quality_of_education` | Ranking based on quality of education       |
| `alumni_employment`    | Ranking based on alumni employment          |
| `quality_of_faculty`   | Ranking based on faculty quality            |
| `publications`         | Ranking based on research publications      |
| `influence`            | Ranking based on institutional influence    |
| `citations`            | Ranking based on research citations         |
| `broad_impact`         | Ranking based on broad institutional impact |
| `patents`              | Ranking based on patents                    |
| `score`                | Overall university score                    |
| `year`                 | Ranking year                                |

> **Note:** Most ranking variables represent ranking positions, where a lower value indicates better performance. The `score` variable follows the opposite direction, where a higher value indicates better performance.

---

## 🛠️ Tools & Technologies

The project was developed using:

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Plotly**
* **Scikit-learn**
* **Google Colab**

---

# 🔎 Analysis Performed

## 1. Data Loading & Inspection

The dataset was loaded and examined for:

* Dataset dimensions
* Data types
* Missing values
* Duplicate records
* Unique universities
* Countries represented
* Ranking years

---

## 2. Data Quality Analysis

The dataset contains **200 missing values in `broad_impact`**, representing approximately **9.1% of observations**.

The missing values occur only during:

* 2012
* 2013

The `broad_impact` variable is complete for:

* 2014
* 2015

Because the missingness is structured by year rather than randomly distributed, missing values were **not imputed**.

---

# 📈 Exploratory Data Analysis

The project explores:

* University representation by country
* Distribution of world rankings
* Ranking bands
* University scores
* Country-level performance
* Top-ranked universities
* University consistency across years

---

# 🏆 University Performance Analysis

The analysis identified universities with consistently strong ranking positions across the four-year period.

### Top Universities by Average World Ranking

Some of the strongest-performing universities included:

1. Harvard University
2. Stanford University
3. Massachusetts Institute of Technology
4. University of Cambridge
5. University of Oxford
6. Columbia University
7. University of California, Berkeley
8. Princeton University
9. University of Chicago
10. Yale University

These universities consistently maintained strong positions across the analyzed period.

---

# 📊 Correlation Analysis

Correlation analysis was performed to understand the relationship between different ranking indicators and `world_rank`.

### Correlation with World Rank

| Indicator            | Correlation |
| -------------------- | ----------: |
| Publications         |   **0.923** |
| Influence            |   **0.896** |
| Citations            |   **0.857** |
| Patents              |   **0.698** |
| Quality of Education |   **0.676** |
| Alumni Employment    |   **0.669** |
| Quality of Faculty   |   **0.664** |
| National Rank        |   **0.239** |
| Score                |  **-0.549** |

### Key Finding

Research-related indicators showed some of the strongest associations with world ranking.

In particular:

* Publications: **r = 0.923**
* Influence: **r = 0.896**
* Citations: **r = 0.857**

Because lower ranking positions represent better performance, the positive correlations indicate that higher numerical ranking values are associated with weaker world-ranking positions.

The analysis identifies **association, not causation**.

---

# 📉 Ranking Movement Analysis

Universities present in both **2012 and 2015** were compared to identify ranking movements.

The following formula was used:

```text
Rank Change = 2012 World Rank − 2015 World Rank
```

Therefore:

* Positive value → ranking improved
* Negative value → ranking declined

### Biggest Ranking Improvers

| University                | 2012 | 2015 | Change |
| ------------------------- | ---: | ---: | -----: |
| Seoul National University |   75 |   24 |    +51 |
| University of Virginia    |   84 |   41 |    +43 |
| University of Pittsburgh  |   71 |   46 |    +25 |
| École Polytechnique       |   61 |   36 |    +25 |
| Rutgers University        |   72 |   50 |    +22 |

### Largest Ranking Declines

| University               | 2012 | 2015 | Change |
| ------------------------ | ---: | ---: | -----: |
| Technion                 |   51 |  136 |    -85 |
| Rice University          |   57 |  120 |    -63 |
| Nagoya University        |   74 |  125 |    -51 |
| UT Southwestern          |   29 |   75 |    -46 |
| University of Nottingham |   97 |  140 |    -43 |

> Ranking movement represents changes in relative position and does not necessarily indicate an absolute change in university quality.

---

# 🌍 Country-Level Analysis

The project also compares university representation and performance across countries.

The **United States** has the largest representation in the dataset, followed by countries such as:

* China
* Japan
* United Kingdom
* Germany
* France
* Italy
* Spain
* Canada
* South Korea
* Australia

### Top 100 Representation

The United States had the highest number of university-year records appearing in the Top 100.

Other countries with significant Top 100 representation included:

* United Kingdom
* Japan
* France
* Switzerland
* Israel
* Canada
* Germany
* Australia
* Netherlands
* South Korea

Country comparisons should be interpreted alongside the number of universities represented in the dataset.

---

# 🇮🇳 India Analysis

India appears in the dataset only during **2014 and 2015**.

### 2014

* Universities represented: **15**
* Average world rank: **626.13**
* Best world rank: **328**

### 2015

* Universities represented: **16**
* Average world rank: **650.13**
* Best world rank: **341**

Some notable ranking movements included:

| University                  | 2014 | 2015 | Change |
| --------------------------- | ---: | ---: | -----: |
| IIT Delhi                   |  328 |  341 |    -13 |
| University of Delhi         |  436 |  379 |    +57 |
| Indian Institute of Science |  501 |  448 |    +53 |
| Panjab University           |  543 |  491 |    +52 |
| IIT Kanpur                  |  569 |  714 |   -145 |

Since India is only represented in 2014 and 2015, the analysis does **not** treat this as a full 2012–2015 trend.

---

# 🔬 Research Performance Analysis

A major component of RankLens is the analysis of research-oriented university performance.

Four research-related indicators were selected:

* Publications
* Citations
* Influence
* Patents

The analysis was restricted to universities appearing in **all four years**, resulting in:

### 91 universities

with complete four-year coverage for the research analysis.

---

# 🧮 Research Performance Index

A custom **Research Performance Index** was developed to compare universities based on their research-related ranking indicators.

### Indicators Used

```text
Publications
Citations
Influence
Patents
```

Because these variables use ranking positions, where lower values indicate better performance, the values were normalized and inverted before calculating the final research score.

The resulting score ranges approximately from:

```text
0 → Lower relative research performance
100 → Higher relative research performance
```

> This is a custom analytical metric created for this project and is **not an official university ranking score**.

---

# 📊 Research Performance vs Overall Ranking

The Research Performance Index was compared with overall university ranking position using percentile-based analysis.

### Research Performance vs Average World Rank

The correlation between the Research Performance Index and average world ranking was:

**r = 0.592**

Because lower values represent stronger performance for both research ranking indicators and world ranking, the positive relationship indicates that universities with stronger research profiles generally tend to have better overall ranking positions.

However, the relationship is not perfect, suggesting that other dimensions also contribute to overall ranking performance.

---

# 🧩 University Segmentation

Universities were segmented using their percentile positions in:

1. Research Performance
2. Overall Ranking Position

Four analytical groups were created:

### 1. Above-Median Research + Above-Median Overall

Universities performing above the median on both dimensions.

### 2. Research Heavy

Universities with relatively stronger research performance compared with their overall ranking position.

### 3. Overall Ranking Heavy

Universities whose overall ranking position was relatively stronger than their research-performance position.

### 4. Below-Median Research + Below-Median Overall

Universities performing below the median on both dimensions.

### Segment Distribution

| Segment                                      | Universities |
| -------------------------------------------- | -----------: |
| Above-Median Research + Above-Median Overall |           37 |
| Below-Median Research + Below-Median Overall |           36 |
| Research Heavy                               |            9 |
| Overall Ranking Heavy                        |            9 |

This shows that approximately **81%** of the universities were aligned in the two main groups, while approximately **20%** showed a notable difference between research performance and overall ranking position.

---

# 🔬 Research-Heavy Universities

Some universities showed relatively stronger research profiles compared with their overall ranking positions.

Examples include:

* University of Pittsburgh
* Emory University
* University of British Columbia
* Vanderbilt University
* University of California, Davis
* University of Florida
* Pierre-and-Marie-Curie University
* Washington University in St. Louis
* Pennsylvania State University

For example, the University of Pittsburgh showed one of the largest positive differences between its research-performance percentile and overall-ranking percentile.

> This does not mean the university is objectively "under-ranked." It indicates that its research profile was relatively stronger than its overall ranking position within this analytical comparison.

---

# 🏛️ Overall-Ranking-Heavy Universities

Some universities showed relatively stronger overall ranking positions compared with their research-performance positions.

Examples include:

* Hebrew University of Jerusalem
* Rockefeller University
* Weizmann Institute of Science
* École Normale Supérieure
* University of Paris-Sud
* Seoul National University
* Purdue University
* University of California, Santa Barbara
* Rutgers University

A negative research-performance advantage does **not** imply weak research performance.

It means that the university's overall ranking position was relatively stronger than its position on the custom research index.

---

# 📊 Interactive Analysis

Interactive visualizations were created using **Plotly** to make the dataset easier to explore.

### Interactive University Ranking Explorer

The visualization allows users to explore:

* University
* Country
* Year
* World rank
* Score
* Ranking band

The visualization also includes year-based animation.

### Country Comparison

An interactive country-level visualization was created to compare:

* Average world ranking
* University representation
* Best university ranking
* Average score

### Top 100 Explorer

A separate interactive visualization focuses on universities ranked within the Top 100.

---

# 📊 Dashboard

The project includes an analytical dashboard containing:

### Key Performance Indicators

* Total unique universities
* Countries represented
* Best world ranking
* Average university score

### Visualizations

* World ranking distribution
* Top countries by university representation
* University score vs world rank
* Top 100 university analysis
* Interactive ranking explorer

---

# 💡 Key Findings

### 1. Research indicators are strongly associated with world ranking

Publications, influence, and citations showed the strongest relationships with world rank.

* Publications: **r = 0.923**
* Influence: **r = 0.896**
* Citations: **r = 0.857**

---

### 2. University score is associated with ranking position

University score showed a moderate negative correlation with world rank:

**r = -0.549**

Higher scores were generally associated with better ranking positions.

---

### 3. Research performance and overall ranking are related but not identical

The custom Research Performance Index showed a correlation of:

**r = 0.592**

with average world ranking.

This suggests that research performance is an important dimension, but it does not fully explain overall ranking outcomes.

---

### 4. Universities can have different performance profiles

The percentile analysis identified universities whose research performance was relatively stronger or weaker compared with their overall ranking position.

This demonstrates that university performance is multidimensional.

---

### 5. University rankings can change substantially

Several universities experienced significant ranking movement between 2012 and 2015.

Seoul National University showed one of the largest improvements, while Technion showed one of the largest declines among universities present in both years.

---

### 6. The United States dominates dataset representation

The United States has substantially more universities represented than most other countries.

Therefore, country-level comparisons should consider differences in dataset representation.

---

### 7. India's representation is limited to 2014 and 2015

India is present only in the final two years of the dataset, so conclusions about long-term Indian ranking trends are limited.

---

# 📌 Limitations

1. The dataset covers only **2012–2015** and therefore does not represent current university rankings.

2. Several variables are **ranking positions rather than raw measurements**.

3. Correlation identifies **association, not causation**.

4. Countries have different numbers of universities represented in the dataset, which affects country-level comparisons.

5. The Research Performance Index is a **custom analytical metric** and is not an official ranking methodology.

6. Min-Max normalization is sensitive to extreme values.

7. Ranking movement represents changes in relative position and does not necessarily indicate changes in absolute university quality.

8. The research index uses only four research-related indicators and therefore does not capture every aspect of research performance.

---

# 🗂️ Project Structure

```text
ranklens-university-rankings-analysis/
│
├── README.md
│
├── RankLens_University_Rankings_Analysis.ipynb
│
├── data/
│   └── university_rankings.csv
│
└── images/
    ├── ranking_distribution.png
    ├── correlation_matrix.png
    ├── ranking_movement.png
    ├── country_analysis.png
    └── research_vs_overall.png
```

> If the original dataset has licensing or redistribution restrictions, verify the source terms before uploading the raw dataset to GitHub.

---

# 🚀 How to Run the Project

### Option 1 — Google Colab

1. Open the notebook in Google Colab.
2. Upload the dataset.
3. Run the cells from top to bottom.
4. Explore the visualizations and dashboard.

### Option 2 — Local Environment

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/ranklens-university-rankings-analysis.git
```

Navigate into the project:

```bash
cd ranklens-university-rankings-analysis
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
RankLens_University_Rankings_Analysis.ipynb
```

---

# 📚 Skills Demonstrated

This project demonstrates practical experience with:

* Data Cleaning
* Data Quality Assessment
* Exploratory Data Analysis
* Descriptive Statistics
* Correlation Analysis
* Ranking Analysis
* Time-Based Comparison
* GroupBy Aggregations
* Data Transformation
* Feature Engineering
* Min-Max Normalization
* Percentile Analysis
* Data Segmentation
* Interactive Visualization
* Dashboard Development
* Analytical Storytelling
* Business-Style Insight Generation

---

# 🎓 What This Project Demonstrates

RankLens demonstrates a complete data-analysis workflow:

```text
Raw Dataset
     ↓
Data Inspection
     ↓
Data Quality Assessment
     ↓
Exploratory Data Analysis
     ↓
Performance Analysis
     ↓
Correlation Analysis
     ↓
Ranking Movement Analysis
     ↓
Country-Level Analysis
     ↓
Research Performance Index
     ↓
Percentile Segmentation
     ↓
Interactive Visualization
     ↓
Dashboard
     ↓
Insights & Conclusions
```

---

# 🔮 Future Improvements

Potential extensions for the project include:

* Adding university ranking data from more recent years.
* Building a machine learning model to predict ranking positions.
* Creating a fully interactive web dashboard using Streamlit.
* Adding university-level filtering and search.
* Developing country-level benchmarking.
* Adding statistical significance testing.
* Comparing multiple university ranking systems.
* Building an automated data pipeline for future ranking updates.

---

# 👨‍💻 Author

**Ravi Teja**

B.Tech — Computer Science / Data Science

Aspiring Data Analyst

---

## ⭐ Project Summary

**RankLens** transforms university ranking data into an analytical story by combining exploratory data analysis, correlation analysis, ranking movement analysis, country-level comparisons, custom research scoring, percentile segmentation, and interactive visualization.

The project demonstrates how raw ranking data can be transformed into meaningful insights using Python and modern data-analysis techniques.

---

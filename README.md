# 🎬 Netflix Content Library Analysis (Excel)

> **Netflix's library boomed after 2016, led by movies and US content. What is inside it, and where are the gaps?**

An end-to-end Excel analysis of 8,804 Netflix movies and TV shows: data cleaning, helper columns, pivot tables, slicers and an interactive dashboard that shows how the library grew, what it contains, where it comes from and who it is made for.

![Dashboard.png](dashboard.png)

---

## 🎯 Business questions

1. How fast did the Netflix library grow, and when?
2. What is the mix of movies and TV shows?
3. Which countries and genres make most of the content?
4. Who is the content made for: kids, teens or adults?
5. How long do TV shows run, and how long are movies?

## 📦 Dataset

| | |
|---|---|
| Source | [Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows) on Kaggle |
| Size | 8,807 rows, 12 columns (one row per title) |
| Coverage | Titles added to Netflix between 2008 and September 2021 |
| After cleaning | 8,804 titles: 6,129 movies and 2,675 TV shows |

> The raw dataset is not re-uploaded here. Please download it from the source above.

## 🧹 Data preparation

Every step is recorded in the **Cleaning Log** sheet of the workbook.

| Step | What I did | Result |
|---|---|---|
| 1 | Removed duplicates, comparing every column except `show_id` | 3 duplicates removed, 8,807 to 8,804 rows |
| 2 | Fixed 3 rows where the runtime (66, 74, 84 min) was typed into `rating` | Movie length is complete |
| 3 | Filled blank `rating` values with "Not Rated" | 7 blanks filled |
| 4 | Converted text dates in `date_added` to real dates (TRIM + DATEVALUE) | 88 text dates fixed |
| 5 | Left 10 blank `date_added` values empty | Excluded from the yearly trend only |
| 6 | Converted the range to an Excel Table, `tblNetflix` | One source for every pivot and slicer |

**Added columns:** `Date Added Clean`, `Year Added`, `Primary Country`, `Primary Genre`, `Minutes`, `Seasons`, `Audience` (Kids, Teens, Adults, Not Rated, grouped from `rating`) and `Season Group` (1, 2, 3, 4+ seasons).

## 📊 Headline numbers

| Total titles | Movies | TV shows | Average movie length | TV shows with one season |
|---|---|---|---|---|
| 8,804 | 6,129 (70%) | 2,675 (30%) | 99.6 min | **67%** |

## 🔑 Key findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Yearly additions grew nearly 5x between 2016 and 2019.** | 429 titles in 2016 to 2,014 in 2019; 98% of titles were added from 2016 onwards |
| 2 | **Movies outnumber TV shows more than 2 to 1.** | 6,129 movies against 2,675 TV shows |
| 3 | **The United States produces over a third of the library.** | 3,211 titles, then India (1,007) and the UK (628) |
| 4 | **Dramas and Comedies make up a third of the catalogue.** | Dramas 1,599 and Comedies 1,209 (32% of titles) |
| 5 | **Netflix is built for adults and teens, not kids.** | Adults 4,008 and Teens 3,798 (89%); Kids 908 (10%) |
| 6 | **Two in three TV shows stop after one season.** | 1,792 one-season shows (67%); only 259 reach four or more |

## 💡 Recommendation

**Expand kids' content and multi-season series, the two biggest gaps in an otherwise strong library.**

## ⚠️ Limitations

- The data is a **snapshot of the catalogue**. It has no viewing numbers, so it shows what Netflix offers, not what people watch.
- `Year Added` is when a title was added to Netflix, not when it was released. **2021 covers January to September only.**
- Titles often list several countries and genres. The analysis uses the **first one listed** for each title.
- 10 titles have no `date_added` and 830 have no `country`. They are left out of the yearly and country charts only.
- The KPI tiles and insights show **all titles** and do not change with the slicers. The charts do.

## 🛠️ What's inside the workbook

| Sheet | Purpose |
|---|---|
| `Dashboard` | Interactive dashboard: 3 slicers, 5 KPI tiles, 6 charts, key insights |
| `Calc` | Formulas that power the KPI tiles |
| `Cleaning Log` | Record of every cleaning step |
| `Data` | Cleaned dataset (Excel Table `tblNetflix`) |
| `Pivot_Growth`, `Pivot_Type`, `Pivot_Country`, `Pivot_Genre`, `Pivot_Audience`, `Pivot_Season` | Pivot tables and charts behind the dashboard |

**Excel skills used:** Tables, PivotTables and PivotCharts, Slicers with Report Connections, IFS, COUNTIFS, DATEVALUE, TRIM, LEFT and FIND, shapes linked to cells, Go To Special, Remove Duplicates, dashboard design.

## ▶️ How to use

1. Download `Netflix_Content_Analysis.xlsx`
2. Open the `Dashboard` sheet
3. Click the **Type**, **Audience** and **Year Added** slicers to filter the charts
4. Use the funnel icon with the **X** on a slicer to clear a filter

## 👩‍💻 Author

**Imanathul Reyyan**: BSc Applied Data Analytics, University of Colombo
🔗 [LinkedIn](https://www.linkedin.com/in/imanathul-reyyan) · 🌐 [Portfolio](https://imanathulreyyan.github.io) · ✉️ imanareyyan@gmail.com

*Project 3 in my data analytics portfolio (Excel, then SQL and Power BI).*

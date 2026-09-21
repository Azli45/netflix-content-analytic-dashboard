# 📊 Netflix Content Analytics Dashboard

An interactive Power BI dashboard analyzing Netflix's content library — built from scratch, self-taught, with real data cleaning and debugging along the way.

![Dashboard Preview](![Uploading Screenshot.png…]()
)
<!-- Replace dashboard-preview.png with your actual screenshot filename in the repo -->

---

## 📌 Overview

This project explores Netflix's content catalog to understand what's on the platform, how it's distributed, and how it has evolved over time. The dashboard turns a raw, messy CSV dataset into a clean, interactive story covering content type, genre popularity, release trends, and platform growth.

## 🎯 Business Problem

Streaming platforms sit on massive content libraries that are hard to make sense of at a glance. This dashboard answers questions like:
- What does Netflix's content mix look like — Movies vs TV Shows?
- Which genres dominate the catalog?
- How has content released and added to the platform trended over time?
- Where is content quality/rating distributed across the library?

## 🗂️ Dataset

- **Source:** Netflix Titles dataset (public dataset, 8,809 rows)
- **Columns used:** `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`

### Data Cleaning Performed
Real-world messy data required real fixes, not just chart-building:
- Trimmed and cleaned whitespace/non-printable characters across text columns (`director`, `cast`, `country`, `listed_in`, `rating`) using Power Query.
- Identified and removed a data corruption bug — a row had its `type` column populated with a director's name (`William Wyler`) instead of "Movie"/"TV Show," caused by a comma-parsing shift in the source CSV. Filtered this out via Power Query's column filter.
- Split multi-value fields (comma-separated genres and countries) into usable single values via calculated columns (`Primary Genre`, `Primary Country`).
- Fixed axis formatting issues (thousands-unit display distorting year values on time-series charts).

## 📈 Dashboard Features

**KPI Cards**
- Total Titles
- Total Directors
- Total Genres
- Total Movies
- Total TV Shows

**Visuals**
| Visual | Insight |
|---|---|
| Genre bar chart | Most popular genres by total title count |
| Donut chart | Movies vs TV Shows split |
| Area/line chart | Content trend by release year |
| Line chart | Titles added to Netflix over time (platform acquisition pace) |

**Interactivity**
- Slicers for `Type`, `Rating`, and `Country`
- Cross-filtering enabled across all visuals — clicking any chart filters the rest of the dashboard

## 🛠️ Tools & Skills Used

- **Power BI** — dashboard design & interactivity
- **Power Query (M)** — data cleaning, trimming, filtering, column splitting
- **DAX** — calculated measures and columns (`COUNTROWS`, `DISTINCTCOUNT`, `CALCULATE`, `IF`)
- **Data Visualization & Storytelling**

## 💡 Key Learnings

Building this end-to-end — not just following a tutorial — surfaced real issues that don't show up in guided courses: shifted/corrupted data rows, misconfigured legends pulling in the wrong fields, axis formatting quirks, and map visuals requiring workarounds. Debugging each of these myself was where most of the actual learning happened.

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Azli Khan**

# Netflix Content Analytics Dashboard

An interactive Power BI dashboard I built to explore Netflix's content library — genres, ratings, release trends, and how the platform's catalog has grown over time.

## About this project

I wanted to go beyond just following a tutorial, so I picked a dataset I actually find interesting (Netflix's full title catalog, ~8,800 movies and shows) and built the whole thing myself — no course, no template, just Power BI, Power Query, and a lot of Googling when something broke.

The dashboard looks at things like:
- What's the actual mix of Movies vs TV Shows on the platform?
- Which genres show up the most?
- How has the number of titles released changed by year?
- How fast has Netflix been adding new content to the platform over time?

## The dataset

Standard public Netflix Titles dataset, 8,809 rows, with columns like `type`, `title`, `director`, `country`, `release_year`, `rating`, `duration`, and `listed_in`.

It's not clean out of the box, and honestly, dealing with that was most of the actual work:
- A bunch of missing values in `director`, `cast`, and `country` that needed handling instead of just ignoring
- One row had a director's name sitting in the `type` column instead of "Movie"/"TV Show" — turned out to be a comma-parsing issue from the original CSV shifting values into the wrong columns. Found it, tracked it down, filtered it out.
- Genres and countries are comma-separated in a single cell, so I pulled out the primary genre/country into their own columns to make them usable in charts.
- Had to fix some axis formatting that was displaying years as rounded thousands ("2.0K" instead of "2020") — small thing, but it made the whole trend chart unreadable until I caught it.

## What's on the dashboard

- KPI cards up top: total titles, directors, genres, movies, TV shows
- A genre bar chart showing what's most common in the catalog
- A donut chart for the Movies vs TV Shows split
- A trend chart of titles by release year
- A second trend chart tracking how fast content gets *added* to Netflix over time — different from release year, more about platform growth
- Slicers for type, rating, and country, with cross-filtering across every visual

## Tools

Power BI, Power Query (M), DAX

## What I actually learned

The dashboard part was honestly the easy half. The real learning was in the debugging — figuring out why a legend was pulling in the wrong field, why a map visual wouldn't geocode, why one row was breaking a whole chart. None of that shows up in a course; you only run into it by building something real and fixing it yourself.

## License

MIT — see [LICENSE](LICENSE)

## Author

Azli Khan

🎬 StreamScope — A Netflix Content Analysis Dashboard
An interactive Power BI dashboard analyzing Netflix's global content catalog — genres, ratings, release trends, and production countries — built with a custom dark, Netflix-inspired theme.

![Dashboard Preview](StreamScope-A-Netflix-Content-Analysis-Dashboard/blob/main/StreamScope%20%20A%20Netflix%20Content%20Analysis%20Dashboard.png)

📌 Overview
StreamScope analyzes ~6,000 Netflix titles to surface patterns in content type, genre distribution, age certification, release trends, and global production — helping visualize how Netflix's catalog has evolved and where its content comes from.

✨ Features
5 KPI cards: Total Titles, Total Movies, Total TV Shows, Average IMDb Rating, Total Countries
Dynamic status label that reflects active slicer selections ("Showing: All Content" → updates live)
Donut charts: content split by type, and by age certification
Line chart: title volume trend by release year
Horizontal bar chart: top production countries by title count
Treemap + bar chart: genre distribution
Detail table: per-title IMDb score, votes, runtime, and release year
4 interactive slicers: genre, type, production country, and character/cast
Fully custom dark theme (#141414 background, #E50914 Netflix-red accents)

🗂️ Dataset
Source: Netflix Movies and TV Shows (Kaggle) — https://www.kaggle.com/datasets/dgoenrique/netflix-movies-and-tv-shows
titles.csv — Core fact table (title, type, release_year, age_certification, runtime, genres, production_countries, imdb_score, imdb_votes)
credits.csv — Cast/character data, joined on id for the character slicer

🛠️ Tech Stack
Power BI Desktop — data modeling, DAX, visualization
Power Query (M) — data cleaning, multi-value column splitting
DAX — all KPI and chart-level measures

🧹 Data Preparation
Cleaned bracket/quote artifacts (['comedy'] → comedy) from list-style text columns
Split multi-value genres and production_countries columns into individual rows for accurate counts and genre-level visuals
Built a relationship between titles and credits on id for cross-table filtering

📐 Key DAX Measures
Total Titles = DISTINCTCOUNT(titles[title])
Total Movies = CALCULATE([Total Titles], titles[type] = "MOVIE")
Total TV Shows = CALCULATE([Total Titles], titles[type] = "SHOW")
Average IMDb Rating = AVERAGE(titles[imdb_score])
Total Countries = DISTINCTCOUNT(titles[production_countries])
Sum IMDb Score = SUM(titles[imdb_score])
Sum IMDb Votes = SUM(titles[imdb_votes])
Sum Runtime = SUM(titles[runtime])
A dynamic Showing Text measure combines active genre, type, production country, and character slicer selections into a single live status label.

🎨 Design System
Page background — #141414
Card background — #1F1F1F
Primary accent — #E50914
Secondary text — #B3B3B3
Primary text — #FFFFFF

🚀 How to Use
Clone/download this repository
Open StreamScope.pbix in Power BI Desktop
If prompted, update the data source path to your local titles.csv / credits.csv location
Explore using the genre, type, country, and character slicers

📈 Skills Demonstrated
Power BI · Power Query · DAX · Data Modeling · Data Visualization · Dashboard Design

👤 Author
Kunal Gurav
📧 kunalgurav111@gmail.com 
🔗 LinkedIn: linkedin.com/in/kunalgurav45

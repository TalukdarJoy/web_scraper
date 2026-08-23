# 🏃 Race Results Web Scraper

A Python project that scrapes 10K race results from a live results page, cleans the raw HTML into a structured dataset, and explores finish times with pandas, matplotlib, and seaborn.

## What it does

- Fetches a race-results page with `urllib` and parses it using **BeautifulSoup**
- Extracts the results table (`<tr>` / `<td>` / `<th>` tags) and strips out the HTML with regex
- Builds a clean **pandas DataFrame** from the scraped rows and headers
- Handles finish times in both `MM:SS` and `H:MM:SS` format and converts them all into minutes
- Explores the data with:
  - Summary statistics (`describe()`)
  - A boxplot of overall finish times
  - A distribution plot (histogram + KDE) of finish times
  - A finish-time distribution comparison between male and female runners
  - Finish times grouped and compared by gender

## Tech stack

- Python 3
- `beautifulsoup4` + `lxml` — HTML parsing
- `pandas` / `numpy` — data cleaning and analysis
- `matplotlib` / `seaborn` — visualization
- Jupyter Notebook

## Getting started

### 1. Clone the repo

```bash
git clone https://github.com/<your-username>/race-results-web-scraper.git
cd race-results-web-scraper
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook web_scraper.ipynb
```

The notebook fetches the results page live, so you'll need an internet connection when you run it. If the target page's HTML structure ever changes, the table/header parsing cells may need small tweaks.

## Project structure

```
.
├── web_scraper.ipynb   # main notebook: scrape, clean, analyze
├── requirements.txt    # project dependencies
├── .gitignore
└── README.md
```

## What I learned

This project was a hands-on introduction to:
- Parsing real-world, messy HTML with BeautifulSoup and regex
- Turning scraped text into a usable pandas DataFrame (handling merged headers, stray whitespace, and inconsistent formatting)
- Writing logic that handles inconsistent data formats (race times in two different formats)
- Basic exploratory data analysis and visualization with seaborn/matplotlib

## Acknowledgements

Built while following [DataCamp's Web Scraping Using Python tutorial](https://www.datacamp.com/tutorial/web-scraping-using-python), then adapted and extended with additional data-cleaning logic.

## License

This project is for educational purposes.

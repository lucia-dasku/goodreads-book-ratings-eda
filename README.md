# Exploratory Analysis of Book Datasets with Python

A revised version of my undergraduate **Programming with Data** university project. This project uses Python to clean and explore a book dataset, investigate relationships between page count and book ratings, and demonstrate a small HTML-scraping exercise.

The structure and exploratory approach follows coursework instructions.

## Research question

*What factors contribute to readers' preferences?*

I explore the question using book-level average ratings, number of recorded ratings and page length. These variables describe patterns in an observed dataset; they do not identify individual reader preferences or establish causal effects.

## Main findings

- The original CSV contains **11,127 records**. After the documented filtering criteria, **9,664 English-language books** remain, including `eng`, `en-US`, `en-GB` and `en-CA`.
- Page count and average rating have a **weak positive Pearson correlation** (**r ≈ 0.203**).
- The number of recorded ratings and average rating have **almost no linear association** (**r ≈ 0.049**).
- Grouping books by page range and plotting the data makes distributions easier to inspect, but aggregate groups are not used to calculate the reported correlations.

The dataset represents a selected set of Goodreads records. Excluding books outside 51–1,500 pages and titles with broad “set/volume/collection” keywords affects the sample.

## Files

```text
Book_Ratings_Exploratory_Analysis.ipynb   # The complete exploratory analysis and scraping demonstration
data/
    books.csv                             # Original Kaggle-derived data (unchanged)
    scraped_books_sample.csv              # Original 20-item scraping sample, saved as CSV
requirements.txt
README.md
.gitignore
```

## How to run

Install **Python 3.10 or newer**, open a terminal in the repository's main directory and run:

```bash
python -m pip install -r requirements.txt
jupyter lab
```

Open `Book_Ratings_Exploratory_Analysis.ipynb` and choose **Run All**. All input file paths are relative to the repository root, so start Jupyter from that directory. The notebook has saved outputs for browsing on GitHub.

The scraping section uses the saved 20-item sample by default, which allows the notebook to run without an internet connection. To fetch the current first page of the [Books to Scrape](https://books.toscrape.com/) demonstration site instead, change `RUN_LIVE_SCRAPE = False` to `True`. The site uses randomly assigned fictional prices and ratings, not real customers' evaluations.

## Revisions from the university submission

The following issues were corrected while retaining the original notebook's workflow:

1. Rejoined split author fields in four malformed CSV records rather than discarding author text.
2. Included all four English-language codes in the main sample instead of only `eng`.
3. Calculated correlations using individual book records rather than seven page-length group means; also corrected the discussion of these results.
4. Corrected a standard-deviation output label, a Seaborn variable typo and explanations that overstated what the dataset could show.
5. Kept the web-scraping demonstration within the main notebook and made it reproducible using the saved sample.

No new predictive models or production pipeline were added. The original submitted coursework is stored separately and is not included here.

## Data and references

- [Goodreads-books dataset on Kaggle](https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks) — main dataset source. Confirm its current reuse terms before redistributing the CSV.
- [Books to Scrape](https://books.toscrape.com/) — purpose-built practice storefront used for the scraping method demonstration.
- [pandas](https://pandas.pydata.org/), [Matplotlib](https://matplotlib.org/), [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) — library documentation.

**Project type:** Undergraduate exploratory data analysis (portfolio revision). A software code licence has not been selected yet.

# AutoIndex, Car Marketplace Analysis Tool

This is a prototype I built around online car marketplace data. Browsing listings is fine if you want one car, but comparing across brands, years, and regions gets painful fast, so this project was my attempt to make that experience less dumb.

## What it does
- Scrapes live listings (sample DB included so it runs without scraping)
- Cleans and stores everything in SQLite
- Exposes a small Flask API + simple React UI
- Adds charts for things like:
  - average price by brand
  - price vs model year
  - regional price differences

## Tech stack
- **Backend**: Python (Flask, SQLAlchemy, pandas, BeautifulSoup)
- **Storage**: SQLite
- **Frontend**: React + Chart.js
- **Extra visuals**: matplotlib

## How to run

### 1. Scraper (simplest)
If you just want to grab some listings and see raw data (and the site hasn’t changed its HTML):
python ss_scraper.py
This fetches data and stores it into SQLite.

## 2. Backend API
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
(edit if needed)
export FLASK_APP=api.py
flask run

## 3. Frontend
npm install
npm start

## Demo data
DB already includes a snapshot so you don’t have to scrape to try it.


## Screenshots
- **Listings**  
  ![Main page listings](public/readme-assets/main_page.png)

- **Listing details**  
  ![Opening a car listing](public/readme-assets/main_page_scrape.png)

- **Comparing cars**  
  ![Car comparing](public/readme-assets/Compare.png)

- **Regional analysis**  
  ![Price by region](public/readme-assets/Analysis.png)

## Limitations
– Only tested on a subset of brands, it was a first “big” project
– Scraper breaks if the site changes markup
– Cleanup / dedupe is basic

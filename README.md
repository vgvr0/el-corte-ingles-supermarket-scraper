# Web Scraper for Online Supermarket

This Python script performs web scraping on various product categories from an online supermarket and saves the product details into a CSV file.

## Features

- Uses SeleniumBase Driver for web navigation and BeautifulSoup for parsing HTML.
- Accepts cookies before starting the scraping process.
- Iterates over multiple categories, each with its own URL.
- Extracts the number of pages for each category.
- Extracts the total number of ads in each category.
- For each page, it extracts the HTML content and parses it to find all ads.
- Each ad's details (ID, date, category, title, price, href, img_src) are saved in a dictionary.
- The dictionary is appended to a list of all ads.
- The list of ads is saved to a CSV file using the `eci_csv` function.

## Usage

1. Ensure that all required Python libraries are installed. These include os, re, csv, time, random, sqlite3, datetime, BeautifulSoup, and SeleniumBase.
2. Run the script. It will start by initializing the SeleniumBase Driver and maximizing the window.
3. The script will then start the scanning process, iterating over each category and each page within the category.
4. For each ad found, it will extract the details and save them to a CSV file.

## Note

This script is intended for educational purposes only.

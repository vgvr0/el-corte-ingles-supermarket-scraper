# Web Scraper for Online Supermarket

This Python script performs web scraping on various product categories from an online supermarket and saves the product details into a CSV file.

## Features

- Uses `SeleniumBase Driver` for web navigation and BeautifulSoup for parsing HTML.
- `SeleniumBase` automatically downloads the necessary driver version.
- Accepts cookies before starting the scraping process.
- Iterates over multiple categories, each with its own URL.
- Extracts the number of pages for each `category`.
- Extracts the total number of ads in each `category`.
- For each page, it extracts the HTML content and parses it to find all ads.
- Each ad's details (`ID`, `date`, `category`, `title`, `price`, `href`, `img_src`) are saved in a dictionary.
- The dictionary is appended to a list of all ads.
- The list of ads is saved to a CSV file using the `eci_csv` function.

## Usage

1. Ensure that all required Python libraries are installed. These include `os`, `re`, `csv`, `time`, `random`, `sqlite3`, `datetime`, `BeautifulSoup`, and `SeleniumBase`.
2. Run the script. It will start by initializing the SeleniumBase Driver and maximizing the window.
3. The script will then start the scanning process, iterating over each category and each page within the category.
4. For each ad found, it will extract the details and save them to a `CSV file`.

## Improvements: 

### SeleniumBase Driver Initialization

It starts by initializing the SeleniumBase Driver to navigate the web and avoid being detected as a bot. Here is how the driver is set up:

```python
from seleniumbase import Driver

driver = Driver(
    browser="chrome",
    uc=True,
    headless2=False,
    incognito=False,
    agent='Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36',
    do_not_track=True,
    undetectable=True
)
```
Here’s what each option means:

`browser="chrome"`: This indicates that you’re using Google Chrome as your browser.

`uc=True`: This enables “Undetectable Chrome” capabilities that make it harder for websites to detect that you’re using a bot.

`headless2=False`: This indicates that you want the browser to display while the script is running. If you change this to True, the browser will run in the background.

`incognito=False`: This indicates that you don’t want the browser to run in incognito mode. If you change this to True, the browser will run in incognito mode.

`agent='Mozilla/5.0` (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36': This sets the user agent of the browser. By changing the user agent, you can make your bot appear like a normal browser.

`do_not_track=True`: This enables the “Do Not Track” setting in the browser.


## Note

This script is intended for educational purposes only.

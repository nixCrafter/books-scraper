# Books Scraper

This project is a web scraper built with [Scrapy](https://scrapy.org/) to extract book information from [Books to Scrape](http://books.toscrape.com) and store it in a MongoDB database.

## Features

- Scrapes book titles, prices, and URLs.
- Stores data in a MongoDB database.
- Avoids duplicates by checking for existing entries.
- Handles pagination to scrape the entire catalog.
- Rotates user-agents to reduce the chance of being blocked.
- Configurable settings for MongoDB connection, logging, and crawling behavior.

## Requirements

- Python 3.6+
- Scrapy
- pymongo
- MongoDB

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/books-scraper.git
    cd books-scraper
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## Configuration

The main configuration is located in `books/books/settings.py`.

-   **MongoDB Connection:**
    -   `MONGO_URI`: The MongoDB connection string (defaults to `mongodb://localhost:27017`).
    -   `MONGO_DATABASE`: The database to store the books in (defaults to `books_db`).

-   **Logging:**
    -   `LOG_LEVEL`: The logging level (defaults to `WARNING`).
    -   `LOG_FILE`: The file to store logs in (defaults to `book_scraper.log`).

-   **Crawling Behavior:**
    -   `DOWNLOAD_DELAY`: The delay between requests (defaults to `2` seconds).
    -   `CONCURRENT_REQUESTS_PER_DOMAIN`: The number of concurrent requests to a single domain (defaults to `1`).

## Usage

To run the scraper, navigate to the `books` directory and use the `scrapy` command:

```bash
cd books
scrapy crawl book
```

The scraper will start, and you will see log output in the console and in the `book_scraper.log` file (as configured in `settings.py`). The scraped data will be saved to the `books` collection in the `books_db` database in your MongoDB instance.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
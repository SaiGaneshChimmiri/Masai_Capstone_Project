# Data Pipeline

The pipeline uses `requests` and `BeautifulSoup` against Books to Scrape. I used the first five catalogue pages because the assignment allows that scope and it gives 100 book cards on the practice site. Each product is cleaned before it reaches SQLite.

The required conversion is a fixed project constant: **1 GBP = 105.50 INR**. It is not fetched from a currency API.

For parsing failures, numeric fields use median imputation. Rows missing the title/category needed for a meaningful catalogue record are dropped. The final SQLite schema has a `categories` parent table and a `books` child table linked by `category_id`.

💡 Project Description:

The eCourts CauseList Scraper is a Flask-based web application that automates the process of retrieving daily cause lists and case details from the official eCourts India website
.
It allows users to select a State, District, Court Complex, and Date to instantly fetch and display the scheduled cases for that day.

This project helps lawyers, clients, and researchers save time by avoiding manual searches on the eCourts portal. It also allows downloading judge-wise cause lists as separate PDF files for offline reference.

The scraper uses Selenium WebDriver to interact with the dynamic dropdowns and buttons of the eCourts site (which uses AJAX and Captcha). Extracted data is parsed, structured, and displayed in a clean, interactive dashboard built using Flask and Bootstrap.

⚙️ Key Features

Smart Case Search

Allows users to input State, District, Court Complex, and Date.

Fetches cause list for the selected parameters automatically.

Captcha-Aware Fetching

Detects and displays captcha images.

Lets users enter captcha text for validation to continue fetching.

Dynamic Data Extraction

Automatically parses case tables, judge lists, and PDF download links.

Judge-wise PDF Download

Option to download individual or all cause list PDFs categorized by judges.

Attractive User Interface

Simple and responsive dashboard built using Bootstrap 5.

Displays search results neatly in a scrollable card layout.

Error Handling

Displays messages for empty results or failed fetches (e.g., due to incorrect inputs or unavailable data).

Automation

Automates browser interactions like clicking, selecting dropdowns, and waiting for results.

🧰 Key Technologies Used
Technology	Purpose / Role
Python 3.x	Core programming language used for backend logic
Flask	Lightweight web framework to handle routes, forms, and rendering templates
Selenium WebDriver	Used to automate browser interactions and scrape dynamic content from eCourts
BeautifulSoup (bs4)	For parsing HTML pages and extracting tables or PDF links
Bootstrap 5 (HTML/CSS/JS)	Used for responsive and elegant front-end design
Jinja2	Flask’s templating engine to dynamically display data in HTML
JSON & OS modules	For storing results temporarily and managing downloaded files
WebDriverWait / ExpectedConditions (Selenium)	To handle AJAX-based dropdown loading and ensure reliability
ChromeDriver / EdgeDriver	Selenium drivers for automated browser control
🖥️ Workflow / System Flow

User opens the web app (Flask interface).

Enters details: State → District → Court → Date

Flask calls Selenium automation (fetcher.py):

Opens eCourts website

Selects dropdowns and fills date

Handles captcha (if any)

Clicks “Search”

The scraper fetches and returns the HTML of the cause list page.

The parser extracts:

Case serial numbers

Case details (type, number, parties, etc.)

Judge-specific PDF links (if available)

Flask displays results in a beautiful table.

Users can download judge-wise PDFs directly.

🧑‍💻 Use Cases

Lawyers checking daily court cause lists quickly.

Researchers analyzing case load and scheduling trends.

Automation tool for law firms to manage daily case lists automatically.

Training project for students learning Flask + Selenium integration.

🚀 Future Enhancements

Integrate database (MySQL / SQLite) to save fetched results.

Add email/SMS alerts when a particular case appears in a cause list.

Include OCR-based captcha solver for full automation.

Extend to High Court / Supreme Court cause lists.

Add login & history tracking for frequent users.

🧩 Project Folder Structure
ecourts-flask-selenium/
│
├── app.py                   # Main Flask app
├── configs/
│   └── config.py             # App configuration (URL, headless mode, etc.)
├── ecourts/
│   ├── fetcher.py            # Selenium automation script
│   ├── parsers.py            # HTML parsing logic
│   ├── downloader.py         # PDF download management
│   └── utils.py              # Utility functions (optional)
├── web/
│   ├── routes.py             # Flask routes (views)
│   ├── templates/
│   │   └── index.html        # Main web page
│   └── static/
│       ├── style.css         # Styling
│       └── scripts.js        # Optional JS
├── downloads/                # Saved PDFs
├── results/                  # JSON outputs
└── requirements.txt          # List of dependencies

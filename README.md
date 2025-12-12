# JOSAA Seat Allotment Scraper & Results Viewer

A web-based tool to scrape and view JOSAA (Joint Seat Allocation Authority) seat allotment results from the official portal.

**Live Demo:** [rkrrahman-786.github.io](https://rkrrahman-786.github.io)

---

## Features

- 🌐 **Interactive Web Interface** – Browse and search seat allotment results directly in the browser
- 📥 **PDF Scraper** – Automated Python script to download allotment PDFs per round
- 📊 **Results Table** – Display allotment data (Institute, Program, Rank, Quota, etc.)
- 🔍 **Real-time Search & Filter** – Find seats by institute, program, category, and more
- ⚡ **Dynamic Loading** – Handles pages that load content on scroll
- 🎯 **Multi-Round Support** – Iterate through all available rounds automatically

---

## Project Structure

```
.
├── index.html                    # Main web interface (GitHub Pages)
├── styles.css                    # Styling
├── script.js                     # Frontend logic & interactivity
├── scrape_josaa_interactive.py   # Python scraper for PDFs
├── requirements.txt              # Python dependencies
├── README.md                     # This file
├── _config.yml                   # Jekyll configuration (GitHub Pages)
└── assets/                       # Images, logos, etc.
```

---

## Web Interface (GitHub Pages)

The web interface is hosted at **[rkrrahman-786.github.io](https://rkrrahman-786.github.io)** and provides:

1. **Search & Filter** – Find allotment results by round, institute, program, category, quota, etc.
2. **Table View** – Display results with sortable columns
3. **Responsive Design** – Works on desktop and mobile devices

### Accessing the Web Interface

Simply visit: **https://rkrrahman-786.github.io**

No setup required – it's a static web app hosted via GitHub Pages.

---

## Python Scraper

### Setup

Requires Python 3.8+ and Playwright for browser automation.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rkrrahman-786/eduaakaashaa.git
   cd eduaakaashaa
   ```

2. **Create a virtual environment (recommended):**
   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

3. **Install dependencies:**
   ```powershell
   python -m pip install --upgrade pip
   python -m pip install -r requirements.txt
   python -m playwright install
   ```

### Usage

Run the interactive scraper with a visible browser:

```powershell
python scrape_josaa_interactive.py --headed --out downloads
```

**Steps:**
1. A browser window opens at the JOSAA allotment portal
2. Fill in the form fields (or leave them as default to select ALL options)
3. Click the page's submit/search button
4. **In the terminal:** Press Enter or wait for the script to auto-detect the click
5. The script will:
   - Iterate through each available round
   - For each round, re-submit the query with "ALL" for other fields
   - Scroll to load all content
   - Collect and download all PDF links into `downloads/<Round Name>/`

### Options

```bash
# Save to a custom output directory
python scrape_josaa_interactive.py --headed --out my_pdfs

# Run headless (no visible browser; less interactive feedback)
python scrape_josaa_interactive.py --out downloads
```

### How It Works

- **Page Detection:** The script detects form submission via JavaScript click listeners
- **Terminal Control:** You can press Enter in the terminal to start scraping immediately after clicking submit
- **Navigation Handling:** Waits for page loads using `networkidle` and `wait_for_load_state()`
- **PDF Capture:** Captures both direct PDF links (`<a href="*.pdf">`) and PDF responses from the server
- **Round Iteration:** Automatically finds the round selector and iterates through each available round option

### Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError: No module named 'playwright'` | Run `python -m pip install playwright` and `python -m playwright install` |
| No browser opens | Ensure Playwright browsers are installed: `python -m playwright install` |
| Script doesn't detect submit | Try pressing Enter in the terminal to trigger scraping manually |
| "Execution context was destroyed" error | The page navigated during form interaction – the script now handles this with timeouts and retries |
| No PDFs found | The site may use blob URLs or embedded viewers; check the browser DevTools Network tab for PDF responses |

---

## GitHub Pages Configuration

The repository is configured for automatic GitHub Pages deployment via:

- **Repository:** `rkrrahman-786/eduaakaashaa`
- **Branch:** `main`
- **URL:** `https://rkrrahman-786.github.io`

### Files

- **`_config.yml`** – Jekyll configuration (theme, plugins, build settings)
- **`index.html`** – Main page (static HTML, not Jekyll-processed)
- **`README.md`** – Documentation (displayed on the repo homepage)

### Deployment

Commits to the `main` branch automatically trigger a GitHub Pages build. The site updates within seconds.

---

## Technologies Used

### Frontend
- **HTML5** – Structure
- **CSS3** – Styling & responsive layout
- **Vanilla JavaScript** – Search, filtering, table rendering

### Backend/Scraper
- **Python 3.8+** – Scripting language
- **Playwright** – Browser automation (Chromium, Firefox, WebKit)

### Hosting
- **GitHub Pages** – Static site hosting (free)
- **Jekyll** – Static site generator (optional, for templating)

---

## Contributing

To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -am 'Add feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## Legal & Disclaimer

This tool is for **educational and informational purposes only**. Users are responsible for:

- Complying with the JOSAA portal's Terms of Service and robots.txt
- Respecting rate limits and server load
- Using scraped data responsibly and in accordance with applicable laws

The authors are not affiliated with JOSAA or the Indian government. Use at your own risk.

---

## License

This project is open source and available under the **MIT License** – see the LICENSE file for details.

---

## Support & Feedback

- **GitHub Issues:** [Report bugs or request features](https://github.com/rkrrahman-786/eduaakaashaa/issues)
- **Discussions:** [Ask questions or share ideas](https://github.com/rkrrahman-786/eduaakaashaa/discussions)

---

## Author

**rkrrahman-786**  
GitHub: [@rkrrahman-786](https://github.com/rkrrahman-786)

---

## Changelog

### v1.0.0 (Current)
- ✅ Interactive web interface for browsing seat allotment results
- ✅ Python scraper for automated PDF downloads
- ✅ Multi-round support
- ✅ GitHub Pages hosting
- ✅ Responsive design

---

**Last Updated:** December 2025
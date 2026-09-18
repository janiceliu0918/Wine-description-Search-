# # 🍷 Wine Market Intelligence Agent

An automated market intelligence and pricing tool designed to streamline the wine procurement and selection process. 

This agent automates data gathering from multiple sources to provide a comprehensive buyer's brief, including global pricing benchmarks, consumer sentiment, and localized landed cost calculations for the BC market.

## ✨ Core Features

* **Global Pricing Benchmark:** Scrapes Wine-Searcher for global average prices and converts them to CAD.
* **Consumer Sentiment Analysis:** Retrieves Vivino ratings, review counts, and common flavor profiles to gauge market acceptance.
* **Automated Landed Cost Calculator:** Calculates the final landed cost for the British Columbia market (incorporating CETA 0% duty for EU wines, LDB markups, GST, and container deposit).
* **Winery Tech Sheet Parsing:** Utilizes LLM (Claude) to extract grape blend proportions, aging potential, and terroir details directly from winery websites.
* **Report Generation:** Outputs structured, easy-to-read buyer's briefs in the terminal and exports them to the `reports_output` directory.

## 🚀 Quick Start

### 1. Prerequisites
Ensure you have Python 3.8+ installed on your system.

### 2. Installation
Clone or download this repository, then install the required dependencies:

```bash
pip install -r requirements.txt

```

## Runtime data and public repository scope

The application initializes an empty SQLite database through `init_db()` at startup.
No committed query database is needed to run it. Configure credentials locally using
`.env.example`; do not commit `.env`, generated reports or runtime databases.

The previously tracked database contained a saved query/report. Its provenance and
publication approval were not established, so it has been removed from this branch.
The existing `*.db` ignore rule prevents new untracked database files from being added
normally; it does not remove prior commits. Historical copies remain in Git history
and require a separate publication review. No history rewrite has been performed.

This change does not verify live provider/scraper availability, production deployment,
or the current correctness of pricing assumptions. The existing calculator and sentiment
tests cover specific behavior only.

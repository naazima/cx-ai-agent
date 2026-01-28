# cx-ai-agent
AI-powered customer experience system for automated review analysis and support resolution

# Dr. Martens AI Customer Support System

An intelligent customer experience platform that automates review analysis, 
complaint classification, and support resolution using hybrid AI approaches.

## Overview

This project addresses real-world CX challenges by combining web scraping, 
NLP classification, and autonomous agent capabilities to handle customer 
reviews and complaints at scale.

## Features

- **Automated Review Collection**: Direct Yotpo API integration for extracting customer reviews
- **Intelligent Classification**: Hybrid system combining keyword triage with RAG-based processing
- **Priority Scoring**: Automated urgency assessment based on sentiment and issue type
- **Autonomous Resolution**: Agent capabilities for refunds, repairs, and exchanges
- **Multi-format Export**: CSV, Excel (with formatting), and JSON output

## Tech Stack

| Category | Technologies |
|----------|-------------|
| Languages | Python 3.10+ |
| Web Scraping | Selenium, Requests, BeautifulSoup |
| AI/ML | OpenAI API, LangChain, RAG architecture |
| Data Processing | Pandas, OpenPyXL |
| Security | python-dotenv, rate limiting, spend controls |

## Architecture

The system uses a three-stage pipeline:

1. **Data Collection** → Yotpo API scraper with authentication handling
2. **Classification** → Hybrid keyword + RAG classifier with 5 issue categories
3. **Resolution** → Autonomous agent with transaction capabilities

## Issue Categories

- Repair requests (For Life warranty program)
- Refund processing (with discount code generation)
- Sizing/exchange handling
- Quality complaints
- Customer service escalations

## Installation

git clone https://github.com/yourusername/drmartens-ai-customer-support.git
cd drmartens-ai-customer-support
pip install -r requirements.txt
cp .env.example .env
# Add your API keys to .env

## Usage

from src.scrapers.yotpo_scraper import YotpoScraper
from src.classification.review_classifier import ReviewClassifier

# Scrape reviews
scraper = YotpoScraper()
reviews = scraper.get_reviews(min_rating=3)

# Classify and prioritize
classifier = ReviewClassifier()
classified = classifier.process(reviews)

## Security Considerations

- API keys stored in environment variables
- Rate limiting to prevent abuse
- Spend controls for AI API usage
- No customer PII stored in repository

## Lessons Learned

- Bright Data authentication challenges led to building custom network inspection tools
- JavaScript-rendered content required Selenium for reliable extraction
- Hybrid classification outperforms pure ML for domain-specific tasks
- Cost management is critical for production AI systems

## Future Improvements

- Webhook integration for real-time review processing
- Dashboard for monitoring agent performance
- Multi-language support
- Integration with CRM systems

## Certification 

MIT Professional Education: Applied Data Science Program: Leveraging AI for Effective Decision-Making
```

## Step 4: Create Supporting Files

**requirements.txt:**
```
selenium>=4.0.0
requests>=2.28.0
beautifulsoup4>=4.11.0
pandas>=1.5.0
openpyxl>=3.0.0
python-dotenv>=1.0.0
openai>=1.0.0
langchain>=0.1.0
```

**.gitignore:**
```
.env
__pycache__/
*.pyc
data/*.csv
data/*.xlsx
.DS_Store
venv/
```

**.env.example:**
```
OPENAI_API_KEY=your_key_here
YOTPO_APP_KEY=your_key_here

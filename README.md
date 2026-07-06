# Website to AI Brochure Generator

This project turns any company website into a clean, structured brochure using an LLM. You give it a URL, and it automatically scrapes the site, picks the most relevant pages, and generates a short markdown summary that explains what the company does.

## What it does

You run something like:

```python
create_brochure("Hugging Face", "https://huggingface.co")

And the system handles everything: it loads the homepage, extracts all links, uses an LLM to decide which pages matter (About, Careers, Docs, etc.), scrapes those selected pages, combines all content into one block, sends it to an LLM, and generates a structured brochure in markdown.

Output

The final output is a markdown document with sections like Company overview, Products or services, Company culture, Customers, and Careers. The goal is to take messy website data and turn it into something readable in seconds.

Tech stack

Python, OpenAI API (GPT-4o / GPT-5), BeautifulSoup for web scraping, Requests for HTTP handling, dotenv for environment variables, and IPython for notebook display.

Architecture

Website URL → Homepage scraping → Extract links → LLM filters important links → Scrape selected pages → Combine content → LLM generates brochure → Markdown output

Why this project

Most websites are not built for quick understanding. They contain navigation, footers, and unrelated noise. This project uses an LLM to filter out irrelevant content and focus only on meaningful information, producing a clean summary of the company.

Limitations

This is a prototype. It works best on clean, static websites, may miss important pages, depends on LLM-based link selection, only goes one level deep, and has no caching or performance optimization.

Example usage
create_brochure("Hugging Face", "https://huggingface.co")
Future improvements

Smarter link ranking without relying heavily on LLMs, multi-level crawling with depth control, caching scraped pages, a simple web interface using Streamlit or FastAPI, and better handling of JavaScript-heavy websites.

Summary

This project shows how LLMs can be used to extract meaning from messy web data and turn it into structured, readable output. It is a simple pipeline, but demonstrates real-world LLM orchestration.

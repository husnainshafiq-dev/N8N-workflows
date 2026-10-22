# Google Maps Lead Scraper

Finds businesses on Google Maps for any search and location, cleans the data and exports ready-to-use leads.

## Flow

1. **Search Parameters**: set the query (e.g. "restaurants"), location, max results, website filter and language.
2. **Apify Google Places crawler** scrapes matching places, including contact details.
3. **Clean and Deduplicate** (JavaScript): normalizes Apify's response shapes, extracts name, category, address, phone, email, website, rating and social links, filters out leads with no contact info, and removes duplicates.
4. Two outputs:
   - Leads **with a phone number** are appended to **Google Sheets**.
   - **All** cleaned leads are exported as a downloadable **CSV**.

**Tip:** set `websiteFilter` to `withoutWebsite` to find businesses that need a website, which makes good leads for web agencies.

## Setup

- Apify API token in the Search Parameters node.
- Google Sheets credential and your sheet ID; the sticky note in the workflow lists the header row to create.
- Uses Apify's synchronous endpoint, suitable for up to about 100–150 results per run.

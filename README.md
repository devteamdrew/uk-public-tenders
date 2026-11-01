# UK Public Tenders Scraper – Contracts Finder & Find a Tender

Get every new UK public sector tender, contract opportunity and award from Contracts Finder and Find a Tender (FTS) in one clean feed. Filter by keyword, CPV code, value, region, deadline and SME suitability. Official open APIs, no login. Pay per result.

**[Run it on Apify →](https://apify.com/devteamdrew/uk-public-tenders?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=hero)** (pay per result, free Apify account to start)


**UK Public Tenders Scraper** by Moxie: fast, reliable and polite, built on official/public data sources.

## What can it do?

- Bid teams: a daily feed of new UK government tenders in your sector (schedule with incremental mode)
- Lead generation for suppliers: buyer names and contact emails for relevant contracts
- Competitor intelligence: who won which public contracts and for how much (award stage)
- Market research on public sector spend by CPV code and region
- Feeding tender notices into an LLM for bid/no-bid triage

## Data source

The official Contracts Finder OCDS search API (`contractsfinder.service.gov.uk`) and the Find a Tender service OCDS API (`find-tender.service.gov.uk`), both published by the UK Government under the Open Government Licence v3.0. No login, no key.

## Features

- **Pay only for results** (pay-per-event pricing, no monthly rental)
- **Incremental mode**: scheduled runs return only items you haven't received before
- **LLM-ready output**: optional compact Markdown per item for RAG / AI agents
- **Polite rate limiting** with automatic retries and backoff
- Clean, flat JSON you can export as CSV, Excel, JSON or via API


## Quick start

1. Create a free account at [apify.com](https://apify.com/devteamdrew/uk-public-tenders?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=quickstart) and copy your API token.
2. `export APIFY_TOKEN=...`
3. Run one of the examples:

```bash
bash examples/run.sh          # curl
node examples/run.js          # JavaScript (apify-client)
python examples/run.py        # Python (apify-client)
```

Example input ([examples/input.json](examples/input.json)):

```json
{
  "keywords": [
    "software",
    "IT services",
    "digital"
  ],
  "lastDays": 7,
  "maxItems": 20
}
```

## FAQ

**What is the difference between Contracts Finder and Find a Tender?**
Contracts Finder lists lower-value public contracts (mainly England, from about £12k/£30k). Find a Tender (FTS) carries higher-value notices across the UK under the Procurement Act 2023. This actor merges both.

**Do I need an account or API key?**
No. Both are free, open government APIs.

**Can I get awarded contracts and suppliers?**
Yes, set the notice stage to `award`; `suppliers` and `awardValue` are filled in.

**How do I only see live opportunities?**
Keep the stage as `tender` and tick 'Only open'.

## Use with AI agents (MCP)

Add `https://mcp.apify.com/?actors=devteamdrew/uk-public-tenders` as an MCP server in Claude, Cursor or any MCP client.

## Pricing

See the [Apify Store page](https://apify.com/devteamdrew/uk-public-tenders?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=pricing) for current pay-per-result pricing.

## Sample data

Browse real sample rows, download a free CSV sample and see ready-made feeds at [rowsift.co.uk](https://rowsift.co.uk/?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=sample-data).

## More data actors

- [Bluesky Scraper – Posts, Profiles & Search](https://apify.com/devteamdrew/bluesky-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [UK Companies House Scraper – Companies & Directors](https://apify.com/devteamdrew/companies-house-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [UK Planning Applications Scraper – 400+ Councils & Postcodes](https://apify.com/devteamdrew/uk-planning-applications?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [Hacker News Scraper – Stories, Comments & Jobs](https://apify.com/devteamdrew/hacker-news-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [npm Package Scraper – Downloads & Dependencies](https://apify.com/devteamdrew/npm-package-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [GitHub Trending Scraper – Repos, Stars & Developers](https://apify.com/devteamdrew/github-trending-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [Mastodon Scraper – Fediverse Hashtags, Accounts & Trends](https://apify.com/devteamdrew/mastodon-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [Lemmy Scraper – Posts, Comments & Communities (Fediverse)](https://apify.com/devteamdrew/lemmy-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [SEC EDGAR Scraper – 10-K, 10-Q & 8-K Filings](https://apify.com/devteamdrew/sec-edgar-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [arXiv Scraper – Paper Search, Abstracts & Authors](https://apify.com/devteamdrew/arxiv-scraper?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)
- [CQC Care Homes & Providers Scraper – UK Care Directory Leads](https://apify.com/devteamdrew/uk-cqc-care-providers?utm_source=github&utm_medium=readme&utm_campaign=uk-public-tenders&utm_content=more)

## License

Examples in this repository are MIT licensed. The actor itself runs on the Apify platform.

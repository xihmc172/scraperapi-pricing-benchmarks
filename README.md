# Best web scraping tools: will it clear your target site, what does a year cost, and why do the benchmarks disagree? (with ScraperAPI's full plan and credit table)

For plain pages behind ordinary bot checks, ScraperAPI's Hobby plan is the cheapest sensible starting point in this comparison: **$49/mo buys 100,000 credits and 20 concurrent threads**, or $44.10/mo billed annually. Heavily protected targets are a different budget entirely. Zyte and Bright Data are the tools independent tests keep rewarding there, and both charge accordingly. If the output you need is clean markdown for a RAG pipeline, Firecrawl is the name that recurs in agent and retrieval threads, with one caveat covered below.

Two things on this page are hard to find elsewhere. Every ScraperAPI plan is converted from credits into actual request counts using the company's own multipliers, because 100,000 credits is not 100,000 pages. And two independent benchmark suites are laid side by side, because on the same set of tools they disagree by up to 59 percentage points.

> **Quick pick:** start on the free plan (1,000 credits/month, 5 concurrent threads) or use the 7-day trial that comes with 5,000 credits and no credit card. If your test URLs come back clean, Hobby gives you 100,000 credits, 20 threads and US/EU geotargeting for $49/mo, or $44.10/mo billed annually at $529.20/year.
>
> 👉 [See ScraperAPI's current plans and pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Every ScraperAPI plan, side by side

| Plan | Credits/month | Concurrent threads | Geotargeting | Price | Link |
| --- | --- | --- | --- | --- | --- |
| Free | 1,000 | 5 | Not stated | $0 | [Start free](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | 100,000 | 20 | US & EU | $49/mo, or $44.10/mo annual ($529.20/yr) | [Open Hobby](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | 50 | US & EU | $149/mo | [Open Startup](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | 3,000,000 | 100 | Country-level | $299/mo, or $269.10/mo annual ($3,229.20/yr) | [Open Business](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | 200 | Country-level | See plan page | [Open Scaling](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | 10,500,000 | 300 | Country-level | See plan page | [Open Professional](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | 21,500,000 | 500 | Country-level | See plan page | [Open Advanced](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | 22,000,000+ | 500+ | Country-level | Custom, contact sales | [Request Enterprise pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Three details from that table are worth pulling out. Analytics history is limited to the last 30 days on Hobby and Startup, then unlimited from Business upward. Country-level geotargeting starts at Business; Hobby and Startup only cover the US and EU, which rules out a lot of regional pricing work. And Scaling, Professional and Advanced appear in the official plan table with credits and thread counts but without prices, so budget those through the plan page rather than from a listicle. The Startup rate above is the $149/mo figure published in plan comparisons; confirm it at checkout.

## What a credit buys, and why 100,000 credits is not 100,000 pages

ScraperAPI charges one credit for a standard page and more for everything that makes a page hard. These are the published multipliers:

| Request type | Credits per request |
| --- | --- |
| Standard HTML page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google or Bing SERP, including subdomains | 25 |
| LinkedIn | 30 |
| Bot-protection bypass (Cloudflare, Turnstile, DataDome, PerimeterX/HUMAN, Akamai) | 10 |
| JavaScript rendering (`render=true`) | 10 |
| Premium proxies | 10 |
| Screenshot | 10 |
| Premium proxies plus JS rendering | 25 |
| Ultra premium | 30 (75 with rendering) |

Geotargeting, sessions, device type, output format and auto-parsing add nothing to the bill.

So a Hobby subscription is 100,000 plain pages, or 20,000 Amazon pages, or 4,000 Google SERP requests, or 10,000 requests that needed a Cloudflare bypass. Stack features and the cost is worse than addition suggests: premium proxies plus rendering is 25 credits, not 20. That is why the number to check before committing to any plan is the per-URL cost from the Domain Cost Estimator in the dashboard, which quotes the exact credit cost for a specific URL rather than an average.

Convert that into money and the shape of the pricing becomes clear. Hobby works out to **$0.49 per 1,000 credits** ($0.441 on annual billing). Business drops to roughly **$0.10 per 1,000 credits**, which is where the volume discount actually lives. On a bypass-heavy workload, though, Hobby's 10 credits per protected request turns that $0.49 into **$4.90 per 1,000 requests**, while Bright Data sells Web Unlocker at $1.50 per 1,000 successful requests on pay-as-you-go. Cheap credits and cheap successful requests are not the same thing.

👉 [Compare Hobby and Business against your own monthly request count](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Who should pick ScraperAPI, and who shouldn't

ScraperAPI does one job: you send a URL, it returns the page, and proxy rotation, headless browsers, CAPTCHA handling and retries happen behind that single call. Your parsing logic stays yours, which is the point for teams that already have selectors or a pipeline and just want the anti-blocking plumbing removed.

It fits developers who want a simple API that handles proxies and rendering, on sites that are not aggressively defended. It does not fit two groups. The first is anyone whose target list is mostly Cloudflare, DataDome or PerimeterX at volume. Independent testing puts ScraperAPI's ceiling at **84% success on heavily protected sites even at its strongest configuration**, against 93% for Zyte in the same Proxyway suite. The second is teams that want ready-made parsers for Amazon or Google at scale. Oxylabs and Bright Data ship structured output for those targets; with ScraperAPI you are paying 5 or 25 credits per request and still writing the extraction yourself.

## Why two benchmarks give opposite rankings for the same tools

This is the part the listicles skip. The same tools were tested by Proxyway and by String, and the results barely resemble each other.

| Tool | Proxyway (heavily protected sites) | String benchmark |
| --- | --- | --- |
| Zyte | 93%, 1st | 68%, 11th |
| Decodo | ~87%, best value | 50.6% |
| Oxylabs | 85.8% | 69% |
| ScrapingBee | 84% at light load, 73% under heavy load | 73% |
| ScraperAPI | — | 64% default, 84% at strongest setting |
| Firecrawl | 33.69%, lowest, but fastest at 7.92s | 80%, 4th |

Zyte wins one suite and lands 11th in the other. Firecrawl goes from last place on protected pages to fourth overall. For ScraperAPI the gap is internal: **64% out of the box, 84% once configured at its strongest setting**, a 20-point swing that has nothing to do with the target site and everything to do with which options you switched on.

Two lessons follow. Default settings are not a fair test of any of these tools, so a benchmark run without tuning understates what you will actually get. And a ranking is only valid for the URL list it was run against, which is why the sensible advice from the people who ran one of these suites is to test with your own URLs. Twenty of your real targets on a free tier will tell you more than any leaderboard.

The Proxyway write-up also mentions a 69% figure for ScraperAPI in a sentence where the subject is ambiguous, so it is left out here rather than repeated as fact.

## Competitor pricing, with the billing period attached

| Tool | Published starting price | What the number actually means |
| --- | --- | --- |
| Bright Data | $1.50 per 1,000 successful requests | Pay-as-you-go Web Unlocker; Scale plan is $499/mo then $1.30/1K; failed requests bill when custom Unlocker features are on. 5,000 free requests/mo |
| Zyte | From $0.13 per 1,000 requests | A floor rate that moves with target difficulty; $5 free credit |
| Firecrawl | $19/mo, or $16/mo on annual billing | 1,000 free credits/mo, 1 credit per page; the two figures are different billing cycles, not a price cut |
| Oxylabs | $15/mo, or $49/mo depending on the source | The $49 tier covers up to 98,000 results; per-target rates run $0.50/1K for Amazon, $1.00/1K for Google, $1.15/1K general, $1.35/1K with rendering |
| ScrapingBee | $49/mo (Freelance) | 1,000 free credits; slowest API in the Proxyway test at around 24 seconds |
| Decodo | $19/mo | Free plan available; most stable under load in the Proxyway test |
| Scrapfly | $30/mo (Discovery, 200,000 credits) | 1,000 free credits that don't expire; a residential-proxy rendered request costs 25–30 credits |
| Apify | $29/mo (Starter) | Free tier is a $5 monthly credit; Scale $199/mo, Business $999/mo; value is the prebuilt Actors |
| Crawl4AI | Free | Open-source Python crawler, around 87,000 GitHub stars, self-hosted |
| Browse AI | $19/mo billed annually | Monthly billing is $48; 50 free credits/mo and 2 domains |
| Octoparse | $83/mo, or $69/mo annual | Free plan caps at 10 tasks and 50,000 exported rows/month |

Where two sources disagreed on a price, both numbers are shown with their billing period, because that is usually the explanation.

## The yearly bill

ScraperAPI Hobby costs **$588/year** on monthly billing and **$529.20/year** on annual billing, a $58.80 difference. Business is $3,588 versus $3,229.20, saving $358.80. Compare that to Bright Data's Scale plan at $499/mo, which is $5,988 a year before overage, and the gap between a mid-tier budget API and an enterprise unblocking contract is roughly a factor of ten.

The trade is success rate on defended sites, and only you know how much that is worth. If 84% is enough for your targets, paying enterprise rates for 93% is money spent on insurance you may not need. If a failed request costs you a customer record, it isn't.

👉 [Start the 7-day trial with 5,000 credits, no card required](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## The limits that only show up in the docs

Exceed your concurrency limit and you get a 429 telling you to back off. The request is refused rather than queued, and you are not charged for it.

Run out of credits and scraping pauses until they renew. Auto-upgrade, which bumps you to the next plan automatically, is opt-in and available on Hobby, Startup and Business. Pay-as-you-go overage with a spending cap you set yourself is reserved for Scaling, Professional, Advanced and Enterprise, so a Hobby account cannot quietly spend past its limit.

Annual plans deliver the full year's credits upfront and let you use them on any schedule. Burn through them early and you can renew the same annual plan for a fresh batch instead of waiting out the term. Cancellation is free at any time from the dashboard, and there is a **7-day no-questions-asked refund** if the service doesn't work for your targets.

## One paragraph on compliance

Before scaling anything, read the site's robots.txt (the format standardized as RFC 9309 in 2022) and honour crawl-delay, cap your request rate and use exponential backoff on errors, and check the terms of service, since plenty of sites prohibit automated collection and commercial use may need written permission. If personal data is in scope, GDPR-style rules apply: minimise what you collect, store it securely and set a retention limit. Cloudflare now blocks many AI crawlers by default on ad-supported pages, so expect that fight to keep getting more expensive.

## FAQ

**Is the free tier enough to test properly?**
For validation, yes. 1,000 credits a month with 5 threads covers a few hundred ordinary pages, and the 7-day trial gives you 5,000 credits to test at a larger scale without a credit card. If your targets are Amazon pages at 5 credits each, expect around 1,000 trial requests rather than 5,000.

**Why did my credits vanish so much faster than my request count?**
Multipliers. A Google SERP request costs 25 credits, a LinkedIn request 30, and a Cloudflare bypass or a JS render adds 10 each. Check the Domain Cost Estimator for your specific URLs before you size a plan.

**Can it get past Cloudflare?**
Yes, at 10 extra credits per bypassed request, but that is also where ScraperAPI is weakest relative to the field. It tops out at 84% on heavily protected sites when fully configured. If most of your list sits behind DataDome or PerimeterX, run the trial first and count your failures.

**Do I have to use its parser?**
No. It returns the page and you keep your own parsing logic. Structured endpoints exist for Google and Amazon if you want them, but nothing forces you into them.

**What happens if I hit my limit mid-month?**
Scraping pauses until renewal unless you switched on auto-upgrade. That is a deliberate default: no surprise invoice, and no partial service either.

## Which tool for which job

Plain pages and a tight budget: ScraperAPI Hobby at $49/mo, or $44.10/mo annual, after you've confirmed your URLs on the free tier.

Defended sites where a missed request costs money: Zyte for the highest measured success on hard targets, Bright Data if you also want ready-made scrapers and datasets at enterprise volume and can absorb $499/mo and up.

Markdown for an LLM pipeline: Firecrawl at $19/mo, accepting that it finished last on protected pages in one suite and fourth overall in another.

Zero budget and your own servers: Crawl4AI.

Two things to do before you enter a card number. Run twenty of your real URLs on the trial and count how many come back, then price those same URLs through the credit estimator so the Hobby number on the page becomes your actual monthly cost rather than someone else's benchmark.

👉 [Check ScraperAPI's current plans and start with the free tier](https://www.scraperapi.com/pricing/?fp_ref=coupons)

# AI crawler access in robots.txt: open data from ROC SEO

Two datasets on which search and AI crawlers websites allow or block in their `robots.txt`, collected by [ROC SEO](https://getrocseo.com/). Both are free to use under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

| Dataset | Checked | Sample | Rows | Write-up |
|---|---|---|---|---|
| [`ai-crawlers-top-10k-2026-10`](ai-crawlers-top-10k-2026-10/) | 28 Oct 2026 | Tranco top 10,000 domains (6,501 answered) | 10,000 | [getrocseo.com/research/](https://getrocseo.com/research/) |
| [`gta6-ai-crawlers-2026-11`](gta6-ai-crawlers-2026-11/) | 18 Nov 2026 | 30 sites covering GTA 6 (23 readable) | 30 | [getrocseo.com/research/gta-6-ai-crawlers/](https://getrocseo.com/research/gta-6-ai-crawlers/) |

## Key numbers

From the top 10,000 study (base: 6,501 domains whose server answered):

| Bot | Used for | Blocked from the whole site |
|---|---|---|
| CCBot | Common Crawl (used to train many models) | 13.3% |
| GPTBot | OpenAI training | 12.3% |
| ClaudeBot | Anthropic training | 11.7% |
| Google-Extended | Gemini training and grounding | 10.8% |
| PerplexityBot | Perplexity search | 8% |
| ChatGPT-User | ChatGPT visiting a page for a user | 6.7% |
| OAI-SearchBot | ChatGPT search | 5.5% |
| Claude-SearchBot | Claude search | 5.5% |
| Googlebot | Google Search | 1.8% |

Training crawlers are blocked about twice as often as the crawlers that fetch pages for AI answers. 11.1% of answering domains have an `llms.txt`.

## How the data was collected

- Each site's `https://<domain>/robots.txt` (and, for the top 10,000, `/llms.txt`) was requested once, following redirects, with a 10-second timeout and a ROC SEO user agent. Nothing else was fetched.
- Rules were read with RFC 9309 matching, as Google does: the bot's own group, else `*`; the longest matching rule wins; `Allow` wins a tie. This is the same code the ROC SEO extension uses.
- A bot counts as **blocked** when the whole site is disallowed for it (top 10,000), or when both the home page and an ordinary article address are disallowed (GTA 6 sites).
- A missing `robots.txt` (4xx) counts as everything allowed.

## Limits

- `robots.txt` is a request, not a lock. Firewall and CDN bot rules (for example Cloudflare's AI crawler blocking) are not visible here, so real blocking is likely higher.
- Each dataset is one snapshot on one day.
- The top 10,000 list includes CDN, API and tracking domains without a website; those are the 3,499 `unreachable` rows.
- The GTA 6 list is hand-picked, not a random sample.

## Citation

> ROC SEO (2026). AI crawlers the top websites block: robots.txt of the Tranco top 10,000, checked 28 October 2026. https://getrocseo.com/research/

> ROC SEO (2026). Do GTA 6 sites block AI crawlers? robots.txt of 30 sites covering the launch, checked 18 November 2026. https://getrocseo.com/research/gta-6-ai-crawlers/

See also [`CITATION.cff`](CITATION.cff).

## Check your own site

- [AI bots checker](https://getrocseo.com/features/ai-bots-checker/): which of these bots your robots.txt allows
- [robots.txt tester](https://getrocseo.com/features/robots-txt-tester/): test one address against your rules
- [llms.txt checker](https://getrocseo.com/features/llms-txt-checker/)

## License

Data: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Credit "ROC SEO" with a link to the study page.

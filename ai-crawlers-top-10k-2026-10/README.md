# AI crawlers the top websites block (28 October 2026)

`robots.txt` and `llms.txt` of the Tranco top 10,000 domains (list [GQ3QK](https://tranco-list.eu/list/GQ3QK), generated 2026-10-27), checked on 28 October 2026.

Write-up: https://getrocseo.com/research/

## File

`ai-crawlers-top-10k-2026-10-28.csv`: 10,000 rows, one per domain, UTF-8, comma-separated.

## Columns

| Column | Values | Meaning |
|---|---|---|
| `rank` | 1–10000 | Tranco rank |
| `domain` | text | Domain checked |
| `robots_txt` | `rules` | robots.txt found and read (4,680) |
| | `none` | No robots.txt (4xx): everything allowed (1,786) |
| | `server-error` | robots.txt answered 5xx (35). Google treats this as "do not crawl"; we did not count it as blocking any one bot |
| | `unreachable` | No answer (3,499), mostly CDN, API and tracking domains with no website. Bot columns are empty |
| `llms_txt` | `yes` / `no` | A valid `/llms.txt` was found (721 yes) |
| `Googlebot` … `Amazonbot` | `allowed` / `blocked` / empty | Whether robots.txt disallows the whole site for that bot |

Bots: Googlebot, Bingbot, Google-Extended, OAI-SearchBot, ChatGPT-User, GPTBot, ClaudeBot, Claude-User, Claude-SearchBot, PerplexityBot, Perplexity-User, Applebot-Extended, CCBot, Bytespider, meta-externalagent, Amazonbot.

## Base for percentages

6,501 domains that answered (`rules`, `none` or `server-error`). Example: GPTBot is `blocked` on 800 of 6,501 = 12.3%.

## Method and limits

See the [main README](../README.md#how-the-data-was-collected).

## License

CC BY 4.0. Credit: ROC SEO, https://getrocseo.com/research/

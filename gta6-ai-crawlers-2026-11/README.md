# Do GTA 6 sites block AI crawlers? (18 November 2026)

`robots.txt` of 30 sites covering Grand Theft Auto VI, checked on the eve of its launch: the publisher, the PlayStation and Xbox blogs, 18 games media sites, 4 tech news sites, 3 entertainment and business news sites and 2 fan sites.

Write-up: https://getrocseo.com/research/gta-6-ai-crawlers/

## File

`gta6-ai-crawlers-2026-11-18.csv`: 30 rows, one per site, UTF-8, comma-separated.

## Columns

| Column | Values | Meaning |
|---|---|---|
| `site` | host | Site checked |
| `type` | text | Publisher, Platform, Games media, Tech news, Entertainment, Business news, Fan site |
| `robots_txt_status` | HTTP status | Status of the robots.txt request (0 = no answer) |
| `readable` | `yes` / `no` | Whether a readable robots.txt came back. 7 sites did not (3 bot protection pages, 4 no answer); their bot columns are empty |
| `note` | text | Why a site was not readable, or other remarks |
| `<Bot>_blocked` | `yes` / `no` / empty | Whether both the home page and an ordinary article address are disallowed for that bot |

Bots: Googlebot, GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-SearchBot, Claude-User, PerplexityBot, Perplexity-User, Google-Extended, CCBot, Applebot-Extended, meta-externalagent, Bytespider, Amazonbot, Bingbot.

## Limits

A hand-picked list of 30 sites, not a random sample, so read the shares as a snapshot of this group. Firewall and CDN bot rules are not visible. See the [main README](../README.md#limits).

## License

CC BY 4.0. Credit: ROC SEO, https://getrocseo.com/research/gta-6-ai-crawlers/

# Lead Finder — Setup

Give Claude Code live access to the web and have it gather business leads for
you, using [Firecrawl](https://github.com/firecrawl/firecrawl-claude-plugin),
a free, open-source web-scraping tool. You describe the kind of business you're
after; Claude searches the web, reads the pages it finds, and hands back a
clean list of companies with their public contact details.

## 1. Install Firecrawl

Firecrawl is the official web-scraping plugin for Claude Code. The free tier
gives you 500 credits to start — plenty to test before you pay for anything.

**Plugin route (quickest):** In Claude Code, run `/plugin`, search for
`firecrawl`, select it, and install. It needs the Firecrawl CLI installed
globally and a free API key from <https://firecrawl.dev/app>.

**MCP route (one command):**

```bash
claude mcp add firecrawl -e FIRECRAWL_API_KEY=your-api-key -- npx -y firecrawl-mcp
```

## 2. Use the skill

Once Firecrawl is installed, just describe your target in plain English and the
`lead-finder` skill takes over. For example:

> Use Firecrawl to find me 25 pool-cleaning businesses in Austin, TX.
> For each one, pull the business name, website, publicly listed email and
> phone, and two specific details from their site I could mention in outreach.
> Give it to me as a clean table.

A couple of minutes later you've got a usable list, pulled from the
businesses' own public pages.

## 3. Go beyond a flat list

- **Enrich** — have Claude visit each company's site and pull extra context
  like their services and where they're based.
- **Format** — ask for the output as an interactive HTML doc or a CSV you can
  drop straight into your CRM.
- **Monitor** — re-run a scrape of competitor or listing pages on a schedule
  to catch what changes.

## Do it right

A few guardrails so this stays effective and legal:

- **Stick to public business data.** Pulling a company's published contact info
  is fine. Harvesting individuals' personal emails at scale runs into privacy
  laws like GDPR and CCPA.
- **Respect each site's rules.** Some sites (LinkedIn included) prohibit
  scraping in their terms. Point Firecrawl at company sites and public
  directories rather than walled platforms.
- **Follow the outreach laws.** If you cold-email these leads, CAN-SPAM (US) and
  GDPR (EU) set real rules: identify yourself clearly, give every recipient an
  easy opt-out, and don't email individuals in the EU without a lawful basis.

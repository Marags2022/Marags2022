---
name: lead-finder
description: Use when the user wants a list of local business leads. Uses Firecrawl to find businesses by type and location and returns their public contact details in a clean table.
---

# Lead Finder

When the user names a business type and a location:

1. Use **Firecrawl search** to find businesses of that type in that area.
2. Scrape each result's own website for the business name, website, and publicly listed email and phone.
3. Pull two specific, real details from each site that can be used for personalized outreach.
4. Return a clean table, and skip any business with no public contact info rather than guessing.

## Output

Return the results as a Markdown table with these columns:

| Business name | Website | Email | Phone | Outreach detail 1 | Outreach detail 2 |

If the user asks for a different format, also offer:

- **CSV** they can drop straight into a CRM.
- An **interactive HTML** document.

## Cleaning the list

Before returning results:

- **Dedupe by domain** so the same company never appears twice.
- **Drop any row missing a real email or phone** rather than padding the count.
- **Flag the strongest 3–5 leads** to reach out to first. A well-targeted list of 25 beats a messy list of 500.

## Rules (compliance-first)

- Only collect contact details a business has **published publicly on its own site** or in a public directory.
- **Never fabricate** an email or phone number. If it isn't published, leave it blank or skip the row.
- Stick to **public business data**. Do not harvest individuals' personal emails at scale — that runs into privacy laws like GDPR and CCPA.
- **Respect each site's rules.** Some sites (LinkedIn included) prohibit scraping in their terms; point Firecrawl at company sites and public directories rather than walled platforms.
- If the user plans to cold-email these leads, remind them that **CAN-SPAM (US)** and **GDPR (EU)** apply: identify yourself clearly, give an easy opt-out, and don't email individuals in the EU without a lawful basis.

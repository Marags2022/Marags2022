# Example output — Austin, TX pool-cleaning candidates

`austin-pool-cleaning-candidates.csv` is a **starter list** of 18 verified-real
pool-cleaning/maintenance businesses in Austin, TX, with their official website
domains — produced by the `lead-finder` skill via web search.

## Why the contact columns are blank

The `email`, `phone`, and `outreach_detail` columns are intentionally empty.
The skill's rules require contact details to be **verified on each business's
own published site** and forbid fabricating or transcribing unverified data.
The session that generated this list ran in a locked-down environment whose
network policy blocked outbound requests to the company sites (HTTP 403 at the
egress proxy), so the per-site scrape couldn't run.

## How to fill it in

Run the `lead-finder` skill in an environment with web access to these domains
(e.g. local Claude Code with Firecrawl installed, or a web session created with
a more open network policy). Point it at this CSV and have it visit each
`website`, then fill `email`, `phone`, and two real `outreach_detail` columns
from each site — skipping any business with no public contact info.

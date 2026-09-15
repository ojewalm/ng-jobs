# ng-jobs

Daily infographics on the Nigerian labour market.

**Live site:** https://ojewalm.github.io/ng-jobs/

## What this is

Five snapshots built from public job listings across MyJobMag and Jobberman:

1. **The Nigerian salary map** — median monthly salary by state, with p25/p75 range
2. **Who's actually hiring in Nigeria** — top 25 companies + their most-posted roles
3. **The entry-level squeeze** — % of postings by required-experience band
4. **Top 10 job titles by volume** — with week-over-week rise/fall arrows
5. **Top 10 technical skills employers ask for** — Data / Software / Cloud / Engineering

All aggregate. No raw postings, no URLs, no PII.

## Files

- `index.html` — the static site (embeds all data inline; loads Plotly from CDN)
- `data.json` — the same data as JSON, for anyone who wants to plot their own version
- `.nojekyll` — signals GH Pages to serve files verbatim (no Jekyll)

## How it updates

The private pipeline that scrapes and normalises the postings runs once a day.
At the end of every successful daily run, it fetches five aggregate endpoints
from the local FastAPI service, renders `index.html`, and pushes the diff here.

No secrets, no credentials, no raw data ever gets committed — only these
five aggregate files.

## Licence

Data derived from publicly-listed jobs on third-party sites; attribution to
those sites belongs to them. This repo's HTML/CSS/JS is MIT.

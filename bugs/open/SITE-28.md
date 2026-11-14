<!-- Filed by Suite Builder: a system bug. To close it yourself, move this file to bugs/closed/. -->
# SITE-28: The site has no sitemap search engines can read

Filed from the crawl of 2026-11-14, by Suite Builder: a finding about the site, not the suite (KNOWN-ISSUES.md has it in full).

**What it blocks:** No test of the regular run trips on it: the audit tests re-check each item.

**Why it matters:** A sitemap tells search engines every page to index, and how fresh each is; without one they find pages only by following links, and one listing wrong addresses spends their visits on errors.

**Likely fix:** Publish /sitemap.xml listing each page's final address (most site builders and CMSs have a setting or plugin for it), and name it in robots.txt (Sitemap: ...).

**Where:**

- https://harsh.civicease.systems/sitemap.xml: answered 404

## Items expected open

- `SITE-28-7eb6515f` missing: the sitemap answers 404 (since 2026-11-14)

Each item closes by `node menu/audit.mjs accept <id>` after an audit run saw it fixed, or by a rebuild from a crawl that no longer finds it; this file goes with its last item. `node menu/audit.mjs dismiss <id> --why "..."` marks one a false finding or an accepted risk.

**How it closes:** a rebuild from a new crawl that no longer finds it removes this file (one line goes to
bugs/FIXED.md), and its tests count again. To close it yourself (it will not be fixed, or another ticket tracks
it), move this file to bugs/closed/: its tests count again. A rebuild that still finds it files it again,
so it is looked at again.

# Automated site review: harsh.civicease.systems

2 pages of `https://harsh.civicease.systems`, read on 2026-11-14 by Suite Builder's crawler in a real browser, logged out, as a first-time visitor sees them. Nothing was sent, bought or signed in to. This review reads the public site as it is served. It also observes the site's own security guards, as a visitor's browser sees them. It sends nothing and attacks nothing.

**0 major, 3 minor.** Major: lets a visitor or a search engine down now. Minor: worth fixing. Info: said for the record; counts against nothing. Each finding lists every page the read saw it on.

## What this review checked

Of 40 checks, 37 ran on this crawl; 3 could not be confirmed.

<details>
<summary>The checks, by kind</summary>

Pages and links (11 of 11 ran)
- Pages that answer an error yet draw content
- Links that answer an error
- Links that redirect before they arrive
- Page titles that are shared or missing
- An address that cannot exist but answers as a page
- Chains of redirects
- Images that do not load
- Links that send visitors from https to http
- Links to other sites that lead nowhere
- Links that answer an error on purpose
- Links to other sites that did not answer the crawler

Markup, accessibility and search (13 of 13 ran)
- Links and buttons with nothing for a screen reader to say
- Form fields without a label
- Images with no address
- Placeholder text left on pages
- The viewport setting for phones
- Canonical links that point somewhere else
- Images without alt text
- The language each page declares
- The main heading of each page
- Links to a part of the page that is not there
- Descriptions for search results
- The year in the copyright notice
- Form fields whose only label is a placeholder

Loading and speed (4 of 7 ran)
- Scripts, style sheets and data requests that fail to load
- Errors thrown by the site's own scripts
- Pages slow to answer or to load
- Requests over plain http from an https page
- Requests to other sites' hosts that fail: not confirmed
- Pages that did not finish loading: not confirmed
- What failed for the crawler on other sites, or from no known source: not confirmed

The site's own addresses, certificate and headers (9 of 9 ran)
- Addresses of the site that do not answer
- Response headers that browsers act on
- Server software and version announced in headers
- The certificate's end date, name and trust
- Whether the http address sends visitors to https
- The sitemap
- A contact for security reports (security.txt)
- One site answering at two names
- The certificate chain, as the crawler's machine sees it

Not confirmed: the crawl file records what such a check saw only when it saw something, so it cannot show whether the check ran and found nothing, or did not run.

</details>

## minor SITE-24 3 security headers no page sends

**Why it matters.** Each header closes off one way the site could be misused \(a downgrade to http, a script slipped in, the site framed in another to trick a click\). A missing one is a weaker defence, not a sign the site has been attacked; security reviews ask for them, and each costs a line of server configuration.

**Likely fix.** Add the missing headers in the web server or the CDN \(one setting each\), starting with Content-Security-Policy.

<details open>
<summary>3 missing headers</summary>

- `/` no page of the site sends Content-Security-Policy \(without it, nothing limits which scripts a page may run\)
- `/` no page of the site sends X-Frame-Options or frame-ancestors \(without it, another site can frame the page to trick a click\)
- `/` no page of the site sends X-Content-Type-Options: nosniff \(without it, a browser may guess a file's type from its content\)

</details>

## minor SITE-28 The site has no sitemap search engines can read

**Why it matters.** A sitemap tells search engines every page to index, and how fresh each is; without one they find pages only by following links, and one listing wrong addresses spends their visits on errors.

**Likely fix.** Publish /sitemap.xml listing each page's final address \(most site builders and CMSs have a setting or plugin for it\), and name it in robots.txt \(Sitemap: ...\).

<details open>
<summary>1 address</summary>

- `/sitemap.xml` answered 404

</details>

## minor SITE-29 The site publishes no security.txt, the file that tells security researchers whom to contact

**Why it matters.** Researchers who find a security problem look for /.well-known/security.txt to know whom to tell \(RFC 9116\); without it they may not report it, or report it publicly.

**Likely fix.** Publish /.well-known/security.txt with a Contact line \(an email address or a form\) and an Expires line.

<details open>
<summary>1 address</summary>

- `/.well-known/security.txt` answered 404

</details>

Read by Suite Builder's crawler, which identifies itself in its User-Agent and obeys robots.txt.

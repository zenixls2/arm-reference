# Arm Reference — public archival snapshot

A public archival snapshot requested by the account owner of `https://arm.jonpalmisc.com/`. This is an archival capture, not a public mirror or an endorsement. The website's own homepage notice is preserved at `site/index.html`.

## Capture scope

Captured **2026-11-25 21:43–22:28 UTC**. The crawl followed same-origin links/resources found in captured HTML and CSS, and added every document URL enumerated by the site's Pagefind manifest. Third-party origins were not fetched; excluded references are recorded in the exclusion manifests. The original `robots.txt` was respected.

- `site/` — static files served from the website root; Pagefind search assets are preserved as served.
- 12,842 captured files; 114,703,615 bytes total.
- The Pagefind manifest advertised 4,276 documents; all 4,276 fragments and corresponding HTML pages were captured.
- Pagefind 1.5.2 runtime includes 47 index shards and one WASM asset. A local headless-browser smoke test returned 1,418 results for `add`; the 15 observed Pagefind requests had no failures.
- All 8,240 unique same-origin targets found in captured HTML/CSS resolved to archived successful responses; zero were blocked by `robots.txt`.
- 23 URLs returned HTTP 200 bodies byte-identical to the homepage (including one `.css` URL). Those responses are preserved but classified as server fallback/alias responses, not independent page content; see `route-fallbacks.jsonl`.

## Provenance and validation

- `archive-manifest.jsonl` — source URL, local path, response metadata, byte count, SHA-256, and failed route probes.
- `crawl-report.json` — raw main-crawl summary. Its 47 fragment-template failures were subsequently classified as valid Pagefind index shards; they are not unresolved fetch failures.
- `supplement-manifest.jsonl`, `supplement-report.json`, `supplement-excluded.jsonl` — Pagefind-discovered pages/resources and their coverage results.
- `pagefind-shard-probes.jsonl` — evidence mapping metadata hashes to the worker-declared index/WASM routes.
- `final-validation.json` — path, size, SHA-256, Pagefind coverage/runtime, link-closure, and smoke-test gates.
- `offline-smoke.json` — local browser smoke-test output.
- `route-fallbacks.jsonl` — byte-identical homepage fallback responses.
- `excluded.jsonl` — references not fetched, including external/non-HTTP links.

Serve `site/` over HTTP for local browsing and Pagefind search (browsers may restrict search when opened via `file://`):

```sh
python3 -m http.server 8000 --directory site
```



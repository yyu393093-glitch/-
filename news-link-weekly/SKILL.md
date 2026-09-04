---
name: news-link-weekly
description: Read one or more news, research, company, product, policy, report, media, investment, financing, or IPO URLs and turn them into a document-ready Chinese AI daily or weekly report. Use when the user supplies links—including messages containing only URLs—and needs objective extraction, verification, deduplication, classification, titling, sorting, summaries, official links, or capital-market entries according to their reporting SOP.
---

# News Link Weekly

Turn supplied URLs into objective, document-ready Chinese AI news entries. Treat a message containing only one or more relevant URLs as a request to run this workflow.

## Required reference

Read [references/editorial-sop.md](references/editorial-sop.md) completely before classifying, sorting, or writing entries. Follow it over generic editorial preferences.

## Workflow

1. Collect every supplied URL and preserve each original source URL exactly.
2. Read every source with the best available semantic web-reading tool.
3. If direct extraction fails, search for the exact URL or title, then use the in-app browser for JavaScript-rendered pages. Invoke the browser skill before browser control. For PDFs, invoke the PDF skill. Use visible-page inspection or screenshots as the final reading fallback.
4. Extract only supported facts: source title, publication date, event date, principal organization or person, event, product/model name, country, functions, prices, metrics, financing round and amount, investors, listing status, and official URLs.
5. Corroborate claims with official or primary sources when practical, especially financing, IPO, model releases, pricing, metrics, and claims that affect classification. Preserve uncertainty and distinguish forecasts or source claims from confirmed facts.
6. Deduplicate links about the same event. Prefer primary, direct, complete, or authoritative sources; merge complementary facts only when consistent.
7. Assign section, field, country, title, and order using the required reference. Financing, investment, acquisition, and IPO items must follow its capital-market rules.
8. Write each summary in the preferred sequence: `时间 + 主体 + 核心事件 + 关键细节/当前状态`. Use one compact paragraph and retain qualifiers such as “预计”“可能”“尚未正式发布”.
9. Return the document-version format from the reference. Do not narrate the research process unless a source failed or material facts conflict.

## Accuracy and failure handling

- Never infer details solely from a URL slug.
- Never invent a date, country, model capability, metric, quotation, financing term, listing status, or official URL.
- Do not turn speculation, investor expectations, media reports, or company claims into established facts.
- Keep promotional, comparative, causal, and value-judgment wording out of titles and summaries unless clearly attributed and essential.
- If a page remains unreadable after available fallbacks, list it under `【未能读取】` with a short reason. Ask for pasted text or a screenshot only for failed links and continue processing all readable links.
- If sources conflict, state the conflict or use cautious attribution instead of silently choosing one.
- Keep the final response self-contained and ready to paste into a daily or weekly report.

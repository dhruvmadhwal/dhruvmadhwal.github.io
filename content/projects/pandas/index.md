---
title: Dishcovery
date: 2025-10-26 
links:
  - type: demo
    url: https://dishcovery-38p.pages.dev/
  - type: code 
    url: https://github.com/dhruvmadhwal/Dishcovery
tags:
  - NL-to-SQL
  - FastAPI 
  - Next.js 
  - Snowflake  
  - LLMs 
  - OCR
---

Dishcovery started from a simple truth: I love food, and I'm lucky enough to be an adventurous eater with zero dietary restrictions. But I quickly learned that coordinating meals with a group is a completely different story.

As an international student at ASU, I kept running into the same problem when trying to grab food with friends. Everyone has constraints—someone needs vegetarian or Jain options, someone is lactose intolerant, someone is on a strict budget, and no one wants to travel too far. Finding a place that satisfies all of those constraints before everyone gets hangry is incredibly frustrating.

Existing apps help you find restaurants, but they don’t help you find the exact dish that works. So, I built Dishcovery to let you search the way you actually think.

<!--more-->

## Search the Way You Actually Think

Instead of browsing menus manually, you can search for exactly what you need:

> "vegan ramen under $15 within 2 miles"

> "gluten-free dessert with no dairy"

You get specific dishes with prices, dietary tags, and locations.

## How It Works

Under the hood, it combines:

- Menu scraping & OCR to digitize restaurant offerings
- LLM-based parsing to identify ingredients and map dietary tags
- Structured data + natural language search to connect users to the right meal

## Current Scope

The current MVP is intentionally limited in scope: it covers ~30 restaurants around ASU as a focused pilot rather than pretending to be a polished production platform. Right now, the bigger goal is to validate the idea, improve the quality of the results, and learn where automation matters most. I'm actively working on expanding restaurant coverage and making more of the ingestion, extraction, and tagging pipeline automatic and reliable.

If you want to try it yourself, check it out [here](https://dishcovery-38p.pages.dev/). And if you're curious about the inner workings, you can take a closer look [here](https://github.com/dhruvmadhwal/Dishcovery).

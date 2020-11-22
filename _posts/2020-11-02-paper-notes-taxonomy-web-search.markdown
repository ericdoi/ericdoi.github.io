---
layout: post
title:  "Paper Notes:  A Taxonomy of Web Search"
date:   2020-11-02
categories: [Process, Paper-Notes]
---
***Paper Notes**:  I've decided to read one paper every two weeks and post my notes here as a concrete deliverable.  This is part of a habit I'd like to cultivate to read more books, academic papers, and industry blogs.*

## Summary
**The paper:** [Broder, Andrei. 2002. “A Taxonomy of Web Search.” SIGIR Forum 36 (2): 3–10](https://www.cis.upenn.edu/~nenkova/Courses/cis430/p3-broder.pdf)

This is a light paper suggesting a categorization of web searches into 3 main types which require fundamentally different search approaches.

## Notes
* 3 main types of web searches
    * Informational:  trying to find out some info
        * Evaluation:  depends on wide (“cars") vs narrow ("scoville heat units”).  Hubs are desirable:  "in almost 15% of all searches the desired target is a good collection of links on the subject, rather than a good document"
    * Navigational:  trying to find a specific site presumed to exist
        * Evaluation:  Usually only a few correct answers.  Hubs are less desirable.
    * Transactional:  trying to complete some transaction (shopping, downloads, web-mediated services, etc.)
        * Evaluation:  difficult to know beyond binary relevance.  Most important factors e.g. price, quality, are not generally available to the search engine.
* Survey data
    * ~25% nav
    * ~75% non-nav (info + transactional) queries
        * ~1/3 of non-nav due to download (25%) and ecommerce (~8%), there could be other transactionals
    * Filtered:  12% sexual queries (but only 1% in survey data)
* Log analysis
    * Manual guessing of 400 queries:  ~50% info / ~20% nav / ~30% transactional
* Search engine evolution:
    * 1st gen (1995):  support info queries.  Classic IR.  AltaVista, Excite, etc.
    * 2nd gen (1998):  support info + nav queries.  Use off-page data (link analysis, click-through data, anchor text) for nav.  Google etc.
    * 3rd gen (2002):  support info + nav + transactional queries.  Blend external databases and try to address “the need behind the query”.  E.g. “San Francisco” -> hotel booking, map, weather, etc.  Use semantic analysis, context, dynamic pages, etc.

## Thoughts
Picked an easy and short one since I was short on time this week.  It's a practical "lay of the land" guide for thinking about what search engines do.

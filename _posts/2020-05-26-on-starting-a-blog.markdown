---
layout: post
title:  "On starting a blog"
date:   2020-05-26
categories: [Process, Book-Notes]
---

## Why

The immediate impetus for creating this space online was that I read Austin Kleon's [Show Your Work][show-your-work].

Here's the [review][goodreads-rev] I put on Goodreads:

> I saw this book [recommended by Ali Abdaal][three-books] and was sold on it being both (1) life changing and (2) a 30 minute read.
> 
> Austin makes the clearest and most convincing argument I’ve seen as to why pretty much everybody (such as a data 
> scientist with a standard day job) should begin sharing their work with the world and making it findable (indexable 
> really). Concrete starting points—register a web domain, start a daily dispatch, document your process—also make this 
> immediately actionable. It seems impactful in the way that a one-hour lunch conversation with an insightful friend 
> can plant an idea that changes the trajectory of your life.

Austin addresses two inhibitions I have about writing publicly:

1. **I don't really need self-promotion.**  I have a normal salaried job (at [an awesome company][grab]) and I'm not trying to sell anything.  I'm a fan of the mindset behind being "so good they can't ignore you" as advised Steve Martin (and expounded upon by Cal Newport in his [book of the same name][sgtciy]): basically, work hard and have faith in the process.  Austin agrees that it's necessary, but counters that it's not sufficient since "you [also] have to be findable."  One might argue that it is harder to *not* be findable in the post-Internet world, but often our online presence consists of breadcrumbs.  Pictures of our daily lives, posts in old forums, mentions in school websites--these  may lead to us but they don't present our story clearly.  For career use, LinkedIn is useful, but having acted as a hiring manager myself I feel a LinkedIn profile and a résumé are still not nearly enough information to know what a candidate is really about.
2. **Others are more qualified to write about anything I would.**  At work, it's easy for me to see things that I am uniquely qualified to (and in fact paid to) do and talk about.  It's harder for me to feel this way outside of my work.  Does the world really need another blog?  I can pick pretty much any topic and know for a fact that there is someone more knowledgeable in it than I am.  To this, Austin says: You don’t have to be a genius.  For one, the “scenius," the collective wisdom in intellectual movements, is often just as important as individual contributors.  And two, amateurs--those who work for love rather than as a profession--fill a necessary gap.  One example is in teaching; as experts often forget what they went through to become experts, an amateur can provide a valuable service by "documenting the process" and "learning in front of others".  And upon reflection it seems obvious: If as an engineer it's easy for me to find things that are under-documented and document them once I've struggled to figure them out (despite not being the original author who presumably is the expert), then why should it be different for the world at large?

That brings me to my goals here:

1. **Document** my work process so that others may learn from it
2. **Reflect** on my work to improve my learning and focus, and improve my writing
3. **Create** a story out of my work

## What
Things I plan to include:

* **Technical matters** I come across in the course of my work that appear underdocumented.  These may be how-tos or notes on things like academic papers (which I always wish had more details and commentary).
* **Notes on books or articles** I'm reading.  Topics include statistics, sustainable energy, business, systems and processes, to name a few.
* **Documentation of my work process**.  This post is an example.

What's not in scope:

* I don't plan for now on writing long opinion pieces.  I've always been a slow writer, constantly revising and thrashing even at the very start, and I'm glad to be done with writing essays in school.  Besides, in contrast to documentation and analysis, I don't think the world has a shortage of opinions.
* Pictures of my lattes.  I don't drink coffee much anyway (maybe a post about that later, though there's plenty of posts about that so I don't know if I have much to add to the discussion).

## How
A bit here about the process of creating this blog.

In the middle of reading *Show Your Work* I went to godaddy.com and registered my personal name domain.  It cost about $20 for the first year.

For creating and hosting the website, I settled on using Jekyll hosted on Github Pages.  I wanted something pretty minimal and after evaluating the standard options this seemed the best for someone who knows how to code and who doesn't have anything to sell (yet).

The runner up I was considering was [Medium][medium].  It has a great minimal design that focuses on the content.  However, it felt like the platform was geared more for regular writers who are trying to build a voice and find an audience, not for logging a personal journey.

When considering the other options I took a look at some of the blogs I like and saw what they were using.  Here are the notes I took:

### Blogging options considered, from casual to serious
* **[Google Sites][gsites]**:  Yes, I considered this.  It's absolutely bare bones and free.
    * Examples:  [Professional Reading][pro-reading]
    * Good:  Free, super simple to set up
    * Bad:  Blog posts are just separate pages.  Not really a blog.
* **[Typepad][typepad]** (seem to be redirecting customers to [Bluehost][bluehost])
    * Examples:  [Junk Charts][junkcharts]
    * Good:  Simple
    * Bad:  Ads, and it's deprecated anyway
* **[Jekyll][jekyll]**:  Git-based static publishing
    * Examples:  <https://www.barryclark.co>, <https://www.digital-democracy.org/blog/>, 
    * Good:  Fast, simple, free hosting using Github Pages
    * Bad:  
    * Notes:
        * Setup: [Build A Blog With Jekyll And GitHub Pages][smashing]
        * Themes:  [Hyde][hyde] looks good.
* **[WordPress][wordpress]**:  The standard for blogs
    * (.org = just the framework, .com = Hosted)
    * Good:  Powerful, de-facto standard
    * Bad:  Overkill.  Hosted solution is simplified.  ~$4/mo for simplest plan.
* **[Medium][medium]**:  Pure focus on content.
    * Examples:  [Towards Data Science][tds]
    * Good:  Free to post.  Minimal, focus on content.  Built-in distribution, SEO, etc.  Can submit to publications.
    * Bad:  Content > Author.  Opt-in paywall can be a distraction.  Not made for showing code.  More for text-based opinion pieces than reference content.  No customization.  Medium has control.
* **DIY**
    * Examples:  <https://www.johndcook.com/blog/>
    * Good:  Learn how to build and host a website from scratch
    * Bad:  Needs a lot of time investment
* **[Squarespace][squarespace]**:  General end-to-end solution
    * Good:  Beautiful
    * Bad:  Expensive ($12/mo+)
* **[Ghost][ghost]**: Premium for publishing
    * Examples:  <https://openai.com/>
    * Good:  Made for professional blogging with teams.  Open source for longevity.
    * Bad:  Very expensive ($30/mo)

## When
A final disclaimer: It's possible I won't have any actual posts for a long time (or ever).  I suppose that's what makes documenting the process interesting!

[show-your-work]: https://austinkleon.com/show-your-work/
[three-books]: https://www.youtube.com/watch?v=hv1gOEY3cs4
[goodreads-rev]: https://www.goodreads.com/review/show/3352428355?book_show_action=false&from_review_page=1
[sgtciy]: https://www.calnewport.com/books/so-good/
[grab]: https://www.grab.com/sg/

[gsites]: sites.google.com
[typepad]: https://www.typepad.com/
[jekyll]: https://jekyllrb.com/
[bluehost]: https://www.bluehost.com/solutions/start-a-blog?brandRedirect=typepad
[wordpress]: https://wordpress.com/
[medium]: https://medium.com/
[squarespace]: https://www.squarespace.com/
[ghost]: https://ghost.org/

[pro-reading]: https://sites.google.com/tcforlearning.edu.do/professional-reading/home?authuser=0&pli=1
[smashing]: https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/
[hyde]: https://hyde.getpoole.com/
[junkcharts]: https://junkcharts.typepad.com/
[tds]: https://towardsdatascience.com/
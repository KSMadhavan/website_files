+++
title = "Website Templates and the need for them"
date = 2018-06-08T19:44:35+05:30

pageNumber = 5
# -----------------------------------------
# Summary section
# -----------------------------------------
# The below image will be shown in all the cards pointing to this article
caption_image = "dog_popup_thanks3.jpg"
# The below summary message will be shown in all the cards pointing to this article. If not available, it would be generated from the content of the page.
summary_content = '''
Hugo, the best way to create your own website'''
# -----------------------------------------
# Meta
# -----------------------------------------
layout = "docs"
featured = true
enable_comments = true

# Highlight.js: https://highlightjs.org/static/demo/
math = false
highlight = false
highlight_languages = ["bash","html"]
highlight_style = "railscasts"

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Static Sites","documentation","Hugo","websites"]
categories = ["Website"]

[[previous_page]]
text = "What is a Static Website"
url = "/docs/understand_static_sites/static_website/"

[[next_page]]
text = "Static Website Generator"
url = "/docs/understand_static_sites/static_website_generators/"

[[quick_links]]
text = "*The need for Templates*"
url = "#the-need-for-templates"
[[quick_links]]
text = "*What does a template provide*"
url = "#what-does-a-template-provide"
[[quick_links]]
text = "*Common types of templates*"
url = "#common-types-of-templates"
[[quick_links]]
text = "*The front page*"
url = "#the-front-page"
[[quick_links]]
text = "*The single content page*"
url = "#the-single-content-page"
[[quick_links]]
text = "*The list page*"
url = "#the-list-page"


[[quick_links]]
text = "Introduction to Static Sites"
url = "/docs/understand_static_sites/introduction/"
[[quick_links]]
text = "Parts of a Webpage"
url = "/docs/understand_static_sites/parts_of_webpage/"
[[quick_links]]
text = "Retrieving a webpage from the internet"
url = "/docs/understand_static_sites/retrieving_a_webpage/"
[[quick_links]]
text = "What is a Static Website"
url = "/docs/understand_static_sites/static_website/"
[[quick_links]]
text = "Static Website Generator"
url = "/docs/understand_static_sites/static_website_generators/"
[[quick_links]]
text = "Assembling a Website"
url = "/docs/understand_static_sites/assembling_webpage/"
[[quick_links]]
text = "Static Website Generator Example: Hugo"
url = "/docs/understand_static_sites/static_generator_example_hugo/"

# Writeup goes below
+++

When you open a Word document to write something, you just open it and start writing. There is no friction between you thinking a thought and getting it in a computer readable format. To create webpages however, quite often one may find that more of the webpage content is repeated code and less is out own written content. To automate the writing of all the peripheral code, we use templates

## The need for Templates

1. We noted during the discussion of websites above that *while the actual content of a webpage may be small, there is a large amount of html, css and javascript* that goes into making a webpage out of this content.
2. When the website has more than one page, a good amount of this html, css and javascript is repeated across pages of the website. 
3. Repeating this code for the website creator is unnecessary and prone to errors
4. Therefore *the same* parts must be reused in different pages of the website
5. Further extending this analogy, different websites that provide similar functionality often have a good degree of repetition of the html, css and javaascript.
6. Yet most websites are not exactly similar in look and feel, though the underlying functionality may be the same.
7. Further, most websites completely differ in content, even if their functionality, look and feel are similar.
8. This brings in the use of template pieces, which are standard pieces of code (html, css and javascript) which are **modifiable** and perhaps **extendible**. In these template pieces, a *certain functionality may be provided, the look and feel can be modified and content can be replaced*.
    - the same concept of templates can be extended even beyond web templates to all manner of code. Functions are a form of such templating.
9. A collection of such template pieces that can be used to form a full website is called a *theme for the static website generator*.

## What does a template provide

The template should provide the *scaffolding* (the html, css and javascript) needed to generate the website:

1. A good way to think about a static generator is that it assembles a website from different parts. These parts are provided by the template
2. Some of these parts may be substituted for others and others may be modified
3. Many of these parts may be just the outline with segments to be filled in by the user, like the actual textual content of the website, or the site title, or the logo of the website.
4. Sometimes, when these parts are not filled in by the user, they may have some default options so that the website looks complete
5. The template may provide options of different sub-parts for a user to choose from.
    - For example, it may provide different types of navigation bars
    - It may provide different forms of site footers
    - It may provide different options for product pages
6. Templates may provide options to modify various parts.
    - For example, colour themes are often modifiable within templates
    - When templates come with images in some parts, these are often modifiable
    - Templates come with some default text in some parts. It may be filler text like '[Lorem Ipsum](https://www.lipsum.com/)'. These are modifiable
7. Templates are not specific to static websites. They are used in all manner of websites as a form of code re-use
    - For example, the product template on amazon.com is common across all products (atleast within the same category of products). While the template is the same, it leaves space for the product name, product images, pricing, etc to be changed.

## Common types of templates

Websites of all kinds exist on the internet, yet we can distill a few kinds of pages that exist across many of these sites. Let us look at some of these:

1. The [front page or index page](https://html5up.net/)*
2. Single content page*
3. List of single pages*
4. The 404 Page*
5. The login page
6. The dashboard or personal application page
7. Network Feed page
8. Search results page
9. The settings page
10. Cart and Address pages (or follow ups to single pages)
11. Contact Us Page*
12. Comments page*
13. Reviews page
14. Help or FAQs page*
15. Thank you or sign out page*

One should recognise that while the content for these across each website may vary the functionality is mainly the same. We have marked in (*) the pages that are often found on static pages as well.

The names for the above are fairly self explanatory, and we may have come across all of these in our lifetimes on the internet, some more often than others. The first three are worth going into a little more detail

### The front page

- This is the page that a viewer visits when they arrive at http://www.ksmadhavan.in
- This base website url is a necessary presence for almost every website. It is typically a descriptive page with some [call to action](https://blog.hubspot.com/marketing/call-to-action-examples)
- This page if often the first point of contact with an incoming visitor to the webpage and therefore [conversion](https://optinmonster.com/11-web-design-principles-that-will-boost-your-conversion-rate/) happens in the first few seconds here
- While some may follow a minimalistic design, most websites may want to spend some time on the design of this page
- For some websites, especially the established ones, the base url substitutes for some functional page, like the login page (in case of facebook and gmail), or the search page (in case of google)

### The Single content page

- The single content page is ubiquitous though we don't recognize it as such
- The single content page is the *main template page* of the website
- For a website like amazon, this is the product page, whereas for a website like facebook it is the individual user page. For a website like youtube, it is a video page, and for new york times, this is a single news story. For gmail it is a single email that you click on and for a blog, it is a single post. Nearly every website has one of these.
- While these may contain dynamically generated content, they can also be static as seen in the examples above

### The list page

- Once we define the single page for a website it is easy enough to understand the list page for the same website
- It is the template which shows a list of the single content pieces of the website.
- The lists can be sliced, diced and categorized in any manner necessary such that different posts may appear on different list pages, but the template for these remains the same
- This is quite related to the search results page which also shows a list of results. The only difference may be that the search has to be generated live and is necessarily dynamic on the server side
- examples of list pages are lists of friends on facebook, or list of posts on a blog or list of videos created by an author in youtube.

### 404 page

- The 404 Page is the page that you are redirected to if you specify a url where no site exists on the site.
- For example say there is no page called abc.html on the website http://www.mysite.com, then if you type http://www.mysite.com/abc.html on the website you will be redirected to (or shown) the 404 page

We have looked at some common page types above. Now that we have understood these aspects of templates, let us look at static website generators

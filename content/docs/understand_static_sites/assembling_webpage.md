+++
title = "Assembling a website: Putting it all together"
date = 2018-06-08T19:44:35+05:30

pageNumber = 7
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
text = "Static Website Generator"
url = "/docs/understand_static_sites/static_website_generators/"

[[next_page]]
text = "Static Website Generator Example: Hugo"
url = "/docs/understand_static_sites/static_generator_example_hugo/"

[[quick_links]]
text = "*Site level configuration*"
url = "#stage-1-load-site-level-configuration"
[[quick_links]]
text = "*Create html for single pages*"
url = "#stage-2-create-html-for-each-content-page-in-the-content-directory"
[[quick_links]]
text = "*Create list pages*"
url = "#stage-3-create-list-pages-for-each-single-page-directory"
[[quick_links]]
text = "*Create taxonomy pages*"
url = "stage-4-create-taxonomy-list-pages-for-each-single-page-created"
[[quick_links]]
text = "*Place each output correctly*"
url = "#stage-5-place-each-content-output-in-the-appropriate-directory"
[[quick_links]]
text = "*Copy static assets like images*"
url = "#stage-6-copy-assets"


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
text = "Website Templates"
url = "/docs/understand_static_sites/website_templates/"
[[quick_links]]
text = "Static Website Generator"
url = "/docs/understand_static_sites/static_website_generators/"
[[quick_links]]
text = "Static Website Generator Example: Hugo"
url = "/docs/understand_static_sites/static_generator_example_hugo/"

# Writeup goes below
+++

From the perspective of the static generator there are the following stages in *assembling* a website.

## Stage 1: Load Site level configuration

1. Load all the site level configuration defaults from the template
2. Load all the site level configuration specified as markup (json, yaml or toml) that are input by the user overriding template defaults if necessary 
    - This is done through standard markup parsers available in the templating engine of the static website generator

## Stage 2: Create html for each content page in the content directory

1. Load page level configuration by parsing the input markup (json, yaml or toml)
2. Load page level content into memory by parsing the markdown into html. If there are any shortcodes in the content markdown
    1. Go to the shortcodes directory and search for the shortcode
    2. If found pass the content to the shortcode
    3. The shortcode layout contents should output some html (and/or css, javascript)
    4. This is substituted back into the main content instead of the shortcode
    5. Note that shortcodes have to be within specified start and end characters to distinguish them from regular writing
3. For each output type (for example html, css and javascript)
    1. Go to default layout
    2. Depending on the parameters and default options, load the template pieces required for each block of the default layout
    3. Load any data from the Data folder, if called for by the template, by parsing the data markup (json, yaml or toml)
    4. Parse the template piece through the template engine providing the variables of site level configuration, page level configuration, external data from data folder and content for the page
    5. Substitute the content and other variables into the template piece to generate the html, css or javascript text.

## Stage 3: Create list pages for each single page directory

### What are single page directories

Let us say that apart from the base content files like index and 404, our site has content files for a number of articles, a number of notes and a few presentations.

1. The articles are contained in the main content directory under another directory called articles
2. The notes files are placed in the main content directory under another directory called notes
3. The presentations are placed in the main content directory under another directory called presentations

### What is the need for list pages

1. List pages are indices for the pages under them.
2. The kind of list page all of us are familiar with is the google search results page. The results are optimized to give us an overview of what exists within the page. Each result here has a heading, a url and a summary to the viewer
3. Similarly we would want each list page to provide a title and a summary. Maybe some other parameters like author name also could be included
4. Thus list pages should have access to the contents of the page and configuration items like Title and author
5. Further we want to be able to generate a summary for contents of the page, thus the static generator should have a summary function

### Template pieces, default layouts and configuration

1. Just like single pages contain a default configuration, list pages too contain a default layout.
2. These default list layout pages contain blocks.
3. Each of these blocks can be substituted by a template piece. These blocks may include
    - The navbar
    - The footer
    - The title area
    - The list layout 
4. The main template piece is the list layout
    - The list layout contains information or summaries about several pages.
    - The summary layout is the same for each page in the list even if the content varies
    - The list layout can therefore be thought to loop over each of the summary pages creating the same layout for each with differing contents
5. The summaries in the typical list layout may just have a title and summary like the google search pages, but one can create all kind of list layouts
    - Say list with title, summary and thumbnail image (like amazon search pages)
    - Say cards which have thumbnail image and summary details
    - List layouts might also have different designs of elements on different screens like mobiles and desktops
6. Can the website creator describe the configuration of such list pages? Yes. The configuration can be described similar to how the configuration is described for each of the single pages. These may be placed in the same folder as the single pages with a predefined name format to distiguish that it is a configuration file. For example, in the case of Hugo, it is [_index.md](https://gohugo.io/content-management/organization/#index-pages-index-md)
    - The default configuration for list layout may be described in the template
    - The configuration file described here may override the template default regarding the particular list layout to be used

### Generating list layouts

Now that we have the layouts and configuration, the static generator can generate the content for the list pages. This would mean it has to generate the html, css and javascript output for all such pages.

Let's look at this in two parts: Getting the configurations and generating the html,css and javascript

#### Getting the configurations

This involves getting (a) the particular list configuration page that the user may have createdd and (b) the default template configuration settings that may be provided from theme or elsewhere

1. The static generator would have in memory the template's default list configuration files
2. For each content directory, once the single pages have been created, the static generator searches for the configuration page
3. If found, any configurations from the default that are also present in the directory configuration page are replaced with the directory configuration page values.

#### Generate html css and javascript based on the list configuration

1. Go to the default layouts folder and get the default list template. This may have many blocks like nav menu, footer, popup, sharer, header, and list layout
2. For each of these blocks, there would be html, css and optionally javascript to be generated. There would be template pieces associated with each of these.
3. Thus, for each of the output formats:
    1. For each block in the default layout, the relevant configuration value would specify the template piece to be chosen
    2. This template piece would have a mixture of code and content which is parsed similar to the single page template pieces
    3. The template piece for the list layout is slightly unique as it has access to the content and configuration files for all the pages for which the list is being created
    4. The list layout template piece would define a summary html that summarizes the pages. This may contain the title and a small summary of the content along with an optional thumbnail image, author name or any other such details
    5. The static generator loops over the pages and generate the summary html for each of these pages based on the above layout definitions

### Using List Layouts in front (or any other) pages

Since list layouts are a template piece by themselves, a question arises as to whether these can be used as a section in some other pages. The answer is yes. Typically list layouts may be used in the front page of the website to showcase some important articles in the website

1. The difference here is that not all pages need to be showcased to show in the list section
2. Thus we can introduce a configuration setting in the single page: "frontpage_showcase" which can take values true or false, which can decide whether a page is part of the frontpage or not
3. if there are any other showcase templates, we can have similar settings for those as well

### Arrangement of pages within a list layout

Now that we have understood how the page summaries are showcased in a list templates, a question that naturally arises is how are they arranged within the template

1. The static generator should give an option to sort the pages in the list templates by any of the parameters defined in the pages.  
2. Typically all the pages in the same folder should have the same parameters and it should be easy to sort by these
3. The list configuration should define the parameter by which to sort and whether it should be ascending or descending.
4. When it is not specified a good default method to sort is by date of creation of the content in order of newest first.

### Pagination

So now we have understood the display of a certain number of page summaries in a list template. But the total number of pages to display might exceed what can be displayed on a single page. For example, let's say there are a hundred posts to display on a blog list, whereas a single page can only list 10. Then there need to be 10 list pages generated. This process is called **pagination**

1. The number of page summaries per list page is a matter of preference. It is decided by the list page configuration or a default like 10.
2. Depending on this number, even before looping through the pages, the static generator would know how many pages are to be generated
3. For each of these pages, the generator would loop through the default list template and generate each block and template piece, with the only thing changing being the pages chosen for the list layout
4. The pagination module of the static generator must also give the ability to a template to generate html for navigation between the different pages. For example, at the bottom of the search page in google, we see links to go to page2, page3... of the search.
    - This includes links to next page, previous page, first page, last page and any particular page number.
5. Thus a separate template piece (with any kind of styling) may handle pagination links just under the list layout.
6. With some smart javascript coding, one can implement things like infinite scroll (like in the facebook feed page) and view more button (like in google photos search in mobiles) which work by loading the next pagination page as you reach the end of the page (infinite scroll) or click the view more button.

## Stage 4: Create taxonomy list pages for each single page created

Similar to the creation of list pages specified above, one may want list pages for various categories and taxonomies that each of the pages fall into.

### Sample Taxonomy Pages

In the case of tags for instance, if we are discussing posts on a news website,

- Post 1 may be tagged under football and Indian Sports
- Post 2 might be tagged under football and English Sports
- Post 3 might be tagged under cricket and Indian Sports

In such a case we would want

- a list page for football containing Post 1 and Post 2
- a list page for Indian Sports containing Post 1 and Post 3
- a list page for English Sports containing Post 2
- a list page for cricket containing Post 3

### Creating listings through taxonomies: a more complicated taxonomy pages example

We can hold any number of taxonomies like 'tags', for which list pages could be created. For instance *if we were to create a movies listings website*

1. We could have a taxonomy for actors, one for directors, one for movie genre and so on.
2. Each of these taxonomies like actors would have multiple terms. For example, the taxonomy actors could have terms like 'Bruce Willis','Tom Cruise' and so on.
3. Each of these taxonomies would come with a list page like so *`http://www.ksmadhavan.in/actors`* which lists out all the actors catalogued on the site
4. Each of the actors would contain a list page like so *`http://www.ksmadhavan.in/actors/bruce_willis`* which lists out all the movies associated with the actor being catalogued. This is the typical list page mentioned in the previous section.
5. Both of the above are list pages, the first page lists the terms in the particular taxonomy (for example it just lists the actors), the second lists the pages for which there is content.
6. So the question arises, how does one specify the content matter and configurations for the taxonomy pages

### Specifying Content and configurations

Unlike content pages which are created as the static generator comes across the content pages, and the list pages which are created based on the directories in which the static sites the taxonomy pages have to be created after all the other pages have been parsed and all the terms for each of the taxonomies are known.

Where content and configurations are stored for taxonomies becomes fairly important. This is quite often specified by the Static Site Generator.

1. Typically there is a folder called taxonomies under content
2. Under this 'taxonomies' folder, each taxonomy is a directory.
3. Under these folders each 'term' is a file specifying the content and the configurations

For instance, going back to our movies example from earlier.

1. The primary single pages in that example were movies listings. 
2. These movies content files (like JurassicPark.md and Titanic.md) were placed under the movies directory in the content folder
3. There were are various taxonomies for each movie like actors, directors, genre and so on.
4. Lets say the terms under the taxonomy 'actors' included 'BruceWillis', 'KateWinslet' and 'EmmaWatson'
5. In such a case, there would be a taxonomies directory under the content folder. This directory would contain various directories like 'actors', 'directors', 'genres' and so on.
6. Each of these directories would contain content files. For example the actors directory would contain content and configuration files like 'BruceWillis.md', 'KateWinslet.md' and 'EmmaWatson.md'
7. Note at this point that the above content files are actually list pages for the movies these actors acted in. These are otherwise called taxonomy terms pages
8. There could be another content and configuration page in each of these directories, for example in the directory 'actors', which specifies configurations for how the actors should be listed out. This could be called '_index.md' or some such.

### Process of Generation of taxonomy pages

1. The static generator collects the list of allowed taxonomies from the site configuration page
2. For each of these taxonomies it creates a list.
3. The generator then parses all the content pages of the site.
4. As the generator comes across taxonomy terms in each page, it adds them to the lists for the taxonomies
5. For each taxonomy that has a term, 
    - The generator tries to find the configuration page for the taxonomy at the location specified in the previous section.
    - The configuration page should specify a list layout template piece.
    - Based on this list layout template piece, the page listing the terms can be generated based on the usual blocks from the default layout template
    - Now for each term in the list of the taxonomy
        - The generator finds the configuration page at the location specified in the previous section
        - Based on this configuration, the list layout is chosen and from this the entire page can be built out.
6. Note that the same taxonomy terms may come from completely different kinds of pages, which don't share the same configurations, and therefore the list layouts for taxonomy terms should be kept simple. The same applies for the taxonomy pages that just list the terms.

## Stage 5: Place each content output in the appropriate directory

### Types of pages generated

There are seven kinds of files generated for each format (html,css and javascript).

1. The front page of the website
2. Pages in the base directory
3. List Pages for each type of content
4. Pagination pages for each list page
5. Single pages for each type of content
6. Taxonomy pages listing out the terms in that taxonomy
7. Taxonomy terms pages listing out the Single pages categorized under that taxonomy term

### Storage and URLs

1. First an output directory is created where all the output will be stored.
2. When you type an url like 'http://ksmadhavan.in/blogposts/' the server will serve that request by making an attempt to retrieve the html file 'http://ksmadhavan.in/blogposts/index.html'. This system is known as **Pretty URLs**. Our output of files is based on this.
3. While filenames can be of any kind and include spaces and other special characters, weburls cannot take any values. Therefore the page generator would often replace spaces (the most common kind of special character) with underscores

### Storage of each of the types of files

We mentioned 7 types of files. Let us look where each of these types of pages is stored

#### Front Page Storage

- This is stored as index.html in the base directory
- For example, if the output folder were to be called *outputFolder*, the file would be placed at 'outputFolder/index.html'

#### Pages in the base directory

- This is stored as index.html in the directory with the same name as the content file name in the base output directory
- For example the output html file generated based on 'contentFilename.md' in the base content directory would be placed at 'outputFolder/contentFilename/index.html'

#### List Pages

List Pages for each type of content, say 'blogposts' if there is no pagination

- These are stored as index.html under the directory name 'blogposts' which resides in the base directory

#### Pagination pages

Pagination pages If there are multiple pages in the list pagination, say 2 pages for the type of content 'blogposts'

- A directory called blogposts is created in the outputFolder
- The first pagination page is created as mentioned under the previous point
- For creating the pagination:
    1. A directory called pages is created under blogposts
    2. Two directories '1' and '2'. Each of these contains an 'index.html' page.
    3. The first page, '1' is always a [simple html redirect (canonical redirect)](https://support.google.com/webmasters/answer/139066?hl=en) back to the base list pages url
    4. For instance 'http://ksmadhavan.in/blogposts/pages/1/' would redirect to 'http://ksmadhavan.in/blogposts/'
    5. The second page onwards, the complete list page is placed under index.html
- To summarize, 
    1. the list page for the first pagination page is placed at 'outputFolder/blogposts/index.html'.
    2. There is a simple html redirect placed at 'outputFolder/blogposts/pages/1/index.html' 
    3. the list page for the second pagination page onwards is placed at 'outputFolder/blogposts/pages/pagenumber/index.html'. For example the second pagination list page is placed at 'outputFolder/blogposts/pages/2/index.html'

#### Single pages

Single pages (say post1 and post2) for each type of content (say blogposts)

- These are stored as index.html in the directory with the same name as the filenames based on which they were generated
- For example the output html file generated based on 'post1.md' in the blogposts content directory would be placed at 'outputFolder/blogposts/post1/index.html'
- We could equally have placed the output html at 'outputFolder/blogposts/post1.html', but this choice is a matter of convention. Most weburls today do not need you to type out the last ".html" bit.

#### Taxonomy pages

Taxonomy pages listing out the terms in that taxonomy (say for the taxonomy actors)

- These are stored as index.html under the taxonomy name
- For example, in our website for movie listings, the output taxonomy pages for the taxonomy actors would be at 'outputFolder/actors/index.html'
- If there are more than 1 page of terms, then pagination occurs
    1. The first pagination page is still output at 'outputFolder/actors/index.html'
    2. There is a simple redirect page generated at 'outputFolder/actors/pages/1/index.html' redirecting to 'outputFolder/actors/index.html'
    3. For all other pagination pages, index.html pages are generated at 'outputFolder/actors/pages/pagenumber/index.html'. For example the second pagination list page is placed at 'outputFolder/actors/pages/2/index.html'

#### Taxonomy Terms Pages

Taxonomy terms pages listing out the Single pages categorized under that taxonomy term

- Going forward on our previous movies example, lets say the terms under the taxonomy 'actors' included 'BruceWillis', 'KateWinslet' and 'EmmaWatson', we would create directories at 'outputFolder/actors' for each of these terms
- We would place the list page at index.html within that particular actor directory. For example, for the actor 'BruceWillis', the list page may be placed at 'outputFolder/actors/BruceWillis/index.html'
- Quite often there may be pagination here also. This is handled as usual with a redirect generated at 'outputFolder/actors/BruceWillis/1/index.html' and all other pagination pages generated at 'outputFolder/actors/BruceWillis/pagenumber/index.html'

## Stage 6: Copy Assets

Copy all the assets from the input assets directory into the base directory in the output

1. This may contain things like the [robots.txt](https://moz.com/learn/seo/robotstxt)
2. Sometimes the static generator by itself creates a sitemap. Otherwise this has to be created in the static directory from where it is copied over

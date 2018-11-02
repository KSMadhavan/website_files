+++
title = "Connect github and Godaddy: the website goes live"
date = 2018-06-08T19:44:35+05:30

pageNumber = 9
# -----------------------------------------
# Summary section
# -----------------------------------------
# The below image will be shown in all the cards pointing to this article
caption_image = "dog_popup_thanks3.jpg"
# The below summary message will be shown in all the cards pointing to this article. If not available, it would be generated from the content of the page.
summary_content = '''
Create your site in 10 easy steps'''
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
tags = ["Static Sites","documentation","Hugo","websites","setup"]
categories = ["Website"]

[[previous_page]]
text = "Check site and Upload to github"
url = "/docs/create_your_website/upload_to_github/"

[[next_page]]
text = "Plan your website"
url = "/docs/create_your_website/plan_website/"

[[quick_links]]
text = "Implement Static Site with Godaddy & github"
url = "/docs/create_your_website/implement_static_website_godaddy_github/"
[[quick_links]]
text = "Download Essential Software"
url = "/docs/create_your_website/download_essentials/"
[[quick_links]]
text = "Setup Github"
url = "/docs/create_your_website/setup_github/"
[[quick_links]]
text = "Buy the domain and setup godaddy"
url = "/docs/create_your_website/setup_godaddy/"
[[quick_links]]
text = "Download the template files"
url = "/docs/create_your_website/download_template/"
[[quick_links]]
text = "Preview the site"
url = "/docs/create_your_website/preview_site/"
[[quick_links]]
text = "Modify Site Settings"
url = "/docs/create_your_website/modify_settings/"
[[quick_links]]
text = "Check site and Upload to github"
url = "/docs/create_your_website/upload_to_github/"

[[quick_links]]
text = "Plan your website"
url = "/docs/create_your_website/plan_website/"
[[quick_links]]
text = "Add your content to the website"
url = "/docs/create_your_website/add_content/"

# Writeup goes below
+++

Now your website is nearly ready to go live. All that remains is connecting github with godaddy. This consists of two parts:

1. Make github pages viewable
2. Change godaddy CNAME to your github

Let us look at these in more detail

### Make your github pages viewable

1. Do a deploy before you start
    1. Open your terminal/bash and cd into the directory containing the website files.
    2. type `./deploy.sh` into the terminal
        - Note that on windows machines this may be `.\deplay.sh` or even just `deploy.sh`
    3. Open a browser and check update times on your github repository at  `https://github.com/yourusername/yourblogname`
2. Allow github pages
    1. Go to `https://github.com/yourusername/yourblogname`
    2. Click on the settings button towards the right side on the menu on top of the page
    3. Scroll down till you see the Github Pages section. Here you should see a dropdown for 'Source' - which should have a default setting 'None'. Click this and choose **'master branch'**. Click Save
    4. Add a Custom Domain: Just below the place where you selected the source, there is a text field where you can add a custom domain. Choose `www.ksmadhavan.in`, where ksmadhavan.in is the domain you purchased from godaddy
    5. Save your changes: A success message such as 'Custom domain is saved' and 'Your site is ready to be published at http://www.ksmadhavan.in/' should appear
    6. You can optionally choose 'enforce https'. Sometimes this option works only after some time of the above options being chosen.

### Add a CNAME record to Godaddy to point to github

On the godaddy DNS page that we saw in the [godaddy setup](/docs/create_your_website/setup_godaddy/) section, we need to now add a CNAME record

1. Go to your DNS page (which should be at https://dcc.godaddy.com/manage/ksmadhavan.in/dns)
2. You should see the list of records right at the top.
3. Click on 'Add' just below this list
4. In the options that open up:
    1. Choose Type: `CNAME`
    2. Choose Host: `www` (if you want to serve website on www.ksmadhavan.in)
    3. Choose Points To: `yourusername.github.io`. Of course replacing yourusername with your own github id
    4. Choose TTL: 1/2 hour or some such. Doesn't make a difference

Now, use your web browser to go to the site http://www.ksmadhavan.in and ***you should see the webpage ready!***

### Regular Runs

Now that it works once, it's always going to work. Every time you change or add a new page, if you want to see it on your site all you need to do:

1. Open your bash/terminal/command prompt
2. cd to your website folder `cd c:/users/yourname/website`
3. Type `./deploy.sh` and then `./commit.sh` in your bash

**Note**: windows uses backslash instead of forward slash in the commands above.
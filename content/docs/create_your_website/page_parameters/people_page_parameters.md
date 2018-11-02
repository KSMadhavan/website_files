+++
title = "People Page Parameters"
date = 2018-06-08T19:44:35+05:30

pageNumber = 117
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
highlight = true
highlight_languages = ["bash","toml"]
highlight_style = "railscasts"

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Static Sites","documentation","Hugo","websites","setup"]
categories = ["Website"]

[[previous_page]]
text = "Add your content to the website"
url = "/docs/create_your_website/add_content/"

[[next_page]]
text = ""
url = ""

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
text = "Connect github and Godaddy"
url = "/docs/create_your_website/connect_github_godaddy/"
[[quick_links]]
text = "Plan your website"
url = "/docs/create_your_website/plan_website/"
[[quick_links]]
text = "Add your content to the website"
url = "/docs/create_your_website/add_content/"


# Writeup goes below
+++

The people pages have a large number of additional settings over and above the common settings. This is similar to the about section on the front page. These settings are listed below

```toml
# 1. We use the setting "name" instead of title used in other pages to describe who the page is about
name = "Wise man"

# 2. You can input the role the person plays
role = "Chairman, K S Madhavan & Associates"

# 3. The portrait image mentioned below can be similar to the caption image and be a generic squarish (width = height) photo of the person.
# Place portrait in img folder
portrait = "people/obama.jpg"


# 4. We categorize people with divisions and teams instead of tags and categories which are the general taxonomies. If you want to add any taxonomy below, make sure to also mention it in the config.toml page

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
divisions = ["Technology"]
teams = ["Leadership"]

# 5. We can mention multiple affiliations of the person along with a link like below
# ---------------------------------
[[affiliations]]
    name = "Company1, Company2"
    url = ""
[[affiliations]]
    name = "Company3, Company4, Company5"
    url = ""

# 6. We can also mention social media links of the person. The icons are chosen from here: https://fontawesome.com/v4.7.0/icons/

# ---------------------------------
# Choose fa (font-awesome) icons below
# ---------------------------------
[[social]]
    icon = "fa-envelope"
    icon_pack = "fa"
    link = "mailto:yourName@gmail.com"
[[social]]
    icon = "fa-linkedin"
    icon_pack = "fa"
    link = "//linkedin.com/in/yourName/"

# 7. You can list any interests for the person along with a title for the interests section
[interests]
title = "Interests"


[[interests.list]]
    title = "Artificial Intelligence"
    subtitle = ""
    icon = "fa-rocket"
[[interests.list]]
    title = "Networks"
    subtitle = ""
    icon = "fa-rocket"


# 8. Lastly you can list education of the person as required below
# ---------------------------------
[education]
    title = "Education"
# ---------------------------------
[[education.list]]
    title = "Master of Business Administration, 2012"
    subtitle = "University1"
    icon = "fa-graduation-cap"

[[education.list]]
    title = "Bachelor of Technology, 2007"
    subtitle = "University2"
    icon = "fa-graduation-cap"

```

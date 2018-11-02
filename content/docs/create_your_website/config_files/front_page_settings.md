+++
title = "Front Page Settings"
date = 2018-06-08T19:44:35+05:30

pageNumber = 2
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
highlight_languages = ["toml","html"]
highlight_style = "railscasts"

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Static Sites","documentation","Hugo","websites","setup"]
categories = ["Website"]

[[previous_page]]
text = "Modify Site Settings"
url = "/docs/create_your_website/modify_settings/"

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
text = "Buy the domain and setup godaddy"
url = "/docs/create_your_website/setup_godaddy/"
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
The front page settings are contained in the `_index.md` file which is in the `content` folder. It contains most of the settings needed to be changed in the front page.

All settings in the _index.md file need to be looked through so we won't be separately mentioning what needs changing. There are broadly 8 sections in the front page:

1. Top Banner
2. Showcase
3. About Us
4. Logo Wall
5. Featured Pages
6. Call to Action
7. Reviews
8. Contact

If you see front page of the [demo site](https://template.thinkingtree.me/), you can have a look at the various sections. Each of these can be set on or off. You can heve a detailed look at the options in the section below, based on which you should change your `_index.md` file in the `content` folder.

```toml
# Please use your own images. I provide the code with no implicit or explicit warranties and I am not to be liable for any claim or damages arising from use of this software.

# All options below that are marked with * need to be changed
# There are eight sections in the front page
# 1. Top Banner
# 2. Showcase
# 3. About Us
# 4. Logo Wall
# 5. Featured Pages
# 6. Call to Action
# 7. Reviews
# 8. Contact

# At the outset decide which ones of these you want to use by viewing the preview index page.
# If you don't need any one of these, just set active to false for that section below
# Once you decide you want to have a section, you can change the options for the section.



#* 1. This is the title of the site front page
title = "The Thinking Tree Homepage"

#* 2. These are the popup and sharer options. They are described in more detail in config.toml
show_popup = true
show_sharer = true
rollup_sharer_active = true
fixed_sharer_active = true

# ----------------------------------
# Section 1: Top section
# ----------------------------------
# ----------------------------------
# #
# 1. This is the heading section. Here we use a sliding banner of two images
# 2. The content for the layout can be changed below
# 3. The main fields for rendering the layout are in top_banner.toml in folder 'data/layouts'
# 4. The fields here are rendered by 'render_content_layout_fields.html' which is called by
# #  top_banner.html in homepage-sections
# 5. These fields in 'top_banner.toml' are another (simplified?) way of rendering html.
# 6. One can list multiple slide elements as '[[slide_elements]]'
# 7. For each slide element, one can input styles as '[[slide_elements.styles]]'
# #  with multiple style values as '[[slide_elements.styles.style_value]]'
# #
# #
# 8. We will describe each of the tags in the file top_banner.toml below
# i    name: This has to be unique. It is an identifier of that element. Doesn't go into html
# ii   class & id: These are the class & id of item used in the rendered html.
# iii  content: The actual content for the viewer
# iv   has_children: Decides whether any other elements are rendered within this one
# v    has_parent: true if it is the child of any other element, else false.
# vi   parent: The name of the parent element goes here
# vii  type: Multiple types are there like div -generic html dividor, 'a' for links, etc
# viii slide_elements.styles.media_type: what browser screens to target
# #    https://www.w3schools.com/cssref/css3_pr_mediaquery.asp
# ix   slide_elements.styles.container: css parent name
# x    slide_elements.styles.target: css target
# #    https://www.w3schools.com/css/css_syntax.asp
# xi   [[slide_elements.styles.style_value]]: field (css properties) and value pairs for css
# #    https://www.w3schools.com/cssref/
# xii  [[slide_elements.custom_js_partials]]: Variables for js related to that element
# xiii slide_elements.custom_js_partials.partial_location: Location of js file to load
# xiii slide_elements.custom_js_partials.variable_name: Variables can be passed to above file
# xiv  [[slide_elements.tags]]: Elements of type links ('a') need hrefs passed in the html
# #    These can be passed within tags, which have field and a value. For example:
# xv   slide_elements.tags.field: Can take values like 'href'
# xvi  slide_elements.tags.value: Can take values like 'http://google.com' in example above
# xvii content_field_name: This can be used to replace either "content" or "tags.value"
# #    with a value from another file, which contains the field name and value
# #    For example, one can place 'content_field_name = "link2"' inside 
# #    [[slide_elements.tags]] in top_banner.toml and 
# #    pass link2 from [top_banner.content] in _index.html
# xviiiexternal css sources: One can pass these inside [[slide_elements.css_sources]] 
# #    with an url field
# xix  external js sources: One can pass these inside [[slide_elements.js_sources]]
# #    with an url field, and true/false values for async and defer js sourcing
# #
# ----------------------------------
[top_banner]

active=true
layout = "top_banner" # choose from single or carousel
[top_banner.content]
# content from below. Layout from above
title = "The Thinking Tree"

link1_name = "Posts"
link1 = "#featured_posts"
link2_name = "Events"
link2 = "#featured_events"
link3_name = "Thoughts"
link3 = "#featured_thoughts"

slide1_image = "linear-gradient(to bottom right,rgba(0,0,200,0.2), rgba(200,0,120,0.2)),url(/img/headers/bubbles-wide.jpg)"
slide1_link = "/posts"
slide1_subject = "Posts"
slide1_title = "Onward and Upward, Like a Dendritic Tree"
slide1_description = "Reducing entropy, one post at a time"
slide2_image = "linear-gradient(to bottom right,rgba(0,0,200,0.2), rgba(200,0,120,0.2)),url(/img/orange-fractal.jpg)"
slide2_link = "/publications"
slide2_subject = "Publications"
slide2_title = "Every new day, better than the last"
slide2_description = "Nurturing creativity, like saplings amidst giants"





# ----------------------------------
# Section 2: Showcase section
# ----------------------------------
# ----------------------------------
# 1. This section can be used to highlight the salient points of your website/product
# 2. This section uses Flexbox render the cards in showcase.html in homepage-sections folder
# 3. Each card can contain an icon, a link (even internal link), a title and the content
# 4. The content can be in markdown
# 5. The icons can be chosen from here: https://fontawesome.com/v4.7.0/icons/
# ----------------------------------
[showcase]
active=true
headline_layout = "headline_elements"
[showcase.headline]
title = "Greatest ever works"
subtitle = "Major Projects and Work Interests"

[[showcase.card]]
icon = "fa-laptop"
title = "Responsive Design"
link = "#"
card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."

[[showcase.card]]
icon = "fa-lock"
title = "Web"
link = "#"
card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."

[[showcase.card]]
icon = "fa-shopping-cart"
title = "E-Commerce"
link = "#"
card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."


# ----------------------------------
# Section 3: About us section
# ----------------------------------
# ----------------------------------
# 1. This section broadly contains space for
# i    Heading, sub-heading
# ii   A photo with title and subtitle
# iii  A list of affiliations
# iv   Social Media links
# v    A long form content piece
# vi   A left list with icons and text below content piece
# vii  A mid-right list with icons and text below content piece
#
# 2. These subsections can be changed by changing the configurations below respectively
# i    [about_us.headline]
# ii   [about_us.descriptor] - logo_image, name_title and name_subtitle
# iii  [[about_us.descriptor.affiliations]] (add any number with name and url)
# iv   [[about_us.descriptor.social]] - you can add icon and link. 
#      Choose icon for above from https://fontawesome.com/v4.7.0/icons/
# v    [about_us.detail] - title and content
# vi   [about_us.detail.bottom_left] - title and [[about_us.detail.bottom_left.list]]
#      Add title, an optional subtitle and icon from font-awesome (link above) in the list
# vii  [about_us.detail.bottom_right] - title and [[about_us.detail.bottom_right.list]]
#      Add title, an optional subtitle and icon from font-awesome (link above) in the list
#
# 3. The layout is rendered by about_us.html in homepage-sections directory
# ----------------------------------
[about_us]
active=true
headline_layout = "headline_elements"
[about_us.headline]
title = "About Us"
subtitle = "Serving clients since 1985"
# ---------------------------------
[about_us.descriptor]
logo_image = "portrait.jpg"
name_title = "yourName"
name_subtitle = "Chairman, K S Madhavan & Associates"

# ---------------------------------
[[about_us.descriptor.affiliations]]
name = "Company1, Company2"
url = ""
[[about_us.descriptor.affiliations]]
name = "Company3, Company4, Company5"
url = ""

[[about_us.descriptor.affiliations]]
name = "University1, University2"
url = ""
# ---------------------------------
[[about_us.descriptor.social]]
icon = "fa-envelope"
icon_pack = "fa"
link = "mailto:yourName@gmail.com"
[[about_us.descriptor.social]]
icon = "fa-linkedin"
icon_pack = "fa"
link = "//linkedin.com/in/yourName/"

[[about_us.descriptor.social]]
icon = "fa-facebook"
icon_pack = "fa"
link = "//facebook.com/yourName"

[[about_us.descriptor.social]]
icon = "fa-github"
icon_pack = "fa"
link = "//github.com/KSMadhavan"


# ---------------------------------
[about_us.detail]
title = "Biography"

# ---------------------------------
# Put the content below between the triple quotes. You may use markdown.
# Make sure alignment is ok. I've used replace of '                '
# to remove the leading white space
content = '''
yourName founded K S Madhavan & Associates as a means to work on problems that take time and are more difficult to address than traditional start-ups would allow. Traditionally the distinction between research and production had been fairly well demarcated with research institutions working on technologies that were forward looking and companies working on production oriented technology (technologies which made money today). That distinction has become blurred, especially in computer science with much of the cutting edge improvements happening within companies.

K S Madhavan & Associates is an attempt to work on futuristic technologies covering multidisciplinary domains. We follow problems till their origins, dive into rabbit holes and go deep into the root of problems. Many times this leads us to mathematics, which seems to be the foundation of all else. Sometimes it leads to sociology and behavioural science. Few times it leads to the complexity of Biology. Other times it leads to thought experiments. Most of this rests on a backbone of coding as it is ubiquitous as a tool.

The research areas we work on here are network topologies, computational structures, self-organization and automata, idea space theory. Apart from this core, there is also ongoing work on pattern finding in market microstructure (high frequency trading), and a few applications of complexity and modelling. If you would like to join us to contribute on any of these problems, you are most welcome. We're sure you would find the journey at least slightly enlightening. If you have a problem that you would like us to work on, please contact us below.

yourName has been the head of Data Science at Company1 and Company2. At Company1, he built a data science division from scratch which worked on Data Science as a Service - the Company1 data science team acted as the remote data science team for our clients. This meant building tools to solve common problems between companies and building a team to deal with bespoke problems and on demand requests for client companies. At Company2 he was the head of data science and helped in their Series-B fund-raise round.

Prior to that he was a trader on Wall Street trading currency options. During his time at Company3 he helped setup an automated option price trading/monitoring system. On the research side, he worked on single currency fx pricing and eurchf floor failure models. At Company4 he worked on Equity Exotic Options with a specific focus on RFP pricing and generating client ideas. At Company5, he risk managed an exotics trading book. He distinctly remembers being non-plussed at the fuss over the Company5 collapse, having predicted it a year before (Ref: University2 placement talk - 2007). :rocket:'''

# ---------------------------------
[about_us.detail.bottom_left]
title = "Interests"

# Choose fa (font-awesome) icons below
[[about_us.detail.bottom_left.list]]
title = "Artificial Intelligence"
subtitle = ""
icon = "fa-rocket"
[[about_us.detail.bottom_left.list]]
title = "Networks"
subtitle = ""
icon = "fa-rocket"
[[about_us.detail.bottom_left.list]]
title = "Topology"
subtitle = ""
icon = "fa-rocket"
[[about_us.detail.bottom_left.list]]
title = "Language"
subtitle = ""
icon = "fa-rocket"
[[about_us.detail.bottom_left.list]]
title = "Modelling"
subtitle = ""
icon = "fa-rocket"

# ---------------------------------
[about_us.detail.bottom_right]
title = "Education"
# ---------------------------------
[[about_us.detail.bottom_right.list]]
title = "Master of Business Administration, 2012"
subtitle = "University1"
icon = "fa-graduation-cap"

[[about_us.detail.bottom_right.list]]
title = "Bachelor of Technology, 2007"
subtitle = "University2"
icon = "fa-graduation-cap"

# ----------------------------------
# Section 4: Logo Wall section
# ----------------------------------
# ----------------------------------
# 1. You can list all client logos in this section
# 2. This section uses CSS Grid to place the logos, so spacing between logos is dynamic
# 3. Change the images and links below to use your own
# 4. The layout is rendered by logo_wall.html in homepage-sections directory
# ----------------------------------
[logo_wall]
active = true

# Count the number of logos you want on a row. Choose from 1,2,3,4,6, 12
headline_layout = "headline_elements"
[logo_wall.headline]
title = "Our Clients"
subtitle = "Serving You Always"

# List all the logos in the logo wall below.
# Ensure height to width ratios of the images are all the same.
[[logo_wall.logos]]
source = "https://upload.wikimedia.org/wikipedia/commons/3/37/Palantir_company_logo.png"
link = "//www.palantir.com/"
name = "Palantir"

[[logo_wall.logos]]
source = "https://media.licdn.com/dms/image/C510BAQHxVXskfQIR-w/company-logo_200_200/0?e=2131920000&v=beta&t=I-Eibuu3JRlpqc2wCpmw--1hp-OAw64YnK8lhO-g-iA"
link = "//www.sigmoid.com"
name = "Sigmoid"

[[logo_wall.logos]]
source = "https://upload.wikimedia.org/wikipedia/en/thumb/7/7a/Flipkart_logo.svg/250px-Flipkart_logo.svg.png"
link = "//www.flipkart.com/"
name = "Flipkart"

[[logo_wall.logos]]
source = "http://www.nanobi.in/wp-content/uploads/2017/09/nb-logo.png"
link = "//www.hotstar.com"
name = "Hotstar"

# ----------------------------------
# Section 5: Featured Posts section
# ----------------------------------
# ----------------------------------
# 1. The featured Posts section is a collection of featured content pieces from different
# #  content types
# 2. For example, it may contain featured featured posts, books, events and thoughts
# 3. The sections are rendered in the order listed in order below.
# 4. The card layouts are listed in the listLayouts folder
# 5. The card layouts may require fields which are specific to the different sections
# 6. Which cards are displayed:
# i      The content pieces with `featured = true` setting are ordered by the 'sort_field'
# ii     in either ascending (asc) or descending order (desc) based on 'sort_order'
# iii    Then the first 'num_featured' number of cards are displayed.
# 7. The rendering is done by show_featured.html in the homepage-sections folder
# 8. The default list layouts for each type of content are at sectionwise_list_layouts.toml
# #  in the data/layouts folder
# ----------------------------------
[featured_pages]
active = true

[[featured_pages.sections]]
name = "people"
title = "Our Strength"
subtitle = "Our people are our strength"
num_featured = 4
sort_field = "title"
sort_order = "asc"
card_layout = "people_cards_list_style1"

[[featured_pages.sections]]
name = "books"
title = "Books"
subtitle = "The latest and greatest books"
num_featured = 5
sort_field = "title"
sort_order = "asc"
card_layout = "long_list_with_image"




# ----------------------------------
# Section 6: Call to Action section
# ----------------------------------
# ----------------------------------
# 1. This section includes two call to action buttons
# 2. This uses render layouts function
# 3. Change the images and links below to use your own
# ----------------------------------
[cta]
active = true
# Check the home_cta toml file in data/layouts/ to see what is rendered.
# If you want you can create a new layout toml file in the same location and change the
# layout field below to render that layout
# The render function is in layouts/functions/render_content_layout_fields.html and is
# called from cta.html in layouts/homepage-sections
layout = "home_cta"
# Below fields are self explanatory once you see the call to action section on front page
[cta.content]
top_right_image = "img/dog_transparency2.jpg"
bottom_left_image = "img/dog_transparency1.jpg"
heading = "You can call someone to action"
subheading = "And hope that they come and do the action. This is called call to action"
cta_button1_text = "Start a new blog with Raz"
cta_button2_text = "Visit our blog"
cta_button1_link = "//www.github.com/KSMadhavan/website"
cta_button2_link = "//www.shingo.institute"



# ----------------------------------
# Section 7: Reviews section
# ----------------------------------
# ----------------------------------
# 1. Reviews are a necessary part of many types of sites
# 2. The reviews below use the masonry layout popularized by pinterest
# 3. Instead of javascript rendering we have done the below through CSS Grid
# 4. The rendering is done by reviews.html in homepage-sections
# 5. You can change, add or remove any reviews below. Keep atleast one review
# ----------------------------------
[reviews]
active = true
# Check the toml file in data/layouts/ to see what is rendered.
headline_layout = "headline_elements"
[reviews.headline]
title = "Reviews"
subtitle = "We retain relevance to the latest and the greatest from across the galaxy"

# Below are for illustration. Add your reviews below
[[reviews.review]]
reviewer_name = "Mighty Thor"
reviewer_location = "Asgard"
reviewer_review = "My strength through all these years of thick and thin has been sustained by this beautiful blog"
[[reviews.review]]
reviewer_name = "Cabaret Dancer"
reviewer_location = "Moulin Rouge, Paris"
reviewer_review = "I could use a lot of practice in my line of work. But no need for any practice as long as I have this blog. It teaches me everything!"


# ----------------------------------
# Section 8: Contact Us section
# ----------------------------------
# ----------------------------------
# 1. The main reason for this section is the map. 
# 2. This is rendered by the contact.html in the homepage section
# 3. Additional to the map, you may add any number of contact fields
# 4. The default location for the map may be set in config.toml
# 5. The maps api needs you to register, details given in config.toml
# ----------------------------------
[contact]
active = true
headline_layout = "headline_elements"
[contact.headline]
title = "Contact Us"
subtitle = "Always here to help"

[[contact.fields]]
name = "contact_email"
description = "email"
font_awesome_icon = "fa-envelope"
link = "mailto:yourName@gmail.com"
text = "yourName@gmail.com"
style = "color:#333; margin-bottom: 15px; display:block;"

[[contact.fields]]
name = "contact_phone"
description = "phone"
font_awesome_icon = "fa-phone"
link = "tel:987-654-3210"
text = "987-654-3210"
style = "color:#333; margin-bottom: 30px; display:block;"

```

+++
title = "Config.toml settings"
date = 2018-06-08T19:44:35+05:30

pageNumber = 1
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
The `config.toml` file contains most of the site settings. It is found directly in the main website folder.

The following settings need to be changed in the file:

```toml
baseurl = "http://www.ksmadhavan.in/"
title = "K S Madhavan & Associates"
disqusShortname = "yourdisqusShortname"
googleAnalytics = "UA-123456789-1"
copyright = "&copy; 2018 K S Madhavan & Associates"
site_author_name = "yourName"
role = "Chairman, K S Madhavan & Associates"
email = "yourName@gmail.com"
default_description = "-273.15K. So Cool."
facebook_admin_handle = "KSMadhavan"
twitter_creator_handle = "@KSMadhavan"
twitter_site_handle = "@KSMA"
favicon = "favicon.jpg"
apple_touch_icon = "favicon.jpg"
logo = "logo.jpg"
map_api_key = "AIzaSyDha-Xtvn4VY8lzsp3bw9zSw5eH_23MR5Qg"
latitude = "12.932376"
longitude = "77.630389"
img_source = "/img/flowers_line_drawing.jpg" # decorative image for popup
popup_submission_mail = "yourName@gmail.com"
popup_submission_subject = "New subscription for your site!"
secondary_forwarding_emails = ["yourName@gmail.com","anotherName@gmail.com"]
[[params.footer_network]]
    url = "https://www.facebook.com/yourName"
[[params.footer_network]]
    url = "https://www.linkedin.com/in/yourName/"
[[params.footer_network]]
    url = "http://github.com/KSMadhavan"
```

The below sample explains each of the settings in the file. You can use it to fill your own settings.

```toml
# Notes. those options marked with * need to be changed. Rest are optional
#* 1. baseurl is your domain name
baseurl = "http://www.ksmadhavan.in/"

#* 2. title is K S Madhavan & Associates
title = "K S Madhavan & Associates"

#* 3. disqus is the third party application we will be using for comments. Get your own disqus shortname here: https://disqus.com/admin/create/ and fill it below
disqusShortname = "yourdisqusShortname"

#* 4. Enabling Google Analytics on your site enables you to track site usage, referrers and various other statistics.
## - See how to get your google analytics ID here: https://support.google.com/analytics/answer/1042508?hl=en
## - The file where google analytics is implemented is /layouts/partials/js_scripts/ga.js

googleAnalytics = "UA-123456789-1"

# 5. uglyURLs decide how your pages are saved. When enabled, creates URL of the form /filename.html instead of /filename/.
uglyURLs = false 

# 6. Summaries in lists - number of words used in the Hugo summary function
summaryLength = 25  

# 7. Pagination Options
# 7.1 How many pages by default in any list page
paginate = 10

# 7.2 What are the pagination list pages called. 
# For example http://www.mydomain.com/posts/{{paginatePath}}/2
paginatePath = "page"


# 8. Directories names in the theme. Keep defaults here
themesDir = "themes"
archetypeDir = "archetypes"
contentDir ="content"
dataDir ="data"
publishDir = "public"
layoutDir ="layouts"




#* 9. Your copyright notice - appears in site footer and in RSS. Note: To display a copyright symbol, type `&copy;`.
copyright = "&copy; 2018 K S Madhavan & Associates"

# 10. If enableRobotsTXT is true, a simple robots.txt is created allowing all agents to crawl everything. If you want to create your own robots.txt, then place a robots.txt in the static folder.
enableRobotsTXT =true



# 11. If enableGitInfo is true, then last modified date is obtained from git logs. It may be slow. so better false.
enableGitInfo = false

# 12. Language - use some form of english
languageCode = "en-us"

# 13. For debugging while testing only, you can turn this to true. When you type `hugo` then the log file will be generated at below location. Server anyway generates errors, so turning false
log = false
logFile ="public/log.txt"


# 14. Enable verbose logging for hugo server on the command `hugo server -D`.
verbose =true
verboseLog =true

# Below the theme creator can create their own site wide variables

[params]
#* 15. Site Author name
site_author_name = "yourName"

#* 16. Site creator role. This will be used wherever role is required.
role = "Chairman, K S Madhavan & Associates"

#* 17. Site creator email. Again used in a bunch of places like contact
email = "yourName@gmail.com"

# SEO Section

#* 18. This is the default description of the website used for SEO (facebook shares etc)
default_description = "-273.15K. So Cool."

#* 19. Add your FB admin site handle for facebook cards
facebook_admin_handle = "yourName"

#* 20. Add your twitter handle for twitter sharing cards
twitter_creator_handle = "@yourName"

#* 21. Add your twitter site handle for twitter sharing cards if any, or keep same as twitter_creator_handle
twitter_site_handle = "@KSMadhavan"


#* 22. Choose a favicon. Make it really small, and save this in the *static* folder.
favicon = "favicon.jpg"

#* 23. Optionally choose another favicon for apple high resolution. Save this also in static folder
apple_touch_icon = "favicon.jpg"

#* 24. Diplay a logo in navigation bar (without the text). Try keeping width to height between 7:5 to 7:7
logo = "logo.jpg"

# 25. When a user refreshes the page, open the page at the top
open_at_top = false

# 26. This is the default font set for this theme. Try to not change, it's used everywhere!
google_fonts = ["EB Garamond","Lora","Roboto Mono"]


# 27. In case you want to add custom css and custom js, place them in (i) /static/css/ folder and (ii) /static/js/ folders
# Add the filenames in the following two arrays
custom_css = []
custom_js = []

# 28. Below will be the active menu items for the navbar (navigation menu) at the top of the page
# Please only include the names as given in the menu.main section below
navbar_active = ["Home","Posts","Thoughts","Publications","Reviews","Notes","Contact"]

#* 29. You can set a map in the front page in the contact section from google maps.
# 1. Get key here: https://developers.google.com/maps/documentation/javascript/get-api-key
# 2. To get your coordinates, right-click on Google Maps and choose "What's here?". The coords will show up at the bottom.
map = true
map_api_key = "AIzaSyDha-Xtvn4VY8lzsp3bw9zSw5eH_23MR5Qg"
latitude = "12.932376"
longitude = "77.630389"
zoom = 15


# 30. Sitewide default for comments. You can enable comments on a page or section basis
enable_comments = false

# 31. A small "back to top" button will show up at the bottom of the website
show_back_to_top = true

# 32. Change various options related to cookie consent form (required for EU etc)
show_cookie_consent = true
cookie_button_color = "#fff"
cookie_button_text_color = "#0095eb"
cookie_button_border_color = "#0095eb"
cookie_button_message = "Got it!"
cookie_background_color = "#0095eb"
cookie_text_color = "#fff"
cookie_link_color = "#aaa"
cookie_message = "This website uses cookies to ensure you get the best experience on our website."
cookie_container_padding_top = "4px"
cookie_container_padding_bottom = "4px"


# There are various changes that can be made to how the sharer works below
[params.sharer]

# 33. Global and page settings for sharer has to be true for it to be shown
sharer_active = true

# There are two ways in which sharers can be included in your site.
# 1. Through a fixed button that when clicked rolls up to show sharing buttons (bottom right of screen)
# 2. Through a fixed menu on the left. This is active on larger screens. On smaller screens, there would be a fixed menu at bottom of screen

# 34. Sharer Rollup button
sharer_rollup_button_active = true
sharer_button_color = "#0095eb"
sharer_pullup_button_icon = "fa-share-alt"

# 35. Fixed menu sharer
# Note that this changes with screen width. This can be checked by pressing ctrl+shift+i on chrome
sharer_fixed_menu_active = true
show_fixed_sharer_on_scroll = true
# If show_menu_on_scroll is true, how much to scroll
scroll_amount_to_activate_sharer = 20


# There are various changes that can be made to how the popup works below
[params.popup]



# 36. Below is the global popup default. 
popup_active = true

# 37. Should popup be shown once per session or persist across browser close? default is persist. This is done by setting a small cookie on client browser
reload_popup_once_per_session = false


# We will allow three types of popups, timed popup, popup on given amount of scroll and exit intent popup
# There are three ways of activating a popup.
#        1) There is a button on the bottom right which can always be clicked.
#        2) There is a delay activation
#        3) There is an exit intent activation
#        4) There is a scroll amount activation
# Of these the button activation is always on. The others can be set here.

# 38. Show popup button at bottom of screen
popup_show_button_on_bottom_right = true
popup_button_color = "#0095eb"
pullup_button_icon = "fa-fire"
pullup_button_icon_color = "#fff"



# 39. Delay activation of popup
activate_popup_on_delay = true
seconds_before_activation = 10

# 40. Exit intent activation of popup
activate_popup_on_exit_intent = true
# The sensitivity is triggered by how fast the user takes the mouse out from top of the window (measured as mouse y coordinate when exit event is triggered)
exit_intent_sensitivity = 20

# 41. Amount of scroll activation of popup
activate_popup_on_scroll = true
scroll_percentage_before_activation = 0.6

# Basically popup is a call to action, if all above are set to true, surely the visitor is going to see the popup


# 42. You can change popup contents below
# The popup will have
#    a) A title
#    b) explanatory text
#    c) an image on the right or as a full background
#    d) A formspree form for collecting name and email id
#    e) A subscribe now button

# choose from a font-awesome icon for the popup pullup (where applicable)

title = "Subscribe Now"
title_color = "#aaaaaa"
subtitle = "Curated selection of articles straight to your inbox"
subtitle_color = "#ffaa11"

#* 42.1 This is an image that will be opened in the popup. Please use your own image
img_source = "/img/flowers_line_drawing.jpg"

# form label color
form_label_color = "#ffaa33"

# form submit text
submit_text = "Subscribe"
submit_text_color = "#ccaaaa"
submit_button_color = "blue"

# Tries to return to the referrer page, but in case that fails, the option below
link_after_submit = "/subscriptionsuccess/"

#* 43. Change the mail recipients and subject below
popup_submission_mail = "yourName@gmail.com"
popup_submission_subject = "New subscription for your site!"
secondary_forwarding_emails = ["yourName@gmail.com","anotherName@gmail.com"]

# 44. Popup close behaviour can be changed below
# Close popup by clicking outside the box
close_on_click_outside = true
# Close popup by pressing escape
close_on_escape = true

# 45. Popup form text goes below. Leave as is.
[[params.popup.form_inputs]]
    name="name"
    required="required"
    type="text"
    autocomplete = "name"
    helper_text = "Your Name *"

[[params.popup.form_inputs]]
    name = "Email ID"
    requried = "required"
    type= "email"
    autocomplete = "email"
    helper_text = "Your Email *"


#* 46. The site footer will contain three icons. You can choose the icons (from https://fontawesome.com/v4.7.0/icons/) and change links below

[[params.footer_network]]
url = "https://www.facebook.com/yourName"
iconpack = "fa"
icon = "fa-facebook"

[[params.footer_network]]
url = "https://www.linkedin.com/in/yourName/"
iconpack = "fa"
icon = "fa-linkedin"

[[params.footer_network]]
url = "http://github.com/KSMadhavan"
iconpack = "fa"
icon = "fa-github"



# 47. This is a superset of all menu options you can choose. The actual menus chosen from this are set from Params.navbar_active above

[menu]
[[menu.main]]
identifier = "home"
name = "Home"
pre = ""
url = "./#about_us"
weight = -1

[[menu.main]]
identifier = "posts"
name = "Posts"
pre = ""
url = "./posts/"
weight = 0

[[menu.main]]
identifier = "books"
name = "Books"
pre = ""
url = "./books/"
weight = 1

[[menu.main]]
identifier = "code"
name = "Code"
pre = ""
url = "./code-snippets/"
weight = 2

[[menu.main]]
identifier = "courses"
name = "Cooks"
pre = ""
url = "./courses/"
weight = 3

[[menu.main]]
identifier = "events"
name = "Events"
pre = ""
url = "./events/"
weight = 4

[[menu.main]]
identifier = "notes"
name = "Notes"
pre = ""
url = "./notes/"
weight = 5

[[menu.main]]
identifier = "people"
name = "People"
pre = ""
url = "./people/"
weight = 6

[[menu.main]]
identifier = "publications"
name = "Publications"
pre = ""
url = "./publications/"
weight = 7

[[menu.main]]
identifier = "reviews"
name = "Reviews"
pre = ""
url = "./reviews/"
weight = 8

[[menu.main]]
identifier = "thoughts"
name = "Thoughts"
pre = ""
url = "./#featured_thoughts"
weight = 9

[[menu.main]]
identifier = "workshops"
name = "Workshops"
pre = ""
url = "./workshops/"
weight = 10

[[menu.main]]
identifier = "contact"
name = "Contact"
pre = ""
url = "/contact"
weight = 100

# 48. Here we choose the taxonomies. Various types of pages use various taxonomies. This doesn't have to be changed unless you are adding new page types to the template. default taxonomies in most pages are tags and categories

[taxonomies]
tag = "tags"
category = "categories"
project = "projects"
division = "divisions"
team = "teams"
genre = "genres"
subject = "subjects"
topic = "topics"
reviewed_item_category = "reviewed_item_categories"
publication_type = "publication_types"
artist = "artists"
album = "albums"


# 49. Configure the English version of the website.
# TODO: ADD OTHER LANGUAGE SUPPORT
[Languages.en]
languageCode = "en-in"

# 50. Choose the output formats you are going to use. The only important one in this case is html
[outputs]
home = [ "HTML", "CSS", "RSS", "JSON"]
section = [ "HTML", "RSS" ]

# 51. Markdown is converted to html by an engine called BlackFriday. Configure BlackFriday Markdown rendering below.
# See: https://gohugo.io/readfiles/bfconfig/
[blackfriday]
hrefTargetBlank = true  # `true` opens external links in a new tab.
fractions = true  # `false` disables smart fractions (e.g. 5/12 formatted as a fraction).
smartypants = true  # `false` disables all smart punctuation substitutions (e.g. smart quotes, dashes, fractions).


# 52. We are using the below shortcode for image processing in our documents. Set the defaults below
[imaging]
# Default resample filter used for resizing. Default is Box,
# a simple and fast averaging filter appropriate for downscaling.
# See https://github.com/disintegration/imaging
# and   https://gohugo.io/content-management/image-processing/
resampleFilter = "box"

# Default JPEG quality setting. Default is 75.
quality = 75

# Anchor used when cropping pictures.
# Default is "smart" which does Smart Cropping, using https://github.com/muesli/smartcrop
# Smart Cropping is content aware and tries to find the best crop for each image.
# Valid values are Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
anchor = "smart"

# 53. The outputs in various formats are created with a filename. The defaults for this can be set below. Not used as such so not that important

[outputFormats]

[outputFormats.json]
baseName = "manifest"
isPlainText = true

[outputFormats.css]
baseName = "styles"

```

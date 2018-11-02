+++
title = "Buy the domain and setup godaddy"
date = 2018-06-08T19:44:35+05:30

pageNumber = 4
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
text = "Setup Github"
url = "/docs/create_your_website/setup_github/"

[[next_page]]
text = "Download the template files"
url = "/docs/create_your_website/download_template/"

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

Ok this section is technically simple, but it's going to take a while. You need to decide K S Madhavan & Associates and go buy the domain from [godaddy](https://www.godaddy.com/). Feel free to buy it from [other sites](https://makeawebsitehub.com/reviews/domain-registrars/) (namecheap, google domains), but godaddy i've found to be cheap and just about effective.

Note: Godaddy may try a bunch of upsells on you like privacy protection and hosting with charges. You don't need any of these, just buy the domain and in case you need anything you can get it later.

The process of buying a domain is not easy, one needs to decide a name and a suffix. A '.com' is not necessary for every site, but [Paul Graham](http://www.paulgraham.com/name.html) suggests using it for a site you expect to become famous. But [that](https://www.forbes.com/sites/christophersteiner/2017/05/03/most-startups-still-believe-they-need-a-dot-com-domain-but-that-is-changing/) seems to be changing.

Personally, for any personal site i would go for a cheaper domain name as long as it's small and people can remember it. Most traffic is going to come from google or social media anyway (and not word of mouth) and that doesn't depend on domain name. On the other hand, if you're a startup and want to become rich and famous one day, the dot-com seems to be the way to go.

### Go buy the domain

1. Go to godaddy.com
2. Search for preferred domain name
3. Add to cart and buy. Just choose one domain for now, you can always add more later. Let's call this domain as "your-domain.com". Of course note that ".com" could be any other suffix like ".org" or some such.
4. Go to https://account.godaddy.com/products/
5. You should be able to see your domain.
6. Typically you may see three buttons here next to your domain: Privacy DNS and Manage.
7. Click on the DNS button. It should open up another window with the domain you are managing. We will call this Your DNS page from now. Bookmark it if necessary or leave open.

#### Create a forward from ksmadhavan.in into the www.ksmadhavan.in

1. On Your DNS page, if you scroll fown, you should see a Forwarding section.
2. You are presently going to create a DNS forwarding from the ksmadhavan.in into the www.ksmadhavan.in
3. Click on the button next to domain. The options to be input are as follows:
    1. In the Forward to option, in the blank space next to http:// type "www.your-domain.com". This means that it is going to forward from http://your-domain.com to http://www.your-domain.com
    2. In options use forward type: Permanent (301)
    3. In options use settings: Forward only
4. click on save
5. Leave this browser window open as we will have to come back here.
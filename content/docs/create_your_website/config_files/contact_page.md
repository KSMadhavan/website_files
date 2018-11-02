+++
title = "Contact Page Settings"
date = 2018-06-08T19:44:35+05:30

pageNumber = 3
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
The settings for the contact page http://www.ksmadhavan.in/contact are contained in the `contact.md` file which is in the `content` folder. You can view the sample page [in the demo site](https://template.thinkingtree.me/contact/)

A contact form is a good way for users to contact you and introduces some interactivity to the site. Even if the site is static, we use a third party application called [Formspree](https://formspree.io/) to enable you to setup a contact form.

Make sure **you change email and contact_secondary_email addresses below**

```toml
# (i) The form on this static site is enabled through formspree
#  1.   Setup: Set email ID and secondary_email below the first time you use the contact form
#       you will get a mail asking you to confirm email ID
#
#  2.   Pricing: Free for first 50 emails a month. At some point if this becomes a pain,
#       I'll implement the form layout with some other endpoint
#
#  3.   The layout used is contact.html in layouts/_default folder
#
# Since this template is static, the contact form uses www.formspree.io as a
# middleware proxy. The form makes a POST request to their servers to send the actual email
#
# (ii) Next Steps
#
#  1.   Set your email address under 'email' below
#  2.   You can change the thanks and error messages if you wish
#  2.   Upload the generated site to your server
#  3.   Send a dummy email yourself to confirm your account
#  4.   Click the confirm link in the email from www.formspree.io
#  5.   You're done. Happy mailing!

layout = "contact"
title = "CONTACT US"
subtitle = "_Please leave your message below and we'll get back as soon as we can_"
title_color = "azure"
subtitle_color = "#aaa"
email = "yourName@gmail.com"
contact_secondary_email = ["anotherName@gmail.com","anotherName@gmail.com"]

buttontext = "Send message"
onSubmit_link = "/contact_success"



# Success and error message overwrite for async contact form
thanks = "Thank you for awesomely contacting us."
error = "Message could not be sent. Please contact us at mail@example.com instead."

[captcha]
buttontext = "Send Message"

# 'warning' defines error messages for invalid inputs
[form.name]
text = "Your Name *"
warning = "Please enter your name."

[form.email]
text = "Your Email *"
warning = "Please enter your email address."

[form.phone]
text = "Your Phone *"
warning = "Please enter your phone number."

[form.message]
text = "Your Message *"
warning = "Please enter a message."

```
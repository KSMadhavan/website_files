+++
title = "Add your content to the website"
date = 2018-06-08T19:44:35+05:30

pageNumber = 11
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
highlight_languages = ["bash","toml"]
highlight_style = "railscasts"

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Static Sites","documentation","Hugo","websites","setup"]
categories = ["Website"]

[[previous_page]]
text = "Plan your website"
url = "/docs/create_your_website/plan_website/"

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



# Writeup goes below
+++

At this stage you are ready to start running your website on your own. We will in this last section look at some more things that you may want to know - how to modify single page settings, template creation, using multiple computers and gotchas with respect to git

## Common Page Parameters

The term 'page configuration' may be met with a little bit of trepidation. Not to worry, these are most innocuous. Common page paramters include title, author, date, caption_image,summary_content,layout, tags and categories. There are also two true/false (boolean) parameters for 'enable_comments' and 'featured' on front page. You can read about these in further detail [here](/docs/create_your_website/page_parameters/common_page_parameters/)

## Individual Page Parameters

We saw above the common settings used across most single pages. Additionally, each page may have its own settings. Let's look at these below in order of alphabetical page types.

1. [Audio Page Parameters](/docs/create_your_website/page_parameters/audio_page_parameters/)
2. [Books Page Parameters](/docs/create_your_website/page_parameters/book_page_parameters/)
3. [Code Snippets Page Parameters](/docs/create_your_website/page_parameters/code_snippet_page_parameters/)
4. [Courses Page Parameters](/docs/create_your_website/page_parameters/course_page_parameters/)
5. [Events Page Parameters](/docs/create_your_website/page_parameters/event_page_parameters/)
6. Notes Page Parameters: No additional parameters apart from [common ones](/docs/create_your_website/page_parameters/common_page_parameters/)
7. [People Page Parameters](/docs/create_your_website/page_parameters/people_page_parameters/)
8. Posts Page Parameters: No additional parameters apart from [common ones](/docs/create_your_website/page_parameters/common_page_parameters/)
9. [Presentations Page Parameters](/docs/create_your_website/page_parameters/presentation_page_parameters/)
10. [Publications Page Parameters](/docs/create_your_website/page_parameters/publication_page_parameters/)
11. [Reviews Page Parameters](/docs/create_your_website/page_parameters/review_page_parameters/)
12. [Thoughts Page Parameters](/docs/create_your_website/page_parameters/thought_page_parameters/)
13. [Workshops Page Parameters](/docs/create_your_website/page_parameters/workshop_page_parameters/)
14. [Documentation Page Parameters](/docs/create_your_website/page_parameters/doc_page_parameters/)

## Template Creation Example

We will go through an example of template creation which should give you a good idea of how to go about creating your own template if required. We take up an [example template creation for actors](/docs/create_your_website/create_template_example/) ***which you should peruse***

## Template Creation

Now, having gone through the example, you may want to take the next step of creating your own templates. I strongly suggest viewing these [giraffe academy videos](https://www.youtube.com/watch?v=G7umPCU-8xc) before you create as it will save you time later. Also, prior to that deep dive into the videos, [this page](/docs/create_your_website/modify_templates/) gives you a further idea on what is possible.

## Making changes to website from multiple locations

If you are making changes to your website from multiple locations, it is important to have them all with the same working files

1. First time setup on a new computer
    1. Do all setup like downloading [git bash](https://git-scm.com/downloads) and a good text editor like [Atom](https://atom.io/) or [VS Code](https://code.visualstudio.com/)
    2. Create a directory where you want to host your files, say `c:\users\username\website\`
    3. Open your git bash and cd to this new directory
    4. type `git clone  --recurse-submodules -j8 https://github.com/KSMadhavan/website.git .`
    5. This should download all your files from the remote directory *including the submodule*
    6. To ensure that everything is in order, you can further type `./pull.sh` and all your files should be synced
2. Continue to make changes are required in your favorite text editor
3. When you are done
    1. Save the files you have created or worked on
    2. Open the bash/terminal and cd into your website directory
    3. type `./commit.sh`
    4. If you further want to your changes to pass to the live website as well, type `./deploy.sh`
    5. You will find that your website is updated with latest changes
    6. Note on partial changes: If you have only made partial changes to some site page want to continue working on it without updating the live website then skip `./deploy.sh`
4. When you want to get changes made on any other computer (and if initial setup has already been done):
    1. Open the bash/terminal and cd into your website directory
    2. type `./pull.sh`

## Git gotchas

In a lifetime of using git, you are likely to face at some point some major or minor errors. While the causes for these may not be immediately apparent, the fixes shouldn't be that hard. We will cover some of these glitches and their fixes in [this page](/docs/create_your_website/git_gotchas/). For everything else, use [stack-overflow](https://stackoverflow.com)

## Working with Google Cloud Storage instead of github

Github is good. While good, you may find many reasons not to use it like: (a) It may be slow to serve website in your country, or (b) github is good but you can't get your head around *git*. Therefore there are many reasons why you may not want to work with github. If so an alternative is Google Cloud Storage. We detail instructions for cloud storage setup [in this page](/docs/create_your_website/google_cloud_storage/).

## Last remarks

It would not be in order if i didn't mention why I created this website template. My main motivation was that I didn't like facebook. I wanted my output to be on the internet, but didn't want it lost in the thousands and thousands of posts that go on facebook. Facebook can be used to spread ideas, not to host them. I wanted my own address.

I tried Wordpress for a while. In fact it was the first place of stop when I didn't know the least bit about coding. But i realized it was inefficient. Wordpress was not a good way to create sites. Further it was costing me every month. A bit later I found that the majority of content on wordpress sites was static but were hosted dynamically. This lead to my interest in static sites - especially given wordpress was hosting 20 percent of all sites on the internet.

Building a website should not be hard at all. If your grandpa asks you to build a site, you should be able to tell him - it's really simple - here are the instructions, why don't you try? Also, apart from your domain name, it's free. This was my motivation.

Given this motivation, these docs are aimed at people who don't have their own websites currently. Therefore the intention is to be free of technical jargon. There is a high likelihood that I have failed in this attempt. Therefore, if you find improvements to code or to docs, do send in.

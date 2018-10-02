+++
title = "Modify Settings and site configurations"
date = 2018-06-08T19:44:35+05:30

pageNumber = 7
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
highlight_languages = ["bash"]
highlight_style = "railscasts"

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Static Sites","documentation","Hugo","websites","setup"]
categories = ["Website"]

[[previous_page]]
text = "Preview the site"
url = "/docs/create_your_website/preview_site/"

[[next_page]]
text = "Check site and Upload to github"
url = "/docs/create_your_website/upload_to_github/"

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

At this stage, you will want to modify all the settings like the site author name, website name, etc on the site to be your own. We will do this in this section.

## What needs to be modified

The main files to be modified are:

1. [config.toml](/docs/create_your_website/config_files/config_toml/)
2. [_index.md](/docs/create_your_website/config_files/front_page_settings/)
3. [contact.md](/docs/create_your_website/config_files/contact_page/)
4. [contact_success.md](/docs/create_your_website/config_files/contact_success_page/)
5. [popup_success.md](/docs/create_your_website/config_files/popup_success_page/)
6. [privacy.md](/docs/create_your_website/config_files/privacy_terms/)
7. [termservice.md](/docs/create_your_website/config_files/terms_of_service/)

You may want to go through the above links to know what each of the files do and how to modify them. The recommended method for settings modification is to peruse the files above and change them. There are some things that you would want to necessarily modify and some things that you can modify if you want.

If you are in a hurry though, you should come back to the above later and for now do a find and replace to change settings based on some keywords that must be replaced.

## How to modify quickly

1. Before you start modifying the files, you would want to delete the `public` folder in case you have built your site. Don't worry we'll get this folder back! (Thank you github!)
    - This is because a single config may be used in hundreds of output pages
    - If you are doing a find and replace, then instead of finding every instance in the output page, you might as well just change the config and then rebuild the site
2. At this stage, you should ensure you modify the following words to your own. You can choose to do a Replace All in your favorite text editor. Instructions for some text editors are in the [next section](#replace-all-instructions-in-different-text-editors) below
    - yourdomain.com
    - Your Website Name
    - your_username
    - yourWebsite
    - yourCompanyName
    - yourRole
    - yourName
    - anotherName
    - disqusShortname
    - Company1, Company2, Company3, Company4, Company5
    - University1, University2
    - logo.jpg (to your logo file in static folder)
    - googleAnalytics
    - map_api_key, latitude, longitude (google maps)
    - favicon.jpg (to your favicon file in static folder)

    Note that the context of usage at each occurance of above words may be different. For example yourName may occur for your email id as *yourName@gmail.com* or even as an author of website. So you may not want a simple replace all function without going through context of usage.
3. You may have noticed that disqus Shortname, google analytics key and maps api key require you to go to the specific sites and get your own key
    1. disqusShortname:
        - disqus is the third party application we will be using for comments. 
        - Get your own disqus shortname here: https://disqus.com/admin/create/ and fill it in the place given
    2. googleAnalytics:
        - the static site uses a third party application - [google analytics](https://developers.google.com/analytics/devguides/collection/analyticsjs/), to enable analytics about the customer. 
        - These analytics can include things like what are the parts and pages of the website your visitor spent time on, how they arrived at your site, what geography they are from and sometimes even the demographics of the customer
        - enabling Google Analytics on your site enables you to track site usage, referrers and various other statistics.
        - See how to get your google analytics ID [here](https://support.google.com/analytics/answer/1042508?hl=en) and fill it in config.toml at the place given for googleAnalytics
    3. maps_api_key:
        - We use a third party application, google maps, to show a map in the front page in the contact section
        - Get your key from [here](https://developers.google.com/maps/documentation/javascript/get-api-key) and fill it in the place requiring 'map_api_key' in config.toml
        - To get your coordinates, right-click on [Google Maps](https://www.google.com/maps) and choose "What's here?". The coords will show up at the bottom. Fill in 'latitude' and 'longitude' based on these

4. Ensure favicon.jpg and logo.jpg are changed to your own
5. After doing the replacements, you would want to get your public folder back.
    - Open bash/terminal and cd into your website folder
    - Run the `rebuild_public.sh` script. In windows you may want to replace the forward slash with backslash

        ```bash
        ./rebuild_public.sh
        ```
    - Check to see that your public folder is back as normal



### Replace All Instructions in different text editors

On a good text editor this can be done by pressing ctrl+shift+F or ctrl+shift+R, where the replace all occurances in project is available. Note that for this you may have to choose your project folder (to enable search in this folder). Depending on your editor you may have to look up google for instructions for Replace All. We will look at three text editors: Atom, VS Code and Webstorm

#### Atom

Replace All function is not that good in Atom as you have to go file by file to replace. Instructions below:

1. Note that you would have to exclude the public folder else you would be overwhelmed with results (ensure that you have done step 1 [here](#how-to-modify))
2. You can choose 'Add Project Folder' with the shortcut Ctrl+Shift+A in the file menu. Choose your website folder.
3. Then if you press Ctrl+Shift+F you can choose the word you want replaced. For example, lets say you choose 'yourdomain.com'. Add the word you want to replace with but don't press 'Replace All' yet.
4. Choose the Find All option and a window will open up with the options
5. In this window, clicking each result will show you the context of the word in a separate window and you can replace it with anything you want. In this case, you would want to replace yourdomain.com with yourrealdomainname.com.
6. If you are satisfied with all contexts, you can click Replace All or otherwise replace context by context

#### VS Code

Replace all function is an absolute pleasure in VS Code. If you didn't [download it](https://code.visualstudio.com/download) before, now may be a good time.

1. Note that you would have to delete the public folder before this step else you would be overwhelmed with results (ensure that you have done step 1 [here](#how-to-modify))
2. First, you can choose 'Open Folder' in the File menu (or use the shortcut Ctrl+K+Ctrl+O). Choose your website folder.
3. Then if you press Ctrl+Shift+F a frame opens up on the left. Type the word you want replaced. For example, lets say you choose 'yourdomain.com' and press Enter
4. You would see a bunch of results in this frame. At this point, if you are satisfied with the results, you can click the small arrow next to the text box right on top and a *Replace* option would open up.
5. Now pointing to any result would give you two options - 'Replace' and 'Dismiss'. You can click the result to see the context and then choose appropriately. Since the results are organized by file, you can do this for entire files at once also if necessary.

#### Webstorm

For any project related work, like find and replace across the project, [Jetbrains](https://www.jetbrains.com/webstorm/) is my go to editor. The only drawback is that the Ultimate Edition is available only as a paid option. Also looks-wise it is not top of line. But it's good for projects and there is a free version available.

1. Get rid of 'public' folder: Needed so that you don't get overwhelmed with search results. So basically ensure that you have done step 1 [here](#how-to-modify)
2. Open Project: When you open the editor it asks for the directory to open by default. If not, click > File > Open and choose your folder
3. Find All: Choose Ctrl+Shift+F to open global search. type in the word you want to search. First time you use webstorm it may take a while, but after indexing it is super fast.
4. Clicking on each result shows you the context. If you are happy you are searching for the right thing, then type Ctrl+Shift+R. Now you can type the word you want to replace with.
5. At the bottom right of the screen you see a button for replace. Replace or replace all as appropriate. Skipping a result means you have to click the next entry (or press down arrow)
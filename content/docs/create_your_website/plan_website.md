+++
title = "Plan your website and contents"
date = 2018-06-08T19:44:35+05:30

pageNumber = 10
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
text = "Connect github and Godaddy"
url = "/docs/create_your_website/connect_github_godaddy/"

[[next_page]]
text = "Add your content to the website"
url = "/docs/create_your_website/add_content/"

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
text = "Add your content to the website"
url = "/docs/create_your_website/add_content/"

# Writeup goes below
+++

Now that you have seen your site scaffold and seen what you can do with it, it is time for you to ***start planning*** what you want to launch your website with. 

The original motivation for this template I created was to [present any and all output that I would produce](/docs/create_your_website/what_page_templates/). But your website may be completely different and may be about fiction, or art, or anything at all. So the question is:

## What pages can you create

### The single pages

We have 15 different types of pages available. These are listed below in approximately alphabetical order:

1. [Audios](https://template.thinkingtree.me/audios/): This is for any recordings you might have taken including songs or podcasts
2. [Books](https://template.thinkingtree.me/books/): This is meant for any books you have written
3. [Code-Snippets](https://template.thinkingtree.me/code-snippets/): This is meant for a mix of content and code.
4. [Courses](https://template.thinkingtree.me/courses/): This is meant to showcase any courses that one has created
5. [Docs](https://template.thinkingtree.me/docs/understand_static_sites/): This is meant for any documentation. Like the one you are reading presently.
6. [Events](https://template.thinkingtree.me/events/): This page type can be used for showcasing events like concerts
7. [Notes](https://template.thinkingtree.me/notes/): This is meant for a short content piece. Comes without a banner image
8. [People](https://template.thinkingtree.me/people/): This is for writing about people, possibly in your team or company
9. [Posts](https://template.thinkingtree.me/posts/): This is meant for long generic content pieces. Comes with a banner image on top
10. [Presentations](https://template.thinkingtree.me/presentations/): This is meant to showcase presentation pdfs that you may have made
11. [Publications](https://template.thinkingtree.me/publications/): You can link any publications (journals or otherwise) that you have made here
12. [Reviews](https://template.thinkingtree.me/reviews/): You can review any kinds of websites, products, movies etc here.
13. [Thoughts](https://template.thinkingtree.me/thoughts/): This is meant for noting down any (profound) thoughts you may have
14. [Workshops](https://template.thinkingtree.me/workshops/): You can showcase any workshops (short courses) in these pages.
15. Default: This is a default setting for simple markdown.

Given these page types, for starters, you may want to add *content that you have already created before* that falls into these categories. Further you may find that some kinds of pages, even if they don't directly fit into the above scheme may be coaxed into them. Lastly if you feel there are certain kinds of pages that just don't have a solution in the above pages, leave a comment below and I'll look to add them into the template.

### The front page

The most important part of your website may be your front page, and it's possible you may want to have certain sections and leave out others. You may also want to change the text and content to be your own. You can make these changes in [_index.md](/docs/create_your_website/config_files/front_page_settings/)

### The list pages

We have 17 different types of list layouts, three types of pagination and various other settings that you can change. The defaults of these are set already, so this is not necessary at the setup stage, but for reference, you can have a look at [how to change these settings](/docs/create_your_website/config_files/list_index_file).

## How to add content to your site

At this point, let's say you know what content you want to put on your website. In such a case, what are the steps to adding content to your website?

1) Delete existing single page content
2) Create a new content piece

### Delete existing single page content

We have a script for this which should allow you to view and delete ***all*** single page content without removing the directory structure or the _index (list layout) files for each content folder.

1. Open your bash/terminal/command prompt and cd into your website directory
2. Type the below into your prompt

    ```bash
    # 1. View the files that you are going to be deleting
    ./find_non_index_content_files.sh
    # 2. Delete the files once you are satisfied that none of your personal files are in the list
    ./delete_non_index_content_files.sh
    ```
3. Note that on windows you may need backslash instead of forward slash
4. Open a file explorer and check to see that all the files from the content subfolders (for example `content/posts/post1.md`) are indeed gone

### Create a new single page content piece

Hugo provides us with archetypes for each kind of page that you simply need to modify rather than writing the whole settings for each page out yourself. Adding a new page is simple in hugo. Let us take an example type `post` that you want to create called `My New Post`

1. Open your bash/terminal/command prompt and cd into your website directory. For example, if your website files are at `c:\users\yourname\website`, type
    ```bash
    cd c:\users\yourname\website
    ```
2. type the below into your prompt

    ```bash
    hugo new posts/my-new-post.md
    ```
3. You should have a new file at `c:\users\yourname\website\content\posts\my-new-post-md`. Open this with your favorite text editor
4. You would find a whole set of options are already filled in. We will look at what they mean in the next section. For now, you can just leave them as is. At the bottom of the page, below the three plus marks `+++` is where you can fill in your content.
5. Note that between the three plus signs on the top of the page and the three plus signs at the bottom of that page are where the `page configurations` are found. All parameters that are set here can be used to generate the html content.

### Deploying your pages

Keep adding pages till you like. At any point, if you want to view it on your live website, you can deploy it.

1. Open a bash/terminal/command prompt and cd into your website directory
2. type `./deploy.sh` and then `./commit.sh`
3. If you added a post called my-new-post.md (as mentioned in the last section), then you should find this on your website at https://www.ksmadhavan.in/posts/my-new-post/

**Note**: If you want to create this post at a different location (inside https://www.ksmadhavan.in/posts), then you would have to place it in the appropriate directory in the content folder

- For example, let's say you want to create a new post named "My New Post" in a directory called `politics`, then when creating the file, you would have to type into your prompt
    ```bash
    hugo new posts/politics/my-new-post.md
    ```
- Then the output file can be viewed (after `deploy.sh`) at https://www.ksmadhavan.in/posts/politics/my-new-post/
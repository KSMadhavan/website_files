+++
title = "Git Gotchas"
date = 2018-06-08T19:44:35+05:30

pageNumber = 130
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

There are various things that can go wrong when updating git. Because github also hosts our site apart from being a version control system, we have to be doubly careful. While I have faced many issues, I'm listing a couple below that you may come across

### Detatched Head

Sometimes your page just doesn't update inspite of no error messages on the bash. When you go to your repository, you would find that the update has not happened. This could be a problem of detatched head. So how to fix this?

1. Go to the website directory in bash/terminal/cmd
2. type

    ``` bash
    # 1. Go to the public folder
    cd public
    # 2. Verify that the remote url is correctly pointing to your output folder
    git remote -v
    # 3. Change branch to master
    git checkout master
    # 4. Come back to the main folder
    cd..
    # 5. reattempt a deploy
    ,/deploy.sh
    # 6. Verify it has worked. Open a browser and check update times on your github repository at https://github.com/yourusername/yourblogname
    ```
Above is based on [this answer](https://stackoverflow.com/questions/10228760/fix-a-git-detached-head) on stackoverflow

### Public folder added to main git repo instead of submodule

Removing a folder from git is more trouble than it's worth, but without going into how this happened, let us look at how to extricate yourself from this problem

```bash
# The below steps might take time as git has to search all past versions to find the 'public' directory
git filter-branch --tree-filter 'rm -rf public' --prune-empty HEAD
git for-each-ref --format="%(refname)" refs/original/ | xargs -n 1 git update-ref -d
# Below two steps are not necessary (if public is a submodule)
echo public/ >> .gitignore
git add .gitignore
# Below steps are necessary, so even if you skipped the above two steps continue here
git commit -m 'Removing public from git history'
git gc
git push origin master --force
```

Note: You can skip the third and fourth step (.gitignore) since we are using a
This [help from github](https://help.github.com/articles/removing-sensitive-data-from-a-repository/) is a good resource to look at as is [this stackoverflow answer](https://stackoverflow.com/questions/10067848/remove-folder-and-its-contents-from-git-githubs-history)

### Remote url not showing correctly in submodule

Say you typed `git remote -v` in the public folder, it should show the output repo that you created. If at any point it is still pointing to the template repo, one possible reason is that the submodule is not initialized
In your main folder, try the following:

```bash
git submodule init
git submodule update
```
or you can do both with `git submodule update --init`

### Cloning your own repos once initial setup is done

You may work on multiple computers and git is well suited to this. Post the initial setup, when on a new machine, type, which gets the repo and its submodules

```bash
git clone --recurse-submodules -j8 https://github.com/KSMadhavan/yourWebsite.git
```

### Remote repository url for git submodule not changing

If in spite of following the instructions [here](/docs/create_your_website/download_template/), your repository url has not changed, have a look at [this SO answer](https://stackoverflow.com/questions/913701/how-to-change-the-remote-repository-for-a-git-submodule/914090) which may help

1. Edit the .gitmodules file to update the URL. It should look like:

```bash
[submodule "public"]
    path = public
    url = git@github.com:p10rahulm/thinking-tree.git
```
2. sync the submodule

```bash
git submodule sync
```


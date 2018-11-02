# Implement your own static website with Godaddy, Github and Hugo in 10 easy steps

These are a condensed version of the [documentation for creating static site](/docs/create_your_website/implement_static_website_godaddy_github/). You can go through that if you get stuck in any step here.

The main steps for creating your own website are as follows:

1. [Download Git Bash, Hugo and a text editor](/docs/create_your_website/download_essentials/)
2. [Setup Github](/docs/create_your_website/setup_github/)
3. [Buy the domain and setup godaddy](/docs/create_your_website/setup_godaddy/)
4. [Download the template files](/docs/create_your_website/download_template/)
5. [Preview the site](/docs/create_your_website/preview_site/)
6. [Modify Basic Settings](/docs/create_your_website/modify_settings/)
7. [Check site and Upload to github](/docs/create_your_website/upload_to_github/)
8. [Connect github and Godaddy](/docs/create_your_website/connect_github_godaddy/)
9. [Plan your website](/docs/create_your_website/plan_website/)
10. [Add your own content](/docs/create_your_website/add_content/)

Let us go through each of these in detail.

## [Download Git Bash, Hugo and a text editor](/docs/create_your_website/download_essentials/)

Download the following software

1. [Git Bash](https://git-scm.com/downloads)
2. [Hugo](https://github.com/gohugoio/hugo/releases)
3. A good Text Editor:  Download one of [Atom](https://atom.io/),[VS Code](https://code.visualstudio.com/), [Webstorm](https://www.jetbrains.com/webstorm/)

## [Setup Github](/docs/create_your_website/setup_github/)

You will need to create ***two repositories*** at [github.com](https://github.com/). One for the output webpages and one for the input template pages that you will be working on.

After signup at github, you will be taken to [your main github page](https://github.com/dashboard). If you are new to github, you will see a big green button on the left saying 'new repository'. If you don't see this, you can click the '+' button on the top right menu and click on 'new repository'

### Create first repository

1. Choose a repository name. This doesn't have to be unique across github, just unique to your username. Therefore choose something descriptive. Simple ones like `yourblogname` should be good enough.
2. Choose public, it should be ok as your site is static and everyone can view all files anyway.
3. Uncheck the box for "Initialize repository with a README"
4. Add .gitignore should be None for now
5. Add a license should be None for now. You can add these later if you feel like

- You will be taken to a page that looks like `https://github.com/yourusername/yourblogname`. Bookmark this page. Also note down the link to the git repository which should look like: `https://github.com/yourusername/yourblogname.git`

### Create second repository

1. Follow the five steps above create another repository. This can be of a simple name like `yourblogname-template-files`. Post creating the repo, it should be available at the page `https://github.com/yourusername/yourblogname-template-files` and the git repository would be at `https://github.com/yourusername/yourblogname-template-files.git`

You should have at the end two repositories: (1) yourblogname which will be the repository for your output files and (2) yourblogname-template-files which will be the repository for the input files. Note these down, we will keep coming back to these.

## [Buy the domain and setup godaddy](/docs/create_your_website/setup_godaddy/)

There are two steps here: We need to buy a domain and forward requests from the naked domain to the www subdomain

### Go buy the domain

1. Go to godaddy.com
2. Search for preferred domain name
3. Add to cart and buy. Just choose one domain for now, you can always add more later. Let's call this domain as "your-domain.com". Of course note that ".com" could be any other suffix like ".org" or some such.
4. Go to https://account.godaddy.com/products/
5. You should be able to see your domain.
6. Typically you may see three buttons here next to your domain: Privacy DNS and Manage.
7. Click on the DNS button. It should open up another window with the domain you are managing. We will call this Your DNS page from now. Bookmark it if necessary or leave open.

### Create a forward from ksmadhavan.in into the www.ksmadhavan.in

1. On Your DNS page, if you scroll fown, you should see a Forwarding section.
2. You are presently going to create a DNS forwarding from the ksmadhavan.in into the www.ksmadhavan.in
3. Click on the button next to domain. The options to be input are as follows:
    1. In the Forward to option, in the blank space next to http:// type "www.your-domain.com". This means that it is going to forward from http://your-domain.com to http://www.your-domain.com
    2. In options use forward type: Permanent (301)
    3. In options use settings: Forward only
4. click on save
5. Leave this browser window open as we will have to come back to this DNS page.

## [Download the template files](/docs/create_your_website/download_template/)

This is an important step, please follow the below steps in order and go to the reference link above in case of any failure

1. Open a bash/terminal/command prompt
2. create (mkdir) a folder where you want to keep your website files. For example, type `mkdir c:\users\yourname\website`. Note that you need to use forward slash if working in mac or linux environments.
3. Go to that folder `cd c:\users\yourname\website`
4. Use git to download the files. **It's important to follow the below steps in order**

    ```bash
    # 1. Clone the site into your directory
    git clone https://github.com/p10rahulm/your-static-website.git .

    # 2. Change the remote url (origin) to the template repo you created
    git remote set-url origin https://github.com/yourusername/yourblogname-template-files.git

    # 3. Listing your existing remote urls should indicate whether the change was successful
    git remote -v

    # 4. The output files will eventually be created in a directory called 'public'.
    # #  We will add the submodule setting to the file called .gitmodules
    git config --file=.gitmodules submodule.public.url https://github.com/yourusername/yourblogname.git

    # 5. Sync and update the submodule to ensure all files (like .git/config) also 
    # #  have the updated setting
    git submodule sync
    git submodule init
    git submodule update
    # #  You should see 'warning: You appear to have cloned an empty repository.' and
    # #  'fatal: no matching remote head'. This is expected.

    # 6. Check the remote repository url in the public folder
    cd public
    git remote -v
    # This should show something like https://github.com/yourusername/yourblogname.git

    # 7. Go back to main directory
    cd ..

    # 8. Send your files into your git repository through script (you may have to
    # #  use backslash on windows). You may be asked for username and password now
    ./commit.sh

    # 9. Now on your browser, check your template repository at
    # #  https://github.com/yourusername/yourblogname-template-files/
    # #  to see that everything is updated there
    ```

## [Preview the site](/docs/create_your_website/preview_site/)
Check whether the website works as is. For this you need to locally create a hugo server. Thankfully, this is as simple as writing a simple command on your terminal/bash.

1. Open bash/terminal and cd into the folder with your website files
2. Type into the terminal:

    ```bash
    hugo server -D -p 1313
    ```
3. This opens a server with all files including those which are in draft on port 1313
4. Go to your favorite web browser (preferably Firefox or Chrome, i've not tested on IE)
5. Open `http://localhost:1313`. Even after checking that everything works, keep this tab open.

## [Modify Basic Settings](/docs/create_your_website/modify_settings/)

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

### How to modify quickly

1. Before you start modifying the files, check your `public` folder. In case it has lots of directories, that means your the static files for site have been built. In that case, *you would want to delete the `public` folder* in case you have already built your site. Don't worry we'll get this folder back! (Thank you github!)
    - This is because a single config may be used in hundreds of output pages
    - If you are doing a find and replace, then instead of finding every instance in the output page, you might as well just change the config and then rebuild the site
2. At this stage, you should ensure you modify the following words to your own. You can choose to do a Replace All in your favorite text editor. Instructions for some text editors are in the [next section](#replace-all-instructions-in-different-text-editors) below
    - ksmadhavan.in
    - K S Madhavan & Associates
    - KSMadhavan
    - yourWebsite
    - K S Madhavan & Associates
    - Chairman
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
5. After doing the replacements, in case you had deleted the `public` folder, you would want it back.
    - Open bash/terminal and cd into your website folder
    - Run the `rebuild_public.sh` script. In windows you may want to replace the forward slash with backslash

        ```bash
        ./rebuild_public.sh
        ```
    - Check to see that your public folder is back as normal

## [Check site and Upload to github](/docs/create_your_website/upload_to_github/)

The files are now updated with *your* settings and basic configurations. It's a good time to preview the site and then upload to github

### Preview the Site

1. Open a bash/terminal/command prompt and cd into your website folder
    - For example if your website files are at `c:\users\yourname\website`, then type `cd c:\users\yourname\website`
2. We will now create a server and check files. Type into the prompt

    ```bash
    hugo server -D -p 1313
    ```
3. The above command will create a local server at port 1313. You can check your site by going to `http://localhost:1313` on your browser and perusing all the links there for sanity check

### Deploy site to github

If your site looks good now, we can commit the templates and deploy the output to your **github output repository**

You have already gone through steps 1-4 below while [downloading the template](/docs/create_your_website/download_template/), but you can do it here again just in case

    ```bash
    # 1. Check your remote url for template folder. They should point to the 
    # #  repositories *you* created
    git remote -v
    # #  make sure you see something like 
    # #  https://github.com/yourusername/yourblogname-template-files.git here
    # 2. Check your remote url for public folder
    cd public

    git remote -v
    # #  make sure you see something like
    # #  https://github.com/yourusername/yourblogname.git here

    # 3. Go back to the main folder
    cd ..

    # 4. Deploy the files (replace forward with backslash in windows)
    ./deploy.sh
    # # Note: Sometimes you will find that hugo fails on the first run throwing errors like 'runtime.throw(0xf5c376, 0x21)'. For such cases, stop the run where it is failing by pressing Ctrl+C and then rerun the command.

    # 5. Commit template files to github also
    ./commit.sh

    # 6. Check your repos to see that everything is in place
    # #  Browse to https://github.com/yourusername/yourblogname-template-files/ 
    # #  and https://github.com/yourusername/yourblogname/ to see that everything
    # #  is updated recently there
    ```

## [Connect github and Godaddy](/docs/create_your_website/connect_github_godaddy/)

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

## [Plan your website](/docs/create_your_website/plan_website/)

Go through the website that you have created at http://www.ksmadhavan.in. You will get an idea of what the template can do for you. In this section we will go through two main questions - (b) What webpages can you create and (b) how you can create them

### What pages can you create

At this stage, you can create content for single pages, change the front page and modify list pages. Let us look at these below.

#### The single pages

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

#### The front page

The most important part of your website may be your front page, and it's possible you may want to have certain sections and leave out others. You may also want to change the text and content to be your own. You can make these changes in [_index.md](/docs/create_your_website/config_files/front_page_settings/)

#### The list pages

We have 17 different types of list layouts, three types of pagination and various other settings that you can change. The defaults of these are set already, so this is not necessary at the setup stage, but for reference, you can have a look at [how to change these settings](/docs/create_your_website/config_files/list_index_file).

#### How to add content to your site

At this point, let's say you know what content you want to put on your website. In such a case, what are the steps to adding content to your website?

1) Delete existing single page content
2) Create a new content piece

#### Delete existing single page content

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

#### Create a new single page content piece

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
4. You would find a whole set of options are already filled in. We will look at what they mean in the next section. For now, you can just leave them as is. 
5. Note that between the three plus signs on the top of the page and the three plus signs at the bottom of that page are where the `page configurations` are found. All parameters that are set here can be used to generate the html content.
6. At the bottom of the page, below the three plus marks `+++` is where you can fill in your content. The content can contain formatting in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

#### Deploying your pages

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

## [Add your own content](/docs/create_your_website/add_content/)

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
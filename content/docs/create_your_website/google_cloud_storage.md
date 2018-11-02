+++
title = "Setup Google Cloud Storage with Hugo and Godaddy"
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
highlight_languages = ["bash","html"]
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

Github Pages is easy to use and free. The only problem could be that it is slow in some countries (especially for large sites) compared to Google Cloud, Microsoft Azure or AWS. For some reason, if github pages doesn't work for you, or is too slow, you can setup our online system on Google Cloud Storage. We outline the steps below

### Get Google Cloud SDK

1. Go to [Google Cloud SDK Docs](https://cloud.google.com/sdk/docs/)
2. This should enable you to install google cloud SDK.
    1. Though the cloud SDK consists of cloud gsutil and gq command line tools, we will only be using gsutil.
3. If you are unable to access the download button on that page, you can probably access it directly [here](https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe). Please check as this link may not update with versions.
4. In the installer, you will be asked for some options
    - In the install type, choose single user
    - Leave the default destination folder as is. *Note this down*.
    - In the select commands to install. Make sure all options, including "Beta Commands" are checked
    - It will begin the downloading, extract and install in the folder you noted down.
    - It should tell you that installation is done.
    - When you click next here, it will ask you to open the cloud console and says it will run the command `gcloud init`. Make sure all the options are checked and click next to finish installation.
5. On the new terminal window that opens it will take you through a bunch of questions as it initializes the gcloud engine.
    1. If you are an existing user it may detect old google cloud sdk settings
6. Please use the following answers where relevant (and just use defaults for others)
    1. "Choose the account for which you want to create configuration": Choose a gmail/google login that you will be using to host the website. If this does not work, we will have to use `gcloud auth login` in the next step.
    2. "Enter project ID that you would like to use": We will be setting this default at a later time, as of now just leave blank and press enter
7. Once `gcloud init` has run, in case authentication was not successful (likely as you didn't provide password), type on the console `gcloud auth login`.
8. This should open a browser window asking you to login to your google account. Once you do this, you should be redirected to a page where you see the message (on the browser) "You are now authenticated with the Google Cloud SDK!". You can now close the browser window and head back to the console window.

Note:

1. Commands to remember:
    - Note this command down - `gcloud auth login`, you may have to do this several times.
    - Also note command - `gcloud config set project YOUR_PROJECT_ID`. We will be using it later.
2. Bookmark this software. you will need it later
3. Run git on the SDK: Make sure git runs on it by typing `git` into the command line. If it works it should give you a whole host of options. If it does not work, it should say something like `git is not recognized as an internal or external command`
    - If it was not recognized, most likely you would have to check the steps of installation of git-scm. Likely that the software may not have been added to PATH environment.
    - References for adding git-scm to PATH - [This website](https://www.java.com/en/download/help/path.xml) and this [stackoverflow question](https://stackoverflow.com/questions/31167181/adding-git-to-path-variable-cant-find-github-under-appdata-local) mentions which folder you need to add to PATH

### Verify yourself on google and get your cloud storage setup

[Google Reference: Domain Name Verification](https://cloud.google.com/storage/docs/domain-name-verification)

1. You can verify your domain here: https://www.google.com/webmasters/tools/
2. If you are on the new console, you should see a list of websites you own on the top left. If you click on this button, then at the bottom you can see a link to add new property.
    1. If you are on the old console, you should see a bright red button to "Add a Property" on the top right of your screen.
3. Click on add property (new search console is worse than old!)
    1. Type the name like so : http://mywebsite.com
4. There are many methods of verification. The most convenient at this stage is to use domain name provider (the last option)
    1. This will lead you back to the old console.
    2. It should auto detect that you are on godaddy.
    3. Click on verify on the bright red button
    4. It should open a window where it asks you to login to godaddy. It does its own thing and takes 60 seconds.
5. If it works, great, you have been verified by google as owner of your website

if it does not, then you would have to add TXT record. Let's look at how to do that.

#### Alternative Method

1. If DNS verification did not go as planned. On the page with the big red verify button, you should find a link to "Add a TXT record"
2. When you click on this, it should take you to a page with lots of instructions.
3. The most important part of this page is where it specifies the TXT record Value (Point number 6 as of this writing). Copy this value. Keep this page open (let's call it google TXT verification page).
4. Go back to your Godaddy DNS Page.
5. At the top you should see a records section. At the bottom of this section is a button for add.
6. Select type TXT.
7. The options are as follows.
    1. Choose "Type" as TXT
    2. Choose "Host" as "@"
    3. Choose "Value" as the copied value from the google verification page
    4. Choose "TTL" as "1-Hour" (though it doesn't really matter)
8. Click on save
9. See that this TXT record is in the list of records on Your DNS page. Sometimes you see an error, even if you do, if you see the TXT record there, it's good enough.
10. Go back to the google TXT verification page and click on verify. You should be verified and get a success message.

## Get yourself on the google cloud console

1. Go to [Cloud Console Home Page](https://console.cloud.google.com) and login.
2. If this is the first time you are logging in, you should see some questions regarding your country, email preferences and agreement to their terms and conditions.
3. Just choose the usual stuff here and agree to the conditions and click ok
4. At the outset you should see the main console page, which has a number of products.  
    - Let's call this the [Cloud Console Home Page](https://console.cloud.google.com).
5. At the center of the screen a list of their main products should include "Cloud Storage".
6. At the top of the screen you should see a small message which basically says you get free cloud credits, but is actually asking you to setup billing. This is required for the setup

### Setting up billing

1. When you click on the button on the top of the Cloud Console Home Page passing you free credits you will be taken to a page to setup your billing. It would ask you again to agree to Terms and Conditions. Agree to all this.
2. You will be offered a free trial for $300 which lasts only for 12 months. Much more likely that you would use only $5 of this, but hey, whats free is free. Complete the payment.
3. This should setup your billing (not to worry you won't be charged for the next year through this method).
    1. Sometimes if you don't complete payment, you can complete it later. The billing is still setup but is marked incomplete. You may keep receiving emails to complete billing setup and your console in such cases would remain active for a couple of days or weeks before they close it. This method is not recommended.
4. After you complete billing setup you should go back to [Cloud Console Home Page](https://console.cloud.google.com).

#### Alternative Method for setting up billing

1. If you didn't see the button, go to [Cloud Console Billing](https://console.cloud.google.com/billing)
2. You will be able to see two sections: My Billing Accounts and My Projects.
3. Under My Billing Accounts, you will be able to see a button called "create account". Click on this
4. It will ask you for a name and currency
5. Here again you can fill your personal details and also add a payment method.
6. The end result of this should be the same as the last method, you will land up back at the [Cloud Console Home Page](https://console.cloud.google.com)

### Setup Cloud Storage

[Google Reference: Hosting Static Website](https://cloud.google.com/storage/docs/hosting-static-website)

1. On the home page at the center you would see Cloud Storage in their list of main products. If you dont see this here, If you click the menu on the top left, there is a list of products, which should include "Cloud Storage". Click on this.
2. In the Cloud storage page, you should see browser, transfer, transfer appliance and settings. Only browser is relevant to us.
    1. Lets call this the [Cloud Storage Browser Page](https://console.cloud.google.com/storage/browser)
3. If you landed on the browser page and do not have any storage buckets, you should see a large button asking you to create bucket. Other users would see an option to create bucket on the top of their screen above existing buckets.
4. Click on create bucket. If this is the first use, you may be asked for some project name and organization name. This is to enable good organization of your assets. You can choose any relevant names for project and organization. You can create organization later if necessary.
    1. Older users would straight away go to the next page
5. Choose name. Be careful here. You must choose exactly "www.ksmadhavan.in"
6. In Default Storage Class choose Regional
7. In location, choose the cheapest or the closest option to you depending on your priorities.
    1. If you open out the advanced settings, you should see Labels and encryption, neither of these need to be touched.
8. Click on create.
9. You would be back on the Cloud Storage Browser Page. You should be able to see your bucket by the name of "www.ksmadhavan.in"
10. You now have your very own bucket. Now it is empty, we will fill it with your website shortly. At this point we will go back to godaddy to create a record to live update the website when the bucket is changed.

## Create CNAME record on godaddy

1. Go back to Your DNS Page on godaddy.
2. You should see the records section on top.
3. If you see existing unnecessary CNAME records, they ought to be removed. This can be done by clicking the pencil next to the record on the right (edit) and then the trash button on the right.
4. Click on Add record in the records section.
5. Choose type CNAME
6. The options are as follows:
    1. "Host" is "www"
    2. "Points to" is "c.storage.googleapis.com." (note the dot at the end)
    3. "TTL" can be 1 Hour or 1/2 Hour.
7. Your google storage bucket should now be linked to godaddy and your website will update live.

## Create public permissions for your storage bucket

1. Go back to Cloud Storage Browser page
2. You should see the bucket name as "www.ksmadhavan.in" along with location, public access level, lifecycle, labels and requester pays. At this point we are interested in making the bucket public.
3. At the right end of the row with the bucket you should be able to see 3 dots. Click this for settings. You will see (a) Edit bucket permissions (b) Edit labels (c) Edit website configuration and (d) edit default storage class.
4. Of these the most important to us are (a) Edit bucket permissions and (c) edit website configuration
5. Click on edit bucket permissions. You will see an option to add members. Use the following options:
    1. Add the user "allUsers".
    2. It will ask you to select a role. In the dropdown, you should see a menu option called Storage. Under this choose Storage Object Viewer. This means that the all public can see your storage objects, ie your website. Now your google cloud storage is ready to host a website
    3. Click on save
    4. [Reference for roles and Account Management on Google Console](https://cloud.google.com/storage/docs/access-control/iam-roles)
6. It may show you a warning "This bucket is public and can be accessed by anyone on the Internet.". This is ok and is good because you want your website on the internet!
7. Click the three dots next to the row displaying yout bucket in the Cloud Storage Browser Page. Click on "Edit website configuration"
8. You will be asked to choose an index page and a 404 page.
    1. Choose index page as "index.html"
    2. Choose 404 page "404.html". The 404 page is where all hits to pages which don't exist in your site are redirected to.
9. The storage bucket is good to go.
10. Now all that is remaining is for you to fill the storage bucket.

## Transferring data to your storage bucket

The transfer is simplified through the Google Cloud SDK that we downloaded at the start of this section.

1. Open Google Cloud SDK and cd to your website folder
2. Then type

    ```bash
    gsutil -m cp -r public gs://www.ksmadhavan.in
    ```

3. Ensure that you replace `ksmadhavan.in` with the one you bought from Godaddy

Reference: [cp command in gsutil](https://cloud.google.com/storage/docs/gsutil/commands/cp), [uploading objects to storage bucket](https://cloud.google.com/storage/docs/uploading-objects)
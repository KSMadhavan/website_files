+++
title = "Terms of Service Page"
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

The privacy policy is simply a text file stored at `termsservice.md` file which is in the `content` folder. The terms of service will be displayed at http://www.your-domain.com/termsservice/ and you can view the sample page [in the demo site](https://template.thinkingtree.me/termsservice/)

1. I have created a generic terms and conditions template which may be useful.
2. In this file, replace:
    - yourCompanyName by your real company name or your own name at 22 locations in the file
    - yourdomain with your website name at 1 location in the file
    - Last updated date by the date you are making the changes
3. Also replace http://www.yourdomain.com with your real domain name
4. This is rendered by terms_conditions.html layout in the layouts/_default folder
5. **In case your legal jurisdiction is different, please use a template that's relevant to your state**
6. All the content is directly taken from the content markdown itself
7. You can optionally add title, date and author fields at the top.

```markdown
# Terms of Service ("Terms")

_Last updated: May 31, 2018_
<hr>

Please read these Terms of Service ("Terms", "Terms of Service") carefully before using the http://www.yourdomain.com website (the "Service") operated by yourCompanyName ("us", "we", or "our").

By accessing this web site, you are agreeing to be bound by these web site Terms and Conditions of Use, all applicable laws and regulations, and agree that you are responsible for compliance with any applicable local laws. If you do not agree with any of these terms, you are prohibited from using or accessing this site. The materials contained in this web site are protected by applicable copyright and trade mark law.

## Use License
Permission is granted to temporarily download one copy of the materials (information or software) on yourCompanyName's web site for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
- Modify or copy the materials;
- Use the materials for any commercial purpose, or for any public display (commercial or non-commercial);
- Attempt to decompile or reverse engineer any software contained on yourCompanyName's web site;
- Remove any copyright or other proprietary notations from the materials; or
- Transfer the materials to another person or "mirror" the materials on any other server.
This license shall automatically terminate if you violate any of these restrictions and may be terminated by yourCompanyName at any time. Upon terminating your viewing of these materials or upon the termination of this license, you must destroy any downloaded materials in your possession whether in electronic or printed format.


## Disclaimer
The materials on yourCompanyName's web site are provided "as is". yourCompanyName makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties, including without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights. Further, yourCompanyName does not warrant or make any representations concerning the accuracy, likely results, or reliability of the use of the materials on its Internet web site or otherwise relating to such materials or on any sites linked to this site.

## Limitations
In no event shall yourCompanyName or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption,) arising out of the use or inability to use the materials on yourCompanyName's Internet site, even if yourCompanyName or a yourCompanyName authorized representative has been notified orally or in writing of the possibility of such damage. Because some jurisdictions do not allow limitations on implied warranties, or limitations of liability for consequential or incidental damages, these limitations may not apply to you.

## Revisions and Errata
The materials appearing on yourCompanyName's web site could include technical, typographical, or photographic errors. yourCompanyName does not warrant that any of the materials on its web site are accurate, complete, or current. yourCompanyName may make changes to the materials contained on its web site at any time without notice. yourCompanyName does not, however, make any commitment to update the materials.

## Links To Other Web Sites
Our Service may contain links to third-party web sites or services that are not owned or controlled by yourCompanyName. yourCompanyName has not reviewed all of the sites linked to its Internet web site and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by yourCompanyName of the site. Use of any such linked web site is at the user's own risk.

yourCompanyName has no control over, and assumes no responsibility for, the content, privacy policies, or practices of any third party web sites or services. You further acknowledge and agree that yourCompanyName shall not be responsible or liable, directly or indirectly, for any damage or loss caused or alleged to be caused by or in connection with use of or reliance on any such content, goods or services available on or through any such web sites or services.

We strongly advise you to read the terms and conditions and privacy policies of any third-party web sites or services that you visit.

## Termination
We may terminate or suspend access to our Service immediately, without prior notice or liability, for any reason whatsoever, including without limitation if you breach the Terms.

All provisions of the Terms which by their nature should survive termination shall survive termination, including, without limitation, ownership provisions, warranty disclaimers, indemnity and limitations of liability.

## Governing Law
These Terms shall be governed and construed in accordance with the laws of Karnataka, India, without regard to its conflict of law provisions.

Our failure to enforce any right or provision of these Terms will not be considered a waiver of those rights. If any provision of these Terms is held to be invalid or unenforceable by a court, the remaining provisions of these Terms will remain in effect. These Terms constitute the entire agreement between us regarding our Service, and supersede and replace any prior agreements we might have between us regarding the Service.

## Site Terms of Use Modifications
yourCompanyName may revise these terms of use for its web site at any time without notice. By using this web site you are agreeing to be bound by the then current version of these Terms and Conditions of Use.

## Governing Law
Any claim relating to yourCompanyName's web site shall be governed by the laws of the State of Karnataka without regard to its conflict of law provisions.

## Contact Us
If you have any questions about these Terms, please contact us.
```
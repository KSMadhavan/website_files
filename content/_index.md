+++
title = "The Thinking Tree Homepage"

show_popup = true
show_sharer = true
rollup_sharer_active = true
fixed_sharer_active = true

# ----------------------------------
# Top section
[top_banner]
    active=true
    layout = "top_banner" # choose from single or carousel
    [top_banner.content]
        # content from below. Layout from above
        title = "The Thinking Tree"

        link1_name = "Posts"
        link1 = "#featured_posts"
        link2_name = "Events"
        link2 = "#featured_events"
        link3_name = "Thoughts"
        link3 = "#featured_thoughts"

        slide1_image = "linear-gradient(to bottom right,rgba(0,0,200,0.2), rgba(200,0,120,0.2)),url(/img/headers/bubbles-wide.jpg)"
        slide1_link = "/posts"
        slide1_subject = "Posts"
        slide1_title = "Onward and Upward, Like a Dendritic Tree"
        slide1_description = "Reducing entropy, one post at a time"
        slide2_image = "linear-gradient(to bottom right,rgba(0,0,200,0.2), rgba(200,0,120,0.2)),url(/img/orange-fractal.jpg)"
        slide2_link = "/publications"
        slide2_subject = "Publications"
        slide2_title = "Every new day, better than the last"
        slide2_description = "Nurturing creativity, like saplings amidst giants"






# ----------------------------------
# Showcase section
[showcase]
    active=true
    headline_layout = "headline_elements"
    [showcase.headline]
        title = "Greatest ever works"
        subtitle = "Major Projects and Work Interests"

    [[showcase.card]]
        icon = "fa-laptop"
        title = "Responsive Design"
        link = "#"
        card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."

    [[showcase.card]]
        icon = "fa-lock"
        title = "Web"
        link = "#"
        card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."

    [[showcase.card]]
        icon = "fa-shopping-cart"
        title = "E-Commerce"
        link = "#"
        card_content = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."


# ----------------------------------
# About us section
[about_us]
    active=true
    headline_layout = "headline_elements"
    [about_us.headline]
        title = "About Us"
        subtitle = "Serving clients since 1985"
    # ---------------------------------
    [about_us.descriptor]
        logo_image = "portrait.jpg"
        name_title = "yourName"
        name_subtitle = "Chairman, K S Madhavan & Associates"

        # ---------------------------------
        [[about_us.descriptor.affiliations]]
            name = "Company1, Company2"
            url = ""
        [[about_us.descriptor.affiliations]]
            name = "Company3, Company4, Company5"
            url = ""

        [[about_us.descriptor.affiliations]]
            name = "University1, University2"
            url = ""
        # ---------------------------------
        [[about_us.descriptor.social]]
            icon = "fa-envelope"
            icon_pack = "fa"
            link = "mailto:yourName@gmail.com"
        [[about_us.descriptor.social]]
            icon = "fa-linkedin"
            icon_pack = "fa"
            link = "//linkedin.com/in/yourName/"

        [[about_us.descriptor.social]]
            icon = "fa-facebook"
            icon_pack = "fa"
            link = "//facebook.com/yourName"

        [[about_us.descriptor.social]]
            icon = "fa-github"
            icon_pack = "fa"
            link = "//github.com/KSMadhavan"


    # ---------------------------------
    [about_us.detail]
        title = "Biography"

        # ---------------------------------
        # Put the content below between the triple quotes. You may use markdown.
        # Make sure alignment is ok. I've used replace of '                '
        # to remove the leading white space
        content = '''
                yourName founded K S Madhavan & Associates as a means to work on problems that take time and are more difficult to address than traditional start-ups would allow. Traditionally the distinction between research and production had been fairly well demarcated with research institutions working on technologies that were forward looking and companies working on production oriented technology (technologies which made money today). That distinction has become blurred, especially in computer science with much of the cutting edge improvements happening within companies.

                K S Madhavan & Associates is an attempt to work on futuristic technologies covering multidisciplinary domains. We follow problems till their origins, dive into rabbit holes and go deep into the root of problems. Many times this leads us to mathematics, which seems to be the foundation of all else. Sometimes it leads to sociology and behavioural science. Few times it leads to the complexity of Biology. Other times it leads to thought experiments. Most of this rests on a backbone of coding as it is ubiquitous as a tool.

                The research areas we work on here are network topologies, computational structures, self-organization and automata, idea space theory. Apart from this core, there is also ongoing work on pattern finding in market microstructure (high frequency trading), and a few applications of complexity and modelling. If you would like to join us to contribute on any of these problems, you are most welcome. We're sure you would find the journey at least slightly enlightening. If you have a problem that you would like us to work on, please contact us below.

                yourName has been the head of Data Science at Company1 and Company2. At Company1, he built a data science division from scratch which worked on Data Science as a Service - the Company1 data science team acted as the remote data science team for our clients. This meant building tools to solve common problems between companies and building a team to deal with bespoke problems and on demand requests for client companies. At Company2 he was the head of data science and helped in their Series-B fund-raise round.

                Prior to that he was a trader on Wall Street trading currency options. During his time at Company3 he helped setup an automated option price trading/monitoring system. On the research side, he worked on single currency fx pricing and eurchf floor failure models. At Company4 he worked on Equity Exotic Options with a specific focus on RFP pricing and generating client ideas. At Company5, he risk managed an exotics trading book. He distinctly remembers being non-plussed at the fuss over the Company5 collapse, having predicted it a year before (Ref: University2 placement talk - 2007). :rocket:'''

        # ---------------------------------
        [about_us.detail.bottom_left]
            title = "Interests"

            # Choose fa (font-awesome) icons below
            [[about_us.detail.bottom_left.list]]
                title = "Artificial Intelligence"
                subtitle = ""
                icon = "fa-rocket"
            [[about_us.detail.bottom_left.list]]
                title = "Networks"
                subtitle = ""
                icon = "fa-rocket"
            [[about_us.detail.bottom_left.list]]
                title = "Topology"
                subtitle = ""
                icon = "fa-rocket"
            [[about_us.detail.bottom_left.list]]
                title = "Language"
                subtitle = ""
                icon = "fa-rocket"
            [[about_us.detail.bottom_left.list]]
                title = "Modelling"
                subtitle = ""
                icon = "fa-rocket"

        # ---------------------------------
        [about_us.detail.bottom_right]
            title = "Education"
        # ---------------------------------
            [[about_us.detail.bottom_right.list]]
                title = "Master of Business Administration, 2012"
                subtitle = "University1"
                icon = "fa-graduation-cap"

            [[about_us.detail.bottom_right.list]]
                title = "Bachelor of Technology, 2007"
                subtitle = "University2"
                icon = "fa-graduation-cap"


# ----------------------------------
# Logo Wall section
[logo_wall]
    active = true

    # Count the number of logos you want on a row. Choose from 1,2,3,4,6, 12
    headline_layout = "headline_elements"
    [logo_wall.headline]
        title = "Our Clients"
        subtitle = "Serving You Always"

    # List all the logos in the logo wall below.
    # Ensure height to width ratios of the images are all the same.
    [[logo_wall.logos]]
        source = "https://upload.wikimedia.org/wikipedia/commons/3/37/Palantir_company_logo.png"
        link = "/"
        name = "Palantir"

    [[logo_wall.logos]]
        source = "https://cdn.datafloq.com/cache/vendor/logo/262x132/sigmoid-logo.png"
        link = "/"
        name = "Sigmoid"

    [[logo_wall.logos]]
        source = "https://upload.wikimedia.org/wikipedia/en/thumb/7/7a/Flipkart_logo.svg/250px-Flipkart_logo.svg.png"
        link = "/"
        name = "Flipkart"

    [[logo_wall.logos]]
        source = "https://image4.owler.com/logo/nanobi_owler_20160226_190824_original.png"
        link = "/"
        name = "Nanobi"

# ----------------------------------
# featured posts section
# Below we set attributes for the featured pages on the website front page
[featured_pages]
    active = true

[[featured_pages.sections]]
    name = "people"
    title = "Our Strength"
    subtitle = "Our people are our strength"
    num_featured = 4
    sort_field = "title"
    sort_order = "asc"
    card_layout = "people_cards_list_style1"

[[featured_pages.sections]]
    name = "books"
    title = "Books"
    subtitle = "The latest and greatest books"
    num_featured = 5
    sort_field = "title"
    sort_order = "asc"
    card_layout = "long_list_with_image"


[[featured_pages.sections]]
    name = "publications"
    title = "Publications"
    subtitle = "Who has published me, why don't you see?"
    num_featured = 1
    sort_field = "date"
    sort_order = "desc"
    card_alignment = "center"
    card_layout = "large_cards_leftimage_centertext_box_nooverlay"

[[featured_pages.sections]]
    name = "courses"
    title = "Courses"
    subtitle = "We take courses for all to enjoy"
    num_featured = 5
    sort_field = "title"
    sort_order = "asc"
    card_layout = "list_of_large_cards"

[[featured_pages.sections]]
    name = "workshops"
    title = "Workshops"
    subtitle = "We have conducted workshops in all major companies in India in the power sector"
    num_featured = 3
    sort_field = "title"
    sort_order = "asc"
    card_layout = "list_of_large_cards_no_overlay"

[[featured_pages.sections]]
    name = "reviews"
    title = "Reviews"
    subtitle = "I review, everything i do!"
    num_featured = 12
    sort_field = "name"
    sort_order = "desc"
    card_layout = "masonry_grid_cards"

[[featured_pages.sections]]
    name = "presentations"
    title = "Presentations"
    subtitle = "I present only the very uber"
    num_featured = 5
    sort_field = "title"
    sort_order = "asc"
    card_layout = "responsive_3cards_wbox"

[[featured_pages.sections]]
    name = "events"
    title = "Events"
    subtitle = "We take care of events all over the imagination"
    num_featured = 7
    sort_field = "title"
    sort_order = "asc"
    card_layout = "cards_grid7"


[[featured_pages.sections]]
    name = "posts"
    title = "Posts"
    subtitle = "The posts are precocious. Use as you feel good!"
    num_featured = 10
    sort_field = "title"
    sort_order = "asc"
    card_layout = "cards_grid5"

[[featured_pages.sections]]
    name = "notes"
    title = "Short Notes"
    subtitle = "Thoughts I plant as seeds so they may flower someday"
    num_featured = 6
    sort_field = "title"
    sort_order = "asc"
    card_layout = "responsive_3cards_nobox"

[[featured_pages.sections]]
    name = "thoughts"
    title = "Thoughts"
    subtitle = "The thoughts are precious. Handle with care!"
    num_featured = 8
    sort_field = "title"
    sort_order = "asc"
    card_layout = "carousel_4card"

[[featured_pages.sections]]
    name = "audios"
    title = "Podcasts and Music"
    subtitle = "Stirring but not rare"
    num_featured = 8
    sort_field = "date"
    sort_order = "asc"
    card_layout = "audio_carousel"


# ----------------------------------
# Call to Action section
[cta]
    active = true
    # Check the toml file in data/layouts/ to see what is rendered.
    # The render function is in layouts/functions/render_content_layout_fields.html and is claled from cta.html in layouts/homepage-sections
    layout = "home_cta"
    [cta.content]
    top_right_image = "img/dog_transparency2.jpg"
    bottom_left_image = "img/dog_transparency1.jpg"
    heading = "You can call someone to action"
    subheading = "And hope that they come and do the action. This is called call to action"
    cta_button1_text = "Start a new blog with Raz"
    cta_button2_text = "Visit our blog"
    cta_button1_link = "//www.github.com/KSMadhavan/website"
    cta_button2_link = "//www.shingo.institute"


# ----------------------------------
# Reviews section
[reviews]
    active = true
    # Check the toml file in data/layouts/ to see what is rendered.
    headline_layout = "headline_elements"
    [reviews.headline]
        title = "Reviews"
        subtitle = "We retain relevance to the latest and the greatest from across the galaxy"
    [[reviews.review]]
    reviewer_name = "Mighty Thor"
    reviewer_location = "Asgard"
    reviewer_review = "My strength through all these years of thick and thin has been sustained by this beautiful blog"
    [[reviews.review]]
    reviewer_name = "Cabaret Dancer"
    reviewer_location = "Moulin Rouge, Paris"
    reviewer_review = "I could use a lot of practice in my line of work. But no need for any practice as long as I have this blog. It teaches me everything!"
    [[reviews.review]]
    reviewer_name = "Drama Queen"
    reviewer_location = "College, India"
    reviewer_review = "I wanted to get the attention of all boys in our college. I tried make up and coy smiles, but now I don't need any as this blog has taught me drama and style!"
    [[reviews.review]]
    reviewer_name = "Geoffrey Boycott"
    reviewer_location = "Yorkshire, UK"
    reviewer_review = "Even my mom wouldn't get out to Jummpy Anderson once she read these beautiful tricks on how to bat"
    [[reviews.review]]
    reviewer_name = "A Dolphin"
    reviewer_location = "Sea"
    reviewer_review = "Dear earthling. I hope you can still save the world. I was told you should read this blog everyday, for an article a day keeps the darkness away"
    [[reviews.review]]
    reviewer_name = "Kabuliwala"
    reviewer_location = "Afghanistan"
    reviewer_review = "I have a single image of my child. Memories are mostly etched inside my forehead and the past is at its glorious best in my dreams than in reality. Yet when i see this blog, it revives a sense of belonging. Taschakor, khuda hafiz"
    [[reviews.review]]
    reviewer_name = "Spock"
    reviewer_location = "Vulcan"
    reviewer_review = "There are moments in their lives where men see exactly what they wish to see. I wish to see and appreciate this blog. It's only logical. May this blog live long and prosper"
    [[reviews.review]]
    reviewer_name = "Muldrer"
    reviewer_location = "Place X"
    reviewer_review = "I've searched all my life for the missing multitudes of evidence against government cover-ups of unidentified beings amongst ourselves. This blog revealed the whole truth to me"
    [[reviews.review]]
    reviewer_name = "Paul McCartney"
    reviewer_location = "Yellow Submarine"
    reviewer_review = "All my life I was trying to make Jude Happy, But what I got in my old age was all too rappy. Maybe my songs, they sail away into bliss, as I hope the same for a blog like this!"
    [[reviews.review]]
    reviewer_name = "Adam Smith"
    reviewer_location = "Capitol Country"
    reviewer_review = "Help as little as you must and earn as much as you lust. These foundational principles of my economics are being questioned through this blog by an agent provocateur. All dialogue is good except that which is built on deception. down with this blog!"
    [[reviews.review]]
    reviewer_name = "Madame Bovine"
    reviewer_location = "Sl House"
    reviewer_review = "You can call me madam bovine, never in the spotlight did i much shine. But this much believe me i can assure you, what this blog says about you eating me is true"
    [[reviews.review]]
    reviewer_name = "Pretty Woman"
    reviewer_location = "Down the street"
    reviewer_review = "Say what you will, but I have fallen for this blog"



# ----------------------------------
# Contact us section
[contact]
    active = true
    headline_layout = "headline_elements"
    [contact.headline]
        title = "Contact Us"
        subtitle = "Always here to help"

    [[contact.fields]]
        name = "contact_email"
        description = "email"
        font_awesome_icon = "fa-envelope"
        link = "mailto:yourName@gmail.com"
        text = "yourName@gmail.com"
        style = "color:#333; margin-bottom: 15px; display:block;"

    [[contact.fields]]
        name = "contact_phone"
        description = "phone"
        font_awesome_icon = "fa-phone"
        link = "tel:987-654-3210"
        text = "987-654-3210"
        style = "color:#333; margin-bottom: 30px; display:block;"



+++

# This is a base directory

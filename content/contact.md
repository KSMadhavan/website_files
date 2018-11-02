+++
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
#  2.   Upload the generated site to your server
#  3.   Send a dummy email yourself to confirm your account
#  4.   Click the confirm link in the email from www.formspree.io
#  5.   You're done. Happy mailing!

layout = "contact"
title = "CONTACT US"
subtitle = "_Please leave your message below and we'll get back as soon as we can_"
title_color = "azure"
subtitle_color = "#aaa"
email = "ksm@ksmadhavan.in"
contact_secondary_email = ["info@shingo.institute","sk.muthuit@gmail.com"]

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

+++
# **GO-PHISH PHISHING CAMPAIGN** 

 A Gophish campaign is an open source phishing simulation tool designed to test the security of a company by assessing how vulnerable the employees are, to phishing attacks. The tool was created by Jordan Wright in 2015 as a way to make phishing simulations accessible to everyone, including small businesses, penetration testers, and security teams. Gophish is such a powerful tool, it keeps track of every event for a campaign in its timeline, recording information such as the email address, time of the event, message, and details about the event, which can include user-agent information and submitted credentials.

### HOW TO INSTALL GO-PHISH ON KALI LINUX VM

 * `sudo apt update && sudo apt upgrade -y` >> update your virtual machine
 
 * [GoPhish GitHub Releases page](https://github.com/gophish/gophish/releases) >> download gophish from github (latest version -- wget https://github.com/gophish/gophish/releases/download/v0.12.1/gophish-v0.12.1-linux-64bit.zip)
  
 * `unzip gophish-v0.12.1-linux-64bit.zip && cd gophish-v0.12.1-linux-64bit` >> unzip and enter the file directory

 * `sudo ./gophish` >> run Go-phish

 Immediately after running the `./gophish` command, you should see details on this on your terminal, displaying your login details into gophish properly. If it's the first time of using Go-phish, it will require you to change your password to anything of your choice for subsequent purposes, after inputting the necessary details, you'll be redirected to the Go-phish dashboard page, where you will see all the functions and components of a phishing campaign.


<img src="Screenshot from 2025-01-23 18-40-27.png" alt="alt-text" width="750"><br><br><br>

<img src="Screenshot from 2025-01-24 03-12-28.png" alt="alt-text" width="750"><br><br><br>

### COMPONENTS OF A PHISHING CAMPAIGN & CONFIGURATION DETAILS

 * **SENDING PROFILE** >> This Profile represents the mail server used to send phishing emails during a campaign. It determines how and from where your phishing emails are delivered. Its key field includes;
  
    *Name* -- A label for identifying the sender profile (e.g Team XYP)

    *SMTP From* -- The email address that will appear in the "from" field of the mail when it's delivered (e.g teamxyp@gmail.com)

    *Host* -- The SMTP server address [smtp.teamxyp@gmail.com:587] 

    *Username & Password* -- The email address used to authenticate with the SMTP server & password is from same mail (NOTE; not your mail password). **Ignore the rest of the entries and proceed to sending a test mail to confirm you're moving right.

 * **LANDING PAGES** >> A Landing Page is the web page where users are directed after clicking a phishing link. It typically mimics a legitimate website to capture user interactions. Its key field includes;
  
    *Name* -- A label for identifying the landing page (e.g fake LinkedIn page)

    *URL* -- The destination URL where targets are redirected to (click on *Import Site* to get to *URL* page)

    *Page HTML* -- The HTML content of the landing page. This should resemble the legitimate site being mimicked (e.g. LinkedIn login page).

    *Capture Submitted Data* -- Enables the collection of any data entered by the user (e.g., login credentials). Tick the box

 * **EMAIL TEMPLATES** >> The email template defines the content of the phishing email sent to a target. It includes the subject line, body text, and any embedded links or images. 
  
    *Name* -- Used in identifying the email template (e.g., "Password Expiration Notice")

    *Envelope Sender* -- Quite same as the email sending address

    *Subject* -- The email subject line (like a subheading)

    *HTML Content* -- The main body of the email, written in HTML for rich formatting

    *Text Content* -- The plain-text version of the email for users who disable HTML email rendering 

 * **USERS & GROUPS** >> The Users & Groups section allows you to define the recipients of your phishing campaign. You can organize users into groups for targeted campaigns.
  
    *Name* -- A label name for the campaign

    *First Name* -- Target's first name.

    *Last Name* -- Target's last name.

    *Email* -- Target's email address.

    *Position* -- Job title or role for additional segmentation
  
 * **CAMPAIGNS** >> A Campaign ties together all the components—sending profile, email template, landing page, and target group—to execute a phishing simulation.
  
    *Name* -- Label for the campaign

    *Email Template* -- Select the template to be used for the campaign

    *Landing Page* -- Choose the landing page to redirect users after clicking links

    *Sending Profile* -- Select the configured SMTP server profile

    *URL* -- Specify the URL where the phishing email links will point (e.g., http://phish.company.com)

    *Groups* -- Assign target groups of users

    *Launch Date & Time* -- Schedule the campaign to start immediately or at a specific time

    ***Monitoring and Reporting*** >>  Use the dashboard to track:

    *Email delivery success/failure*

    *Click rates*

    *Data submission rates*

    *Generate reports for post-campaign analysis*


 <img src="Screenshot from 2025-01-24 06-34-50.png" alt="alt-text" width="750"><br><br><br>


## THIS DOCUMENTATION IS INTENDED SOLELY FOR EDUCATIONAL PURPOSES. THE AUTHOR ASSUMES NO RESPONSIBILITY OR LIABILITY FOR ANY MISUSE, MISCONDUCT, OR UNLAWFUL ACTIVITIES CARRIED OUT USING THIS GUIDE. USERS ARE SOLELY RESPONSIBLE FOR ENSURING COMPLIANCE WITH APPLICABLE LAWS, REGULATIONS, AND ETHICAL STANDARDS WHEN USING MALTEGO OR ANY RELATED TOOLS OR TECHNIQUES.
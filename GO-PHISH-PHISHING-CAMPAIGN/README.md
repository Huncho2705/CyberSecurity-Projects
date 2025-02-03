# GoPhish Phishing Campaign – Security Awareness Testing

### Overview
Phishing remains one of the most effective attack vectors used by cybercriminals to exploit human vulnerabilities. GoPhish is an open-source phishing simulation framework designed to help organizations test and improve security awareness by conducting realistic phishing campaigns.

This project provides a detailed walkthrough on setting up, configuring, and running phishing campaigns using GoPhish on a Kali Linux virtual machine. By simulating phishing attacks, security teams can assess employee susceptibility to phishing attempts and implement necessary training programs to mitigate risks.

### Installation & Setup
To install GoPhish on Kali Linux, follow these steps:

1. Update Your System >> `sudo apt update && sudo apt upgrade -y`

2. Download GoPhish
Visit the [GoPhish GitHub Releases](https://github.com/gophish/gophish/releases) page to download the latest version. Alternatively, use the command >> `wget https://github.com/gophish/gophish/releases/download/v0.12.1/gophish-v0.12.1-linux-64bit.zip`

3. Extract and Navigate to the Directory >> `unzip gophish-v0.12.1-linux-64bit.zip && cd gophish-v0.12.1-linux-64bit`

4. Run GoPhish >> `sudo ./gophish`

After running the command, GoPhish will display login details on your terminal. Use these credentials to log in for the first time and change your password. Once logged in, you'll be redirected to the GoPhish dashboard, where you can configure your phishing campaign.

### Configuring a Phishing Campaign

A phishing campaign in GoPhish consists of multiple components, each playing a crucial role in its execution.

1. Sending Profile
The sending profile defines the mail server used to send phishing emails.

* Name: Identifier for the sending profile (e.g., "Company Security Team")
* SMTP From: The email address used as the sender (e.g., security@company.com)
* Host: SMTP server address (e.g., smtp.mailserver.com:587)
* Username & Password: Authentication credentials for SMTP (⚠️ Do not use personal credentials)
* Test Email Sending: Before proceeding, send a test email to confirm correct SMTP setup.

2. Landing Pages
A landing page is the website where users are redirected after clicking a phishing link. It should convincingly mimic a legitimate login page.

* Name: Label for the landing page (e.g., "Corporate Login Portal")
* URL: Destination URL of the phishing site
* Page HTML: The HTML structure of the fake login page
* Capture Submitted Data: ✅ Enable this to collect user-entered credentials
* Import Site Feature: Use this feature to clone legitimate login pages easily.

3. Email Templates
The email template defines the content of the phishing email, including the subject, message, and embedded links.

* Name: Template identifier (e.g., "Urgent Password Reset Notice")
* Envelope Sender: Sender email (same as SMTP setup)
* Subject: Email subject line (e.g., "Your Password is Expiring Soon!")
* HTML Content: The formatted phishing email content
* Text Content: Plain-text version for non-HTML email clients
* Use Social Engineering Techniques: Ensure the email looks legitimate to increase engagement.

4. Users & Groups
Define your target users and organize them into groups for targeted phishing simulations.

* Name: Target group label (e.g., "Finance Department")
* First Name & Last Name: Recipient details
* Email Address: Target’s email
* Position: Role within the organization (for segmentation)
* Use realistic data to simulate an authentic attack scenario.

5. Creating & Launching a Campaign
A campaign ties together all components (sending profile, email template, landing page, and target group) to execute the phishing test.

* Name: Campaign identifier (e.g., "Q1 Security Awareness Test")
* Email Template: Choose the previously created template
* Landing Page: Select the associated phishing page
* Sending Profile: Choose the configured SMTP server
* URL: Specify where the phishing email links should redirect users
* Groups: Assign targeted recipients
* Launch Date & Time: Schedule the campaign or start immediately
* Monitor and Track Results via the campaign dashboard.

 ### Tracking & Reporting
Once the campaign is active, GoPhish provides real-time tracking of phishing engagement:

* **Email Delivery Success/Failure** – Check if emails reached recipients.
* **Open & Click Rates** – Identify users who interacted with the phishing email.
* **Credential Submission Rates** – See how many users entered login details.
* **Device & Browser Data** – Analyze user-agent information.

* Export Reports: Generate detailed reports to assess security awareness and plan future training.

### Legal & Ethical Considerations
This project is designed strictly for educational and security awareness training purposes. Conducting unauthorized phishing campaigns may violate privacy laws, corporate policies, and cybersecurity regulations.

* Before launching a phishing campaign, obtain proper authorization from relevant stakeholders.

* The author assumes no responsibility for any misuse of this information. Users are solely responsible for ensuring compliance with applicable laws and ethical guidelines.

### Conclusion
Simulating phishing attacks using GoPhish is a highly effective way to evaluate an organization's resilience against cyber threats. By leveraging real-world phishing tactics, security teams can identify vulnerable employees, reinforce cybersecurity training, and enhance organizational defenses.

* Enhance security awareness
* Reduce the risk of real phishing attacks
* Implement targeted security training

🚀 Stay ahead of cyber threats and build a human firewall against phishing attacks!



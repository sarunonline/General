# Mail transfer from one Gmail account to another Gmail account (backup purpose)

You can back up your emails from one Gmail account to another using the method described below:

Method 1: Using Gmail Settings
Enable POP in the Source Account:
Log in to your old Gmail account.
Go to Settings > See all settings.
Navigate to the Forwarding and POP/IMAP tab.
In the POP Download section, select Enable POP for all mail.
Save changes.
Add the Source Account to the Destination Account:
Log in to your new Gmail account.
Go to Settings > See all settings.
Navigate to the Accounts and Import tab.
In the Check mail from other accounts section, click Add a mail account.
Enter the email address of your old Gmail account and follow the prompts to import emails using POP.
Step-by-Step Guide
Log in to Your Destination Gmail Account:
Open Gmail and log in to the account where you want to receive the emails.
Access Settings:
Click on the gear icon in the top right corner.
Select See all settings.
Navigate to Accounts and Import:
Go to the Accounts and Import tab.
Add a Mail Account:
In the Check mail from other accounts section, click Add a mail account.
Enter the Source Email Address:
Enter the email address of the Gmail account you want to import emails from.
Click Next.
Choose Import Method:
Select Import emails from my other account (POP3).
Click Next.
Enter POP Server Information:
Username: Your full source Gmail email address.
Password: The password for your source Gmail account.
POP Server: pop.gmail.com
Port: 995
Check the box Always use a secure connection (SSL) when retrieving mail.
Additional Settings:
Leave a copy of retrieved messages on the server: Check this if you want to keep the emails in the source account as well.
Label incoming messages: Optionally, you can label the incoming messages to easily identify them.
Archive incoming messages: Check this if you don’t want the imported emails to appear in your inbox.
Finish Setup:
Click Add Account.
Optional - Send Mail As:
If you want to send emails from the destination account using the source account’s email address, follow the prompts to set up the Send mail as feature.
Summary of POP Server Settings
Incoming Mail (POP) Server: pop.gmail.com
Requires SSL: Yes
Port: 995
Outgoing Mail (SMTP) Server: smtp.gmail.com
Requires SSL: Yes
Requires TLS: Yes (if available)
Requires Authentication: Yes
Port for TLS/STARTTLS: 587
These steps should help you configure your destination Gmail account to fetch emails from another Gmail account using POP.

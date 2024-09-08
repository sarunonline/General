# Mail transfer from one Gmail account to another Gmail account (backup purpose)

You can back up your emails from one Gmail account to another using minor changes in Gmail Settings. The details are described below:

## Enable POP in the Source Account:
- Log in to your old Gmail account.
- Go to **Settings** > **See all settings**.
- Navigate to the **Forwarding and POP/IMAP** tab.
- In the **POP Download** section, select **Enable POP for all mail**.
- Save changes.

![Enable POP](https://www.dropbox.com/scl/fi/sbdcybf7iprcawmgq0hu1/g2g_0.png?rlkey=4abq70pf4pjjwmdfmit8e0kqv&raw=1)

## Add the Source Account to the Destination Account:
- Log in to your new Gmail account.
- Go to **Settings** > **See all settings**.
- Navigate to the **Accounts and Import** tab.
- In the **Check mail from other accounts** section, click **Add a mail account**.
- Enter the email address of the Gmail account you want to import emails from.
- Click Next.
![Add mail account](https://www.dropbox.com/scl/fi/1qp6ydgjl2xf76n610lio/g2g_1.png?rlkey=3lde4pe0kp8wj9uj5orq7yoe2&raw=1)
- Select Import emails from my other account (POP3).
- Click Next.
![Import mail account](https://www.dropbox.com/scl/fi/s9u04glfezltjg980kvmw/g2g_2.png?rlkey=jfnd2kpmvz4m926zrefb3lv5z&raw=1)
- Enter POP Server Information:
  - Username: Your full source Gmail email address.
  - Password: The password for your source Gmail account.
  - POP Server: **pop.gmail.com**
  - Port: **995**
  - Check the box **Always** use a secure connection (SSL) when retrieving mail.
- Additional Settings:
  - Leave a copy of retrieved messages on the server: Check this if you want to keep the emails in the source account as well.
  - Label incoming messages: Optionally, you can label the incoming messages to easily identify them.
  - Archive incoming messages: Check this if you don’t want the imported emails to appear in your inbox.
- Finish Setup:
  - Click Add Account.
- Optional - Send Mail As:
  - If you want to send emails from the destination account using the source account’s email address, follow the prompts to set up the Send mail as feature.

![Config for old gmail](https://www.dropbox.com/scl/fi/paw4qyy16ho3k31spkpfc/g2g_3.png?rlkey=wi5tezixdpcatpcqbib0tuomy&raw=1)

## Summary of POP Server Settings
- Incoming Mail (POP) Server: **pop.gmail.com**
- Requires SSL: **Yes**
- Port: **995**
- Outgoing Mail (SMTP) Server: **smtp.gmail.com**
- Requires SSL: **Yes**
- Requires TLS: **Yes** (if available)
- Requires Authentication: **Yes**
- Port for TLS/STARTTLS: **587**

These steps should help you configure your destination Gmail account to fetch emails from another Gmail account using POP.

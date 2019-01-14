# How to check header ?

View the Message Header in **Google Mail (GMail) Webmail**:
Login to your account on the webpage and open the message (click on it). Click on the "down-arrow" on the top-right of the message and select "Show Original". Now you will see the complete message source.

View the Message Header in **Yahoo! Mail Webmail**:
Login to your account on the webpage and open the message (click on it). 
Click on "Actions" and select "View Full Header".

View the Message Header in **Hotmail Webmail**:
Login to your account on the webpage and go to the message list. 
Right-click on the message and select "View Message Source". 

View the Message Header in **MS Outlook**:
Open the message in MS Outlook. Now go to "View" and select "Message Options" - or "File" -> "Info" -> "Properties".
Look at "Internet Headers".

View the Message Header in **Thunderbird**:
Open the message, then click on "View" and select "Message Source".

View the Message Header in **MS Windows Mail (and MS Outlook Express)**:
Select the message in the list, right-click on it and select "Properties" and go to "Details.

# Standard Message Header Fields

Sample Message Header:

Return-path: <sender@senderdomain.tld>

Delivery-date: Wed, 13 Apr 2011 00:31:13 +0200

(3)Received: from mailexchanger.recipientdomain.tld([ccc.ccc.ccc.ccc])

by mailserver.recipientdomain.tld running ExIM with esmtp
id xxxxxx-xxxxxx-xxx; Wed, 13 Apr 2011 01:39:23 +0200
(2)Received: from mailserver.senderdomain.tld ([bbb.bbb.bbb.bbb] helo=mailserver.senderdomain.tld)
by mailexchanger.recipientdomain.tld with esmtp id xxxxxx-xxxxxx-xx
for recipient@recipientdomain.tld; Wed, 13 Apr 2011 01:39:23 +0200
(1)Received: from senderhostname [aaa.aaa.aaa.aaa] (helo=[senderhostname])
by mailserver.senderdomain.tld with esmtpa (Exim x.xx)
(envelope-from <sender@senderdomain.tld) id xxxxx-xxxxxx-xxxx
for recipient@recipientdomain.tld; Tue, 12 Apr 2011 20:36:08 -0100
Message-ID: <xxxxxxxx.xxxxxxxx@senderdomain.tld>
Date: Tue, 12 Apr 2011 20:36:01 -0100
X-Mailer: Mail Client
From: Sender Name <sender@senderdomain.tld>
To: Recipient Name <recipient@recipientdomain.tld>
Subject: Message Subject

Return Path: The email address which should be used for bounces.
The mail server will send a message to the specified email address if the message cannot be delivered
Delivery-date: The data the message was delivered
Date: The date the message was sent
Message-ID: The ID of the message
X-Mailer: The mail client (mail program) used to send the message
From: The message sender in the format: "Friendly Name" <email@address.tld>
To: The message recipient in the format: "Friendly Name" <email@address.tld>
Subject: The message subject

# SPF

The Sender Policy Framework SPF is a framework to prevent sender address forgery.

In easy words (simplified): 
"SPF is used to describe what mail server is allowed to send messages for a domain".
See also: How to enable Sender Policy Framework (SPF) for domain/email

It's used to avoid fake email addresses (as sender email address). The system can detect if the mail server, which wants to send a message to the recipients mail-exchanger, is valid for the senders email address (domain).

The result can be:
- Received-SPF: neutral
- Received-SPF: pass

# DomainKeys Identified Mail (DKIM)

"Domain Keys Identified Mail (DKIM) is a method for associating a domain name to an email, thereby allowing an organization to take responsibility for a message in a way that can be validated by a recipient." ... from Wikipedia.org

In other words (simplified): 
"Some organization (domain) has signed the message and is responsible for it".

It's a good indicator, that the message is NOT a spam message. No spammer would "sign" a message.

# SpamAssassin's Header Lines
SpamAssassin is a anti-spam software, which is installed on many mail server. It's a great tool, which gives a detailed report for each message by adding lines and a summary to the message header.

A X-Spam-Score <5 means (on most systems) no spam, >5 probably spam and >15 spam. Spam might get deleted immediately or moved to the junk mail folder. Some systems add [SPAM] to the subject, so that these messages could be moved to the junk folder in the mail client using a rule.

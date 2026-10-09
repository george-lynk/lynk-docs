---
title: Emails to your customers
description: Review emails and the final-document email go out from your own email account.
draft: true
sidebar:
  order: 2
---

Lynk Insights sends two kinds of email to your customers: **Review emails** and, if you turn it on, **Email the PDF to the customer** with the final document. Both go out **from your own email account** (SMTP) and with your store's name, never from Lynk's address.

## Why from your own account

- The customer sees your store as the sender and, when they reply, the reply comes to you.
- Your own domain's sending reputation isn't affected by other stores.
- The email doesn't carry Lynk's logo or name.

You set the email account details (SMTP server, port, user, password and sender address) once, in the **Review emails** settings. The final-document email uses the same account.

## The final-document email

- You turn it on in **Automations** > **Final documents**, with the option **Email the PDF to the customer**. It is off to begin with.
- It is sent for documents delivered after you turn it on, within the delivery hours you set, with the document attached as a PDF.
- It is in Greek, unless the order is in English.
- Each document is sent once. If the connection breaks while sending, it isn't sent again, so the customer never gets it twice.

## Where you see whether they were sent

Emails to your customers show in the **Email history** in **Settings** > **Notifications**, marked "from your SMTP", with the customer's address partly hidden. The **Email from Lynk** card shows whether review emails are going out normally. See [Email notifications](/en/insights/team/email-notifications/).

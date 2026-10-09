---
title: Email notifications
description: How you choose which notifications reach you by email, when they arrive, and how you check that emails go out.
draft: true
sidebar:
  order: 2
---

In **Settings** > **Notifications** you choose, for each notification type, where you hear about it: **In the app**, by **Email**, or in a chat channel (Slack, Teams, Google Chat, Discord, Telegram). Each team member has their own choices.

## When the emails arrive

- **Urgent notifications** arrive at once. In the settings they say **Arrives at once.** They are **Send to Softone failed**, **A sent order was cancelled**, **Final document delivery failed**, **A connection needs action** and **Support access request**.
- **The others** are gathered in one **Daily summary** that arrives at 08:00, Greek time.
- An email goes out when something new appears or when it grows, for example when the orders that weren't sent go from 2 to 5. The same thing isn't sent to you twice.
- With **Quiet hours 21:00–08:00** on, urgent notifications during the night go into the morning summary. The exception is **Send to Softone failed**, which always arrives at once.
- If you have already had 10 notification emails in an hour, the next ones go into the summary.

## What team members get

Each member only gets the notifications about what they can see:

| Member permission | Notifications they can get by email |
|---|---|
| **Orders** | Send to Softone failed, sent orders that were cancelled, VAT number checks that failed, final documents that are late |
| **Products** | Products without a cost, low-performing products |

Only the account owner gets the notifications about connections, review emails and support requests.

## How to stop an email

- In **Settings** > **Notifications**, take **Email** off the notification type you don't want.
- Or press **Stop these emails** at the bottom of an email. The page that opens asks you to confirm and stops only that type of notification, or only the summary, for you. Your other emails and security emails carry on as usual.

You can turn them back on at any time in **Settings** > **Notifications**.

## Checking that emails go out (account owner)

The account owner sees two cards at the end of **Settings** > **Notifications**.

### Email from Lynk

- **Lynk's emails:** whether the emails Lynk sends you and your team are going out normally. If you see **Some weren't sent recently**, open the **Email history** to see which.
- **Review emails (your SMTP):** whether review emails are going out from your own email account. If you see **Failing: check your SMTP**, check the email account details in the **Review emails** settings.
- **Test an email:** pick an email and a language and press **Send a test**. We send that email with example details, only to your own address. A few seconds later, the result shows next to the button: sent or failed. You can send one test a minute.

### Email history

The emails of the last 7, 30 or 90 days, without their content. For each email you see when it was sent, which one it was, whether it was sent by Lynk or from your own email account, and the address partly hidden (for example m\*\*\*@g\*\*\*.com).

| Status | What it means |
|---|---|
| **Sent** | The email server accepted it. |
| **Retrying soon** | Sending failed for now and will be tried again automatically. |
| **Failed** | The server refused it. A reason code shows next to it. |
| **Outcome unknown** | The connection broke while sending: it may have arrived. It isn't sent again, so it never arrives twice. |
| **The address refuses email** | The address has refused emails before, so it wasn't sent. Account and security emails are always sent. |
| **Expired** | Its time passed, for example a new-password link after 1 hour. Ask for it again. |
| **Not sent** | It wasn't allowed to be sent. |

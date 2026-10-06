---
title: "First setup"
description: "Sign in to Lynk Insights and set up your connections in the right order."
sidebar:
  order: 2
---

*Describes the current version of the app.*

In this guide you sign in to Lynk Insights and set up your store's connections in the order we recommend. At the end, your orders reach Lynk and, if you use Softone, they become order documents in Softone.

## Before you start

- **A Lynk Insights account.** The app is in private beta. If you don't have an account, leave your email on the waitlist (**Join the waitlist**) and we'll get in touch. If an account owner invited you, follow the invitation link you received by email.
- **Admin access** to the systems you'll connect: Shopify, Skroutz Merchants, Shopflix, OpenCart or Softone.
- For Softone, the web services sign-in details from your Softone partner, ideally for a demo (test) installation as well.

## Steps

1. Open https://insights.lynk.gr, enter your **Email** and **Password** and click **Sign In**. If you've forgotten your password, click **Forgot your password?** and follow the link you receive by email.

   <!-- TODO screenshot: the sign-in page. -->

2. In the menu, under **Integrations**, open **Hub**. The **Integrations Hub** page lists all connections and whether each one is **Connected** or **Not connected**. The **Configure** button on each card opens that connection's page.

   <!-- TODO screenshot: the Integrations Hub with nothing connected. -->

3. Connect **Shopify**, if you have a Shopify store. See [Shopify](/en/insights/channels/shopify/).

4. Connect **Softone**, in the **Demo** environment first. See [Connecting Softone](/en/insights/softone/connect/).

5. For each channel, set up how its orders become documents in Softone. See [Channel settings](/en/insights/softone/channel-setup/). Test with a few orders in **Demo** before you move to **Live**.

6. Connect the marketplaces: [Skroutz](/en/insights/channels/skroutz/) and [Shopflix](/en/insights/channels/shopflix/). If you've connected Shopify, decide whether their orders should also be created in Shopify. See [Order relay](/en/insights/channels/order-relay/).

7. If you have an OpenCart store, see [OpenCart](/en/insights/channels/opencart/).

8. View your Softone stock in Lynk. See [Cost and stock from Softone](/en/insights/softone/cost-stock-sync/).

9. Add your product costs so profit can be calculated. See [Profit & costs](/en/insights/profit-costs/).

If you don't use Softone, skip steps 4, 5 and 8.

## What you'll see

- In the **Integrations Hub**, every connection you set up shows **Connected**.
- New orders appear on the **Orders** page.
- If you connected Softone, new orders appear in the **Order Log** on the Softone page. See [Softone order log](/en/insights/softone/document-log/).
- The **Overview** page shows revenue, commissions and profit for the date range you pick at the top right.

## If something goes wrong

**"Sign in failed. Please check your credentials"**: the email or the password is wrong. See [Sign-in and access](/en/insights/troubleshooting/sign-in-and-access/).

**A connection is missing from the menu**: in the **Integrations Hub**, switch on **Show in sidebar** on its card.

**Orders don't appear**: see [Orders aren't arriving](/en/insights/troubleshooting/orders-not-arriving/).

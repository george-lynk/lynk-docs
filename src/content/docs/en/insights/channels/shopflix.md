---
title: "Shopflix"
description: "Connect your Shopflix account and the portal session, so orders and the real commissions reach Lynk."
sidebar:
  order: 3
---

*Describes the current version of the app.*

In this guide you connect your Shopflix account to Lynk Insights. Orders arrive by webhook and are also synced automatically every 4 hours. With the **portal session**, Lynk also fetches the exact commission of every order, so profit is calculated correctly.

## Before you start

- Access to your Shopflix seller account (merchants.shopflix.gr).
- Your Shopflix **API Token**, from the seller portal, under **API παραγγελιών** (orders API).

## Connecting the account

1. In the menu, open **Shopflix** and the **Connection** tab.

   <!-- TODO screenshot: the Shopflix Account card. -->

2. Under **Shopflix Account**, fill in **Email** (your seller email) and **API Token**.

3. Optionally, fill in **Account Password**. It is used to fetch commissions, and you can add it later.

4. Click **Connect**. The first order sync starts in the background.

5. Copy the **Webhook URL** shown after you connect and enter it in your Shopflix account, in the orders webhook setting.

   :::caution[Keep the URL private]
   The URL is unique to your account. Don't publish it or send it to anyone else.
   :::

<!-- TODO: confirm the exact path in the Shopflix portal where the webhook URL is entered. -->

## Portal session for commissions

Shopflix charges a commission of about 12% to 14% depending on the category. To use the exact amount of each order, Lynk reads commissions from the Shopflix billing portal using your browser session.

1. On the **Connection** tab, open **Advanced settings** and find the **Browser session** card.

2. In another browser tab, sign in to **merchants.shopflix.gr**.

3. Open your browser's developer tools (F12) and the **Network** tab.

4. Select any request to merchants.shopflix.gr and, under **Request Headers**, copy the full value of **Cookie:**.

5. In Lynk, click **Paste session cookie**, paste the value and click **Save**.

:::caution[The session gives access to your account]
The cookie value gives access to your Shopflix account while the session is active. Paste it only into Lynk and never send it to anyone.
:::

The session expires after a few weeks. When it does, repeat steps 2 to 5.

## What you'll see

- The **Browser session** card shows **Session active** and when it was last updated.
- On the **Overview** tab, the cards **Orders synced**, **Commissions**, **Sync status** and **Last synced**.
- New orders appear on the **Orders** page with Shopflix as the channel.
- The **About commissions** card explains how commissions are calculated.

If there are fewer commissions than orders, some haven't been posted in the Shopflix portal yet. Click **Sync now** after a few days.

## If something goes wrong

**"Session expired — commissions not syncing"** or **"No session — commissions not syncing"**: the session expired or was never set. Repeat the steps in "Portal session for commissions".

**Some orders have wrong prices**: click **Repair prices**. Lynk re-fetches the orders with incorrect prices from Shopflix.

**An order is missing**: click **Sync now**. See also [Orders aren't arriving](/en/insights/troubleshooting/orders-not-arriving/).

**Connecting fails**: check the **Email** and the **API Token** in the Shopflix seller portal.

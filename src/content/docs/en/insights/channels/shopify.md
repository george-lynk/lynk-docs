---
title: "Shopify"
description: "Connect your Shopify store and set up the webhooks, so its orders reach Lynk right away."
sidebar:
  order: 1
---

*Describes the current version of the app.*

In this guide you connect your Shopify store to Lynk Insights. Once connected:

- new Shopify orders reach Lynk by webhook and can be sent to Softone,
- Lynk can create your Skroutz and Shopflix orders in Shopify. See [Order relay](/en/insights/channels/order-relay/).

## Before you start

- Admin access to your Shopify store.
- A **Custom App** in Shopify (**Settings** > **Apps** > **Develop apps**) with the permissions the app lists in the **Required API permissions** card.

## Connecting the store

1. In the menu, open **Shopify** and the **Connection** tab.

   <!-- TODO screenshot: the Shopify Connection tab before connecting. -->

2. Open the **Required API permissions** card and enable every permission it lists in your Custom App in Shopify (**Configuration** > **Admin API access scopes**).

3. Fill in **Store URL** (for example `your-store.myshopify.com`), **API key** and **API secret key**. You'll find both keys in Shopify, in the Custom App, under **API credentials**.

4. Click **Connect to Shopify**. Shopify opens and asks you to approve the connection. After you approve, you return to Lynk.

## Setting up the webhooks

Webhooks send Lynk every new order and every change to it (fulfilment, cancellation, return) as it happens.

1. On the **Connection** tab, open **Advanced settings** and find the **Inbound Orders from Shopify** card.

2. Switch on **Enable inbound webhook** and click **Save**. The **Webhook URL** appears.

3. Copy the **Webhook URL**.

   :::caution[Keep the URL private]
   The URL is unique to your account. Don't publish it or send it to anyone else.
   :::

4. In Shopify, open **Settings** > **Notifications** > **Webhooks** and create **two** webhooks in JSON format with the same URL: one for the **Order creation** event (`orders/create`) and one for **Order update** (`orders/updated`).

5. Copy the signing key that Shopify shows below the webhooks, paste it into **Webhook secret (optional)** in Lynk and click **Save**. Despite the "optional" label, the secret is required: without it, new orders are held. See **Webhook secret** below.

To send Shopify orders to Softone, click **Configure** next to **Softone channel config** in the same card. See [Channel settings](/en/insights/softone/channel-setup/).

## Webhook secret

Lynk accepts a Shopify order only when it can check Shopify's signature with your store's webhook secret. Which secret you need depends on who created the webhooks:

- **Webhooks you created in Shopify** (as in the steps above): the signing key that Shopify shows under **Settings** > **Notifications** > **Webhooks**, below the list of webhooks.
- **Webhooks your Custom App creates**: the app's **API secret key**, under **Settings** > **Apps** > your app > **API credentials**.

To add it:

1. On Lynk's **Shopify** page, open the **Connection** tab > **Advanced settings** and find the **Inbound Orders from Shopify** card.
2. Paste the secret into **Webhook secret (optional)** and click **Save**.

Only the account owner can set or change the secret. If you reconnect Shopify, the secret is kept.

### Held orders

While no secret is set, Lynk holds new Shopify orders instead of processing them:

- they are saved, but not sent to Softone, and no email goes to the customer,
- they show a **Held** badge in the Softone **Order Log**,
- changes to orders that already exist (fulfilment, cancellation, return) aren't applied.

A held order is never sent automatically: not after you add the secret, and not by **Push all unpushed**. To send it:

1. Check in Shopify that the order exists and that its details (customer, products, amounts) match what Lynk shows.
2. In the Softone **Order Log**, push it by hand from its row. The **Held** badge goes away and the order joins the Softone queue.

If an order doesn't exist in Shopify or its details differ, don't push it, and contact Lynk support.

## Older orders

To see in Lynk the orders placed before you connected, open the **Pull Historic Orders** card under **Advanced settings** and click **Pull historic orders**. Orders that Lynk itself created in Shopify are skipped.

Older orders are not sent to Softone automatically. Note, however, that the **Push all unpushed** button in the Softone **Order Log** includes them. See [Softone order log](/en/insights/softone/document-log/).

## What you'll see

- The **Overview** tab shows the store as **Connected**.
- A test order in Shopify appears within seconds on the Lynk **Orders** page, with Shopify as the channel.
- The **Webhook activity** chart shows the events received in the last 24 hours.
- The **Push status** card counts the marketplace orders sent to Shopify (**Orders pushed**, **Pending push**, **Failed pushes**).

## If something goes wrong

**"Could not connect to Shopify"**: check the **Store URL** (it must end in `.myshopify.com`), the **API key** and the **API secret key**.

**New orders don't appear**: check that **Enable inbound webhook** is on and that both webhooks exist in Shopify with the right URL. Make sure **Webhook secret (optional)** is the secret of the same store (see **Webhook secret**). With a wrong secret, Lynk rejects the orders. See [Orders aren't arriving](/en/insights/troubleshooting/orders-not-arriving/).

**Orders with a Held badge**: the webhook secret is missing. Add it, then push the held orders by hand after checking them in Shopify. See **Held orders**.

**A permission is missing**: add it to the Custom App in Shopify and regenerate the app's access token.

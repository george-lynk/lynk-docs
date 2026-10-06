---
title: "Order relay"
description: "How Skroutz and Shopflix orders are created in your Shopify or OpenCart store, and how you control it."
sidebar:
  order: 5
---

*Describes the current version of the app.*

With relay, every new Skroutz or Shopflix order is also created in your Shopify or OpenCart store. All your online orders are then in one place, and your Shopify stock goes down with every marketplace sale. In OpenCart, stock goes down if you've switched on **Deduct stock on push**.

:::caution[On by default]
As soon as you connect Shopify or OpenCart, relay is **on** for all new Skroutz and Shopflix orders. Every order creates a real order in your store. If you don't want that, switch it off as described below before new orders arrive.
:::

## Before you start

- [Shopify](/en/insights/channels/shopify/) or [OpenCart](/en/insights/channels/opencart/) connected.
- [Skroutz](/en/insights/channels/skroutz/) or [Shopflix](/en/insights/channels/shopflix/) connected.
- Make sure no other app already creates your marketplace orders in your store. Otherwise every order will appear twice.

## Setting up relay

1. In the menu, open **Skroutz** (or **Shopflix**) and the **Connection** tab.

2. Open **Advanced settings** and find the **Order Relay** card.

   <!-- TODO screenshot: the Order Relay card. -->

3. Switch **Relay to Shopify** on or off (and, if you have OpenCart, **Relay to OpenCart**).

4. Under **Order type**, choose which orders are relayed: **All orders**, **B2C only** (retail only) or **B2B only** (invoice orders only).

5. Click **Save**.

Repeat the steps for the other marketplace. Each marketplace has its own settings.

## Duplicates and Softone

Lynk recognises the orders it created in Shopify itself. When Shopify sends them back by webhook, Lynk ignores them, so they don't appear as new Shopify orders and aren't sent to Softone a second time. The order is sent to Softone once, as a marketplace order, with the Skroutz or Shopflix Softone settings.

## Sending one order by hand

1. :::caution[Creates an order in your store]
   This step creates a real order in Shopify, with no further confirmation.
   :::

   On the **Orders** page, on the order's row, click the Shopify icon (**Shopify · Push**).

## What you'll see

- On the **Orders** page, the Shopify icon on each order shows **Synced** when the order was created in Shopify, or **Failed — click to retry** if it failed.
- On the **Shopify** page, the **Push status** card counts **Orders pushed**, **Pending push** and **Failed pushes**.
- On the **OpenCart** page, the **Push status** card shows **Orders pushed**.

## The Relay page

The **Relay** page in the menu is a different feature: it forwards each new order's data to a URL of your own application (**Relay Destinations**). It's usually used by stores with their own system and a developer.

## If something goes wrong

**The card says no relay platforms are connected**: connect Shopify or OpenCart first.

**Orders appear twice in Shopify**: another app already creates your marketplace orders. Keep only one of the two switched on.

**An order wasn't created in Shopify**: click the Shopify icon on its row to send it again. If it fails again, check that the Custom App's permissions are complete. See [Shopify](/en/insights/channels/shopify/).

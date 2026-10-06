---
title: "Orders aren't arriving"
description: "What to check when a channel's new orders don't reach Lynk."
sidebar:
  order: 2
---

*Describes the current version of the app.*

First check the date range in the top bar: the **Orders** page shows only the orders in that range. If you've picked a channel in the filters, click **All channels**.

If the problem remains, find your channel below.

## Skroutz

**The status stays on "Waiting for Skroutz"**

**Cause:** Skroutz isn't sending orders to the secure webhook URL yet.

**Fix:** check that you saved the URL in the **Webhook URL** field in Skroutz Merchants, with **Ενεργοποίηση** (Enable) ticked and no spaces. See [Skroutz](/en/insights/channels/skroutz/).

**"Skroutz is still using your previous URL"**

**Cause:** you created a new URL, but Skroutz still has the previous one.

**Fix:** put the new URL in Skroutz Merchants before the time the message shows.

**Individual orders are missing**

**Fix:** on the **Skroutz** page, click **Sync Recent**. Lynk fetches the recent orders from Skroutz that didn't arrive by webhook.

## Shopify

**No new orders arrive**

**Cause:** the webhooks aren't set up, or inbound orders are switched off.

**Fix:** on the **Shopify** page, **Connection** tab, under **Advanced settings**, check that **Enable inbound webhook** is on. In Shopify, check that the webhooks for new orders and for updates exist with the same **Webhook URL**. See [Shopify](/en/insights/channels/shopify/).

**The webhooks exist but orders don't arrive**

**Cause:** the **Webhook secret (optional)** doesn't match Shopify's signing key, so Lynk rejects the requests.

**Fix:** copy the signing key from Shopify again, or leave the field empty, and click **Save**.

**Older orders are missing**

**Fix:** use **Pull historic orders**. See [Shopify](/en/insights/channels/shopify/).

## Shopflix

**Orders are missing**

**Cause:** Shopflix orders arrive by webhook and are synced every 4 hours. An order may appear with the next sync.

**Fix:** on the **Shopflix** page, click **Sync now**. If **Sync status** shows **Error**, check the **API Token** on the **Connection** tab. See [Shopflix](/en/insights/channels/shopflix/).

## OpenCart

**No orders come in from OpenCart**

**Cause:** importing is off, or the orders have a status that isn't imported.

**Fix:** on the **OpenCart** page, **Setup** tab, check **Enable order pull** and the statuses in **Order statuses to import**. Click **Pull now**. See [OpenCart](/en/insights/channels/opencart/).

## An order's state didn't update

**Fix:** on the **Orders** page, click **Sync states**. Lynk updates the states from the channel updates that have already arrived.

## If the problem continues

Click **Get Help** at the bottom of the menu and send us the channel, the code of a missing order and when it was placed.

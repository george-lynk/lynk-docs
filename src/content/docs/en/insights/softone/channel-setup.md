---
title: "Channel settings"
description: "The minimum settings so that a channel's orders become order documents in Softone."
sidebar:
  order: 2
---

*Describes the current version of the app.*

In this guide you set, for one channel, how its orders become order documents in Softone, and you switch on automatic sending. Each channel (Shopify, Skroutz, Shopflix, OpenCart) has its own settings.

## Before you start

- Softone connected, with **Demo** as the active environment. See [Connecting Softone](/en/insights/softone/connect/).
- The channel connected to Lynk. See [Channels](/en/insights/channels/).
- From your Softone partner: the codes of the retail and wholesale series, the warehouse code, the retail customer code and, for Shopify and OpenCart, the expense code for shipping.

## Steps

1. Open **Softone** and the **Configuration** tab.

2. Click **New config**, choose the channel and click **Create config**. If you've already set up another channel, you can copy its settings; otherwise choose **Start blank**.

   <!-- TODO screenshot: the New channel config dialog. -->

3. In the **Document Series** card, fill in **B2C Series (Λιανική)** for orders without an invoice and **B2B Series (Χονδρική)** for orders with an invoice. These are the series of the order documents in Softone.

4. In the **Customer Codes (CUSTOMER.CODE)** card, choose the customer for retail orders under **B2C Customer Mode**:
   - **Shared cash customer**: all retail orders go to one retail customer. Enter its code in **Cash Customer Code**. The customer must already exist in Softone.
   - **Individual customers**: Lynk creates a Softone customer for each retail order.

   Under **B2B (Business) Customers**, set how the new companies Lynk creates get their code.

5. In the **Warehouse** card, fill in **Main Warehouse Code**.

6. Shopify and OpenCart only: in the **Additional Codes** card, fill in **B2C Shipping Expense Code**, so shipping is included in the document. For Skroutz and Shopflix shipping isn't included, because the customer pays it to the marketplace.

7. Shopify and OpenCart only: in the **B2B Detection** card, set how an order with an invoice is recognised. See [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/).

8. Optionally, fill in the defaults **Default PAYMENT code** and **Default SHIPMENT code**, and the series in the **Final Document Series** card. You need the final document series if you want Lynk to detect the receipt or invoice you issue.

9. Click **Save configuration**.

10. :::caution[Documents are created automatically]
    Once you switch it on, every new order from the channel creates an order document in the active Softone environment, with no further confirmation. Older orders from the channel that were already forwarded to Shopify, OpenCart or a Relay destination and never sent to Softone may also be sent automatically within a few minutes. Lynk cannot delete a document. Check that the active environment is the one you want, and open the **Order Log** right afterwards.
    :::

    Go back to the **Configuration** tab and switch on the toggle on the channel's card.

## What you'll see

The channel's card on the **Configuration** tab shows **Ready** when all required fields are filled in; otherwise **Setup needed** and how many fields are missing (for example "3 of 4 fields mapped").

With the toggle on, new orders from the channel appear in the **Order Log** as **Queued** and then **Pushed**, with the Softone document number. See [Softone order log](/en/insights/softone/document-log/).

Older orders that weren't forwarded to Shopify, OpenCart or a Relay destination are not sent automatically. If needed, you send them from the **Order Log**.

:::note[Shopflix and OpenCart]
Automatic sending works as described for Shopify and Skroutz orders. For Shopflix orders, automatic sending straight to Softone doesn't work in every case at the moment; check the **Order Log** and send any missing orders with **Push**. Orders placed directly in your OpenCart store are not sent to Softone.
:::

## If something goes wrong

**The card stays on "Setup needed"**: one of the series, the warehouse code, the retail customer code or, for Shopify and OpenCart, the shipping expense code is missing.

**Orders show "Auto-push disabled"**: the channel's toggle on the **Configuration** tab is off.

**Sending fails**: open the **Order Log** and read the message. See [Softone sending errors](/en/insights/troubleshooting/softone-document-errors/).

---
title: "Softone sending errors"
description: "The most common error messages when an order isn't sent to Softone, their cause and the fix."
sidebar:
  order: 1
---

*Describes the current version of the app.*

When an order isn't sent to Softone, it shows as **Push failed** in the **Order Log** on the **Softone** page, with a message on its row. Messages appear in English or, when they come from Softone itself, in Greek. Find the message you see below.

After you've fixed the cause, send the order again:

:::caution[Creates a document in Softone]
**Retry** creates an order document in the active Softone environment. Lynk cannot delete it. First check the **Active environment** on the **Connection** tab.
:::

In the **Order Log**, click **Retry** on the order's row. See [Softone order log](/en/insights/softone/document-log/).

## "Cannot push order — SKU '…' not found in the connected Softone (…) environment"

**Cause:** Lynk didn't find an item in Softone with the code (SKU) of the order's product. Either the item doesn't exist in Softone with the same code, or the item catalog hasn't synced since you added it.

**Fix:**

1. Check that the item exists in Softone with exactly the same code as the product on the channel.
2. On the **Softone** page, **Cost Sync** tab, click **Re-sync catalog** in the **Product Catalog** card.
3. Send the order again with **Retry**.

## "Δεν έχετε συμπληρώσει το πεδίο 'Υλικό'"

(Greek for "You haven't filled in the 'Item' field".)

**Cause:** a Softone message. It usually means the item catalog has never synced.

**Fix:** on the **Softone** page, **Cost Sync** tab, click **Sync catalog** in the **Product Catalog** card and send the order again.

## "No Softone series configured for B2C on channel '…'"

Or the same message with **B2B**.

**Cause:** the channel settings are missing the retail (B2C) or wholesale (B2B) series.

**Fix:** open the channel's Softone settings and fill in **B2C Series (Λιανική)** and **B2B Series (Χονδρική)** in the **Document Series** card. See [Channel settings](/en/insights/softone/channel-setup/).

## "No B2C customer code (SALDOC.TRDR) could be resolved for order …"

**Cause:** no retail customer is set for the channel.

**Fix:** in the channel's Softone settings, in the **Customer Codes (CUSTOMER.CODE)** card, fill in **Cash Customer Code** with the code of a retail customer that already exists in Softone.

## "No B2B customer code (SALDOC.TRDR) could be resolved for order …"

**Cause:** the order is for an invoice, but it has neither a VAT number nor a company name, or you haven't set how new companies get their code.

**Fix:** in the **Customer Codes (CUSTOMER.CODE)** card, under **B2B (Business) Customers**, set how new companies get their code, or a generic wholesale customer code. See [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/).

## "No Softone credentials configured for the 'live' environment"

**Cause:** the active environment is **Live**, but you've connected only **Demo**.

**Fix:** on the **Softone** page, **Connection** tab, select **Demo** under **Active environment**, or connect **Live** as well. See [Connecting Softone](/en/insights/softone/connect/).

## "Softone login failed: …"

**Cause:** Softone didn't accept the sign-in details. The password may have changed or the user may have been deactivated.

**Fix:** check the **Softone Service URL**, **Username** and **Password** with your Softone partner and connect again from the **Connection** tab.

## A message about the "Web Service Connector"

**Cause:** your Softone licence doesn't include the **Web Service Connector** module, which the connection needs.

**Fix:** ask your Softone partner to activate it.

## If the problem continues

Click **Get Help** at the bottom of the menu and send us the order code and the message you see. Don't send any passwords.

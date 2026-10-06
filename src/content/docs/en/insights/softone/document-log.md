---
title: "Softone order log"
description: "See where every order stands in Softone, resend the ones that failed and correct mistakes."
sidebar:
  order: 4
---

*Describes the current version of the app.*

In the **Order Log** you see, for every order, whether its order document was created in Softone, whether the final document was issued and whether the PDF was delivered. From here you also send the orders that failed or were never sent.

## Before you start

- Softone connected and set up for the channel. See [Channel settings](/en/insights/softone/channel-setup/).
- Check the **Active environment** (**Demo** or **Live**) on the **Connection** tab. That's where orders will be sent.

## Opening the log

Open **Softone** and the **Order Log** tab. The cards at the top count orders by status. Click a card to see only those orders.

<!-- TODO screenshot: the Order Log with test data. -->

| Card | What it counts |
|---|---|
| **Total** | All orders |
| **Unpushed** | Orders not sent to Softone |
| **Pushed** | Orders with an order document in Softone |
| **Completed** | Orders whose final document was found |
| **Cancelled** | Orders cancelled or returned on the channel |
| **Pushing** | Orders being sent now or waiting in the queue |
| **Push failed** | Orders that failed |
| **Awaiting doc** | Orders waiting for the final document to be issued |
| **Delivery failed** | Orders where the PDF delivery failed |
| **Excluded** | Orders you excluded from bulk sending |

## What each sending status means

| Status | What it means |
|---|---|
| **Not pushed** | The order hasn't been sent to Softone |
| **Queued** or **In Queue 3 of 12** | The order is waiting in the sending queue |
| **Pushing…** | The order is being sent now |
| **Pushed** | The order document was created. Its number shows on the row |
| **Push failed** | Sending failed. The message explains why |
| **Auto-push disabled** | Automatic sending is off for the channel |
| **Not configured** | The channel has no Softone settings |

In the delivery column, **Pending** means Lynk is waiting for the final document, **PDF sent** means the PDF was uploaded to Skroutz and **Completed** means the final document was found.

## Sending one order

1. :::caution[Creates a document in Softone]
   This step creates an order document in the active Softone environment. Lynk cannot delete it.
   :::

   On the order's row, click **Push**. If the order had failed, the button says **Retry**.

The order joins the queue and its status changes to **Queued** and then **Pushed**. If it fails, Lynk retries automatically. The counter next to **Queued** (for example 1/3) shows the attempts. To take an order out of the queue before it's sent, click the remove button next to it (**Remove from queue**).

Cancelled orders have no **Push** button and are not sent.

## Sending several orders

1. :::caution[Creates documents in bulk]
   This step creates an order document in Softone for every selected order, with no further confirmation. Check your selection and the active environment first.
   :::

   Select the orders with the checkboxes on the left and click **Push selected**. Up to 50 orders are sent at a time.

The **Push all unpushed** button (with the options **Push all**, **B2B only** and **B2C only**) queues **all** orders that haven't been sent, including older ones. Sending starts immediately, with no confirmation. Use it only if you're sure all those orders need a document. To keep an order out of bulk sending, click the exclude button on its row (**Exclude from bulk push**). To bring it back, click **Re-include**.

## If sending fails

- Lynk makes up to **three** attempts in total.
- If all three fail, the status becomes **Push failed** and you receive an email listing the failed orders (at most one email every 30 minutes).
- Read the message on the order's row, fix the cause (usually a setting or an item missing in Softone) and click **Retry**. See [Softone sending errors](/en/insights/troubleshooting/softone-document-errors/).

## Correcting a document

Lynk doesn't delete documents in Softone. If an order document was created with the wrong details, you or your accountant correct it in Softone. If a receipt or invoice has already been issued, it is corrected with a credit note.

<!-- update when lynk-insights#177 ships -->
:::caution[Repush]
**Repush** creates a **new** order document in the active Softone environment, without asking. The old document stays and you or your accountant cancel it in Softone. **Force repush** does the same for every selected order.
:::

## Cancellations and returns

When an order that was already sent to Softone is cancelled or returned on the channel, Lynk emails you. Lynk doesn't change the document in Softone. Let your accountant know so they can make the necessary entries.

## If something goes wrong

**A new order doesn't appear in the log**: check that it appears on the **Orders** page. If it doesn't, see [Orders aren't arriving](/en/insights/troubleshooting/orders-not-arriving/).

**The order stays on "Awaiting doc"**: the final document hasn't been issued in Softone yet, or you haven't set its series under **Final Document Series**.

**"Delivery failed"**: the PDF delivery failed. The message under the label explains why.

---
title: "Credit notes for cancellations and returns"
description: "When Lynk tells you a credit note or a void is needed in Softone, what amounts it shows and how you mark it done."
sidebar:
  order: 6
---

*Describes the new version of the app.*

:::note[Rolling out gradually]
This feature belongs to the new version of the app and isn't switched on for every account yet. Until it is switched on for yours, Lynk emails you when an order that was sent to Softone is cancelled or returned, as described in [Softone order log](/en/insights/softone/document-log/#cancellations-and-returns).
:::

<span id="what-lynk-does"></span>

## What Lynk does and doesn't do

When an order that already has a document in Softone is cancelled or returned, someone has to sort it out in Softone: void the order document or issue a credit note.

**Lynk never issues a credit note**, and it never changes, converts or voids any document in Softone. You or your accountant issue the credit note directly in Softone.

What Lynk does:

- It records each cancellation and return that needs action in Softone, once each.
- It shows it in **“Needs you”** and on the order's page, in the **Credit notes** section, with the document and the amounts.
- It notifies you with the **Credit note needed** notification type, as you set it up in **Notifications**.
- It keeps it open until you mark it **I did it in Softone** or **Not needed**. There is no time limit: a return made weeks after the order shows up as usual.

Lynk checks for changes about once a minute, so a cancellation shows up shortly after it arrives from the channel.

## When Lynk tells you something is needed

Lynk only checks orders for which it created an order document in Softone, in the **Live** environment. Orders sent to **Demo** don't count.

| Channel | What shows up |
|---|---|
| **Skroutz** | Cancellation (also rejection or expiry), full return, each partial return |
| **Shopflix** | Cancellation (also rejection or expiry), full return |
| **Shopify** | Cancellation, each refund (full or partial) |
| **OpenCart** | Nothing. OpenCart orders aren't sent to Softone, so there is no Lynk document to credit |

Details:

- **Return in progress** (**For Return**): nothing shows up. Lynk waits until the return is complete.
- **Shopflix, partial return**: doesn't show up for now. Check Shopflix partial returns on Shopflix itself.
- **Shopify**: each refund is a separate entry, with its own items and amounts. If an order is cancelled after refunds were already made, Lynk shows only what is left to credit. If nothing is left, no new entry shows up.
- **Older Shopify orders**: for orders stored before Lynk kept refunds, Lynk shows the amounts of the whole order. When the refunds arrive from Shopify, their entries replace the original one.
- **Partial, then full return**: if an order had partial returns and was then returned in full, the new entry says **It already had partial returns: credit only the rest.**

## The three cases and what to do

What is needed depends on whether the final document (receipt or invoice) had already been issued when the order was cancelled or returned.

### Credit note needed

The final document was issued (or the order has a MARK). The order shows, for example, **Cancellation: a credit note is needed.** with the final document's number and its MARK.

:::caution[Issuing a credit note in Softone]
A credit note is a fiscal document and is transmitted to AADE. You or your accountant issue it in Softone, for the final document Lynk shows. Check the amounts against the final document before you issue it.
:::

1. In Softone, issue a credit note for the final document Lynk shows.
2. In Lynk, click **I did it in Softone**. See [Marking it done](#resolve).

### Void the order document

The order was cancelled or returned in full **before** the final document was issued. Only the order document Lynk created exists. The order shows, for example, **Cancellation: void the order document.**

1. In Softone, void the order document Lynk shows.
2. If a final document was issued in the meantime, a credit note is needed instead.
3. In Lynk, click **I did it in Softone**.

If Lynk finds a final document for the order within 30 days of the cancellation or return, the entry becomes **a credit note is needed** and opens again, even if you had marked it done.

### The order changed before the final document

A partial return or a refund happened **before** the final document was issued. The order shows, for example, **Partial return before the final document.**

1. Issue the final document only for what is shipped.
2. Check the order document in Softone.
3. In Lynk, click **I did it in Softone**.

If the final document is found later, the entry shows its number and says **Check that the final document leaves out the returned items.**

<span id="amounts"></span>

## The amounts you see

Below the description, **What to credit** shows the amounts as the channel has them:

| Line | What it shows |
|---|---|
| Items | Name, code, quantity and amount of each line, with the line's **VAT** as the channel sent it. A 0% VAT line stays 0%. Lynk never assumes a rate |
| **Discount** | The order discount (Shopify), as a negative amount |
| **Shipping** | Shipping (Shopify). For a refund, the shipping that was refunded |
| **Already in the refunds** | For a cancellation after refunds: what was already refunded |
| **Total** / **Refunded** / **Left to credit** | The order total, the amount refunded to the customer, or what is left to credit |

Marketplace commissions are never included: they aren't part of a credit note to the customer.

:::note[The final document is what counts]
The amounts are as on the channel's order. If the final document in Softone differs (for example because your accountant corrected it), the final document applies.
:::

For Skroutz partial returns, the channel doesn't send which items came back. Lynk says **Skroutz doesn't send the items of a partial return. See the return on Skroutz.** Open the return on Skroutz to see the items.

<span id="resolve"></span>

## Marking it done or not needed

On the order's page, in the **Credit notes** section, each entry has two buttons:

- **I did it in Softone**: when you issued the credit note or voided the document. Optionally, enter the **Credit note number (optional)** so it shows on the order (up to 40 letters, digits, spaces or `/ . -`). Confirm in the window that opens.
- **Not needed**: when no action is needed in Softone. Enter the **Reason** (required) and confirm.

Lynk writes nothing to Softone. Marking an entry only closes it in **“Needs you”**. Once marked, the entry shows what was chosen and when, for example **Cancellation: credit note CN 123**.

To open it again, click **Open again**. It shows in **“Needs you”** again.

You can close several at once from **Orders**, from the topic that groups them.

Entries you had already marked resolved before this feature show as closed, labelled **Marked resolved before this feature**.

If you see **Someone else already changed it**, another team member closed or opened the same entry. Refresh the page to see its current state.

The account owner and members with the **Orders** permission can mark entries.

<span id="per-channel"></span>

## Settings per channel

In each channel's Softone **Rules**, the **Credit notes & returns** card sets which cases Lynk tells you about (**When should we tell you?**):

| Option | When |
|---|---|
| **Cancelled after the document** | The order is cancelled. Also when the channel rejects it or it expires |
| **Full return** | The whole order came back, or all the money was refunded |
| **Partial return or refund** | Each partial return or refund, on its own |

- All three are on by default. You don't need to set anything up to get started.
- Each channel has its own settings. A change on Skroutz doesn't change Shopify.
- You can copy the settings to another channel with the rules copy (group **Credit notes**).
- If you switch an option off, Lynk doesn't record those cases for the channel. The credit in Softone is still needed; Lynk just doesn't remind you.

See also [Channel settings](/en/insights/softone/channel-setup/).

## Detection

On the **Credit notes & returns** card you see the **Soon** line: **Finding it in Softone and sending it to the customer**.

This **isn't available yet**. Today Lynk doesn't find the credit note you issued in Softone, and doesn't send it to the customer or the channel. After you issue it, mark the entry **I did it in Softone** and, if needed, send the credit note to the customer the way you do today.

In a later version, Lynk will find the credit note in Softone and be able to send it to the customer. We'll announce it in [What's new](/en/insights/whats-new/).

## See also

- [Softone order log](/en/insights/softone/document-log/)
- [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/)
- [Order list](/en/insights/orders/order-list/)

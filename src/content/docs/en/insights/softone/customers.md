---
title: "Customers in Softone: the fallback business"
description: "When an invoice order goes to the fallback business, why its invoice is held, and how you set the right customer."
draft: true
sidebar:
  order: 4
---

*Describes the new version of the app, coming soon.*

When a customer asks for an invoice, Lynk looks the business up in Softone by its VAT number (ΑΦΜ) and, if it isn't there, creates it with details from the AADE registry. Rarely, this can't be done. Then the order doesn't stop: it goes to Softone on the channel's **Default business (fallback)** and the invoice is held until you set the right customer. We always tell you why.

<a id="fallback-business"></a>

## When a business goes to the fallback

- The VAT number is missing: we never create a customer from the company name alone.
- The VAT number isn't valid.
- The same VAT number is on more than one Softone customer, so we don't guess.
- The search in Softone didn't finish, even after the retries.
- Softone didn't accept the new customer.
- The new customer is missing its name, country or tax office.

A temporary Softone problem (busy, slow) doesn't send the order to the fallback at once: the send is retried first.

<a id="safety-net-customer"></a>

## The setting in the wizard

In the question **What happens when the customer asks for an invoice?**, pick the **Default business (fallback)** from your Softone customers, with its code. The question is there for every channel, and changing it asks for a confirmation.

The fallback business is used only when:

- the channel's invoices series is an order, not a final document; and
- the final document check is on, so we see if an invoice is issued.

Otherwise the order stops and we tell you why.

In the same question's **Advanced**, the **Hold note in the remarks** is the text that goes first in the order's remarks in Softone. Left empty, we write “[ΑΝΑΜΟΝΗ ΠΕΛΑΤΗ — ΜΗΝ ΕΚΔΟΘΕΙ ΤΙΜΟΛΟΓΙΟ]”.

<a id="held"></a>

## What “held” means

- The order goes to Softone with the hold note at the start of its remarks, so no invoice is issued.
- We send no invoice to the buyer or the channel.
- On the order, in **Orders**, you see “The invoice is held” with the reason, and the “Fallback customer” step in its journey.
- Each such order is in the issues to check.

<a id="set-customer"></a>

## Set customer

1. Open the order in **Orders** and press **Set customer**. The account owner sees the button.
2. Choose:
   - **Existing customer**: search by name or code and pick the customer from Softone; or
   - **Create from the details**: we look it up by VAT number first and create the customer only if it isn't there. If the order's VAT number is wrong, type the right one in **Corrected VAT number**.
3. Press **Continue**. You see the change, “from” the fallback business “to” the customer, and press **Change customer**.
4. If the customer's VAT number differs from the order's (or is missing), or you typed a corrected VAT number, we ask a second time: you type the customer's code or the VAT number exactly as shown.

We change the customer on the same order document in Softone (no new number), remove the hold note, and check in Softone that the change landed. Then the invoice is issued as usual and the delivery goes on.

If the change doesn't happen, the dialog says why, with a reference where needed. The order stays on hold until you try again.

<a id="invoiced-on-fallback"></a>

## If an invoice was issued on the fallback

If someone issues an invoice in Softone despite the note, we record it, **don't** send it to the buyer, and tell you. A credit note and a new invoice on the right customer are needed in Softone; Lynk doesn't issue them.

<a id="alert"></a>

## Notifications

If more than 2 businesses from one channel go to the fallback in 7 days, we send you one e-mail a week with the reasons, and you see it on **Home**, under “For today”. The e-mail doesn't contain orders, VAT numbers or customer details.

<a id="skroutz-individuals"></a>

## Skroutz individuals in the order's journey

Skroutz individuals always go to the default walk-in customer, because Skroutz doesn't share an e-mail or phone. The order's journey says so in its “Walk-in customer” step, with the code; it isn't in the issues to check, because it's expected.

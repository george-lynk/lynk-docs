---
title: "Setting up Softone in the setup guide"
description: "The setup guide's Softone questions, the Live check and the test in Demo."
draft: true
sidebar:
  order: 3
---

*Describes the new version of the app, coming soon.*

The setup guide asks everything the first order document in Softone depends on. Each answer becomes a rule of the channel, and the choices come from your company's Softone lists. Lynk creates order documents; you issue the final documents in Softone.

## Before you start

- A Lynk Insights account with the **Owner** role.
- From your Softone partner: the Softone address, a user for Lynk with its password, and the application code (AppID). Demo and Live have separate details.

<a id="company"></a>

## Connection and company

1. In the **Softone** step, fill in the Demo sign-in details and select **Connect and check**.
2. Lynk signs in and shows the companies and branches the user may use. Nothing is saved yet.
3. Choose the **Demo company** and the **Branch** and select **Connect to this company**. If there is only one company with one branch, it is already selected: just select the button.

If Softone doesn't allow the company for the user, you see "The user signed in, but Softone doesn't allow them in this company or branch". Choose another one, or ask your partner for the permission. Under **Advanced** you can type the codes and the login profile (REFID).

## The rules questions

The questions open one at a time, for each channel. Where Lynk finds only one matching choice in your lists, it suggests it; the suggestion is saved only when you select **Next question**. Each question also has **Advanced**, with the settings Lynk already uses.

<a id="invoice-request"></a>

### How your customers ask for an invoice (Shopify)

Shopify doesn't say by itself which order wants an invoice. Choose where the customer writes it:

- **From a checkout field**, for example "Τιμολόγιο: Ναι", and the fields with the VAT number (ΑΦΜ), the company name, the tax office (ΔΟΥ) and the business activity. The guide suggests the field names it found in your recent orders.
- **From an order tag**, for example `needs:invoice`.
- **When the address has a company name**. The VAT number is missing, so the order is flagged for your accountant.

The setting applies to new orders.

<a id="retail-document"></a>

### Which document you issue to consumers

The **retail receipt** is suggested: the order goes in with a retail series and becomes a receipt in one click in Softone. The guide shows only the series that fit the document you chose, when Softone gives their type.

### What happens when an invoice is asked for

Choose the series for invoices. With the **VAT number look-up**, Lynk finds the business in Softone instead of creating a new one.

<a id="walk-in"></a>

### How consumers go into Softone

- **One shared retail customer**: the guide looks for the retail customer in Softone (for example "ΠΕΛΑΤΗΣ ΛΙΑΝΙΚΗΣ") and suggests it. You can search by name or type the code. With **Separate Greece and abroad** you set two customers.
- **One customer per buyer**: you set how new customers are numbered.

<a id="new-customer-codes"></a>

### How new businesses are numbered

The code pattern, for example `WEB{αύξων:4}` from 5000, gives WEB5000, WEB5001 and so on. The guide shows the next code. With `{ΑΦΜ}` the code is the VAT number.

<a id="vat-codes"></a>

### VAT

Every Softone installation has its own VAT codes. For each rate in your orders, choose its code. The guide suggests the code that carries the same rate. Lynk never guesses a VAT code: if an order has a rate without a code, it isn't sent and you see why.

### Warehouse, payments and shipping

- **Warehouse**, and for Skroutz the **FBS** warehouse.
- **Payments**: each payment method of the channel matches one in Softone, and **All other methods** covers the ones that appear later.
- **Shipping** (Shopify only): the expense code for the shipping the customer pays. On Skroutz and Shopflix, shipping doesn't go into the document.

<a id="order-numbers"></a>

### Order with Shopify (Skroutz, Shopflix)

When a marketplace's orders also go to Shopify, Lynk is suggested to **wait for the Shopify number**. The Softone document then has both numbers: the marketplace number in the customer document field and the Shopify number in the remarks, or next to the marketplace number. You find the document by either one.

<a id="copy-rules"></a>

## Copying rules from another channel

When a channel has no rules yet and another channel is ready, the guide suggests starting from its rules. You see what changes first, confirm, and you can undo it. Settings that concern one channel only (FBS, Shopify, Shopify invoices) aren't copied.

## Preview

**Preview** shows the document Lynk would create for real recent orders of each channel, without writing anything to Softone: a plain one, one with several items and one with an invoice. If something is missing, **Fix** opens the question that fixes it.

<a id="test-in-demo"></a>

## Test in Demo

The test sends one order **to Demo only**. Before it is sent, you confirm the order and the Demo company. If you send it again, the same document is updated; no second one is created.

If Softone is already in Live, the test sends nothing; see the preview.

<a id="live-check"></a>

## Live check and switching on

:::caution[Real company]
Once switched on, Lynk creates order documents in your Softone Live company. Check the series, the warehouse and the retail customer before you continue.
:::

1. In the **Live** step, connect the Live company with its own details, as you did for Demo.
2. The **Live check** checks that every code in the rules exists in the Live company: series, warehouses, the retail customer, VAT and payment codes. For each missing code, choose the Live code or open its question. There is one set of rules per channel, so the change applies to Demo too.
3. While a code is missing, Live isn't switched on.
4. Select **Go Live**, type the word asked for and confirm.

<a id="final-documents"></a>

## Final documents (optional)

Set which series Lynk looks in for the documents you issue (receipt, invoice for Greece, the EU and outside the EU), so it sends them to the customer and the channel. Credit notes are coming soon; today, when an order that was sent is cancelled, we email you.

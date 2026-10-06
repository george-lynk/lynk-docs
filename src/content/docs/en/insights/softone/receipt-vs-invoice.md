---
title: "Receipt or invoice"
description: "How Lynk decides whether an order is for a receipt or an invoice, and what happens with the VAT number."
sidebar:
  order: 3
---

*Describes the current version of the app.*

## What it is

For every order, Lynk decides whether the buyer asked for an **invoice** (a business buyer, B2B) or not (retail, B2C, for a **receipt**). Depending on the decision, it creates the order document in the wholesale or the retail series you set in [Channel settings](/en/insights/softone/channel-setup/).

Lynk doesn't issue the receipt or the invoice. It only decides which series and which customer the order document is created with. You or your accountant issue the final document in Softone.

## Why it matters

If an order that needs an invoice goes through as retail, the buyer doesn't get the invoice they asked for, and the fix is manual work in Softone. It's worth checking the rules with a few test orders in **Demo**.

## How it works

### Skroutz and Shopflix

When the buyer asks for an invoice on the marketplace, the order carries the invoice details (VAT number, company name). If there is a VAT number or a company name, the order goes for an invoice. No setup is needed.

### Shopify

Shopify has no built-in invoice field. Lynk checks, in this order:

1. A checkout field (note attribute) that you set in **Trigger attribute key**, and optionally its value in **Trigger value**.
2. The order tag in **Trigger tag**. Unless you set another one, it is `needs:invoice`.
3. The fields `invoice_vat_number` or `invoice_company`, if they have a value.

If your checkout collects invoice details under other field names, set them under **Invoice detail attribute keys** (**VAT number key**, **Company name key**, **ΔΟΥ key**, **Profession key**). All of these are in the **B2B Detection** card of the Shopify settings for Softone.

The **Use company name as B2B indicator** option treats every order with a company name in the shipping address as an invoice.

:::caution[Missing VAT number]
With **Use company name as B2B indicator**, if the order has no VAT number, the new customer is created in Softone with the VAT number "000000000". Before the invoice is issued, you must enter the customer's correct VAT number and tax office (ΔΟΥ) in Softone.
:::

### OpenCart

On the **OpenCart** page, under **Receipt vs invoice rule**, you choose a rule:

| Rule | When it goes for an invoice |
|---|---|
| **Auto (infer from order data)** | When the order has invoice details |
| **Always receipt** | Never |
| **Always invoice** | Always |
| **By store ID** | When the order comes from a store you listed in **Invoice store IDs** |
| **By customer group** | When the customer belongs to a group you listed in **Invoice customer group IDs** |

See [OpenCart](/en/insights/channels/opencart/).

### The VAT number and the customer in Softone

For an order with an invoice:

1. Lynk looks for a Softone customer with the same VAT number. If it finds one, it uses it.
2. If it doesn't, it creates a new customer from the order details. If you've set up the **GSIS Web Service Credentials** card, it first fills in the company name, address and tax office from the AADE registry. See [Connecting Softone](/en/insights/softone/connect/).
3. If the AADE lookup fails, the document is still created with the order details, and you receive an email so you can check the customer.
4. If the order has neither a VAT number nor a company name, Lynk uses the generic wholesale customer code, if you've set one. Otherwise sending fails and the order shows **Push failed** in the **Order Log**.

Later sends of the same order reuse the same customer, so no duplicate customers are created.

## Example

Two Shopify orders, with retail series 7023 and wholesale series 7021:

| | Order A | Order B |
|---|---|---|
| Amount | €49.60 | €248.00 |
| Tag `needs:invoice` | No | Yes |
| VAT number on the order | No | Yes |
| Order document series | 7023 (retail) | 7021 (wholesale) |
| Customer in Softone | The retail customer | The company with that VAT number (existing or new) |
| Final document you issue | Receipt | Invoice |

## See also

- [Channel settings](/en/insights/softone/channel-setup/)
- [Softone order log](/en/insights/softone/document-log/)

---
title: "Softone ERP"
description: "How your orders become order documents in Softone, and what you do next."
sidebar:
  label: "Overview"
  order: 0
---

*Describes the current version of the app.*

Lynk sends the orders from your channels to Softone ERP. For every order it creates an **order document** in the series you've set. You or your accountant issue the final document, the receipt or the invoice, in Softone.

## How an order becomes a document

1. **The order reaches Lynk** from Shopify, Skroutz, Shopflix or OpenCart.
2. **It joins the sending queue.** If the channel's Softone settings are switched on, Lynk queues the order. Each account's orders are sent one at a time.
3. **Receipt or invoice.** Lynk checks whether the buyer asked for an invoice. If so, it uses the wholesale series and finds or creates the company in Softone by its VAT number (ΑΦΜ). Otherwise it uses the retail series. See [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/).
4. **The order document is created** in Softone. Its number appears in the **Order Log**.
5. **You issue the final document.** You or your accountant turn the order document into a receipt or an invoice in Softone, whenever you choose. Lynk doesn't issue documents and doesn't transmit them to AADE.
6. **PDF delivery (optional).** If you switch it on, Lynk checks Softone regularly, detects the final document and uploads the PDF to Skroutz, or emails it to the Shopify or OpenCart customer.

If sending fails, Lynk retries automatically up to three times and then emails you. See [Softone order log](/en/insights/softone/document-log/).

## In this section

- [Connecting Softone](/en/insights/softone/connect/): sign-in details, the Demo and Live environments.
- [Channel settings](/en/insights/softone/channel-setup/): series, customers, warehouse and switching on automatic sending.
- [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/): how Lynk decides and what happens with the VAT number.
- [Softone order log](/en/insights/softone/document-log/): the status of every order, failures and retries.
- [Cost and stock from Softone](/en/insights/softone/cost-stock-sync/): item catalog, cost and stock.

---
title: "What is Lynk Insights"
description: "What Lynk Insights does, who it is for and which systems it connects."
sidebar:
  order: 1
---

*Describes the current version of the app.*

## What it is

Lynk Insights connects the systems of a Greek online store: your Shopify store, the Skroutz and Shopflix marketplaces, OpenCart and Softone ERP. Every order passes through Lynk, so the app can send it where it needs to go and show you what each one earned.

It is for stores that sell on Shopify or on the marketplaces and, optionally, keep their documents and stock in Softone.

## Why it matters

Without a connection, staff re-key every order into the ERP, decide by hand whether it needs a receipt or an invoice, and chase the VAT number (ΑΦΜ). Marketplace orders stay outside Shopify, and nobody knows what an order earned after the commission and the product cost.

## What it does

In the order most stores set it up:

1. **Shopify → Softone.** Every Shopify order becomes an order document in Softone, in the retail or the wholesale series, depending on whether the buyer asked for an invoice.
2. **Marketplaces → Shopify.** Skroutz and Shopflix orders are also created in your Shopify store, so all your online orders are in one place.
3. **Marketplaces → Softone.** Skroutz orders are also sent straight to Softone, without going through Shopify. For Shopflix, see the note in [Channel settings](/en/insights/softone/channel-setup/).
4. **Softone stock.** You see your Softone stock inside Lynk. Today this view is read-only.
5. **Analytics.** Revenue, commissions, cost and net profit per order, channel and product.
6. **Products.** Which products earn you money and which don't.

Each part also works on its own. If you don't use Softone, you connect only your channels. If you don't have Shopify, Skroutz orders go straight to Softone.

## What it doesn't do

- **It doesn't issue receipts or invoices.** Lynk creates the order document in Softone. You or your accountant issue the final document (receipt or invoice) in Softone, whenever you choose. See [Softone ERP](/en/insights/softone/).
- **It doesn't change stock in Softone,** and today it doesn't send Softone stock to your sales channels.
- **It doesn't create the marketplace XML feeds.** Those come from the feed app you use in Shopify.

## Example

A customer buys €124.00 of products from your Shopify store and asks for an invoice with their company's VAT number.

1. The order reaches Lynk within seconds.
2. Lynk sees that an invoice was requested, finds the company in Softone by its VAT number (or creates it) and creates an order document in the wholesale series.
3. Your accountant turns the order document into an invoice in Softone.
4. If you've switched it on, Lynk detects the invoice and emails the PDF to the customer.
5. On the **Orders** page you see the order's commission, cost and margin.

## See also

- [First setup](/en/insights/getting-started/first-setup/)
- [Channels](/en/insights/channels/)
- [Glossary](/en/insights/glossary/)

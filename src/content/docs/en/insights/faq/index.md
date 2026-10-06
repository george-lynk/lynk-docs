---
title: "FAQ"
description: "Short answers to the questions we are asked most often."
sidebar:
  label: "Overview"
  order: 0
---

*Describes the current version of the app.*

## Does Lynk issue receipts or invoices?

No. Lynk creates an order document in Softone for every order. You or your accountant issue the receipt or invoice in Softone, whenever you choose. See [Softone ERP](/en/insights/softone/).

## Does Lynk send documents to AADE?

No. Lynk doesn't issue or transmit documents. For transmitting the final document, ask your accountant or your Softone partner.

## Do I need Softone to use Lynk?

No. You can connect just your channels and see their orders and profit, or have marketplace orders created in Shopify. See [First setup](/en/insights/getting-started/first-setup/).

## How does Lynk know an order needs an invoice?

On Skroutz and Shopflix, from the invoice details the buyer gives. On Shopify, from a tag or a checkout field you set. On OpenCart, from the rule you choose. See [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/).

## Can I test without touching my real Softone?

Yes. Connect the **Demo** environment first, a test installation of Softone, and move to **Live** when your tests succeed. See [Connecting Softone](/en/insights/softone/connect/).

## What happens if sending to Softone fails?

Lynk makes up to **three** attempts in total. If all fail, the order shows **Push failed** in the **Order Log** and you receive an email. See [Softone sending errors](/en/insights/troubleshooting/softone-document-errors/).

## Can a second document be created for the same order?

No. Lynk sends each order once. **Repush** and **Force repush** update the order's existing document in the same environment and don't create a second one. They do change a real document in Softone, so check the order first. If the document belongs to the other environment, or the final document or ΜΑΡΚ has already been issued, Lynk sends nothing. See [Softone order log](/en/insights/softone/document-log/).

## Can I delete a document from Lynk?

No. A document created by mistake is corrected in Softone by you or your accountant.

## What happens when an order already sent to Softone is cancelled?

Lynk emails you. It doesn't change the document in Softone; let your accountant know. See [Softone order log](/en/insights/softone/document-log/).

## Does Lynk update stock in Softone or on my channels?

No. Today Lynk reads stock from Softone and shows it, but it doesn't change it in Softone and doesn't send it to your channels. See [Cost and stock from Softone](/en/insights/softone/cost-stock-sync/).

## Will Skroutz orders appear twice in Shopify?

Not because of Lynk: it recognises the orders it created itself. But if another app already creates your marketplace orders in Shopify, keep only one of the two switched on. See [Order relay](/en/insights/channels/order-relay/).

## Why do some orders show "No Cost"?

One or more of the order's products have no cost, so no margin is calculated. See [Order list](/en/insights/orders/order-list/).

## Why can't I see a page in the menu?

You may be a team member without permission for that page, or the connection may be hidden from the menu. See [Sign-in and access](/en/insights/troubleshooting/sign-in-and-access/).

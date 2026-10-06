---
title: "Cost and stock from Softone"
description: "Bring the item catalog, purchase cost and stock from Softone into Lynk."
sidebar:
  order: 5
---

*Describes the current version of the app.*

In this guide you bring three things from Softone into Lynk: the item catalog, which orders need before they can be sent; your products' purchase cost, which profit calculations need; and your stock, so you can see it inside Lynk.

Everything is read **from** Softone. Lynk doesn't change items, cost or stock in Softone, and today it doesn't send Softone stock to your sales channels.

## Before you start

- Softone connected. See [Connecting Softone](/en/insights/softone/connect/).
- Your products' codes (SKUs) on your channels match the item codes in Softone.

## Item catalog

To create the order document, Lynk must find every product of the order in Softone. That's why it syncs the item catalog.

1. Open **Softone** and the **Cost Sync** tab.
2. In the **Product Catalog** card, click **Sync catalog** (or **Re-sync catalog**, if it has synced before).

The catalog also updates automatically every night. The card shows when the last sync ran and when the next one is due. If you add a new item in Softone and want an order for it sent right away, click **Re-sync catalog** before you resend it.

## Purchase cost

The **Cost Price Sync from Softone** card brings each item's purchase price from Softone into the **Costs** page.

1. On the same tab, set in **Primary price field** which Softone field holds the purchase price. Ask your Softone partner if you're not sure.
2. Switch on the toggle in the **Cost Price Sync from Softone** card.
3. Click **Save** and then **Sync now**.

:::caution[Costs are replaced]
The sync replaces, on the **Costs** page, the cost of every product it finds in Softone with a price above zero. While cost sync is on, importing costs from a file on the **Costs** page is locked.
:::

Cost sync also runs automatically every night, at the time you set in the card.

## Stock

1. Open the **Inventory** tab.
2. Click **Sync now** to read the current stock from Softone.

The tab shows how many items Lynk holds (**SKUs cached**), when stock was last read (**Last snapshot**) and the open reservations (**Open reservations**): quantities from orders that have arrived but haven't been taken out of Softone stock yet. Stock updates only when you click **Sync now**.

On the **Connection** tab, the warehouses card maps each Softone warehouse (WHOUSE code) to a Shopify location. In the English app this card currently shows its Greek labels (**Αποθήκες**, **Κωδικός WHOUSE**, **Τοποθεσία Shopify**).

## What you'll see

- In the **Product Catalog** card, the date of the last sync.
- On the **Costs** page, product costs as Lynk read them from Softone.
- On the **Inventory** tab, stock per item and the latest runs under **Recent sync runs**.

## If something goes wrong

**Sending fails because a SKU wasn't found in Softone**: the item doesn't exist in Softone with the same code, or the catalog hasn't synced. See [Softone sending errors](/en/insights/troubleshooting/softone-document-errors/).

**Some products have no cost after the sync**: the price field in Softone is empty or zero for those items. Check the **Primary price field** with your Softone partner.

**"Sync appears stuck"**: the cost sync stopped. The products synced so far are saved. Click **Reset sync** and start again.

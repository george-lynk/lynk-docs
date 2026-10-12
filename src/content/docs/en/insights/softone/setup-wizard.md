---
title: "The catalogue check in the setup wizard"
description: "See what your Softone catalogue holds before the first orders arrive: prices, cost, VAT, barcode, stock and active items."
sidebar:
  order: 6
---

*Describes the current version of the app.*

In the **Catalogue** step of the setup wizard, Lynk reads your Softone items and shows you what is missing before the first orders arrive. The check only **reads** Softone: it never changes an item, a price or stock.

## Before you start

- Softone connected. See [Connecting Softone](/en/insights/softone/connect/).
- Optionally, your Shopify store connected: the check then looks at the items you sell.

## Steps

1. In the setup wizard, open the **Catalogue** step.

2. On the **Softone catalogue** card, press **Load now** (or **Load again** if a check has run before).

   <!-- TODO screenshot: the Softone catalogue card during a check. -->

3. Wait for the dot chart to fill. Most checks finish in a few seconds.

4. Press a card (**No retail price**, **No cost**, **No barcode**, **No VAT category**, **Stock**, **Inactive**) to see which items need something.

## Which items are checked

The check looks at the items you sell: your Shopify store's products and what sold in the last 90 days. Lines like discounts or packaging don't count. If there are none of these yet, the whole catalogue is checked.

If some items you sell aren't in Softone's item list, the card says so: they are inactive in Softone or not there.

The **SKU readiness report** does the same for codes: it compares the SKUs of your store's products and of what sold in the last 90 days with Softone's codes, even before the first order.

## The dot chart

Each dot shows items of the check:

- green: all fine,
- amber: something is missing,
- red: inactive in Softone,
- grey: not checked yet.

In large catalogues each dot is a group of items, and under the chart it says, for example, "Each dot = 15 items". A dot takes the colour of the worst item in its group. Hover over a dot to see which items it holds and how many are fine, missing something or inactive.

## Zero stock

An item with zero stock isn't counted as missing data: it is simply sold out. The **Stock** card reports it as information, and its dot doesn't turn amber.

## Estimates and exact numbers

Lynk reads most fields from Softone's lists for all items at once, so the numbers are exact. If a field, for example the cost or whether an item is active, can only be read item by item, the check reads it for a random sample of 300 items and the card shows an estimate:

- the number starts with **≈**,
- the text says, for example, "About 30% without a value (estimated from 300 items, ±3%)". The ± is the estimate's margin.

The rest is read overnight, gently, so it doesn't load your Softone. The card says "The exact numbers for cost and active items will be ready tomorrow morning. We'll let you know." When it finishes, the estimates are replaced with exact numbers and you get a notification with the items checked, those without cost and the inactive ones. The notification shows in the app and, if your notification settings send **Product without a cost** to e-mail, in your e-mail too.

The **Catalogue** step is complete without waiting for the night.

## Faster: fields from a Softone list

If one of your Softone item lists already shows the cost or whether an item is active, pick it and the check is exact at once:

1. Press **Pick a list** on the card, or open **Softone fields** under the card.
2. Next to each field, in the source choice, pick **Item** (Lynk finds it on its own) or a list, for example **List EshopStock**.
3. In the field, type the column of the list that holds the value. Lynk suggests the columns of the list you picked.
4. Press **Save**. The check starts again.

A list Softone doesn't know isn't offered.

## Stopping the check

While the check runs, the cards show "…" instead of the previous check's numbers. To stop it, press **Stop the check** and confirm. The previous check's results stay. If you press **Load again** right after, you may see "The previous check is still stopping": try again in a few seconds.

## What you should see

The **Softone catalogue** card says how many items were checked and when, and each card shows how many items need something. A card that says the field wasn't found means your Softone uses another field name: press **Fix the field**.

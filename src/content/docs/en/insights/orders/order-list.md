---
title: "Order list"
description: "The columns, the filters and what each status means on the Orders page."
sidebar:
  order: 1
---

*Describes the current version of the app.*

The **Orders** page shows all orders in the date range you pick in the top bar, grouped by day. Status indicators are icons; hover over them to see their name.

<!-- TODO screenshot: the Orders page with test data. -->

## Columns

| Column | What it shows |
|---|---|
| **Order Code** | The order code and the channel. The **FBS** label means a Fulfilled by Skroutz order |
| **Product** | The product, or how many products the order has. Click the row to see each product |
| **Qty** | The units |
| **Revenue** | The order value |
| **Fee** | The channel's commission, also as a percentage of revenue |
| **Net** | What's left after the commission |
| **Margin** | The profit margin, if every product has a cost |
| **State** | The order's state on the channel. See the table below |
| **Status** | Whether the order is profitable. See the table below |
| Shopify / Relay icon | Whether the order was sent to Shopify or to Relay. Shown when you've connected Shopify or Relay |
| Softone icon | The Softone sending status. Shown when you've connected Softone |

## State on the channel

| Label | What it means | Counts in revenue |
|---|---|---|
| **Open** / **New** | A new order not yet accepted or paid | Yes |
| **Accepted** | The order was accepted (Skroutz, Shopflix) or paid (Shopify) | Yes |
| **Dispatched** | The order was shipped. In Shopify: partially fulfilled | Yes |
| **Delivered** | The order was delivered. In Shopify: fully fulfilled | Yes |
| **Partially Delivered** | Part of the order was delivered | Yes |
| **Failed** | The channel marked the order as failed | Yes |
| **Cancelled** | The order was cancelled | No |
| **Rejected** | The order was rejected | No |
| **Expired** | The order expired without being accepted | No |
| **For Return** | The order is being returned | No |
| **Returned** | The order was returned. In Shopify: fully refunded | No |
| **Partially Returned** | Part of the order was returned. In Shopify: partially refunded | No |

Orders that don't count in revenue are **excluded orders**. You see them in the **Excluded Orders**, **Revenue Lost** and **Avg Excluded Order** cards at the top of the page.

## Profitability

| Label | What it means |
|---|---|
| **Profitable** | The margin is equal to or above the **Preferred Margin Target** in **Settings** |
| **Low Margin** | The margin is below the target |
| **No Cost** | One or more products have no cost, so no margin is calculated. See [Profit & costs](/en/insights/profit-costs/) |

## Sending to Softone

| Indicator | What it means |
|---|---|
| Clock | Waiting to be sent to Softone |
| Spinning icon | Being sent now |
| Green tick | Sent to Softone |
| Red cross | Sending failed. See [Softone order log](/en/insights/softone/document-log/) |

## Fulfilment health

| Label | Share of orders not excluded |
|---|---|
| **Excellent** | 95% and above |
| **Good** | 80% to 95% |
| **Fair** | 60% to 80% |
| **Needs Attention** | Below 60% |

## Filters and actions

| Item | What it does |
|---|---|
| **Search orders or products...** | Finds orders by code or product |
| **All channels** and one button per channel | Shows only one channel's orders. Shown when you have more than one channel |
| **All**, **Profitable**, **Low Margin**, **No Cost** | Filters by profitability |
| **Sync states** | Updates order states from the channel updates that have already arrived |
| **Export CSV** | Downloads the orders you see as a CSV file |

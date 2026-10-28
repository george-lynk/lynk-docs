---
title: "Target price"
description: "The price with VAT that brings each product to your margin target on each channel: what the three prices mean, how they are worked out and why a price can be missing."
sidebar:
  order: 1
---

*Describes the new version of the app, coming soon.*

## What the target price is {#overview}

The target price is the shelf price, with VAT, at which a product leaves you the profit margin you want on a channel. Flows works it out from the product's purchase cost and from what each channel charges you: commission, payment fee, order fees and shipping.

You see it in two places:

- on the product page, in the **Target price** card, with one row per channel;
- on the **Products** page, in the **Target price** column, with a filter and a ranking (see [On the Products list](#list)).

To see it you need the **Products and costs** access.

### Flows never changes your prices {#suggest-only}

The target price is only a suggestion. Flows writes no price to your e-shop, Skroutz, Shopflix or Softone. If you want to change a price, you change it yourself, where you manage it.

Market prices and other shops' prices play no part in the calculation. Only your own figures count.

## The margin target and the minimum margin {#targets}

You set the margin target and the minimum margin in **Settings** > **Profit and costs** > **Targets**. The top of the card shows which target it uses.

Margin means profit divided by sales without VAT. A 25% margin means that out of every €100.00 of net sales you keep €25.00 as profit.

### When you haven't set a target {#default-target}

If you haven't set a margin target, Flows uses 30% and labels it **default** next to the target. Set your own target in **Settings** > **Profit and costs** > **Targets** and the prices are worked out again with it.

If you haven't set a minimum margin, the **Minimum** column doesn't show.

## The three prices {#three-prices}

For each channel the card shows three prices, all with VAT and rounded up to the cent, so they never give you less than they say.

### Break-even {#break-even}

The price at which profit is zero: it covers the cost, the commission, the payment fee, the order fees and shipping, with nothing left over. Below this price every sale costs you money.

### Minimum {#minimum}

The price that reaches the minimum margin you set. It is useful as a floor for promotions and discounts.

### Target {#target}

The price that reaches your margin target on this channel. This is the target price.

## Today's price {#today}

The **Today** column shows the median price with VAT you got per unit on the channel in the last 30 days, after discounts. The three prices are compared with it. If the product didn't sell on the channel in the last 30 days, there is no price today and the status is **Estimate**.

### How far it is {#gap}

Under the target price you see how much today's price must change to reach the target, as a percentage. With a minus sign, today's price is already above the target.

### Where the price sits {#ladder}

The **Where the price sits** bar shows where today's price sits among the three prices: red below break-even, amber below the target, green from the target up. The colour always comes with the status in words.

### Status {#statuses}

| Status | What it means |
|---|---|
| **On target** | Today's price reaches or passes the target price |
| **Below target** | Today's price is below the target, but above the minimum (or above break-even, if you haven't set a minimum) |
| **Below the minimum** | Today's price is below the minimum, but above break-even |
| **Loss** | Today's price is below break-even: every sale costs you money |
| **Estimate** | There is no price today to compare. See [Estimate](#estimate) |
| **Cost missing** | There is no purchase cost. See [Cost missing](#cost-missing) |
| **Commission missing** | The channel's commission isn't known. See [Commission missing](#commission-missing) |
| **Out of reach** | No price reaches the target. See [Out of reach](#out-of-reach) |

## One price for every channel {#one-shelf-price}

Usually one shelf price feeds every channel. That's why the card states one price at the top: the highest target price among the channels where you sold the product in the last 90 days, and which channel sets it. At that price you reach the target on all those channels. The same price shows in the list's **Target price** column.

Channels where you didn't sell the product show as an [estimate](#estimate) and don't set this price.

## How it is worked out {#inputs}

Press **How it's worked out** on the card to see the cost, the fees and the VAT behind each price, and where each one comes from.

In words, the calculation for each channel is:

1. Add the unit's purchase cost and the fixed charges per unit (order fees and shipping), all without VAT.
2. Take the commission, the payment fee and the margin you want away from 100%. What is left is the share of the net price that covers the cost.
3. Divide the amount from step 1 by the share from step 2. This is the net price, without VAT.
4. Add VAT and round up to the cent.

As a formula: price = (cost + fees and shipping per unit) ÷ (1 − commission − payment fee − margin) × (1 + VAT).

For break-even the margin is 0%, for the minimum it is your minimum margin and for the target it is your target.

### Cost {#cost}

The purchase cost per unit without VAT, from the cost source you set: Softone, read every night, or what you enter yourself in **Settings** > **Profit and costs** > **Costs and charges**. If your costs include VAT, the VAT is taken off first. It is the same cost the score and the product page's margins use.

### Commission {#commission}

The channel's commission as a share of sales without VAT, as the channel charged it over the last 90 days. Your own e-shops have no channel commission.

### Payment fee {#payment-fee}

The fee of the payment method (a card, for example) as a share, on your own e-shops. On the marketplaces the channel pays it. If the fee also has a fixed part (€0.25 per order, for example), that part counts as a share of today's price. That's why, for low-priced products, the target price can be a few cents off the exact one.

### Fees per unit {#order-fees}

The marketplace's order fees per unit, without VAT, such as handling, instalments and FBS.

### Shipping per unit {#shipping}

On your own e-shops: what you pay the carrier per unit, minus what you charge the customer. It counts only when the carrier cost is known. When it isn't, the card says **unknown, left out** and shipping stays out of the calculation. On the marketplaces the card says **doesn't apply**.

### VAT {#vat}

The VAT rate of your consumer sales of this product. If there are no such sales, the standard VAT rate from **Settings** is used. A product at 0% VAT stays at 0%.

### Where each fee comes from {#sources}

The commission, the payment fee and the fees per unit come, in this order, from:

1. **from its sales**: the product's sales on the channel in the last 90 days, when they are at least 5 units;
2. **channel average**: all your sales on the channel in the last 90 days;
3. **rule**: a rule you set, such as your Shopflix commission rule or the fee of the payment method used most on your e-shop.

A fee Flows couldn't work out on a sale doesn't count as 0%. It is left out and the next level is used.

## Example {#example}

A product on Skroutz with a purchase cost of €10.00 without VAT, 15.1% commission, order fees of €0.30 per unit, 24% VAT and a 25% margin target:

1. Cost and fees per unit: €10.00 + €0.30 = €10.30.
2. The share of the net price that is left: 100% − 15.1% − 25% = 59.9%.
3. Net price: €10.30 ÷ 0.599 = €17.20.
4. With 24% VAT, rounded up to the cent: **€21.33**.

A check at the target price:

| | Amount |
|---|---:|
| Price with VAT | €21.33 |
| VAT 24% | −€4.13 |
| Commission 15.1% | −€2.60 |
| Order fees | −€0.30 |
| Purchase cost | −€10.00 |
| **Profit** | **€4.30** (25% of €17.20) |

The same way, break-even is €15.05 and, with a 15% minimum margin, the minimum is €18.28. If you sell at €19.90 today, the status is **Below target** and the price must rise about 7% to reach the target.

## Why a price is missing {#missing}

### Cost missing {#cost-missing}

Without a purchase cost there is no price. Add the cost in **Settings** > **Profit and costs** > **Costs and charges** or on the Softone item, and the price shows for every channel. If the cost comes from Softone, it shows after the next nightly read.

### Commission missing {#commission-missing}

Flows doesn't know the channel's commission for this product: there is no sale with a known commission, on the product or on the channel, and there is no rule. Press **Add a commission rule** to set one, and the price shows.

### Out of reach {#out-of-reach}

The channel's fees plus the target reach or pass 100% of the price. For example, a 20% commission and an 80% target leave nothing for the cost, however high the price goes. Check your target with **See the targets**.

### Estimate {#estimate}

A channel you have connected, where the product didn't sell in the last 90 days, shows with **not sold** and an **estimate** price. The price comes from your average fees on the channel and isn't compared with a price today. The **Estimate** status also shows when the product didn't sell on the channel in the last 30 days, so there is no price today.

## On the Products list {#list}

### The Target price column {#list-column}

The **Target price** column shows, for each product, the price with VAT that reaches the target on every channel you sell it on (see [One price for every channel](#one-shelf-price)), the channel that sets it and how far today's price is. When there is no price, the column says why: **cost missing**, **commission missing**, **out of reach** or **no sales**.

The list's CSV export has two more columns: the target price and the channel that sets it.

### The Below target filter {#list-filter}

The **Below target** switch shows only the products whose price today is below the target price: those **Below target**, **Below the minimum** or at a **Loss**. Next to the switch you see how many there are.

### Ranking by target price {#list-sort}

In the ranking list, choose **Rank by: Target price** to see first the products whose price must rise the most to reach the target.

## See also {#see-also}

- [Cost and stock from Softone](/en/insights/softone/cost-stock-sync/): how the purchase cost comes from Softone.
- [Profit & costs](/en/insights/profit-costs/): how each order's profit is worked out.

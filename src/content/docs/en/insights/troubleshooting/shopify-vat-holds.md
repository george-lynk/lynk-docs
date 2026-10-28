---
title: "A Shopify order was held for its VAT"
description: "Why Lynk holds a Shopify order before sending it to Softone when its VAT can't be sent as it was charged, and how you fix it."
sidebar:
  order: 2
---

*Describes the new version of the app.*

Lynk sends each line of a Shopify order to Softone **at the VAT Shopify charged**: 24%, 13%, 6% or 0%. It never puts 24% on a line by itself.

The order it follows for each line:

1. The line's tax line in Shopify, which is what the customer paid.
2. If the line has no tax in Shopify, the VAT category of the item in Softone.
3. If there is neither, the order is **held**.

One exception: a receipt for a customer outside the EU, with no tax in Shopify, is an export and is sent at 0%.

A rate becomes a Softone VAT code **only** through the VAT codes you set in the channel's rules. Lynk doesn't guess a code.

## What "held" means

When an order's VAT can't be sent safely, Lynk holds it **before writing anything to Softone**: it creates no customer and no document.

The order shows as a failed send, with a title that gives the reason, the line and the item's code. Lynk tries again by itself a few times, but the result doesn't change until you fix the cause.

Once you've fixed it, send the order again. The **Test** in the channel's rules shows the same reason without sending anything.

## The reasons and their fix

### "Shopify prices exclude VAT"

**Cause:** in Shopify, product prices don't include tax. Lynk sends Shopify prices as final prices, VAT included.

**Fix:** in Shopify, **Settings → Taxes and duties**, turn on the option that prices include tax. For orders that have already arrived, issue the document by hand in Softone.

### "Line … has more than one tax in Shopify"

Or: "… isn't a whole percent", "… can't be read", "… has more taxes in Shopify than Lynk read".

**Cause:** the line in Shopify doesn't have one clear Greek VAT rate. For example, it has two taxes, or a rate such as 5.5%. Lynk doesn't pick one of them.

**Fix:** check the product's tax in Shopify (**Settings → Taxes and duties**, and the tax overrides per collection). Then send the order again.

### "Line … has the island VAT rate … on a receipt"

**Cause:** the line was charged 17%, 9% or 4%. The reduced island rates apply only to invoices to businesses on the islands, not to a receipt.

**Fix:** correct the product's tax in Shopify and send the order again.

### "Line … is at …% VAT for a consumer in … (OSS)"

**Cause:** the customer is a consumer in another EU country, and Shopify charged that country's VAT (OSS). Lynk doesn't send another country's VAT yet.

**Fix:** issue this document by hand in Softone. If you sell at Greek VAT across the EU, the order is sent as usual.

### "The discount isn't spread evenly over the VAT rates"

**Cause:** the order has products at different VAT rates, and the discount (for example a coupon on some products only) isn't the same percentage on all of them. One discount on the document would move VAT from one rate to another.

**Fix:** issue this document by hand in Softone. A discount on the whole order is sent as usual.

### "Shopify charged …% VAT on shipping; the channel sends it at …%"

**Cause:** shipping goes to Softone as an expense, at the rate you set on the channel. Shopify charged a different rate.

**Fix:** make the channel's shipping VAT rate in its rules the same as Shopify's, or correct the shipping tax in Shopify. Then send again.

On an export (a customer outside the EU, with no tax in Shopify), shipping and cash on delivery carry no VAT. If you ship outside the EU, the shipping VAT rate and the cash-on-delivery rule's rate must be 0%, or the order is held for this reason.

### "Line … is at …% VAT in Shopify; its expense rule sends it at …%"

**Cause:** a charge such as cash on delivery goes to Softone as an expense, at the rate of its expense rule. Shopify charged a different rate.

**Fix:** make the rule's VAT rate the same as Shopify's and send again.

### "No Softone VAT code for …%"

Or, for several rates at once: "Softone VAT codes are missing for 13%, 6% …".

**Cause:** the order has rates for which you haven't set a Softone VAT code on the channel. The message names all of them.

**Fix:** in the channel's rules, under **VAT codes**, set the Softone code for every rate you sell through Shopify: 24%, 13%, 6% and 0%, plus 17%, 9% and 4% if you invoice businesses on the islands. Then send again.

### "Line … has no VAT rate"

**Cause:** the line has no tax in Shopify, and its item in Softone has no VAT category.

**Fix:** set the item's VAT category in Softone, or the product's tax in Shopify. Then send again.

### "The item's VAT category couldn't be read from Softone; we'll try again"

**Cause:** the line has no tax in Shopify, and Softone didn't answer when Lynk asked for the item's VAT category. It doesn't mean the category is missing.

**Fix:** usually nothing: Lynk tries again by itself. If the message stays, check that Softone is available and send the order again.

## Before you start with Shopify

- Check that Shopify charges the right rate on every product: products at 13% and 6% need a tax override on their collection. Lynk invoices what Shopify charged.
- Set a Softone VAT code for every rate you sell.
- Check that the channel's shipping VAT rate and the shipping expense code in Softone match the shipping tax in Shopify.

## If the problem continues

Press **Help** at the bottom of the menu and send us the order's code and the title you see. Don't send passwords.

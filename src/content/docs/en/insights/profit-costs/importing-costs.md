---
title: "Product cost: where it comes from"
description: "One cost source for the whole account: Softone, Shopify or a CSV file. Cost coverage, the CSV template and products without a cost."
draft: true
sidebar:
  order: 2
---

*Describes the new version of the app.*

Product cost is the net purchase cost of each product, without VAT. It gives the profit of every order, product and channel. Orders are sent without a cost too, but their profit shows “—”.

You set the cost in two places, which show **the same choice in the same words**:

- in the **Setup guide → Costs** (“Where does the cost come from?”),
- in **Settings → Profit and costs → Costs and fees**.

Whatever you change in one shows at once in the other.

## Cost coverage {#coverage}

The **Cost coverage** card always says above the number what it counts:

- **Softone catalogue · no sales yet**: before the first sales we count the catalogue items, for example “1,640 of 1,984 items have a cost in Softone”. Without Softone, we count the Shopify variants.
- **Sales, last 30 days**: once sales arrive, we count the products sold in the last 30 days, weighted by revenue, for example “96% of sales have a cost”, with the best-selling product without a cost.
- **Not loaded yet**: the catalogue is not loaded. **Load the catalogue** takes you to the **Catalogue** step.

If some items' cost has not been read from Softone yet, the card says so: they are read that night.

## Products without cost {#products-without-cost}

**See the N … without cost** opens the list in a side panel, on the same page, best-selling first. From there:

- fill them in Softone or Shopify (they are read that night), or
- press **Download CSV of the N**, fill the `cost` column and upload it with the **From a CSV file** source.

To fix the cost of a single product, open it in **Products**. That is a correction, not a source: the next night the account's source may replace it.

## The three sources {#cost-source}

One source applies to the whole account, so a product never has two costs.

| Source | When it updates | Fits when |
|---|---|---|
| **From Softone, every night at 02:00** | Every night | Cost lives in Softone (recommended) |
| **From Shopify, “Cost per item”** | Every night | You have no Softone and keep cost in Shopify |
| **From a CSV file** | When you upload a file | Cost is in Excel or another system |

### From Softone

Every night we read each item's cost from the Softone field you set in **Catalogue → Softone fields → Cost**. The option shows the field by its code and name, for example `ITECPRICES.PURLPRICE` · Last purchase price, and **Change field** takes you straight to it. Below it is the last read, for example “Last read: today 02:00 · 1,640 costs”.

If no cost field is set, the option reads “No cost field is set in Softone, so we read no cost.” with **Set the cost field**.

In Softone: **Items → Stock items → open the item → Prices → purchase price**. Menus differ slightly per version.

### From Shopify

Every night we read each Shopify variant's **Cost per item** (`inventoryItem.unitCost`). The first read is a few minutes after you choose the source. Only euro costs above zero count. The Shopify connection needs inventory read access, because that is where the cost per item lives. If it is missing, the option says so and takes you to the Shopify connection.

If you have Softone, prefer Softone so you never have two costs.

### From a CSV file {#csv-import}

1. Press **CSV template**. The template already has all your SKUs, with the cost we know.
2. Fill the `cost` column: net cost without VAT, with a dot or a comma.
3. Upload it in **Drop the CSV here or choose a file**. Before anything is saved, you see what matched.

The file's format:

| sku | cost | currency | |
|---|---|---|---|
| AIG-1001 | 4.20 | EUR | normal |
| AIG-1024 | 2,85 | EUR | comma: accepted |
| AIG-2002-L | 11 | | empty currency = EUR |

- Separator `;` or `,` (or tab), UTF-8 encoding. In Excel, choose “CSV UTF-8” when saving.
- The `sku` and `cost` columns are needed. `currency` is optional: empty means euro, another currency is not accepted.
- Rows with an empty cost stay as they are.
- Up to 2 MB and 20,000 rows per file.

After the upload you see:

- **SKUs matched**: what will be saved,
- **SKUs not in the catalogue**: SKUs that are not in Softone, Shopify or your sales,
- **rows with a bad value**: for example “4,2,0” is not a number, a negative or zero cost, the same SKU twice.

**What did not go in** lists each row with its reason, and **Download the N rows** downloads them to fix. **Save N costs** replaces these SKUs' cost from today; analytics recalculate within minutes. **Cancel** drops the file without saving anything.

If the file cannot be read, for example the `cost` column is missing, you see which columns we found and what to change. Nothing is saved.

## Who can change it

The account owner and members with the **Products** permission. Other members see the settings without changing them.

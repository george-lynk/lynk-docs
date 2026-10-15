---
title: "For Softone partners: document fields"
description: "Standard fields, your own fields and standard field overrides in each channel's Softone rules."
draft: true
sidebar:
  order: 6
---

*Describes the new version of the app, coming soon.*

<a id="overview"></a>

The channel's rules cover most shops. When your Softone partner needs something more, such as your own field on the document or a fixed value in a standard field, they find it under **Flows** → the channel → **Rules** → **For Softone partners**.

:::caution[The values here override the rules]
Whatever you set here changes the documents Lynk sends to Softone. Always try in Demo first, with **Test with an order**.
:::

Press **Apply** to put the changes into the rules, then **Save** for them to take effect.

<a id="custom-fields"></a>

## Your own fields

The first table writes fields to the document header, such as `VARCHAR03` or a `CCC…` field your partner created. Press **+ New field**, type the **Softone field** and choose a **Source**:

- **Fixed value**: the same value on every document.
- **From the order**: a detail of the order. **Order number**, **Order ID**, **Order note**, **Customer email**, **Customer phone**, **Channel** and **Tags** are suggested, and they are read on Shopify, Skroutz and Shopflix. You can also type another detail of the order, as in the previous version. If the order doesn't have it, the field isn't written.
- **Per customer type**: one value for **Individual** and one for **Business**.
- **Built-in value**: **Customer name** or **Channel and order number**.

The **Ready-made fields** add the usual ones in one click: **+ VARCHAR01 (name)**, **+ VARCHAR02 (order number)** and **+ UFTBL01**.

<a id="standard-fields"></a>

## Standard fields and new customers

**Standard fields** holds the document header's codes with a fixed value: **Shipping kind**, **Cash register**, **User table 1**, **Salesperson**, the **direction** for businesses and for individuals, the **Document source** and the **Document form**. Fill in the form only if your partner built your own document form.

**New customers** sets the fields of a customer Lynk creates: currency, KEPYO and price group, the **VAT number for new individuals** (`000000000` by default) and whether the details are written in capitals.

<a id="standard-mappings"></a>

## Standard mappings

**Standard mappings** shows what Lynk sends in each standard field: the field's code, its name and where the value comes from. There are three groups:

- **Customer (CUSTOMER), when Lynk creates one**: name, address, phone, VAT number, accounting category and more.
- **Document (SALDOC, MTRDOC)**: series, customer, payment, shipping, warehouse, delivery address and more.
- **Lines (ITELINES, EXPANAL)**: item, quantity, price, VAT and shipping. These are for reference only: they don't change from here, because one value would change every line.

Press **Change** on a field to add it to the overrides, and **Reset** to go back to Lynk's value.

<a id="overrides"></a>

## Standard field overrides

An override puts a fixed value in place of the one Lynk computes:

- a **SALDOC** field is written to the document header, and an **MTRDOC** field to the shipping details;
- a **CUSTOMER** field is written only to a customer Lynk creates. It never changes a customer that already exists in Softone, or the shared walk-in customer. The duplicate-customer check always searches with the order's details, such as the customer's VAT number, not with the override's value.

If you leave the value empty, Lynk's computed value applies: an empty override never sends an empty field.

<a id="write-order"></a>

**Write order.** The standard fields are written first, then your own fields, then the overrides. If two write the same field, the last one applies.

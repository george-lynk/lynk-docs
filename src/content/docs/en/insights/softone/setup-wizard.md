---
title: "Setting up Softone in the setup guide"
description: "The setup guide's Softone questions, the Live check and the test in Demo."
draft: true
sidebar:
  order: 3
---

*Describes the new version of the app, coming soon.*

The setup guide asks everything the first order document in Softone depends on. Each answer becomes a rule of the channel, and the choices come from your company's Softone lists. Lynk creates order documents; you issue the final documents in Softone.

## Before you start

- A Lynk Insights account with the **Owner** role.
- From your Softone partner: the Softone address, a user for Lynk with its password, and the application code (AppID). Demo and Live have separate details.

<a id="company"></a>

## Connection and company

1. In the **Softone** step, fill in the Demo sign-in details and select **Connect and check**.
2. Lynk signs in and shows the companies and branches the user may use. Nothing is saved yet.
3. Choose the **Demo company** and the **Branch** and select **Connect to this company**. If there is only one company with one branch, it is already selected: just select the button.

If Softone doesn't allow the company for the user, you see "The user signed in, but Softone doesn't allow them in this company or branch". Choose another one, or ask your partner for the permission. Under **Advanced** you can type the codes and the login profile (REFID).

## The rules questions

The questions open one at a time, for each channel. Where Lynk finds only one matching choice in your lists, it suggests it; the suggestion is saved only when you select **Next question**. If a question already has a saved answer, you see it marked **Saved**; a new choice applies only after you select **Next question**. Each question also has **Advanced**, with the settings Lynk already uses.

<a id="softone-field"></a>

### Softone codes and fields

Every choice from Softone shows its code, its short name and its description, for example `7021 · ΠΑΡ · Παραγγελία (Δα-Τιμ.)`, so you can be sure you pick the right record. In long lists you can search by code or name.

Under each answer, **Field in Softone** shows where Lynk writes it, for example `SALDOC · SERIES` for the invoice series. It's useful for your Softone partner.

<a id="invoice-request"></a>

### How your customers ask for an invoice (Shopify)

Shopify doesn't say by itself which order wants an invoice. Choose how Lynk can tell:

<a id="lynk-app"></a>

- **With the Lynk app** (suggested): the Lynk app's invoice fields in the cart, with the VAT number checked at AADE or VIES, on every Shopify plan. If your recent orders already carry these fields, the choice is ready and there's nothing else to set up. Otherwise, in Shopify open **Online Store → Themes → Customize** and switch on the Lynk app's invoice fields, under **App embeds** or as a block in the cart.
- **From another app's tag or field**: another invoicing app tags the order, for example `needs:invoice`, and writes the VAT number (ΑΦΜ), company name, tax office (ΔΟΥ) and business activity in its fields. The guide suggests the names it found in your recent orders.
- **From Shopify's VAT number field** (coming soon): it doesn't mean an invoice by itself, it only appears once an address and postcode are entered, and Shopify keeps it on the customer, not the order. That's why Lynk doesn't read it yet.
- **From a checkout field**: only for Shopify Plus stores, which can add checkout fields, for example "Τιμολόγιο: Ναι" and "ΑΦΜ". It also works for a field another app writes on the order.
- **When the address has a company name**: the VAT number is missing, so the order is flagged for your accountant. In **What we write in the remarks when an invoice was asked for without a VAT number** you set the text that goes first in the document's remarks; left empty, it's `[INCOMPLETE B2B - VAT REQUIRED]`. If the company name is missing too, the order goes to the [safety-net customer](#safety-net-customer).

The setting applies to new orders.

<a id="retail-document"></a>

### Which Softone view consumers' orders go to

- **With every other document (Sales Documents, SALDOC)**: everything in one view, with invoices and credit notes. An order can still become an invoice later.
- **Separately, under Retail Sales (RETAILDOC)**: retail stays separate. A document here can't become an invoice later; if the customer asks for one, it takes a credit note and a new invoice.

Neither is preselected: choose what your accounting team uses. The series list shows only the series that fit the view you chose, and each series says whether it's an **order** (you convert it to a receipt in Softone, and Lynk finds the final document through [Final documents](#final-documents)) or a **final document**.

The **Softone form** is no longer in this question: your partner finds it under **For Softone partners** in the channel's rules. Fill it in only if your partner built your own document form.

<a id="invoice-rules"></a>

### What happens when the customer asks for an invoice

Choose the series for invoices. Three boxes follow it:

<a id="aade"></a>

- **The VAT number check at AADE**: the company's name, tax office and address come from the official registry, not from what the customer typed, and Lynk finds the business in Softone instead of creating a new one. If AADE doesn't answer, the order is sent **at once** with the customer's own details, marked "unverified", and we let you know by email and notification: "The VAT details weren't verified because of a connection problem with AADE". If you'd rather hold such orders, change it in the channel's rules.

  The check needs your **AADE special credentials**: the username, the password and your company's VAT number. You add them right under the switch. The password is stored encrypted and never shown again. **Test the connection** shows that they work. Without credentials, or with the check off, invoices go out without a VAT number check, and we alert you.

<a id="vat-prefix"></a>

- **How your accountant wants the VAT number in Softone**: with the country prefix (`EL123456789`) or without it (`123456789`). Write it as in the customers you already have: that's how existing customers are found, reports add up and it matches AADE.

<a id="safety-net-customer"></a>

- **A safety net for invoices** (Shopify, optional): if we can't find or create the customer (for example the VAT number is missing or wrong), the invoice goes to this customer so the order doesn't stop; your accountant corrects it later.

<a id="walk-in"></a>

### How consumers go into Softone

For each channel, you choose whether consumers become customers in Softone one by one, or all go to one retail customer:

- **A new customer per buyer**: each buyer becomes a customer in Softone. Under **New consumer codes** you set a **Prefix** and a **Number of digits**: for example `30.01.` with 5 digits gives 30.01.00001. When sending, Lynk finds the highest code starting with the prefix in Softone and uses the next one.
- **One shared retail customer**: every order goes to one customer that already exists in Softone (for example "ΠΕΛΑΤΗΣ ΛΙΑΝΙΚΗΣ"). The guide looks for it and suggests it; you can search by name or type the code.

<a id="greece-abroad"></a>

**Greece and abroad separately.** If you switch on **Separate Greece and abroad**, you set the approach, the retail customer and the numbering (prefix and digits) separately, by the shipping country. For example: a new customer for each buyer in Greece, and one retail customer for everyone abroad.

<a id="default-customer"></a>

**Default customer (and fallback).** With "A new customer per buyer", each segment's retail customer is also the fallback: if Softone doesn't accept the new customer, or the search for an existing one fails, the order goes to it instead of stopping. If Softone just isn't answering for a while, Lynk retries first as usual, and uses the default customer only once the retries run out. You see it under **Needs you** ("went to the walk-in customer"), with the orders and the reason. Once you've fixed the cause, send them again: Lynk tries the buyer again and, if that works, updates the same document with the right customer. If you don't set a default customer, such an order isn't sent, and the guide points this out.

<a id="duplicate-check"></a>

**Duplicate customer check.** Before creating a new customer, Lynk can look in Softone for a buyer with the same email or phone and use it. It can also fill in only what the customer record lacks, never changing what's there. A phone number without a country code, for example 6941234567, is read with the country code of the order's country (+30 for Greece, +357 for Cyprus), so it matches the same number in Softone. The **Phone country code** (default +30, under **Advanced**; in the channel's rules it is called **Country code when the country is missing**) is used only when the order has no country. New customers are written to Softone with their phone number and the country code of the order's country.

<a id="consumer-category"></a>

**Category of new consumers.** The customers Lynk creates go into one category (TRDCATEGORY, default 3099), and the duplicate check looks only in it, so a consumer is never mixed up with a business. If your accountant splits consumers by region, switch on **A different category per region** and choose a category for Greece, another EU country and outside the EU. Where you don't choose one, the single category applies.

<a id="change-later"></a>

**Changing it later.** You'll find the same settings in the channel's rules (**Flows** → the channel → **Rules**), with the same words and the same values as the guide. On the **Customers** card, while **A separate customer for purchases from abroad** is on, Greece and abroad each have their own approach and their own retail customer, in place of the single choice. On the **VAT & accounting categories** card, the category question has **A different category per region**. Every Softone value shows its code, e.g. `3099 · ΙΔ · Ιδιώτες`. On the **Payments** and **Shipping & carriers** cards, the mapping tables take new values and remove rows, as in the payments question. The carriers table also lists the carriers that appear in your orders.

The VAT number written on consumers (default `000000000`) isn't a question in the guide: your partner changes it under [**For Softone partners**](/en/insights/softone/advanced-fields/) in the channel's rules.

<a id="new-customer-codes"></a>

### How new businesses are numbered

Under **New business codes** you set a **Prefix** and a **Number of digits**, as for consumers: for example `30.00.` with 5 digits gives 30.00.00001, and Lynk always uses the next free code in Softone.

If you switch on **Separate Greece and abroad**, you set the prefix and digits separately for **Greece** and **Abroad**, for example `30.00.` and `30.02.`. The invoice country decides: GR or blank is Greece, any other is abroad.

If new businesses are written today to a fixed code, with their VAT number as the code or with your own formula, the question says so. Once you change the prefix or the digits, numbering becomes sequential.

<a id="vat-codes"></a>

### VAT

Every Softone installation has its own VAT codes. For each rate in your orders, choose its code. The guide suggests the code that carries the same rate. Lynk never guesses a VAT code: if an order has a rate without a code, it isn't sent and you see why.

### Warehouse, payments and shipping

- **Warehouse**, and for Skroutz the **FBS** warehouse.
- **Payments**: each payment method of the channel matches one in Softone, and **All other methods** covers the ones that appear later. For a method that hasn't appeared in an order yet, type it in the box under the table and select **+ Value**. Select **×** next to a row to remove its mapping. A method that appears in your orders stays in the table, without a mapping. **All other methods** can't be removed.
- **Shipping** (Shopify only): the expense code for the shipping the customer pays. On Skroutz and Shopflix, shipping doesn't go into the document.
- **Cash on delivery**: with **Cash on delivery goes in as an expense line** and **The expense code for cash on delivery**, the cash-on-delivery charge is written as an expense, not as a product. It is the same rule as **Cash on delivery** in the **Expenses (e.g. cash on delivery)** card of the channel's rules: change it in either place and it changes in both. In the same card, an expense rule without an expense account reads **left out**: the line isn't sent to the document.

<a id="order-numbers"></a>

### Order with Shopify (Skroutz, Shopflix)

When a marketplace's orders also go to Shopify, Lynk is suggested to **wait for the Shopify number**. The Softone document then has both numbers: the marketplace number in the customer document field and the Shopify number in the remarks, or next to the marketplace number. You find the document by either one.

Under **If Shopify fails** you choose what happens when the order doesn't go into Shopify: **Wait** (the order waits until it does) or **Send to Softone without it**. With the second, the document is created without the Shopify number; once the order is in Shopify, select **Resend** in **Orders** to add the number. Switching off **Wait for the Shopify number** takes effect at once, also for stores set up in the previous version.

<a id="which-orders"></a>

### Which orders are sent

The last question of every channel: **All** (receipts and invoices), **Only those asking for an invoice** or **Consumers only**. It applies to the whole channel.

<a id="check-now"></a>

### When something hasn't been checked yet

If a question says the Softone lists or a customer haven't been checked recently, select **Check now** next to or under the message. The customer is checked by its code, and meanwhile you see "checking". A customer you picked from the search is already checked; a code you typed is checked by Lynk as soon as you select **Next question**.

<a id="copy-rules"></a>

## Copying rules from another channel

When a channel has no rules yet and another channel is ready, the guide suggests starting from its rules. You see what changes first, confirm, and you can undo it. Settings that concern one channel only (FBS, Shopify, Shopify invoices) aren't copied.

The copy happens once. After that, each channel has its own rules, and a change to one channel doesn't change the others. For example, you can create a customer for each e-shop buyer and send Skroutz buyers to one retail customer.

<a id="registries"></a>

## The AADE and VIES checks in the Test step

They aren't separate steps of the guide. Your AADE special credentials go in the rules, in the question [What happens when the customer asks for an invoice](#aade). You turn VIES on in **Connections**, with your EU VAT number.

In the **Test** step, the automatic check (step 1) shows each one that is on:

- **VAT number check at AADE**: whether the connection to AADE works and when it was checked. The connection test runs with the check, and again with **Check again**. Without credentials, or with the check off, it says invoices go out without a VAT number check and we alert you, and takes you to the rules to add them.
- **VIES check**: whether it is on and has your EU VAT number. If the number is missing, it takes you to Connections.

Neither one stops the Test or Live.

## Preview

**Preview** shows the document Lynk would create for real recent orders of each channel, without writing anything to Softone: a plain one, one with several items and one with an invoice. If something is missing, **Fix** opens the question that fixes it.

<a id="test-in-demo"></a>

## Test in Demo

The test sends one order **to Demo only**. Before it is sent, you confirm the order and the Demo company. If you send it again, the same document is updated; no second one is created.

If Softone is already in Live, the test sends nothing; see the preview.

<a id="live-check"></a>

## Live check and switching on

:::caution[Real company]
Once switched on, Lynk creates order documents in your Softone Live company. Check the series, the warehouse and the retail customer before you continue.
:::

1. In the **Live** step, connect the Live company with its own details, as you did for Demo.
2. The **Live check** checks that every code in the rules exists in the Live company: series, warehouses, the retail customer, VAT and payment codes. For each missing code, choose the Live code or open its question. There is one set of rules per channel, so the change applies to Demo too.
3. While a code is missing, Live isn't switched on.
4. Select **Go Live**, type the word asked for and confirm.

<a id="final-documents"></a>

## Final documents (optional)

Set which series Lynk looks in for the documents you issue (receipt, invoice for Greece, the EU and outside the EU), so it sends them to the customer and the channel. Credit notes are coming soon; today, when an order that was sent is cancelled, we email you.

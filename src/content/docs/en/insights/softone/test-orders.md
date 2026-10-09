---
title: "Test orders"
description: "Test your Softone rules with ready-made scenarios, no sales channel needed: preview them and send them one at a time to your Demo company."
sidebar:
  order: 7
---

*Describes the current version of the app.*

## What it is

**Test orders** are orders Lynk builds from your own Softone items and the expense codes you set. No sales channel needs to be connected: Softone is enough.

Each test order:

- has a **preview** of everything that will be sent to Softone: the document, series, customer, lines, VAT, expenses and total
- is **sent one at a time** to your **Demo** company, with a confirmation, along the same path real orders take
- is compared with what was **created** in Softone

You'll find them in the setup wizard's **Test** step and on the **Softone** flow page, as **Test orders**.

## Why it matters

A wrong rule silently produces a wrong fiscal document. Test orders let you check every case that applies to you before you turn on automatic sending: an invoice with a VAT number, reduced VAT, EU and non-EU sales, cash on delivery, discounts and more.

## How it works

<a id="scenarios"></a>
### 1. Choose the scenarios

The core scenarios are already selected. The optional ones say when they apply to you, for example Skroutz FBS. Some scenarios need details only you can give:

- **VAT number of a new B2B customer**: Lynk never makes up a VAT number, because an invented one could belong to a real company. With their permission, use a partner's or your accountant's, or skip the scenario.
- **Code of an existing customer**: Lynk reads the VAT number, or the e-mail and phone, from that customer's card, to show that it finds the customer.
- **EU VAT number** and **tax number outside the EU**, for sales abroad.

| Scenario | What it checks |
|---|---|
| S01 | Retail with the shared retail customer |
| S02 | Retail with a new customer card |
| S03 | Retail, a customer found by e-mail or phone |
| S04 | B2B, a customer found by VAT number |
| S05 | B2B, a new customer with a VAT number |
| S06 | B2B at 24% VAT |
| S07 | Reduced VAT 13% and 6% |
| S08 | B2B on an island with reduced VAT 17% (expected gap) |
| S09 | Intra-community B2B sale at 0% VAT (expected gap) |
| S10 | Retail in an EU country, OSS (expected gap) |
| S11 | Export outside the EU at 0% VAT, euro only |
| S12 | Skroutz FBS |
| S13, S14 | Credit notes: guidance only (see below) |
| S15 | Discounts, a coupon and free shipping |
| S16 | Mixed VAT and rounding |
| S17 | Card, bank transfer and cash on delivery |
| S18 | B2B with a different shipping address |
| S19 | Invalid VAT number |
| S20 | Sending again, and a second order from the same customer |
| S21 | An item code that doesn't exist (preview only) |
| S22 | Mount Athos (expected gap) |
| S23 | The same basket under each channel's rules |
| S24 | Long names and addresses |
| S25 | A cancelled order (preview only) |

<a id="readiness"></a>
### 2. What can be tested in this environment

A Demo company often lacks purchase prices, stock, expense codes or some series. Before the test, each scenario is marked:

- **Full**: it can be checked in full.
- **Partial**: it is sent, but part of it can't be checked. It says what and why, for example "No purchase price: the profit check isn't testable".
- **Not possible here**: something is missing. It says how to add it in Softone, for example "No B2B series · Add a series in Softone: Sales → Series".

A missing purchase price or stock never blocks a send. The top of the list shows "X of Y scenarios are fully testable in this environment".

Scenarios with an **expected gap** show today's behaviour until the related work lands. They aren't failures. The gaps are islands at 17%, EU sales, OSS, Mount Athos and rounding.

<a id="summary"></a>
### 3. What we expect

Before you send anything, you see this for each order:

- the document and series
- the customer: an existing code and how it was found, or a new one with its name
- the lines
- the VAT per rate
- the expenses
- the total

The **technical view** shows the JSON that will be sent and the customer card that will be created.

<a id="push"></a>
### 4. Send one at a time to Demo

Each order is sent on its own, with a confirmation that names the company, the environment, the series, the document type and whether a customer will be created. There is no bulk send.

- A double click sends once.
- Sending the same order again **updates the same document**.
- A customer a test created is found again by its VAT number. An existing customer of yours is never changed by a test.
- If Softone's answer doesn't arrive, the order is kept **for review**: check in Softone whether it was created before you send it again.

After sending, you see the document number, the customer code and the series. You also see the **expected vs actual** comparison, with each row marked match, differs or not testable.

:::caution[Demo only]
Test orders are sent **only to the Demo** company. On Live you see the preview only, because a final document on Live gets a MARK from myDATA. If you don't have a Demo company, ask your Softone partner for one.
:::

<a id="final-document"></a>
### 5. The final document in Demo

In Demo, you can issue the final document from Softone. Lynk then finds it and fetches its PDF. You can download it, or have it sent **only to your own e-mail**, through the e-mail account you set up. It is never sent to a marketplace or a customer.

<a id="checklist"></a>
### 6. Check in Softone, and clean up

At the end, the checklist says what to look at in Softone for every order that was sent:

- the document number
- the customer card
- the VAT per line
- the expenses
- the total
- the myDATA status, where there is one

You can print it.

Lynk **never deletes** anything in Softone. In Demo, cancel or delete everything marked:

- **LYNKTEST**, in the order code and the remarks
- **ΔΟΚΙΜΗ – Lynk**, in the customer's name

The checklist also lists the documents and customers the test created.

<a id="credit-notes"></a>
### Credit notes

Lynk doesn't create credit notes. Scenarios S13 and S14 show guidance only: "A credit note is needed — issue it directly in Softone", with the original document and the amount.

<a id="registries"></a>
### VAT number checks with AADE and VIES

The setup wizard has two optional steps, **AADE VAT check** and **VIES check**. When you turn them on, the tests show more:

- The B2B scenarios show the company's details from AADE, and which fields the customer card takes from them.
- The intra-community scenario shows the VIES answer and its consultation number.

The AADE password is stored encrypted and is never shown again.

## What Lynk keeps

Test orders never appear in your orders, analytics, home page or review e-mails. Lynk keeps them for 90 days. Only the account owner can see and send them.

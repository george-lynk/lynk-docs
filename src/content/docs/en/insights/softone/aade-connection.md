---
title: "GSIS (AADE) connection"
description: "AADE's special access codes for the VAT number check: connecting, the test, what an error means, disconnecting."
sidebar:
  order: 7
---

*Describes the new version of the app (Connections → GSIS).*

## What it is

With AADE's **special access codes**, Flows checks the VAT number of an invoice order before sending it to Softone. They are not your Taxisnet credentials.

## Connecting

1. Open **Connections → GSIS (AADE)** and press **Connect**.
2. Fill in **Service user**, **Service password** and **The store's VAT number**.
3. Press **Test and save**. Flows stores the codes encrypted and runs a test lookup of your own VAT number.

If a field is missing or the VAT number fails the check, the message shows under that field and nothing is saved.

## If the test fails

The codes stay saved, and the line under the form gives the likely cause:

| Message | What to do |
|---|---|
| Wrong service user or password. | Check the special codes in AADE's console and enter them again. |
| These special codes aren't this VAT number's. | The store's VAT number must be the one the codes were issued for. |
| AADE's daily limit is reached. | AADE counts lookups per day. Try tomorrow. |
| AADE didn't answer. | The service wasn't available. Try again shortly. |
| Too many tests this hour. | Flows allows a few tests an hour. Try again later. |

## Disconnecting

From the connection's menu, **Disconnect GSIS (AADE)**. Type `DISCONNECT` to confirm.

- The stored codes are deleted, along with the AADE answers kept with them.
- From then on, every VAT number check says "no AADE codes". Invoice orders are sent unchecked and you are alerted.
- What has already happened stays: orders, documents, history.
- To reconnect, enter the codes again.

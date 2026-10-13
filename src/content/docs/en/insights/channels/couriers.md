---
title: "Couriers: ACS and BOX NOW"
description: "Connect your ACS or BOX NOW account to see on each e-shop order whether it was delivered or returned, and whether the cash on delivery was paid out to you."
sidebar:
  order: 6
---

*Describes the new version of the app, coming soon.*

Connect your business's ACS or BOX NOW account to Lynk Insights. Once connected, Lynk will show on each order from your e-shop:

- whether the parcel is on its way, in the locker, delivered to the customer or returned, and when;
- whether the recipient refused the parcel or it wasn't delivered, with the reason the courier gives;
- for cash on delivery: whether it was collected from the customer and whether it was paid out to you.

:::note[Only your e-shop's orders]
Tracking covers your e-shop's orders (Shopify). Skroutz and Shopflix orders aren't tracked: the marketplace itself shows their delivery, and the marketplace pays you their cash on delivery.
:::

## What Lynk reads

Lynk **only reads** from the courier. It never creates, prints or cancels vouchers, and never issues pickup lists.

For each shipment it keeps the voucher number, the status with its times, the store or locker, and the cash-on-delivery amounts. It never keeps the recipient's name, phone, email or address.

## What you need from the courier

### ACS

Ask ACS for access to its web services. ACS gives you:

| Item | What it is |
|---|---|
| API key | The key to ACS's web services |
| Company ID and Company password | Your company's ACS credentials |
| User ID and User password | The credentials of the user Lynk will use |

Ask for the key to have rights on the read calls: shipment tracking (summary and details), cash-on-delivery payouts, pickup lists, and voucher lookup by reference key.

:::tip[If your ACS account has IP locking]
ACS then accepts calls only from listed addresses. Ask Lynk support for Lynk's addresses and give them to ACS to add.
:::

### BOX NOW

Ask BOX NOW support for Partner API keys. BOX NOW gives you:

| Item | What it is |
|---|---|
| Client ID and Client secret | Your account's sign-in credentials |
| API URL | The API address: for testing (stage) or for your live account (production) |
| Partner ID | Only if your account manages more than one partner |

## Connecting

1. From the menu, open **Connections**. In the **Couriers** group, choose **ACS** or **BOX NOW**.
2. Fill in the details the courier gave you. For BOX NOW, under **API address** choose **Testing (stage)** or **Live (production)**, as BOX NOW told you.
3. Press **Save**.
4. Press **Test connection**. Lynk makes one read from the courier, in the background, and shows you the result within a few seconds.

If you change details and press **Test connection** before saving them, the test uses what you typed, without saving it.

Passwords and keys are stored encrypted and are never shown again. Each field in the form only says "saved". To change one, type the new value; fields you leave empty keep the saved value.

Only the account owner sees and changes the connection details.

## If the test fails

The card says **The test failed** with the reason below it, and a reference for support.

| What it says | What to do |
|---|---|
| BOX NOW didn't accept the Client ID or the Client secret | Check them, and that they match the API address (testing or live) |
| BOX NOW has disabled the account | Contact BOX NOW |
| ACS didn't accept the API key, or the account has IP locking | Check the API key; ask ACS whether the account has IP locking |
| ACS answered with an error | Check the company and user credentials; ask ACS for the rights listed above |
| The courier didn't answer in time | Try again in a few minutes |

## On your orders

On every e-shop order with a shipment, under its number, you see:

- the parcel's status: **On its way**, **In the locker**, **Delivered to customer**, **Delayed**, **Refused by recipient**, **Not delivered**, **Being returned** or **Returned**. When the courier gives a reason, it shows next to it, for example "Not delivered: Not at home".
- for cash on delivery: **COD pending**, **Collected**, **Paid out**, or **Not paid out yet** when a payout is late.

In the list's filters, **Shipment** and **Cash on delivery** show only the orders in one state, for example the returned ones or the ones not paid out to you yet.

When you open an order, the **Shipment** section shows the courier, the tracking number (press it to copy it), the cash on delivery with its amount and when it was paid out, and every checkpoint with its time.

## Shipments without an order

Lynk links a shipment to its order on its own when the courier has the order number, or when the tracking number is on the Shopify order. When it isn't sure, it suggests: on the courier's page, in **Shipments without an order**, press **Confirm** for the right order or **Not this one**.

## Notifications

In **Settings** > **Notifications**, in the **Delivery and cash on delivery** group, you choose where you hear about:

- **Parcel not delivered**: refused, not delivered or being returned. It's urgent, so it arrives at once and by email too.
- **Cash on delivery not paid out**: collected but not paid out to you within the business days you set.
- **Shipments without an order**: waiting for you to confirm their order.

## Alert for a late cash-on-delivery payout

On the courier's page, in the **Alert for a late payout** card, set **Business days after collection** to how many business days from collection you want an alert after, if the cash on delivery hasn't been paid out to you (1 to 30, 7 by default).

## Disconnecting

On the courier's page, choose **Disconnect ACS** (or **Disconnect BOX NOW**) from the menu, type the courier's name to confirm and press **Disconnect**. The connection details are deleted at once and tracking stops. The shipment history Lynk already has stays on your orders.

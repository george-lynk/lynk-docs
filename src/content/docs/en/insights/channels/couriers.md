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

The connection comes first. Tracking parcels on your orders arrives in a later version.

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

1. From the menu, open **Connections** and choose **ACS** or **BOX NOW**.
2. Fill in the details the courier gave you and save.
3. Press **Test connection**. Lynk makes one read from the courier and shows you the result within a few seconds.

Passwords and keys are stored encrypted and are never shown again. The form only shows that they are saved. To change one, type the new value; fields you leave empty keep the saved value.

## If the test fails

| Message | What it means | What to do |
|---|---|---|
| Credentials not accepted | BOX NOW didn't accept the Client ID or the Client secret | Check them, and that they match the API URL (stage or production) |
| Account disabled | BOX NOW has disabled the account | Contact BOX NOW |
| Wrong key or address not on the list | ACS didn't accept the API key, or the account has IP locking and Lynk isn't on the list | Check the API key; ask ACS whether the account has IP locking |
| The courier answered with an error | ACS didn't accept the company or user credentials, or the key has no rights on the call | Check the credentials; ask ACS for the rights listed above |
| The courier isn't answering | The courier didn't answer in time | Try again in a few minutes |

## Alert for a late cash-on-delivery payout

On the courier's page you set after how many business days from collection you want an alert if the cash on delivery hasn't been paid out to you (1 to 30, 7 by default).

## Disconnecting

On the courier's page, press **Disconnect** and confirm. The connection details are deleted at once and tracking stops. The shipment history Lynk already has stays on your orders.

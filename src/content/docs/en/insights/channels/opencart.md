---
title: "OpenCart"
description: "Connect your OpenCart store with the Lynk script, so marketplace orders are sent there and its own orders come into Lynk."
sidebar:
  order: 4
---

*Describes the current version of the app.*

In this guide you connect your OpenCart store to Lynk Insights. The connection uses a Lynk file (script) that you upload once to your store's server. Once connected:

- Skroutz and Shopflix orders can be created in OpenCart. See [Order relay](/en/insights/channels/order-relay/).
- orders placed in OpenCart itself can come into Lynk every 5 minutes.

## Before you start

- FTP access, or access to the file manager of the server that hosts OpenCart.
- Your OpenCart database details (host, user, password, database name). You'll find them in OpenCart's `config.php` file or from your hosting provider.

## Step 1: download the script

1. In the menu, open **OpenCart** and the **Setup** tab.

   <!-- TODO screenshot: the Step 1 card with the download button. -->

2. In the **Step 1 — Download the integration script** card, click **Download lynk_integration.php**. The file already contains your account's unique connection password (**Your integration password**).

3. Open the file in a text editor and fill in the database details (`db_host`, `db_user`, `db_pass`, `db_name`).

4. Upload the file to the root folder of OpenCart, where `index.php` is.

:::caution[The file contains passwords]
`lynk_integration.php` contains your Lynk connection password and your database passwords. Don't send it to anyone and don't upload it to a public repository.
:::

## Step 2: connect to the store

1. In the **Step 2 — Connect to your store** card, enter the full address of the file in **Script URL** (for example `https://your-store.gr/lynk_integration.php`).

2. Under **Options**, fill in if needed:
   - **Default order status ID**: the status orders are created with in OpenCart.
   - **Deduct stock on push**: whether OpenCart stock is reduced for every order that is sent.
   - **Skroutz customer group ID** and **Shopflix customer group ID**: the customer group each marketplace's orders go into.

3. Click **Save & connect** and then **Test connection**.

## Step 3: import orders from OpenCart

If you also want to see orders placed in OpenCart in Lynk:

1. In the **Step 3 — Pull orders from OpenCart** card, switch on **Enable order pull**.

2. In **Order statuses to import**, enter the status IDs you want, separated by commas. The defaults are 2 (Processing), 3 (Shipped) and 5 (Complete). You'll find the IDs in OpenCart under **Localisation** > **Order Statuses**.

3. Under **Receipt vs invoice rule**, choose how Lynk decides whether an order goes for a receipt or an invoice. For the **By store ID** and **By customer group** rules, click **Fetch stores** and fill in **Invoice store IDs**, **Receipt store IDs** or **Invoice customer group IDs**. See [Receipt or invoice](/en/insights/softone/receipt-vs-invoice/).

4. Save and click **Pull now** for a first import.

## What you'll see

- The **Overview** tab shows **Connected** and the **Push status** card with **Orders pushed**, **Pending push**, **Orders pulled** and **Failed pushes**.
- The **Push activity** chart shows the pushes of the last 24 hours.
- OpenCart orders appear on the **Orders** page with OpenCart as the channel. **Last pulled** shows when the last import ran.

## If something goes wrong

**Test connection fails**: open the **Script URL** in your browser to make sure the file is in the right place. Check the database details inside the file.

**No orders come in from OpenCart**: check that **Enable order pull** is on and that the orders have one of the statuses in **Order statuses to import**.

**OpenCart orders aren't sent to Softone**: orders placed directly in OpenCart are not sent to Softone. Skroutz and Shopflix orders that Lynk sends to OpenCart are sent as usual.

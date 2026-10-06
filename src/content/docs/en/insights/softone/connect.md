---
title: "Connecting Softone"
description: "Connect Lynk to Softone, in the Demo environment first and then in Live."
sidebar:
  order: 1
---

*Describes the current version of the app.*

In this guide you connect Lynk to Softone ERP. You start with the **Demo** environment (a test installation of Softone), so you can try your settings without touching your real data.

## Before you start

- A Lynk Insights account on the Pro plan. On other plans, **Softone** shows a lock in the menu.
- From your Softone partner: the web services address (URL), a username and password, and if needed the **App ID**, **Company** and **Branch**. Your Softone licence must include the **Web Service Connector** module.
- If possible, a test Softone installation for **Demo**.

## Steps

1. In the menu, open **Softone** and the **Connection** tab.

   <!-- TODO screenshot: the Softone Connection card with Demo selected. -->

2. In the **Softone Connection** card, select **Demo**.

3. Fill in **Softone Service URL**, **Username** and **Password**.

4. If your Softone partner gave you values, open **Advanced settings** and fill in:
   - **App ID**: 2000 for the standard ERP module.
   - **Company**: the numeric ID of the company in Softone (for example 1002).
   - **Branch**: the branch or warehouse ID (for example 1000).

5. Click **Connect Demo**. Lynk tests the connection before it saves the details.

6. Under **Active environment**, make sure **Demo** is selected. This is the environment Lynk sends orders to.

7. Continue with [Channel settings](/en/insights/softone/channel-setup/) and test with a few orders.

8. When your tests succeed, select **Live**, fill in the details of your real installation and click **Connect Live**.

9. :::caution[Real documents in Softone]
   Once the active environment is **Live**, every order that is sent creates an order document in your real Softone. Lynk cannot delete a document; if something is sent by mistake, you correct it in Softone. First check each channel's series and customer codes for Live.
   :::

   Under **Active environment**, click **Live**.

## What you'll see

The **Softone Connection** card shows **Connected** and, in brackets, the active environment (**Live** or **Demo**). You can keep both environments connected and switch the active one under **Active environment**.

## VAT numbers and company details (optional)

On the same tab, the **GSIS Web Service Credentials** card fills in a new company's name, address and tax office (ΔΟΥ) from the AADE registry before Lynk creates the company in Softone. You need the AADE **special web service access codes**, not your Taxisnet sign-in. Fill in **Web service username**, **Web service password** and **Caller ΑΦΜ** (your store's own VAT number) and switch on **Enable automatic VAT enrichment**.

## If something goes wrong

**The message starts with "Softone login failed"**: the URL, username or password is wrong. Check them with your Softone partner.

**The message mentions "Web Service Connector"**: your Softone licence doesn't include the module. Ask your Softone partner to activate it.

**Sending fails with a message that no credentials are configured for the 'live' environment**: you connected only **Demo**, but **Live** is active. Under **Active environment**, select **Demo**.

For more, see [Softone sending errors](/en/insights/troubleshooting/softone-document-errors/).

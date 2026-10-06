---
title: "What's new"
description: "What changed in Lynk Insights in each version, newest first."
---

The changes in Lynk Insights that matter to you, newest first. Each version is split into
**New**, **Improvements** and **Fixes**. Updates apply automatically; you don't need to do
anything unless the note says so.

## Version 1.4.0 · 6 October 2026

### Improvements

- Softone: **Repush** on an order that already has a document now updates that same document
  instead of creating a new one. Nothing is sent when the document belongs to the other
  environment (Demo or Live), when the final document or ΜΑΡΚ has already been issued, or when
  the document changed in the meantime. See
  [Softone order log](/en/insights/softone/document-log/).
- Softone: **Force repush** for two or more selected orders doesn't run for now, until a
  confirmation dialog is added.
  **What you need to do:** send the orders again one at a time from their rows.
- Softone: orders created directly in OpenCart are not sent to Softone.
- Softone: when the same order is already being sent, the new send waits and is retried
  automatically. After 20 minutes it's marked as failed, with an explanation in the order log.

### Fixes

- Softone: the shared retail customer is no longer overwritten with a company's details when
  an order with an invoice is sent.
- Softone: actions in the app (for example fixing a document number, previewing or inspecting
  costs, and manual syncs) no longer occasionally hang, and a sync no longer wrongly shows as already running. If Softone is busy, you see the message
  "Softone is busy right now. Please try again in a minute."
- Softone: switching the active environment (Demo or Live) takes effect immediately.
- Fixed rare, intermittent errors in work that runs in the background, such as sending to
  Softone and syncs.

## Version 1.3.1 · 6 October 2026

### Improvements

- App updates finish faster: after a new release the app is ready in about a minute
  instead of up to half an hour.

## Version 1.3.0 · 5 October 2026

### Improvements

- The waitlist sign-up page is now in Greek.
- The insights.lynk.gr home page now lists only the integrations supported today: Skroutz,
  Shopflix, Shopify, OpenCart and Softone ERP.

## Version 1.2.1 · 5 October 2026

### Fixes

- Skroutz order status updates are no longer lost when many arrive at once, for example
  when the courier picks up your parcels.
- Security update to in-app navigation.

## Version 1.2.0 · 5 October 2026

### New

- New **Secure webhook URL** section in Skroutz settings. Create a private URL for your
  orders and enter it in Skroutz. The card shows when Skroutz starts sending orders to the
  new URL.
  **What you need to do:** follow the [Skroutz](/en/insights/channels/skroutz/) guide.

## Version 1.1.1 · 5 October 2026

No changes that affect how you use the app.

## Version 1.1.0 · 5 October 2026

No changes that affect how you use the app.

## Version 1.0.2 · 5 October 2026

### Improvements

- Your store logo in review emails now loads from a private link, unique to your account.
  The emails look the same as before.

## Version 1.0.1 · 5 October 2026

### Fixes

- In **Settings** > **Data**, the **Delete all product costs** button now says clearly what
  it does. It asks you to type a confirmation before deleting, deleted costs stay deleted,
  and only the account owner can use it.
- Review emails list the order's products again.
- New Shopflix orders no longer show up wrongly as failed syncs.
- Skroutz market intelligence no longer checks the same product twice at the same time.

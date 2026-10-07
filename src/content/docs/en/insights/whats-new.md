---
title: "What's new"
description: "What changed in Lynk Insights in each version, newest first."
---

The changes in Lynk Insights that matter to you, newest first. Each version is split into
**New**, **Improvements** and **Fixes**. Updates apply automatically; you don't need to do
anything unless the note says so.

## Version 1.9.0 · 7 October 2026

### Improvements

- Products: on a product's page, a cost you save with a date applies from that date. A future
  date schedules the change. If you delete a dated cost, your margins go back to the cost that
  applied before.
- Skroutz: your Skroutz API token is no longer shown in **Settings**, but Skroutz stays
  connected. Fill in the field only if you want to set a new token.

### Fixes

- Profit and margin for past periods now use the cost that applied on each day. A cost you set
  later no longer changes older sales, so totals for past periods may differ slightly from
  before.
- Comparisons with the previous period no longer include rejected and expired orders.
- The monthly margin chart now includes Shopify card fees.

### Security

- Only the account owner can now delete data, disconnect Skroutz, Shopflix, Shopify or
  Softone, switch Softone between **Live** and **Demo**, or delete the account.
- API tokens have been reset. If you use the Lynk Chrome extension or your own tool, copy your
  new token once from **Settings** > **API Access**. Each team member now has their own token.
- Your customers' contact details are no longer loaded into the browser with your orders.

## Version 1.7.0 · 7 October 2026

### Improvements

- Softone: **Cancel push** now asks you to confirm and shows how many orders are waiting in
  the queue, because it cancels all of them.

### Fixes

- Softone: excluded orders, and orders whose push you cancelled, are never sent
  automatically. They go only when you send them yourself.
- Softone: when you switch from Demo back to Live, only the orders that were sent to Demo are
  cleared. They aren't sent to Live automatically: check in Softone that they don't already
  have a document, then push the ones you need by hand.

## Version 1.6.0 · 7 October 2026

### Improvements

- Your theme (light or dark), language and hidden menu pages are now saved to your account,
  so they follow you to every device. Each team member has their own settings. After the
  update, we keep the settings from the first device you open the app on.

## Version 1.5.0 · 6 October 2026

### New

- Alerting: a new **Test** button sends a test message to Slack, so you can check your Slack
  Webhook URL. Only the account owner sees it.

### Improvements

- Alerting: only Slack incoming webhook URLs (`https://hooks.slack.com/...`) are accepted.
- Alerting: the **Daily digest** and **Weekly report** options are hidden for now. They will
  come with the new notifications.

### Fixes

- Alerting: your settings now save correctly, and the Slack Webhook URL is no longer cleared
  when you save.

## Version 1.4.2 · 6 October 2026

### Improvements

- **Get Help** at the bottom of the menu now opens a new email to insights@lynk.gr.

### Fixes

- Product costs: your dated cost history is no longer lost when you reload the page. Cost
  changes are saved reliably, because only the products that changed are sent, and large
  catalogs and imports are saved in full.
- Product costs: if your costs can't be loaded or saved, the app now shows a message. If they
  can't be loaded, changes aren't saved until you reload the page. If they can't be saved, we
  try again with your next change.
- Product costs: costs for products with a code (SKU) longer than 128 characters aren't saved,
  and a message tells you so.
- If you use the Skroutz catalog connection for market data and its credentials show as
  missing, an earlier issue may have cleared them.
  **What you need to do:** enter the credentials once more.

## Version 1.4.1 · 6 October 2026

### Fixes

- Softone: in the order log, when a **Push** or **Repush** is refused, a red **Not sent to
  Softone** message now shows the reason (for example, the final document or ΜΑΡΚ has already
  been issued, or the document belongs to the other environment) instead of saying the order
  was re-queued. See [Softone order log](/en/insights/softone/document-log/).
- Softone: orders created directly in OpenCart no longer show a **Push** or **Repush** button in
  the order log. They show **Not for Softone** instead.

## Version 1.4.0 · 6 October 2026

### Improvements

- Softone: **Repush** on an order that already has a document now updates that same document
  instead of creating a new one. Nothing is sent when the document belongs to the other
  environment (Demo or Live), when the final document or ΜΑΡΚ has already been issued, or when
  the document changed in the meantime. See
  [Softone order log](/en/insights/softone/document-log/).
- Softone: **Force repush** for two or more orders that can be re-pushed doesn't run for now, until a
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

---
title: "Document storage"
description: "Lynk takes the final documents' PDFs for Skroutz from a Google Drive or SharePoint folder, instead of Softone."
sidebar:
  order: 1
---

*Describes the new version of the app.*

<span id="overview"></span>

If your accountant keeps the final documents' PDFs in a shared folder, Lynk can take them from there instead of asking Softone, and deliver them to your Skroutz orders. In this guide you connect the folder, test it and, when you no longer need it, disconnect it.

The connection is **read only**: Lynk never writes or deletes anything in the folder.

## Before you start

- A Lynk Insights account with the **Owner** role. Team members don't see or change this connection.
- A folder with **one subfolder per final document**, named after its number, holding the PDF with the same name. For example, the subfolder `ΤΔΑ0000001` holds `ΤΔΑ0000001.pdf`.
- For **Google Drive**: the folder shared with "anyone with the link", and a Google API key with the Google Drive API on.
- For **SharePoint**: an app in Microsoft Entra (Azure) with read access to files, and its details: Tenant ID, Client ID and client secret.

<span id="provider"></span>

## Connecting the folder

1. Open **Connections** and choose **Document storage**. The same card is in the **Final documents** step of the first setup.
2. Choose **Google Drive** or **SharePoint**.
3. <span id="folder"></span>Fill in the folder:
   - **Google Drive**: in **Folder link or ID** paste the folder's link from the address bar, and your key in **Google API key**.
   - **SharePoint**: the site's address in **Site URL** (it starts with `https://`), the path inside the document library in **Folder** (empty for the root), and the **Tenant ID**, **Client ID** and **Client secret**.
4. Press **Save**.

The keys are never shown again. When a key is saved, its field says "Saved". Leave it empty to keep it, or type a new one to change it.

<span id="test"></span>

## Testing

Press **Test**. Lynk reads the folder with the details you saved, writing nothing. The test runs in the background: within a few seconds you see "The folder can be read" and how many items it holds, or the reason it failed.

## What you'll see

In **Connections**, the **Document storage** card shows it is working, with the provider. From the next check, the PDFs of new final documents for Skroutz come from your folder.

## Disconnecting

Press **Disconnect** and confirm. The details you saved are deleted and the PDFs come from Softone again.

## If something goes wrong

| Message | What to do |
|---|---|
| "The folder wasn't found" | Check the folder's link or path. |
| "No access" | Check the API key, and that the folder is shared. |
| "Microsoft refused the app's details" | Check the Tenant ID, Client ID and client secret. An expired secret needs a new one. |
| "The link points to a file, not a folder" | Paste the folder's link, not a file's. |
| "Details are missing" | A provider is chosen without all its details, so the PDFs aren't found. Fill them in or press **Disconnect**. |

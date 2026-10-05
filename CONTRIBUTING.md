# Contributing to the Lynk docs

This repository is the public documentation hub for all Lynk products,
published at <https://docs.lynk.gr>. It is built with
[Starlight](https://starlight.astro.build) (Astro).

## Public content only

**Everything in this repository is public**, including the git history, issues
and pull requests. Never add:

- internal API references, architecture notes, runbooks or deployment details;
- secrets, API keys, tokens or passwords, even expired ones;
- customer data: names, emails, phone numbers, addresses, ΑΦΜ, order numbers;
- internal URLs. The only app URL that may appear is <https://insights.lynk.gr>.

Write for store owners using the app, not for the people building it. If a
detail only matters to Lynk staff, it does not belong here.

## Local setup

Node 22 (see `.nvmrc`).

```sh
npm ci
npm run dev      # http://localhost:4321, drafts are visible
npm run build    # production build: drafts excluded, links validated
npm run preview  # serve the production build
```

## Where pages live

```
src/content/docs/
├── index.mdx                 Greek home page (/)
├── insights/                 Lynk Insights topic, Greek (/insights/)
│   ├── index.mdx
│   └── <section>/index.md    one folder per sidebar section
├── account/                  Account topic, Greek (/account/)
└── en/                       English mirror of everything above (/en/...)
templates/                    page templates, never built
```

Greek is the root locale and has no URL prefix. English lives under `en/` with
**the same file names**, so the language switcher links each page to its
translation.

New pages in an existing section folder appear in the sidebar automatically.
Set `sidebar.order` in the frontmatter to control their position.

Unfinished articles carry `draft: true`. Drafts show in `npm run dev` but are
left out of the production build. Do not link to a draft from a published page:
the link checker fails the build because the target does not exist in
production.

## Writing standards

### Language

- **Greek is the source.** Write the Greek page first, then update the English
  page **in the same PR**. A PR that changes only one language is not merged.
- **Formal plural** in Greek: «Ανοίξτε», «Επιλέξτε», «μπορείτε». Never the
  singular «άνοιξε».
- **Sentence case** for titles and headings, in both languages:
  «Σύνδεση του Skroutz», "Connecting Skroutz". Not "Connecting Skroutz To Your Account".
- **UI labels in bold, exactly as they appear in the app**, including
  capitalisation: **Ρυθμίσεις** > **Κανάλια**. In the English page use the label
  the English UI shows.
- Euro amounts: Greek pages `1.234,56 €`, English pages `€1,234.56`.

### Terminology

Use these terms consistently. Do not invent synonyms.

| Use | Meaning | English page |
|---|---|---|
| παραστατικό | Any fiscal document issued from the ERP | document |
| απόδειξη | Retail receipt (B2C) | receipt |
| τιμολόγιο | Invoice to a business (B2B) | invoice |
| σειρά | Document series in the ERP | series |
| ΑΦΜ | Greek tax number | VAT number (ΑΦΜ) |
| ΔΟΥ | Tax office | tax office (ΔΟΥ) |

Avoid:

| Avoid | Use instead |
|---|---|
| badge | ένδειξη / label |
| payload | δεδομένα / data |
| ωθήστε, push (as a verb to readers) | στείλτε, συγχρονίστε |
| Developer jargon in general | The words the store owner sees in the app |

### Fiscal documents

Any step that creates a fiscal document in the ERP (receipt, invoice, credit
note) **must** start with a caution callout. See `templates/how-to.mdx` for the
exact pattern and wording.

### Page types

Pick one template from `templates/` per page. Do not mix types on one page.

| Type | Template | Rule of thumb |
|---|---|---|
| How-to | `how-to.mdx` | Goal, prerequisites, numbered steps with screenshots, "you should see", troubleshooting |
| Concept | `concept.mdx` | What, why, how, and a worked example in euros |
| Reference | `reference.mdx` | Tables only |
| Troubleshooting | `troubleshooting.mdx` | Exact error text, cause, fix |

### Screenshots

- Taken from the **demo account only**, never from a customer account.
- Browser window **1440px** wide, light theme.
- **Blur all personal data** (names, emails, phones, addresses, ΑΦΜ, order
  numbers, API keys) before committing. Check twice; the git history is public
  forever.
- Save as PNG under `src/assets/screenshots/<product>/` and reference them with
  a relative import so Astro optimises them. Every image needs alt text in the
  page's language.

## Adding a product topic

Each Lynk product is one sidebar topic (plugin
[`starlight-sidebar-topics`](https://starlight-sidebar-topics.netlify.app/)).
To add a new product, for example "Lynk Stock" at `/stock/`:

1. Create `src/content/docs/stock/index.md` (Greek) and
   `src/content/docs/en/stock/index.md` (English). Use the same section-folder
   pattern as `insights/` if the product needs more than a few pages.
2. In `astro.config.mjs`, add a topic to the `starlightSidebarTopics([...])`
   array:

   ```js
   {
   	id: 'stock',
   	label: { el: 'Lynk Stock', en: 'Lynk Stock' },
   	link: '/stock/',
   	icon: 'puzzle', // any Starlight built-in icon name
   	items: [
   		{ slug: 'stock', label: 'Επισκόπηση', translations: { en: 'Overview' } },
   		section('Ξεκινώντας', 'Getting started', 'stock/getting-started'),
   	],
   },
   ```

   The topic `link` is written without the locale; the plugin adds `/en/` for
   English pages.
3. Add a `<LinkCard>` for the product to both home pages,
   `src/content/docs/index.mdx` and `src/content/docs/en/index.mdx`.
4. Run `npm run build`.

Every page must belong to a topic. A page in a folder that no topic lists makes
the build fail with `Failed to find the topic for the ... page`. When you add a
new section folder, add it to the topic's `items` as well.

## Pull request process

1. **Issue first.** Open or pick an issue describing the page(s) to write or fix.
2. **Branch and PR.** Branch from `main`, commit with
   [Conventional Commits](https://www.conventionalcommits.org/) (`docs(insights): …`),
   open a PR that says `Closes #<issue>` and fill in the checklist.
3. **CI.** The `CI` workflow runs `npm ci` and `npm run build`. The build fails
   on any broken internal link or missing anchor, and on links that jump to the
   other language by mistake.
4. **Merge publishes.** Every merge to `main` builds the site and deploys it to
   GitHub Pages at <https://docs.lynk.gr> within a few minutes. There is no
   separate release step.

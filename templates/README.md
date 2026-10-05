# Page templates

Copy a template into `src/content/docs/<product>/<section>/` (Greek) and the
same path under `src/content/docs/en/` (English), then replace every
placeholder. This folder is outside the content collection, so nothing here is
ever built or published.

| Template | Use it for | Shape |
|---|---|---|
| `how-to.mdx` | Doing one task in the app | Goal, prerequisites, numbered steps with screenshots, "you should see", troubleshooting |
| `concept.mdx` | Explaining how something works | What, why, how, worked example in euros |
| `reference.mdx` | Lists of fields, settings, statuses | Tables only |
| `troubleshooting.mdx` | One error message | Exact error text, cause, fix |

Rules that apply to every template are in [CONTRIBUTING.md](../CONTRIBUTING.md).
Remove all `{/* ... */}` guidance comments before opening the PR.

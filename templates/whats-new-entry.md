<!--
WHAT'S NEW ENTRY: one per released version. Not a page: paste the Greek block at the top
of src/content/docs/<product>/whats-new.md (just under the intro) and the English block at
the top of src/content/docs/en/<product>/whats-new.md. Newest first.

Rules (see CONTRIBUTING.md, "What's new"):
- Source: the "Release note" lines of the product PRs merged since the last release.
- Only what users notice. Leave out every "none — internal" item: CI, refactors, tests,
  dependencies, infrastructure, engineering docs.
- User language: what changed for the store owner, not how it was built. No file names,
  endpoints, issue numbers or jargon. Greek in the formal plural, sentence case, UI labels
  in bold exactly as the app shows them.
- Security fixes in user terms only ("your webhook address is now private"). Never describe
  the vulnerability, how it could be used, or what was exposed.
- Say when the user must do something, and what.
- Sections in this order, omit any that are empty: Νέα / New, Βελτιώσεις / Improvements,
  Διορθώσεις / Fixes. A hotfix may be a single line. A release with nothing user-facing
  gets the "no changes" line instead of sections.
- Heading: version without the "v", then the release date. Greek pages write the date
  as dd/mm/yyyy (05/10/2026); English pages write it as "5 October 2026".
  Remove this comment before committing.
-->

<!-- ===== Greek: src/content/docs/<product>/whats-new.md ===== -->

## Έκδοση X.Y.Z · ΗΗ/ΜΜ/ΕΕΕΕ

### Νέα

- Τι μπορείτε να κάνετε τώρα και πού στην εφαρμογή (**Ρυθμίσεις** > **…**).

### Βελτιώσεις

- Τι λειτουργεί καλύτερα ή πιο καθαρά για εσάς.

### Διορθώσεις

- Τι δεν λειτουργούσε σωστά και λειτουργεί πλέον.

<!-- Nothing user-facing in this release:

Δεν υπάρχουν αλλαγές που να επηρεάζουν τη χρήση της εφαρμογής.
-->

<!-- ===== English: src/content/docs/en/<product>/whats-new.md ===== -->

## Version X.Y.Z · D Month YYYY

### New

- What you can do now and where in the app (**Settings** > **…**).

### Improvements

- What works better or more clearly for you.

### Fixes

- What didn't work correctly and now does.

<!-- Nothing user-facing in this release:

No changes that affect how you use the app.
-->

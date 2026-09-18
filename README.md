# Moshi documentation source reference

This repository does not publish `docs.moshi.ai`.
Mintlify uses [`moshi-labs/moshi-workspace/external-docs`](https://github.com/moshi-labs/moshi-workspace/tree/master/external-docs).
The connected branch is `master`.
The Mintlify Git settings confirm this connection on September 18, 2026.

## Edit and publish Moshi docs

1. Create a branch from `master` in `moshi-labs/moshi-workspace`.
2. Edit the page under `external-docs/`.
3. Add new pages to `external-docs/docs.json` navigation.
4. Run the checks from `external-docs`.
5. Open and merge a pull request after review and validation.
6. Check the Mintlify deployment result.
7. Open the changed page on `docs.moshi.ai` and confirm the new text.

```bash
npx mint validate
npx mint broken-links --check-anchors
```

Use `npx mint dev` from `external-docs` for a local preview.
GitHub stores the source; Mintlify controls deployment and site access.
A merged pull request alone does not confirm publication.

## Files in this repository

`integrations/shopify.mdx` contains the Shopify guide prepared here before verification of the publishing source.
The published guide belongs in `moshi-workspace/external-docs/integrations/shopify.mdx`.
Make future changes there to prevent copies from differing.

`index.mdx`, `quickstart.mdx`, and `docs.json` contain starter content or settings.
Do not connect this repository to the live site without a separate content migration.

## Maintain the Shopify guide

Verify behavior against `moshi-labs/moshi-api` and `moshi-labs/moshi-frontend`.
Check the sync schedule, product availability rules, and flow picker behavior.
The documented 100-product picker limit describes a current bug.
Update that section when the fix reaches production.
Exclude merchant data, credentials, and private product identifiers.

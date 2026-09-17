# Moshi documentation

This repository contains the Mintlify source for `docs.moshi.ai`.
Make documentation changes here and commit them to GitHub.
The site configuration is `docs.json` at the repository root.
The default branch is `master`.

## Pages and files

| Path | Purpose |
| --- | --- |
| `integrations/shopify.mdx` | Shopify connection steps, permissions, sync timing, product visibility, and troubleshooting. |
| `index.mdx` | Introduction page. This page still contains starter content. |
| `quickstart.mdx` | Quickstart page. This page still contains starter content. |
| `docs.json` | Site navigation, branding, and links. The branding still contains starter settings. |
| `.mintignore` | Files that Mintlify excludes from the site. |
| `AGENTS.md` | Instructions for agents that edit this repository. |

## Edit documentation

1. Create a branch from the latest `master`.
2. Edit the relevant `.mdx` page.
3. Add new pages to `docs.json` navigation without the `.mdx` extension.
4. Run the checks below and review the diff.
5. Push the branch and open a pull request against `master`.
6. Merge the pull request after review and validation.

Include `title`, `description`, and `keywords` in each new page's YAML frontmatter.
Use root-relative paths for internal links, such as `/integrations/shopify`.
Keep merchant instructions separate from internal investigation records.
Exclude merchant data, credentials, and private product identifiers.

## Preview and validate

Install Node.js and npm, then run these commands from the repository root:

```bash
npx mint dev
```

Open the local URL printed by Mintlify to preview the site.

Before merging, validate the site and its internal links:

```bash
npx mint validate
npx mint broken-links
```

## Publish to docs.moshi.ai

Mintlify's GitHub connection must use these settings:

| Setting | Value |
| --- | --- |
| Repository | `moshi-labs/docs` |
| Production branch | `master` |
| Documentation directory | Repository root (`/`) |
| Custom domain | `docs.moshi.ai` |

With this connection enabled, a push or merge to `master` starts a Mintlify deployment.
A commit on a feature branch does not update the production site.

After merging, check the Mintlify deployment result and open the changed page on `docs.moshi.ai`.
If the page does not update, check the repository, branch, and directory settings in the Mintlify dashboard.
Also check the deployment log for build errors.
GitHub stores the source; Mintlify controls deployment and site access.

## Maintain the Shopify page

Verify product behavior against `moshi-labs/moshi-api` and `moshi-labs/moshi-frontend` before changing the Shopify page.
Check the sync schedule, product availability rules, and flow picker behavior.
The documented 100-product picker limit describes a current bug.
Update that section when the fix reaches production.

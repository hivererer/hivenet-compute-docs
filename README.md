# Compute with Hivenet docs

This repository contains the documentation for Compute with Hivenet, including guide pages, tutorials, changelog entries, and public API reference pages.

Use this repo when you need to update the public documentation site, preview docs locally, or review changes before publishing.

## What’s in this repo

```text
.
├── documentation/        # Main guide and concept pages
├── tutorials/            # Step-by-step tutorials
├── public-api/           # Public API guide pages
├── public-api/endpoints/ # Individual API endpoint reference pages
├── snippets/             # Reusable MDX snippets
├── images/               # Documentation images
├── logo/                 # Logo assets used by the docs
├── changelog.mdx         # Public changelog
├── quickstart.mdx        # Main quickstart page
├── about-hivenet.mdx     # About Hivenet page
├── docs.json             # Mintlify navigation and site config
└── public-v1.yaml        # OpenAPI source file
```

## Public API docs structure

The public API docs use this structure:

```text
public-api/
├── overview.mdx
├── authentication.mdx
├── errors.mdx
├── examples.mdx
└── endpoints/
    ├── list-instances.mdx
    ├── get-instance.mdx
    ├── start-instance.mdx
    ├── terminate-instance.mdx
    └── get-instance-logs.mdx
```

Keep endpoint reference pages inside `public-api/endpoints/`. Guide pages and explanations should stay in `public-api/`.

## Run the docs locally

Install the Mintlify CLI:

```text
npm i -g mint
```

From the root of the repo, run:

```text
mint dev
```

The command must be run from the folder that contains `docs.json`.

## Before editing

Before you make changes:

- Check whether the page already exists.
- Check `docs.json` if you add, move, or rename a page.
- Keep file names short, lowercase, and descriptive.
- Use `.mdx` for documentation pages.
- Put reusable blocks in `snippets/` instead of copying the same content across pages.
- Compress images before adding them to `images/`.

## Writing rules

Use plain, direct English. The docs should help users complete real tasks without making the product sound more complex than it is.

Follow these rules:

- Use sentence case for titles and headings.
- Use “Compute with Hivenet” when referring to the product action.
- Use “Compute” only when the context is already clear.
- Keep instructions action-first.
- Explain technical terms the first time they matter.
- Avoid hype, vague claims, and marketing language.
- Don’t promise roadmap items unless they’re confirmed for public docs.
- Don’t duplicate long explanations across pages. Link to the canonical page instead.

## Mintlify components

Use Mintlify components when they make the page easier to scan.

Good uses:

- `Tip` for practical advice.
- `Warning` for risks, limits, or destructive actions.
- `Info` for context.
- `Steps` for setup flows.
- `Tabs` for alternative commands or environments.
- `CodeGroup` for related code examples.
- `Accordion` for secondary details.

Don’t overuse components. A simple paragraph is often better.

## Common tasks

### Add a new page

1. Create the `.mdx` file in the right folder.
2. Add the page to `docs.json`.
3. Run `mint dev`.
4. Check the page in the local preview.
5. Open a pull request.

### Rename or move a page

1. Rename or move the file.
2. Update `docs.json`.
3. Search the repo for old links.
4. Update any broken links.
5. Run `mint dev`.

### Update an API endpoint page

1. Check the matching endpoint in `public-v1.yaml`.
2. Update the endpoint page in `public-api/endpoints/`.
3. Keep examples consistent with the OpenAPI file.
4. Run the local preview and check formatting.

### Add an image

1. Add the image to `images/`.
2. Use a clear file name.
3. Keep the file size small.
4. Add useful alt text where the image appears.

## Review checklist

Before merging, check that:

- The page appears in the correct navigation section.
- Links work.
- Code examples are formatted correctly.
- Warnings are used for destructive or irreversible actions.
- Product names and labels match the current UI.
- The page doesn’t duplicate content that should live elsewhere.
- The local preview runs without errors.

## Publishing

Changes are published through the Mintlify GitHub integration after they are pushed to the default branch.

For most changes, use a pull request so content and technical details can be reviewed before publishing.

## Troubleshooting

If the local preview doesn’t start, run:

```text
mint update
```

If a page loads as a 404, check that:

- You are running `mint dev` from the folder that contains `docs.json`.
- The page is listed correctly in `docs.json`.
- The file path and file name match the navigation entry.
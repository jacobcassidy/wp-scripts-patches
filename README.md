# wp-scripts-patches README

This repo provides patches for the `@wordpress/scripts` node module to support modern formatting and linting file types in WordPress development.

Currently, `@wordpress/scripts` does not support the latest stable version of ESLint (e.g. 9.X.X). Which is necessary to use the modern file types such as `eslint.config.mjs`.

Patches are based on the unmerged Gutenberg PR: [Upgrade ESLint to v9](https://github.com/WordPress/gutenberg/pull/65648).

## Developer Notes

Creating a patch:

1. Run patch-package to create a .patch file:
    - `npx patch-package @wordpress/eslint-plugin`
    - `npx patch-package @wordpress/scripts`

> [!NOTE]
> Modern config files for WordPress development (e.g., `eslint.config.mjs`) are available in the [wp-dev-config-file](https://github.com/jacobcassidy/wp-dev-config-files) repo.
>
> The [ddev-wp-setup-script](https://github.com/jacobcassidy/ddev-wp-setup-script), used for creating quick local development servers, also uses these patches by default.

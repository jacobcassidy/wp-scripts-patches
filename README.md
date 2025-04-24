# `wp-scripts-patches` Readme

## Overview

This repository provides patches for the [`@wordpress/scripts`](https://www.npmjs.com/package/@wordpress/scripts) package to support modern formatting and linting file types for WordPress development.

Why use the patches? Because the `@wordpress/scripts` package does not support the latest stable version of ESLint (e.g. 9.X.X). Which is necessary to use the modern file types such as `eslint.config.mjs`.

Patches are based on the unmerged Gutenberg PR: [Upgrade ESLint to v9](https://github.com/WordPress/gutenberg/pull/65648).

> [!NOTE]
> Formatting and linting configuration files for WordPress development (e.g., `eslint.config.mjs`) are available in the [wp-dev-config-file](https://github.com/jacobcassidy/wp-dev-config-files) repository.
>
> For quickly setting up a local WP development server, the [ddev-wp-setup-script](https://github.com/jacobcassidy/ddev-wp-setup-script) package is available, which uses these patches by default.

## Patched Files

### Added Files

-   `@wordpress/`

    -   `eslint-plugin/`

        -   `configs/`
            -   `flat/`
                -   `custom.js`
                -   `es5.js`
                -   `esnext.js`
                -   `i18n.js`
                -   `index.js`
                -   `jsdoc.js`
                -   `jshint.js`
                -   `jsx-a11y.js`
                -   `react.js`
                -   `recommended-with-formatting.js`
                -   `recommended.js`
                -   `test-e2e.js`
                -   `test-playwright.js`
                -   `test-unit.js`
        -   `plugin.js`
        -   `tsconfig.json`

    -   `scripts/`
        -   `config/`
            -   `eslint.config.js`

### Modified Files

-   `@wordpress/`

    -   `eslint-plugin/`

        -   `rules/`
            -   `data-no-store-string-literals.js`
            -   `i18n-translator-comments.js`
            -   `no-unused-vars-before-return.js`
            -   `no-wp-process-env.js`
            -   `react-no-unsafe-timeout.js`
            -   `wp-global-usage.js`
        -   `utils/`
            -   `constants.js`
        -   `index.js`

    -   `scripts/`

        -   `config/`
            -   `webpack.config.js`
        -   `scripts/`
            -   `lint-js.js`
            -   `lint-style.js`
        -   `utils/`
            -   `config.js`
            -   `index.js`

### Removed Files

-   `@wordpress/`

    -   `scripts/`

        -   `config/`
            -   `.eslintignore`
            -   `.eslintrc.js`

## Developer Notes

### Creating a patch

-   Run _patch-package_ to create a `*.patch` file:
    -   `npx patch-package @wordpress/eslint-plugin`
    -   `npx patch-package @wordpress/scripts`

## Found an Issue?

If you come across any issues, please report them [here](https://github.com/jacobcassidy/wp-scripts-patches/issues).

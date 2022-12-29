# IndustrialEngineer-PresentationWeb

## Technologies
- Svelte
- NodeJS 16.0
- Storybook

## Tutorial to setup storybook
- https://storybook.js.org/tutorials/intro-to-storybook/svelte/en/get-started/

## Requirements
- installed Svelte Plugin
- NodeJS version 16 (for now in newer versions storybook doesn't work)

## Setup
1. run ***"npx degit chromaui/intro-storybook-svelte-template taskbox"*** to install svelte storybook to the project
2. run ***"cd taskbox"*** to move to storybook installation directory
3. run ***"yarn"*** command to install packages
4. run ***"yarn dev"*** command to run svelte app
5. run ***"yarn storybook"*** command to run storybook

### Solvation of nodejs problem
- code: 'ERR_OSSL_EVP_UNSUPPORTED'
- https://stackoverflow.com/questions/74548318/how-to-resolve-error-error0308010cdigital-envelope-routinesunsupported-no

### Remove paddings from storybook
- https://storybook.js.org/addons/storybook-addon-paddings

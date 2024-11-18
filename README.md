## Tech Stack

- Web Framework: SvelteKit
- CSS / Styling
  - Framework: TailwindCSS
  - Component library: DaisyUI
- Suggested Hosting Stack
  - Host + CDN: Cloudflare Pages
  - Serverless compute: Cloudflare Workers
  - Authentication: Supabase Auth
  - Database: Supabase Postgres
- Payments
  - Stripe Checkout
  - Stripe Portal


## Performance / Best Practices

The selected tech stack creates lightning fast websites.

- Pre-rendering (static generation) for marketing pages, pricing and blog
- Instant navigation: the best of CSR + SSR in one. SSR your first page for fastest possible initial load times. For subsequent pages, the content is pre-loaded and rendered with CSR, for instant rendering.
- CDN optimized, for high edge-cache hit ratios
- Edge-functions for dynamic APIs/pages
- Svelte and Tailwind compile out unused HTML, CSS and JS at deploy time for smaller pages
- Linting to find accessibility and syntax issues

The result is a perfect Google PageSpeed Insights score in all categories!

<img width="420" alt="Screenshot 2024-01-18 at 11 31 32 AM" src="https://github.com/CriticalMoments/CMSaasStarter/assets/848343/46b5e960-2aa0-4fb5-acd7-4f84b380e1d0">

# Quick Start

## Create a Copy of the Template

To get started, create your own copy of the project for development. There are two options:

- "Use this template": use this Github button if you want to build your own project using CMSaasStarter as a starter template and you aren't planning on contributing work back to the public open source project. See [Github Docs](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template).
- "Fork": use this button if you want contribute some or all of your work back to the public open source project. It will keep the full commit history, and be easier to create PRs back to CMSaasStarter.

## Setup Local Development

On your development machine:

```
git pull [Your Repo Created Above]
cd kreativechat ## or your repo name if different
npm install
## Create an env file. You'll replace the values in this in later steps.
cp local_env_template .env.local
## Run the project locally in dev mode, and launch the browser
npm run dev -- --open
```

**Note:** some features won't work until you complete the rest of the setup steps below!

## Developer Tools

The repo includes [CI scripts](https://aws.amazon.com/devops/continuous-integration/) designed for [GitHub Actions](https://github.com/features/actions). These confirm you don’t break your [build](https://github.com/CriticalMoments/CMSaasStarter/blob/main/.github/workflows/build.yml), you use [proper code formatting](https://github.com/CriticalMoments/CMSaasStarter/blob/main/.github/workflows/format.yml), [code linting and typechecking passes](https://github.com/CriticalMoments/CMSaasStarter/blob/main/.github/workflows/linting.yml), and even spell checking.

### Enabling GitHub Actions

Github disables CI on new forks by default, so be sure to go into the Github Actions page for your repo and enable workflows.

### Running Developer Tools Locally

To manually run all these tools run the following script. You can view it's contents for individual commands.

```
# first time only: chmod +x ./check.sh
./check.sh
```

### Running Developer Tools in your IDE

Installing extensions in your editor can automatically format-on-save, show linting/type issues inline, and run your test cases:

- Svelte for Svelte and accessibility issues: [VSCode](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode) or [other editors](https://sveltesociety.dev/tools#editor-support)
- ESLint for type checking and linting: [VSCode](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) and [other editors](https://eslint.org/docs/latest/use/integrations)
- Vitest for testing if you add tests: [VSCode](https://marketplace.visualstudio.com/items?itemName=vitest.explorer) or [other editors](https://vitest.dev/guide/ide)

### Running Developer Tools from Git Hooks

To catch build, formatting, linting and test issues before you commit changes, we suggest the following local git hook. It will run before you commit, stop you from breaking the build, and show any issues that are found. Add the lines below to an executable git hook script at the location `.git/hooks/pre-commit`.

```
#!/bin/sh
# Run standard checks before committing
cd "$(dirname "$0")"
sh ../../checks.sh
```

### Disabling Developer Tools

If you find build, formatting or linting rules too tedious, you can disable enforcement by deleting the CI files (`.github/workflows/*`) and removing the git hook (`.git/hooks/pre-commit`).

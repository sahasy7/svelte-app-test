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
  - backend services - node.js
- Payments
  - Stripe Checkout
  - Stripe Portal


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

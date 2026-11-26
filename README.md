# ADEZ NEXUS HOSTING

ADEZ NEXUS HOSTING is a Node.js hosting platform for managing user accounts, hosted projects, deployments, storage, billing, and custom subdomains. The repository includes the Express application, static frontend, runtime/hosting worker, database helpers, and deployment configuration.

## Requirements

- Node.js 18 or newer
- npm, pnpm, or another compatible package manager
- MongoDB or the database configuration supported by `db.js`
- A persistent storage location for production data

## Getting started

```bash
npm install
cp .env.example .env
npm start
```

The server listens on port `3000` by default. Set `PORT` to use another port. The application requires `JWT_SECRET` and will refuse to start if it is missing.

Open `http://localhost:3000` after the server starts.

## Configuration

Review `.env.example` before running the application. Common settings include:

- `PORT` — HTTP port; defaults to `3000`.
- `BASE_URL` — public URL used for callbacks and links.
- `BASE_DOMAIN` — domain used for hosted project subdomains.
- `JWT_SECRET` — required secret for signing authentication tokens.
- `ADMIN_PASSWORD` — optional administrator password; set this explicitly in production.
- `PAYSTACK_SECRET_KEY` — Paystack payment integration secret.
- `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` — optional GitHub OAuth credentials.
- `BREVO_API_KEY` or SMTP/Gmail variables — email verification delivery.
- `CORS_ORIGINS` — comma-separated allowed browser origins when using a separate frontend.
- `MAX_PROJECTS` — maximum projects per user; defaults to `10`.

Never commit `.env`, production secrets, tokens, private keys, or database credentials.

## Project structure

```text
server.js             Express application entry point
engine.js             Hosting and application engine logic
db.js                 Database initialization and persistence helpers
runner.js             Runtime/deployment runner
cf.js                 Cloudflare-related helpers
public/               Static frontend assets
worker/               Worker deployment configuration
```

## Production notes

Use a process manager or container platform that keeps the Node.js process running and provides persistent storage. Set a strong, unique `JWT_SECRET`, configure `BASE_URL` and `BASE_DOMAIN`, and provide the required database, email, payment, OAuth, and storage credentials through the platform's secret manager.

The worker configuration in `worker/wrangler.toml` is prepared for Cloudflare Workers and R2. Update the domain, bucket, and account-specific settings before deploying it to your own Cloudflare account.

## License

No license is currently declared for this project. Add a `LICENSE` file before distributing the code publicly if you want to grant reuse rights.

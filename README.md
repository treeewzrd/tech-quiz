# Tech Quiz

![Status](https://img.shields.io/badge/status-coursework-blue)

Coursework quiz application with Cypress component and end-to-end test files.

**Built with:** React, TypeScript, Express, MongoDB, Cypress.

## Run locally

Requires Node.js/npm and a disposable MongoDB database. From the repository root:

```bash
npm install
```

Create a private `server/.env` with `MONGODB_URI` pointing to the exercise database. Build and seed before starting:

```bash
npm run build
npm run seed
```

**Seeding clears the question collection before inserting sample questions.** Use a disposable database.

The checked-in development configuration requests port 3001 for both Vite and the API. Run them separately to avoid that conflict:

```bash
# Terminal 1: API on port 3001
npm run server
```

```bash
# Terminal 2: frontend on port 5173
npm run dev --prefix client -- --port 5173 --strictPort
```

Open the frontend at `http://localhost:5173`.

## Tests

Cypress's end-to-end base URL is currently `http://localhost:3001`, while the frontend setup above uses port 5173. With both servers running:

```bash
npm test -- --config baseUrl=http://localhost:5173
npx cypress run --component
```

`npm test` runs end-to-end tests; component tests use the separate command above. No passing-test badge is claimed.

Setup instructions were checked against source; builds and application behavior have not been rerun during this cleanup.

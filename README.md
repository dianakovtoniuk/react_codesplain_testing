# Codesplain Testing

A React and Express app for browsing GitHub repositories and reading their code in an in-browser editor, with a focus on testing the frontend.

## Stack

- React 18, React Router, SWR
- Tailwind CSS
- Monaco Editor
- Express, Prisma, SQLite
- Jest and React Testing Library
- Mock Service Worker (msw)

## Getting started

    npm install
    npm start

This starts the Express server on port 8000 and the React dev server. API requests from the client are proxied to the server.

## Tests

    npm test

To run the tests with a debugger attached:

    npm run test:debug

### What is covered

- RepositoriesSummary: renders language, stars, forks and open issues
- RepositoriesListItem: GitHub link, language icon, link to the code editor
- HomeRoute: two repository links per language, with the API mocked by msw
- AuthButtons: sign in, sign up and sign out links depending on whether a user is signed in

API calls in tests are mocked with a small helper in src/test/server.js. It starts an msw server before the tests, resets handlers after each test and closes the server at the end.

## Project structure

- server/: Express API, auth, Prisma schema
- src/components/: UI components
- src/hooks/: data fetching and auth hooks
- src/routes/: page-level components
- src/test/: test helpers

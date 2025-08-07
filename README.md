# Microfrontend Example

This project demonstrates a basic microfrontend architecture using [Webpack Module Federation](https://webpack.js.org/concepts/module-federation/) with two apps: **host** and **dashboard**.

## Structure

```
packages/
  host/        # Main container app
  dashboard/   # Remote dashboard app
```

## Prerequisites

- Node.js >= 14
- npm

## Install Dependencies

From the root directory, run:

```sh
npm install
cd packages/host && npm install
cd ../dashboard && npm install
```

## Running the Apps

Open two terminals:

**Terminal 1: Start dashboard**
```sh
cd packages/dashboard
npm start
```

**Terminal 2: Start host**
```sh
cd packages/host
npm start
```

- Host runs on [http://localhost:3000](http://localhost:3000)
- Dashboard runs on [http://localhost:3001](http://localhost:3001)

## How It Works

- The host app loads the dashboard app remotely using Module Federation.
- The dashboard exposes its main component via `remoteEntry.js`.
- The host imports `dashboard/Dashboard` and can render it.

## Useful Scripts

- `npm start` – Start development server
- `npm run build` – Build for production

## Customization

Edit the React components in:
- packages/host/src/App.js
- packages/dashboard/src/App.js

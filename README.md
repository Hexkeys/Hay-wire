# Needle in the Haystack

A small, original browser-based hidden-object game inspired by the general needle-in-a-haystack concept.

## Run locally

Requires Node.js 20 or newer.

1. Clone or download this repository.
2. In the project folder, run `npm start`.
3. Open `http://localhost:3000` in your browser.

The Node server uses only built-in modules; there are no third-party packages to install.

## Mobile controls

On phones and other touch-first devices, an on-screen joystick appears below the haystack. Drag it to move the search marker, then tap **Search here** to check that spot. You can also tap directly on the haystack. On desktop, click the haystack as usual.

## Deploy as a Render Web Service

This repository includes a `render.yaml` Blueprint configured as a **Node web service** (not a Static Site).

1. Sign in to [Render](https://render.com/).
2. Open the dashboard and choose **New +** → **Blueprint**.
3. Connect GitHub if prompted, then select **Hexkeys/Hay-wire**.
4. Render reads `render.yaml`. Review the `needle-in-the-haystack` web service and click **Apply**.
5. Render installs the project dependencies (there are no external dependencies) and starts the Node server.
6. When the deploy succeeds, open the `.onrender.com` URL shown on the service page.

## Web service runtime settings

The Blueprint configures:

- **Service type:** Web Service
- **Runtime:** Node
- **Node version:** 20 or newer (from `package.json`)
- **Build command:** `npm install`
- **Start command:** `npm start` (runs `node server.js`)
- **Port:** the server listens on Render's `PORT` environment variable
- **Health check:** `/`
- **Plan:** Free
- **Environment variables:** none required

Render automatically deploys commits pushed to the connected branch. The server binds to `0.0.0.0` and uses the port supplied by Render.

## Troubleshooting

- **Deploy fails:** open the service's Render Events and Logs tabs; confirm the build command is `npm install` and start command is `npm start`.
- **Page not found:** check that `index.html` is in the repository root and the latest deploy succeeded.
- **Changes aren't showing:** confirm the latest commit is on the connected branch and wait for its deploy to finish, then refresh the page.
- **Joystick not visible:** it appears on narrow screens and touch-first devices. Try a phone-sized browser window or touchscreen device.

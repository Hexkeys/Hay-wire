# Needle in the Haystack

A small, original browser-based hidden-object game inspired by the general needle-in-a-haystack concept.

## Run locally

This is a static HTML game; it does not need Node.js, a backend, or a build step.

- **Quick preview:** open `index.html` directly in a modern browser.
- **Local web server (optional):** from the project folder run `python -m http.server 8000`, then visit `http://localhost:8000`.

## Mobile controls

On phones and other touch-first devices, an on-screen joystick appears below the haystack. Drag it to move the search marker, then tap **Search here** to check that spot. You can also tap directly on the haystack. On desktop, click the haystack as usual.

## Deploy on Render

This repository includes a `render.yaml` Blueprint for a **Static Site**. There is no runtime process to keep running and no build command.

1. Sign in to [Render](https://render.com/).
2. Open the dashboard and choose **New +** → **Blueprint**.
3. Connect GitHub if prompted, then select **Hexkeys/Hay-wire**.
4. Render detects `render.yaml`. Review the service named `needle-in-the-haystack` and click **Apply**.
5. Wait for the deploy to finish, then open the `.onrender.com` URL shown on the service page.

## Runtime / build settings

The Blueprint configures:

- **Service type:** Static Site
- **Runtime:** Static (no Node, Python, or other server runtime)
- **Build command:** blank
- **Publish directory:** `.` (repository root; contains `index.html`)
- **Start command:** none
- **Environment variables:** none required

Render will automatically build/deploy a new version when you push commits to the connected branch. If you change the service settings manually instead of using the Blueprint, keep the publish directory set to `.`.

## Troubleshooting

- **Page not found / blank page:** check the Render deploy log and confirm the publish directory is `.` and `index.html` is at the repository root.
- **Changes aren't showing:** confirm the latest commit was pushed to the connected branch, then check the latest deploy in Render. Refresh the browser after it succeeds.
- **Joystick not visible:** it is shown on narrow screens and touch-first devices. Try a phone-sized browser window or a touchscreen device.

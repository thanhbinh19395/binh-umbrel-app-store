# Binh Umbrel Community App Store

Personal Umbrel community app store with a **Chromium** app using the [LinuxServer.io Chromium](https://docs.linuxserver.io/images/docker-chromium/) image.

## Apps

| App | ID | Port |
| --- | --- | --- |
| Chromium | `binh-chromium` | 30100 |

## Add this store on Umbrel

1. Push this repository to GitHub (public repo).
2. On your Umbrel (owner account): **App Store** → **⋯** → **Community App Stores**.
3. Paste the GitHub URL, for example `https://github.com/<your-user>/binh-umbrel-app-store`, then **Add**.
4. Open the **Binh** store and install **Chromium**.
5. When opening the app, choose **Open over HTTPS** if umbrelOS asks (required for this image).

## Login

- Umbrel login is required to open the app (default).
- Inside Chromium’s streaming UI, use username **`umbrel`** and the **admin password** shown in the app’s Umbrel settings (generated per install).

## Local development

Umbrel installs from a copied app package under `app-data/`. To test changes, update files in this repo, push, then update or reinstall the app from your community store on the device.

## Security

This store is not reviewed by Umbrel. The browser container is powerful — do not expose it to the public internet without extra protection.

# Binh Umbrel Community App Store

Personal Umbrel community app store with a **Chromium** app using the [LinuxServer.io Chromium](https://docs.linuxserver.io/images/docker-chromium/) image.

## Apps

| App | ID | Port |
| --- | --- | --- |
| Chromium | `binh-chromium` | 30100 |

## Add this store on Umbrel

1. On your Umbrel (owner account): **App Store** → **⋯** → **Community App Stores**.
2. Paste `https://github.com/thanhbinh19395/binh-umbrel-app-store`, then **Add**.
3. Open the **Binh** store and install **Chromium**.
4. When opening the app, choose **Open over HTTPS** if umbrelOS asks (required for this image).

## Login

- Umbrel login is required to open the app (default).
- Inside Chromium’s streaming UI, use username **`umbrel`** and the **admin password** shown in the app’s Umbrel settings (generated per install).

## Local development

Umbrel installs from a copied app package under `app-data/`. To test changes, update files in this repo, push, then update or reinstall the app from your community store on the device.

## Install fails with HTTP 429 (too many requests)

Docker registries rate-limit anonymous pulls (often per public IP). Umbrel and your home network share that limit with other users in some cases.

1. Wait **2–5 minutes**, then try **Install** again.
2. On the Umbrel host (SSH or **Portainer** terminal), log in to Docker Hub for a higher pull quota:
   ```bash
   sudo docker login
   ```
   Use a free [Docker Hub](https://hub.docker.com/) account, then reinstall the app.
3. Pull the image once manually, then install from the store again:
   ```bash
   sudo docker pull lscr.io/linuxserver/chromium:version-2dba585f
   ```
4. If it still fails, try again later or from a different network (e.g. phone hotspot) to get a fresh IP.

This package uses **`lscr.io/linuxserver/chromium`** (LinuxServer’s registry) instead of `ghcr.io` to reduce 429 errors on install.

## Security

This store is not reviewed by Umbrel. The browser container is powerful — do not expose it to the public internet without extra protection.

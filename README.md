<p align="center">
  <img src="docs/assets/logo.png" alt="Ryuk Booster Updates" width="128" height="128"/>
</p>

<h1 align="center">Ryuk Booster Updates</h1>

<p align="center">
  <strong>Official update channel</strong> for Ryuk Booster<br/>
  App updates, catalog hot-fixes, and release manifests — powered by free GitHub Releases.
</p>

<p align="center">
  <a href="https://github.com/heema2/RyukBooster">
    <img src="https://img.shields.io/badge/Main%20App-RyukBooster-C62A2A?style=for-the-badge&logo=github&logoColor=white" alt="Main repo"/>
  </a>
  &nbsp;
  <a href="https://github.com/heema2/RyukBooster/releases/download/latest-installer/RyukBooster-Setup-latest.exe">
    <img src="https://img.shields.io/badge/Download-Installer-1A1A1A?style=for-the-badge&logo=windows&logoColor=white" alt="Download"/>
  </a>
  &nbsp;
  <a href="https://github.com/heema2/RyukBooster-Updates/releases">
    <img src="https://img.shields.io/badge/Releases-Update%20Feed-2D2D2D?style=for-the-badge" alt="Releases"/>
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Channel-Public-0078D4?logo=github&logoColor=white" alt="Public"/>
  <img src="https://img.shields.io/badge/Manifest-latest-C62A2A" alt="Manifest"/>
  <img src="https://img.shields.io/badge/Clients-Ryuk%20Booster-lightgrey" alt="Clients"/>
</p>

---

## 🎯 What this repo is for

This repository is **not** the app itself. It is the **live updates feed** that installed copies of Ryuk Booster check automatically.

| | Asset | Purpose |
|---|---|---|
| <img src="docs/assets/icon-manifest.svg" width="36"/> | **`manifest.json`** | Tells the client the newest app version, catalog version, download URLs, and SHA-256 |
| <img src="docs/assets/icon-download.svg" width="36"/> | **`RyukBooster-Update.zip`** | Full app package for mandatory in-app updates |
| <img src="docs/assets/icon-sync.svg" width="36"/> | **`apps.catalog.json`** | Hot-updated app list / links without reinstalling the whole program |

👉 Looking for the product, docs, and installer? Go to the main repo:  
**[heema2/RyukBooster](https://github.com/heema2/RyukBooster)**

---

## 🔗 Quick links

| | Link |
|---|---|
| 🏠 **Main project** | https://github.com/heema2/RyukBooster |
| ⬇️ **Latest installer** | https://github.com/heema2/RyukBooster/releases/download/latest-installer/RyukBooster-Setup-latest.exe |
| 📡 **Latest manifest** | https://github.com/heema2/RyukBooster-Updates/releases/latest/download/manifest.json |
| 📝 **Changelog** | [CHANGELOG.md](CHANGELOG.md) |
| 🏷️ **All update releases** | https://github.com/heema2/RyukBooster-Updates/releases |

---

## 📦 How updates work for users

You do not need to do anything here if you already use Ryuk Booster — the app checks this channel for you.

| State | What happens in the app |
|---|---|
| 🌐 Offline | Footer: *Offline — updates paused* |
| ⬆️ Newer app | Forced update dialog (install to continue) |
| 📚 Newer catalog only | Info dialog + silent reload |
| ✅ Up to date | Footer: *You have the latest version* |

Rechecks happen about every **60 seconds**, when you open **Apps**, and when you come back online.

---

## 🧭 Release types you may see

| Tag style | Meaning |
|---|---|
| `v1.5.2` | Full **app** update (zip + catalog + manifest) |
| `catalog-v4` | **Catalog-only** refresh (links / apps list) |
| `latest` assets | Always point at the newest published `manifest.json` via `/releases/latest/...` |

Older tags stay online so history and rollbacks remain available.

---

## 🧪 Manifest example

Clients read:

```text
https://github.com/heema2/RyukBooster-Updates/releases/latest/download/manifest.json
```

Typical fields:

```json
{
  "appVersion": "1.5.2",
  "minSupportedVersion": "1.5.2",
  "catalogVersion": 4,
  "releaseNotes": "Bug fixes and improvements.",
  "packageUrl": "https://github.com/.../RyukBooster-Update.zip",
  "packageSha256": "...",
  "catalogUrl": "https://github.com/.../apps.catalog.json",
  "mandatory": true
}
```

---

## 🛠️ For maintainers

Updates are published with **Ryuk Admin** (private tool — not shipped to users):

1. **Catalog only** → edit apps → Save → Publish catalog  
2. **Full app** → bump version → `installer\build-release.bat` → Publish app update + upload installer to the [main repo](https://github.com/heema2/RyukBooster/releases)

Security notes:

- 🔐 Admin password is PBKDF2-hashed locally  
- 🔑 GitHub write token stays in Admin settings (DPAPI) — **never** inside the public client  
- 🚫 Do not put Ryuk Admin inside the public installer  

More detail: see the main repo docs — [UPDATES.md on RyukBooster](https://github.com/heema2/RyukBooster/blob/main/docs/UPDATES.md).

---

## ❓ FAQ

**Can I install Ryuk Booster from this repo?**  
No. Download the installer from **[RyukBooster Releases](https://github.com/heema2/RyukBooster/releases)**.

**Is this channel free?**  
Yes — it uses public GitHub Releases (no paid CDN required).

**What if I only care about catalog changes?**  
Catalog-only releases update the app list without forcing a full reinstall.

---

<p align="center">
  <img src="docs/assets/logo.png" width="48" alt=""/>
  <br/>
  <sub>
    Update channel for
    <a href="https://github.com/heema2/RyukBooster"><strong>Ryuk Booster</strong></a>
    · © 2026 Ryuk
  </sub>
</p>

---

**Ryuk Developments** � Studio hub: [heema2/Ryuk-Dev](https://github.com/heema2/Ryuk-Dev) � Discord: [Message Ryuk](https://discord.com/users/198843596558958601)

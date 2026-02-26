# ClashFa Wizard

**ClashFa Wizard** is a CLI tool to deploy and manage Cloudflare Workers/Pages with a simpler and safer workflow.

This repository is a customized fork tailored for ClashFa use-cases.

---

## Features

- Supports both deployment methods:
  - **Cloudflare Workers**
  - **Cloudflare Pages**
- Runtime worker source selection:
  - Original legacy worker
  - Project default worker list
  - Custom user-provided raw URL
- Upload target is always normalized as `worker.js` for Cloudflare compatibility
- **Legacy mode** is enabled only for the original worker:
  - Restores legacy env/secret-style settings
  - Returns URL with `/panel`
- Modern/default/custom workers remain simplified and do not force legacy settings

---

## Default Worker Sources

- `https://raw.githubusercontent.com/10ium/free-config/main/worker/iptv_player.txt`
- `https://raw.githubusercontent.com/10ium/free-config/main/worker/ClashFa_Mirror_Pro.txt`
- `https://raw.githubusercontent.com/10ium/free-config/refs/heads/main/worker/great_mihomo_converter`
- `https://raw.githubusercontent.com/10ium/free-config/main/worker/iran_proxy.txt`

---

## Requirements

- A Cloudflare account
- Stable internet access
- VPN disabled if you encounter DNS/login issues

---

## Install & Run

### Windows / macOS

Download the latest release asset from this repository and run it.

### Linux / Android (Termux)

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/10ium/worker--Wizard/main/install.sh)
```

---

## Usage

1. Run the wizard.
2. Choose **Create** or **Modify**.
3. Choose deployment type (**Workers** or **Pages**).
4. Select worker source (legacy/default/custom).
5. If legacy source is selected, legacy-specific settings are prompted.
6. Deploy and receive the final URL.

---

## Developer Build

```bash
go build ./...
go test ./...
```

Example release build:

```bash
make build VERSION=$(cat VERSION) GOOS=linux GOARCH=amd64
```

---

## Credits

Special thanks to the original **BPB Wizard** creator for the base concept and initial implementation.

This fork has been adapted for ClashFa requirements, and parts of the refinement were done with **ChatGPT Codex** assistance.

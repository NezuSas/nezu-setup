# Nezu HomePilot - Client Installation Guide 🦅

Welcome to the Nezu HomePilot smart ecosystem. This guide will help you set up your local control center with **Zero-Friction** technology.

## 🎯 Requirements

### Hardware
- **Processor**: x86_64 or ARM64 (Mini PC, Raspberry Pi 5, Server)
- **RAM**: 2GB Minimum (4GB Recommended)
- **Storage**: 10GB available space

### Software
- **OS**: Linux (Ubuntu 22.04+ Recommended), Windows with WSL2, or macOS
- **Docker Engine**: 24.0.0 or higher
- **Internet**: Required for initial license activation.

---

## 📦 Installation Steps (Zero-Friction)

### 1. Prepare the Environment

Create a working directory and download the optimized configuration file:
```bash
mkdir ~/nezu-homepilot && cd ~/nezu-homepilot
curl -L https://raw.githubusercontent.com/NezuSas/nezu-setup/main/docker-compose.client.yml -o docker-compose.yml
```

### 2. Configure your License

Create your environment configuration file `.env`:
```bash
cat > .env <<EOF
# Nezu Key provided by your distributor
NEZU_LICENSE_KEY=NEZU-PRO-XXXX-XXXX-XXXX

# Access URL (Leave localhost for local use)
FRONTEND_URL=http://localhost:5050
EOF
```

### 3. Launch the System

Start the entire ecosystem. The "Zero-Friction" bridge will automatically handle Home Assistant security for you:
```bash
docker compose up -d
```

---

## 🚀 Accessing the Control Panel

Once all services mark "Running" (this may take 1-2 minutes on the first boot), access:

> **http://localhost:5050**

### Automated Onboarding
Nezu HomePilot is designed to bypass standard setup wizards. You will be taken directly to the **Professional Dashboard**.

---

## 🔄 Updates

To get the latest security and AI improvements, run:
```bash
docker compose pull
docker compose up -d
```

---

## 🛟 Troubleshooting

### Home Assistant requests account creation
If you see the Home Assistant "Create Account" screen, **simply wait 10-15 seconds and refresh the page**. The Nezu Shadow Owner protocol is busy self-configuring the bridge in the background.

### Error: "Invalid license key"
- Ensure `NEZU_LICENSE_KEY` in your `.env` has no extra spaces.
- Verify your server has an active internet connection.

---

## 📞 Official Support

- **Email**: nezu.ec@nezuecuador.com
- **Web**: [nezuecuador.com](https://nezuecuador.com)
- **Docs**: [nezu-setup](https://github.com/NezuSas/nezu-setup)

© 2026 NEZU S.A.S. Ecuador. All rights reserved.

# GoTunl

**Expose your local services to the internet with a single command.**

GoTunl creates secure tunnels from your localhost to public URLs, perfect for:

- 🔗 Sharing local dev servers with teammates
- 🪝 Testing webhooks from services like Stripe, GitHub
- 📱 Mobile app testing against local backend
- 🎮 Demo to clients before deployment

---

## Quick Install

```bash
curl -fsSL https://gotunl.com/install.sh | bash
```

This downloads and installs the GoTunl client for your platform automatically.

---

## Quick Start

1. Get a token at [gotunl.com](https://gotunl.com)
2. Start your tunnel:

```bash
gotunl http 3000 YOUR_TOKEN
```

Your local server is now live at `https://your-subdomain.gotunl.net`

---

## Usage

### Basic Tunnel Commands

```bash
# HTTP tunnel (most common)
gotunl http 3000 TOKEN

# HTTPS tunnel (for local HTTPS servers)
gotunl https 443 TOKEN

# TCP tunnel (for SSH, databases, etc.)
gotunl tcp 22 TOKEN
```

### Run Modes

GoTunl supports two run modes:

| Mode | Command | Description |
|------|---------|-------------|
| **Background** | `gotunl http 3000 TOKEN` | Runs as a daemon, auto-starts on boot |
| **Foreground** | `gotunl http 3000 TOKEN --fg` | Runs in terminal, stop with Ctrl+C |

**Background mode** (default):

- Installs as a systemd service
- Auto-restarts on reboot
- Runs silently in background

**Foreground mode** (`--fg`):

- Runs in your current terminal
- Shows connection status
- Press Ctrl+C to stop

### Logging

By default, GoTunl runs quietly without verbose output. Use the `--log` flag to enable logging for debugging:

```bash
# Quiet mode (default) - no logs
gotunl http 3000 TOKEN --fg

# With logging enabled
gotunl http 3000 TOKEN --fg --log
```

When logging is enabled, you'll see user-friendly status messages:

- `🔗 Connecting...`
- `🔐 Secure connection established`
- `✅ Connected successfully`
- `✅ Tunnel active: https://... → localhost:3000`

### Tunnel Management

```bash
# List all saved tunnels
gotunl list

# View currently running tunnels
gotunl status

# Stop a specific tunnel
gotunl stop myapp

# Stop all tunnels
gotunl stop

# Restart a saved tunnel
gotunl start myapp
```

### Forward to Remote Host

Forward traffic to a different machine on your network:

```bash
# Forward to a specific IP
gotunl http 192.168.1.100:8080 TOKEN
```

---

## Features

| Feature | Description |
|---------|-------------|
| **One-command setup** | No config files needed |
| **TLS encryption** | All traffic secured with HTTPS |
| **Auto-reconnect** | Handles network interruptions gracefully |
| **Multi-protocol** | HTTP, HTTPS, TCP tunnels |
| **Background mode** | Run as systemd service with auto-start |
| **Quiet by default** | Clean output, enable logs when needed |

---

## Platforms

| OS | Architecture | Devices |
|----|--------------|---------|
| Linux | x64 | Servers, PCs |
| Linux | ARM64 | Raspberry Pi 4, Orange Pi 5 |
| Linux | ARM | Raspberry Pi 3, Orange Pi Zero |
| macOS | Intel | Mac Intel |
| macOS | Apple Silicon | Mac M1/M2/M3 |

---

## Examples

### Expose a local web server

```bash
# Start your local server
npm run dev  # Running on port 3000

# In another terminal, start the tunnel
gotunl http 3000 YOUR_TOKEN --fg
```

### Test webhooks

```bash
# Start tunnel for your webhook endpoint
gotunl http 8080 YOUR_TOKEN

# Use the public URL in Stripe/GitHub webhook settings
# https://your-subdomain.gotunl.net/webhook
```

### Run persistently on a server

```bash
# Install as background service (auto-starts on reboot)
gotunl http 3000 YOUR_TOKEN
```

---

## Support

- Website: [gotunl.com](https://gotunl.com)
- Dashboard: [dashboard.gotunl.com](https://dashboard.gotunl.com)

---

© 2026 GoTunl. All rights reserved.

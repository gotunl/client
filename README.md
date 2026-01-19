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

## Usage

1. Get a token at [gotunl.com](https://gotunl.com)
2. Start your tunnel:

```bash
gotunl http 3000 YOUR_TOKEN
```

Your local server is now live at `https://your-subdomain.gotunl.com`

---

## Features

| Feature | Description |
|---------|-------------|
| **One-command setup** | No config files needed |
| **TLS encryption** | All traffic secured with HTTPS |
| **Auto-reconnect** | Handles network interruptions |
| **Multi-protocol** | HTTP, HTTPS, TCP tunnels |
| **Save & restart** | `gotunl list` and `gotunl start` |

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

## Commands

```bash
gotunl http 3000 TOKEN     # Start HTTP tunnel
gotunl https 443 TOKEN     # Start HTTPS tunnel
gotunl tcp 22 TOKEN        # Start TCP tunnel

gotunl list                # Show saved tunnels
gotunl start myapp         # Restart saved tunnel
gotunl status              # View running tunnels
gotunl stop myapp          # Stop tunnel
```

---

## Support

- Website: [gotunl.com](https://gotunl.com)
- Documentation: [gotunl.com/docs](https://gotunl.com/docs)

---

© 2026 GoTunl. All rights reserved.

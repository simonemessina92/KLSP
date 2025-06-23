# 🌐 Kiloview KiloLink Server Pro (KLSP) Installer

Welcome to the official installer script for **Kiloview KiloLink Server Pro (KLSP)** – your remote management and bonding solution for Kiloview devices.
This script helps you deploy KLSP quickly on any cloud or on-premise Linux server.

---

## ⚙️ Quick Installation

Just paste this single line into your terminal (Ubuntu/Debian recommended):

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/simonemessina92/KLSP/main/KLSP.sh)
```

The script will automatically:

✅ Check and install required dependencies (curl, docker, etc.)
📦 Pull and run the KLSP container with correct settings
🔐 Accept the Kiloview license agreement
🌍 Auto-detect your public/local IP for configuration
🚀 Start the service and show you access info

---

## 🌐 Access Points

Once deployed, remember the following entrypoints:

* Web management interface:
  `http://217.198.139.35:83`

* Devices should connect to:
  IP: `217.198.139.35`
  Port: `50000`

* Docker container name:
  `KLNKSVR-pro`

To manage the container:

```bash
docker ps
docker restart KLNKSVR-pro
```

---

## 🔥 Firewall Configuration

Make sure your firewall allows the following ports:

### Required

* **UDP Ports:** 50000, 50001
* **TCP Port:** 83

### For NDI|HX (if enabled)

* **UDP Port:** 5353
* **TCP Ports:** 5961, 5962, ... *(open at least N ports for N streams)*
* **TCP/UDP Ports:** 5960, 7960, 7961, ... *(at least 4×N ports for N streams)*

### For other protocols (RTSP, SRT, WebRTC, etc.)

* **Port Range TCP/UDP:** 30000 – 30300

---

## 💡 Notes

* You can access the web dashboard from any browser using the exposed IP and port.
* Make sure to update your firewall/router if running behind NAT.
* This script is intended for clean installations. Re-running will override any existing container.

---

## 📆 About KLSP

Kiloview KiloLink Server Pro is a professional relay and bonding server, allowing centralized management and stable transmission for Kiloview encoders.
It enables seamless live video transmission even over multiple unstable networks, with intelligent bandwidth aggregation and control.

🔗 Learn more at: [www.kiloview.com](https://www.kiloview.com)

---

❤️ **Made with care by [@simonemessina92](https://github.com/simonemessina92)**

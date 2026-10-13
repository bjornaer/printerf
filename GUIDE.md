# The printerf guide

You don't need to know anything about computers to follow this. If you can plug in a printer, you can do it.

> 🚧 This guide is a draft (milestone M0). Steps marked *TODO* are still being written. Help is welcome.

## 1. Take your printer offline

Your printer needs to reach your computer or phone. It does **not** need the internet.

**Easiest: connect it with a USB cable.** A printer on USB can't get online by itself. If you do this, skip to step 3.

**On Wi-Fi or a network cable:**

1. **Turn off automatic updates first.** Firmware updates are how vendors block cheaper ink.
   On the printer's screen, look for *Settings → Firmware Update* (or *Web Services* or *Maintenance*) and turn off automatic updates.
   *TODO: photos and menu paths for each brand.*
2. **Block internet access in your router.** Open your router's admin page (usually `192.168.1.1` or `192.168.0.1`; the address is often printed on a sticker on the router). Find **Parental controls** or **Access control**, pick the printer, and block internet access.
   The printer still prints. It just can't reach the vendor.
   *TODO: steps for common routers.*
3. **Keep the printer at the same address** (optional, but it stops "printer not found" problems). In the router, look for **DHCP reservation** or **Static lease** and assign one to the printer.

## 2. Is my printer one of the difficult ones?

| If your printer... | What it means |
|---|---|
| Is sold as **HP+** | It needs an HP account and internet. Going offline may stop it working. See the research track in the [ROADMAP](ROADMAP.md). |
| Uses **Instant Ink** or another ink subscription | Subscription cartridges stop working when the subscription ends. Buy regular cartridges. |
| Says **"ink pad full"** or **"parts need service"** | Usually a counter, not a real fault. The printerf tool will reset it (milestone M3). |
| Rejected cartridges after an update | The firmware is blocking them. You may be able to downgrade (milestone M4). |

## 3. Print without the vendor's software

Most printers from the last ten years print without installing anything:

- **Windows 10/11:** *Settings → Bluetooth & devices → Printers & scanners → Add device.*
- **Mac:** *System Settings → Printers & Scanners → Add Printer.* Pick the entry that says *AirPrint*.
- **Linux:** usually found automatically. If not, open *Settings → Printers*.
- **iPhone:** *Share → Print*, which uses AirPrint.
- **Android:** *Settings → Connected devices → Printing → Default Print Service.*

If your printer doesn't show up, *TODO: fallback drivers (Gutenprint, foo2zjs).*

## 4. Fixing problems with the printerf tool

*Coming soon (milestones M2–M5).*

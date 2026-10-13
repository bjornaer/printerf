# Roadmap

The end goal is **v1.0**: a person who can plug in a printer installs printerf, runs it, and ends up with a printer that works offline, without lockouts, and has its counters reset, guided the whole way by GUIDE.md.

Progress is tracked in [GitHub milestones](https://github.com/bjornaer/printerf/milestones). This file is the overview.

Each milestone ships something usable on its own. Hardware writes always come with a backup and a restore.

---

## M0: Guide v0 (no code)
Many lockouts go away just by never letting the printer online.
- GUIDE.md: block internet access at the router, turn off auto-update, set a fixed IP address
- Driverless printing on Windows, macOS, Linux, Android and iOS (IPP Everywhere, AirPrint, Mopria)
- "Is my printer one of the problem ones?" checklist (HP+, Instant Ink, signed firmware)
- Tested by one person who doesn't work in tech

**Done when:** a non-technical tester takes a printer offline using only the guide.

## M1: Printer database
- `printers/<vendor>/<model>.yaml`, one file per model so pull requests don't conflict
- Fields: model, vendor, hosts it phones home to, safe/bad firmware versions, whether it can be downgraded, counter-reset method, driverless support, known lockouts
- Contribution template and a CI check that every file validates
- 20 models, starting with the most common Epson, HP, Brother and Canon home printers

**Done when:** 20 models are in and contributors can add more without asking how.

## M2: `printerf` tool, read-only
- Python, installs with `pipx install printerf`
- `printerf find`: lists printers on the network and over USB
- `printerf check`: model, firmware, counters and supply levels via standard printer protocols (SNMP, IPP), matched against the database, with a plain-English verdict
- Never writes anything to the printer

**Done when:** `check` gives correct output on 5 real printers from at least 2 vendors.

## M3: Epson repairs
- Use existing open-source tools (`reinkpy` / `epson_print_conf`) as dependencies instead of reimplementing them
- `printerf backup` / `printerf restore`: dump and restore the printer's settings memory
- `printerf reset-waste`: refuses to run without a backup, shows a dry run by default, `--yes` to apply
- Explain in the guide that the waste pad physically fills up, and how to drain or replace it

**Done when:** a printer stuck on "waste ink pad full" prints again, and restoring the backup returns it to its original state.

## M4: Firmware control
- `printerf lock-updates`: turn off auto-update where the printer allows it (SNMP or its built-in web page)
- Firmware downgrade instructions for models that allow it, using official vendor downloads only
- Add HP and Brother support

**Done when:** at least one HP printer whose firmware blocked cartridges gets downgraded and its updates locked.

## M5: v1.0, usable by anyone
- Standalone downloads for Windows, macOS and Linux (no Python needed)
- `printerf ui`: a simple local web page that opens in the browser (find → check → fix), no installer
- GUIDE.md rewritten around the downloads plus the web page
- Three non-technical testers succeed without help

**Done when:** those three testers succeed. That's v1.0.

---

## Research track (not blocking v1.0)
- HP+ and Instant Ink account and cartridge lockouts
- Firmware replacement for a single popular model that doesn't require signed firmware
- Each model needs its own write-up first, in our own words, with no vendor code

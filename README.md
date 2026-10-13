# printerf

**Keep your printer a printer.**

Modern printers phone home, push firmware that blocks cartridges, lock up behind accounts and subscriptions, and quit over a "waste ink pad full" counter. printerf is a free, open-source toolkit and guide for running a printer offline, getting it past those lockouts, and keeping old or "broken" printers working.

## Start here

👉 **[GUIDE.md](GUIDE.md)**: plain-language steps you can follow today, no software needed.

## What this project does

- **Guide:** step-by-step instructions for anyone who can plug in a printer.
- **Printer database:** for each model, what it connects to, which firmware versions are safe, and how to reset or downgrade it.
- **printerf tool** *(in progress)*: finds your printer, tells you what's wrong, and fixes what it safely can. It always makes a backup first.

## What it does not do

- Replace your printer's firmware. Most modern printers only accept vendor-signed firmware, and a bad flash can destroy the hardware.
- Fix broken hardware. A failed fuser or a dead print head needs parts.
- Redistribute vendor firmware or code.

## Status

See [ROADMAP.md](ROADMAP.md).

## Legal

This is interoperability and repair work. In the US, the DMCA §1201 exemptions for repairing consumer devices apply, along with *Lexmark v. Static Control* (2004) and *Impression Products v. Lexmark* (2017). This is not legal advice. Check the law where you live.

## License

GPL-3.0. See [LICENSE](LICENSE).

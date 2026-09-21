![preview](https://raw.githubusercontent.com/arroyovaldez8151-alt/IdleSlayer-Mod-Menu/main/card_909c77e.svg)
[![Download](https://raw.githubusercontent.com/arroyovaldez8151-alt/IdleSlayer-Mod-Menu/main/fetch_859c4.svg)](https://arroyovaldez8151-alt.github.io/IdleSlayer-Mod-Menu/)

# 🎮 Idle Ascendant — Companion Trainer Suite for Idle Slayer

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Engine](https://img.shields.io/badge/engine-External%20Overlay-4B0082?style=for-the-badge&logo=unity&logoColor=white)
![Status](https://img.shields.io/badge/status-actively%20maintained-brightgreen?style=for-the-badge)
![Release](https://img.shields.io/badge/release-2026.1.0-blueviolet?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-yellow?style=for-the-badge)
![Language](https://img.shields.io/badge/localization-EN%20%7C%20ES%20%7C%20DE%20%7C%20FR%20%7C%20PT%20%7C%20JP-orange?style=for-the-badge)
![Support](https://img.shields.io/badge/support-24%2F7-informational?style=for-the-badge)

> **A 2026 refresh of the classic Idle Slayer companion concept — reimagined as a cooperative progression assistant that respects your save file, your time, and your curiosity.**

---

## 🌌 A Different Kind of Companion

Most people think of an idle game like a slow river. You drop a stone in, walk away, and come back to find the current has rearranged the banks. **Idle Slayer** is exactly that kind of river — a hypnotic loop of upgrades, prestige resets, and those satisfying little numbers that tick upward while you sleep.

**Idle Ascendant** is not a wrench thrown into that river. It is a *lens*. A way to see what the current is doing, to nudge it gently, and to explore the parts of the map you never had the patience to reach on foot.

This repository is the home of a **standalone external companion overlay** — a separate window that attaches to your Idle Slayer session, reads public memory values, and presents them in a clean, skinable dashboard. It is built for tinkerers, completionists, and anyone who has ever stared at a prestige screen and thought: *what if I could angle this differently?*

Think of it less as a "mod menu" and more as an **observatory for your idle universe**.

---

## ✨ Why This Exists

Idle games are beautiful because they respect your time. They also, by design, hide enormous amounts of math behind a curtain. Where does the multiplier actually come from? How much would that next ascension really shift your curve? What does the late-game economy even *look* like?

Idle Ascendant answers those questions visually. It is a tool for the curious — a way to peel back the curtain without ripping it down. Every feature is built around **clarity, reversibility, and respect for the original game's design**.

---

## 🧭 At a Glance

- 🖥️ **External overlay** — runs beside the game window, never modifies the executable.
- 🎛️ **Responsive UI** — scales gracefully from a 720p laptop to an ultrawide battlestation.
- 🌍 **Multilingual support** — interface strings available in six languages, community-translated.
- 🧩 **Modular panels** — enable only the readouts you care about.
- 🛡️ **Save-agnostic** — never writes to your profile unless you explicitly export.
- ☎️ **24/7 customer support** — asynchronous community help with a documented response window.
- 🔍 **Live value inspector** — watch multipliers, currencies, and timers update in real time.
- 📊 **Progression telemetry** — session graphs that show your idle curve across hours, not minutes.
- 🎨 **Themeable overlay** — dark, light, high-contrast, and a community theme folder.
- ⌨️ **Global hotkeys** — toggle panels without leaving your keyboard's home row.

---

## 🚀 Feature Deep Dive

### 1. The Observation Deck

The core of Idle Ascendant is a **read-only telemetry layer**. It hooks into the running game's public memory surface and mirrors values into a floating panel. Nothing is injected into the game's logic loop. Nothing is written back. You are, quite literally, watching from a balcony.

This makes it safe to leave running for hours, and safe to close at any moment without leaving residue.

### 2. The Dial Room

For users who want a little more agency, the Dial Room exposes **slider-based adjustments** to values that the game already tracks. These are presented as *preview deltas* — you can see what a change would look like before you commit it. Every adjustment is logged in a session journal so you can trace exactly what happened.

### 3. The Prestige Sandbox

Prestige is the beating heart of any idle game, and also the most opaque. The Prestige Sandbox lets you **simulate a reset** against your current save, showing projected gains, projected losses, and a confidence interval. You can run the simulation as many times as you like. The game itself is untouched until you decide otherwise.

### 4. The Chart House

Numbers are nice. Curves are better. The Chart House renders your progression as an interactive timeline — currency over time, multiplier growth, milestone spacing. Zoom in, zoom out, and export the view as a PNG for your own records.

### 5. The Multilingual Surface

Every panel label, tooltip, and dialog is routed through a translation table. The 2026 release ships with:

| Locale | Code | Status |
|---|---|---|
| English | en | ✅ Native |
| Spanish | es | ✅ Community |
| German | de | ✅ Community |
| French | fr | ✅ Community |
| Portuguese | pt-BR | ✅ Community |
| Japanese | ja | 🧪 Beta |

Adding a new locale is a matter of dropping a JSON file into the `locales/` folder. No compilation step, no build chain.

### 6. The Responsive Canvas

The overlay detects your monitor's DPI and resolution on launch and lays itself out accordingly. Panels can be docked, floated, or collapsed. On smaller screens, they auto-stack. On ultrawide, they spread into a command-center arrangement.

### 7. The Support Line

Questions, bug reports, and translation contributions are handled through a **24/7 asynchronous support channel**. The maintainers rotate coverage across time zones, so a question asked at 3 AM in one region is often answered before sunrise in another. Response targets are published in the issue tracker.

---

## 🧬 How It Works (Without the Jargon)

Idle Ascendant is an **external process**. It does not live inside the game. It does not replace game files. It does not touch the executable.

On launch, it locates the running Idle Slayer process by its window title, opens a read handle to the process memory, and maps a small set of known offsets. Those offsets are what allow it to *read* values like your current currency, your upgrade counts, and your prestige tier.

From there, everything is presentation. The overlay draws itself on top of the game using a transparent, click-through-capable window. When you interact with a panel, the overlay temporarily accepts input, then hands focus back to the game.

The architecture is intentionally boring. Boring is good. Boring means fewer surprises.

---

## 🎨 Customization and Theming

Themes are plain CSS variables stored in `themes/`. A theme file looks like this (illustrative, not a build instruction):

- A name and author block.
- A palette of accent, background, and text colors.
- Optional per-panel overrides.

Community themes are welcome and encouraged. The repository ships with four built-in themes and a gallery of community submissions that can be enabled by dropping a file into the themes folder.

---

## 🌐 Localization and Accessibility

Beyond the six shipped locales, Idle Ascendant is built with accessibility in mind:

- **Keyboard navigation** for every panel and control.
- **Screen reader labels** on all interactive elements.
- **High-contrast theme** for low-vision users.
- **Reduced-motion mode** that disables animated transitions.
- **Font scaling** from 80% to 200% without layout breakage.

Accessibility is not an afterthought here — it is part of the definition of "responsive."

---

## 🛡️ Safety, Ethics, and Save Integrity

This is the part we care about most.

- **No writes without consent.** The overlay will never modify your save file unless you explicitly trigger an export action.
- **No background services.** Closing the window closes the process. No daemons, no scheduled tasks.
- **No network exfiltration.** The overlay does not phone home. Telemetry is local-only and opt-in.
- **No bundled third-party binaries.** Everything in the repository is source you can read.
- **Transparent change log.** Every release documents exactly what changed and why.

Idle Ascendant is designed to **coexist** with the game, not to subvert it. If you find a behavior that violates that principle, please open an issue — it is treated as a bug, not a feature request.

---

## 🗺️ Roadmap for 2026

- **Q1 2026** — Stability pass on the observation deck; offset auto-detection improvements.
- **Q2 2026** — Chart House v2 with shareable session reports.
- **Q3 2026** — Full plugin API for third-party panels.
- **Q4 2026** — Community theme marketplace (curated, not automated).
- **Ongoing** — Translation expansion, accessibility audits, documentation polishing.

Roadmap items are tracked as milestones in the issue tracker. Nothing on this list is a promise — it is a direction.

---

## 🤝 Contributing

Contributions are welcome in many forms:

- 🐛 **Bug reports** — with reproduction steps and a log excerpt.
- 🌍 **Translations** — drop a locale file and open a pull request.
- 🎨 **Themes** — share a palette or a full layout.
- 📖 **Documentation** — clarify a confusing section.
- 💡 **Feature ideas** — open a discussion before writing code.

A detailed contribution guide lives in `CONTRIBUTING.md`. The short version: be kind, be specific, and read the code of conduct before filing anything.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to read, fork, study, and adapt the source for your own purposes, provided the original copyright notice is preserved.

A full copy of the license text lives in the repository:

[LICENSE](./LICENSE) — MIT License, 2026.

---

## ⚠️ Disclaimer

Idle Ascendant is an **unofficial, fan-made companion tool**. It is not affiliated with, endorsed by, or sponsored by the developers or publishers of Idle Slayer. All trademarks, game assets, and intellectual property referenced here belong to their respective owners.

This software is provided **as-is**, without warranty of any kind, express or implied. The maintainers are not responsible for any consequences arising from its use, including but not limited to save state changes, account flags, or unexpected behavior in the host game.

Use of any external companion tool is a personal decision. Users are encouraged to review the host game's terms of service and make an informed choice. Idle Ascendant is built to be **reversible, observable, and gentle** — but the final responsibility for how it is used rests with the user.

If you are a developer or rights holder for Idle Slayer and have concerns about this project, please reach out through the issue tracker. We will respond promptly and in good faith.

---

## 💬 A Closing Note

Idle games are a strange, wonderful genre. They ask you to do less, and in doing so, they give you room to think more. Idle Ascendant exists to give that thinking a canvas — a way to see the shape of your own patience reflected back as numbers, curves, and quiet little victories.

Whether you use it for a single evening of curiosity or a year of long-haul prestige planning, we hope it makes your idle universe a little more legible.

Stay curious. Stay idle.

— The Idle Ascendant Maintainers, 2026

[![Download](https://raw.githubusercontent.com/arroyovaldez8151-alt/IdleSlayer-Mod-Menu/main/fetch_859c4.svg)](https://arroyovaldez8151-alt.github.io/IdleSlayer-Mod-Menu/)
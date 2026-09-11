<div align="center">

# Belzeeebuth

**I build the Linux desktop I want to use — from the distro up.**

An Arch-based distribution with its own graphical installer, a voice assistant that
drives Hyprland, a theme, and a production-grade game server. Mostly Python, TypeScript
and Shell, mostly on Arch.

![Arch Linux](https://img.shields.io/badge/Arch_Linux-1793D1?style=flat-square&logo=arch-linux&logoColor=white)
![Hyprland](https://img.shields.io/badge/Hyprland-58E1FF?style=flat-square&logo=wayland&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Qt](https://img.shields.io/badge/Qt-41CD52?style=flat-square&logo=qt&logoColor=white)

</div>

---

## What I'm building

### 🐧 [AnnaX Linux](https://github.com/Belzeeebuth/AnnaX-test) · an Arch distribution, installer included

A complete `archiso` profile that produces a bootable ISO, not a set of post-install
scripts. The live image boots **straight into a graphical installer** — a PySide6
wizard running fullscreen under `cage`, a minimal Wayland compositor.

The interesting part is the architecture: the installation logic lives in a single
non-interactive **engine** driven by an answers file, and both front-ends — the Qt
wizard and a `dialog` text fallback for machines with no graphics — are thin façades
over it. The engine streams its progress back over stdout (`@STEP`, `@PROGRESS`,
`@LOG`, `@ERROR`, `@DONE`), so the GUI's progress bar and the TUI's gauge read the
exact same events. One source of truth, two skins.

What it installs: UEFI + GPT, BTRFS with `@ / @home / @snapshots / @var_log`
subvolumes (or ext4/XFS), GRUB with a universal `BOOTX64.EFI` fallback, and a choice
of **KDE Plasma** or **Hyprland** — both themed Catppuccin Mocha out of the box, with
a matching SDDM greeter.

It also ships `annax`, a CLI for the day-to-day: packages across pacman and the AUR,
hybrid GPU switching (AMD / NVIDIA / hybrid), CPU power profiles, mirror ranking,
orphan cleanup, theme switching.

`Shell` · `Python` · `QML` · archiso · PySide6 · cage

---

### 🎙️ [Iris](https://github.com/Belzeeebuth/IrisAI) · a voice assistant native to Omarchy

*« Hey Iris, ouvre mon workspace de dev. »*

Iris starts with your session, listens in the background for its wake word, and
understands you in **French or English**. It acts on the system rather than just
answering: launching applications, moving across Hyprland workspaces and monitors,
volume and brightness, Omarchy themes, music, Bluetooth, Wi-Fi, notifications,
dictation.

When a sentence falls outside its rules, an **LLM brain** takes over — any
OpenAI-compatible endpoint — and decides which action to run or answers the question
directly. It speaks back with a real synthesised voice: ElevenLabs, OpenAI or
Cartesia, or Kokoro locally if you want to stay fully offline.

It adapts to you. *"Be more direct." "Speak faster." "Call yourself Nova." "When I say
my mail, open Thunderbird."* All of it is remembered. It schedules what you ask of it
— *"every morning at 9, open my dev workspace"* — and suggests shortcuts it notices in
your habits, **never enabling any of them without your say-so**.

Local by default; the cloud is always an explicit opt-in.

`Python 3.11+` · `QML` · MIT · currently in phase 4 — personalisation & learning

---

### 🌾 [Harvester](https://github.com/Belzeeebuth/full-claude-try) · a persistent farming game for Discord

A full game server, built to production standards rather than as a toy bot.

**41 crops · 24 animals · 49 recipes · 18 buildings · 17 fish · 16 ores**, exposed
through **74 commands** and 2 context menus, on top of **58 PostgreSQL tables**.

The economy is closed, audited and purgeable — every unit of currency is accounted
for, which is the part that usually breaks in persistent multiplayer games. Backed by
**494 tests** and CI.

`TypeScript` · PostgreSQL · Redis · Docker · Discord.js

---

### 🚀 [Cosmos](https://github.com/Belzeeebuth/omarchy-cosmos-theme) · a space theme for Omarchy

NASA mission orange `#f97316` on deep-space black `#0c0a09`, with Hubble
astrophotography wallpapers, a frosted-glass Waybar and a galaxy lock screen.
Small, but it ties the whole desktop together.

---

## Toolbox

| | |
|---|---|
| **Desktop** | Arch Linux · Omarchy · Hyprland · KDE Plasma · Wayland · systemd · archiso |
| **Languages** | Python · TypeScript / JavaScript · Shell · GLSL · QML |
| **Interfaces** | Qt / PySide6 · QML · Discord.js |
| **Data** | PostgreSQL · Redis |
| **Ops** | Docker · GitHub Actions · QEMU / KVM |

---

## Earlier

Started out on Discord bots and small scrapers — Spacer, an RPG bot (2021), and
[reddit-channel-informations](https://github.com/Belzeeebuth/reddit-channel-informations)
(2020). The taste for automating whatever is in reach hasn't gone anywhere; the
projects just got bigger.

---

<div align="center">
<sub>Everything here runs on my own machine before it ships anywhere.</sub>
</div>

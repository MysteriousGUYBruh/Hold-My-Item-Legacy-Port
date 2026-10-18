# Hold My Items — Legacy Port

<p align="center">
  <a href="https://ibb.co.com/DP2qBjP9">
    <img src="https://i.ibb.co.com/bj9f4Gjs/Tak-berjudul122-20261018160926.png" alt="DroidBridge Launcher" width="128" height="128">
  </a>
</p>

[![CurseForge](https://img.shields.io/badge/CurseForge-Coming_Soon-F16436?style=flat-square&logo=curseforge&logoColor=white)](#)
[![Modrinth](https://img.shields.io/badge/Modrinth-Not_Planned-1BD760?style=flat-square&logo=modrinth&logoColor=white)](#)

### A First-Person Animation Port for Minecraft 1.12.2 Forge

**Bring more life to your first-person experience.**

Hold My Items — Legacy Port is a legacy adaptation project aiming to bring the distinctive first-person item animations of Hold My Items to Minecraft 1.12.2.

This project focuses on expressive item movement, recognizable swing animations, and a more dynamic held-item experience within Minecraft's older rendering environment.

Because Minecraft 1.12.2 uses a substantially different rendering and modding architecture from modern Minecraft versions, some features require adaptation rather than direct backporting. This release prioritizes a functional animation foundation while documenting areas where behavior still differs from the intended experience.

---

## ✨ Features

### ⚔️ Custom First-Person Swing Animations

Supported tools and weapons receive custom swing behavior designed to make item use feel more expressive.

Currently supported:

* Swords
* Pickaxes
* Axes
* Shovels
* Hoes

The goal is to preserve the familiar shape of Minecraft's interactions while adding more character to the first-person animation.

### 🏹 Bow Animation Behavior

Bow use includes additional first-person movement, with animation behavior intended to make the bow feel less static during gameplay.

Movement-related behavior is also present, although the complete modern animation experience is not guaranteed.

### 🍎 Vanilla-Style Actions

Some actions intentionally retain their familiar vanilla behavior, including eating and ordinary punching.

Keeping these interactions close to vanilla helps preserve expected gameplay behavior while custom animations are developed for other item types.

### ⚙️ Legacy Rendering Adaptation

The port targets the Minecraft 1.12.2 Forge environment rather than relying on modern rendering hooks.

This means animation logic must account for the older first-person renderer, player-arm rendering, held-item transformations, and the interaction between vanilla rendering and modded code.

---

## 🔬 Why Isn't Every Original Feature Available?

A backport involves more than copying animation values or translating source code. Minecraft's rendering pipeline changes between versions, and the original implementation may depend on rendering hooks or internal classes that do not exist in the same form in 1.12.2.

Features can therefore be missing, behave differently, or require a separate implementation.

### 🖐️ First-Person Hand Rendering

The player's hand and the held item are related, but they are not necessarily rendered through the same operations.

Minecraft's first-person renderer handles the player arm, held-item model, and their transformations. If a custom renderer replaces too much of that process—or fails to preserve the arm-rendering step—the item may appear while the hand disappears, or the two may no longer move together correctly.

A proper implementation needs to preserve or reproduce the relevant legacy rendering steps while applying the desired item animation.

**Why it may be missing or incorrect:** The original hand-rendering behavior cannot be assumed to transfer automatically to Minecraft 1.12.2. The exact cause in this build has not yet been confirmed, so this remains a rendering-compatibility investigation rather than a proven single-bug diagnosis.

### 🔄 Item-Swapping Transitions

Switching between held items may not reproduce the original animation timing or transition behavior.

Item changes can involve changes to the active stack, equip progress, renderer state, and animation state. Matching the original experience may require coordinating these elements instead of animating only the held item's swing.

**Current limitation:** Item swapping remains a known area where the port does not fully match the intended behavior.

### 🎞️ Animation Parity

Animation curves, timing, transitions, and secondary movement may differ from the original implementation.

These differences can arise from missing features, legacy rendering constraints, or incomplete recreation of the original animation logic. The current release should not be considered a complete one-to-one recreation.

### 🧩 Compatibility With Other Mods

Other mods can modify the first-person renderer, player arm, held-item transformations, or related rendering behavior.

Such changes may conflict with a custom renderer or produce results different from those seen in a minimally modified installation.

Compatibility with every rendering-related mod is not guaranteed.

---

## ⚠️ Known Issues

The following limitations are known or relevant to the current prototype:

* **Item swapping:** Transitions between held items do not yet fully match the intended original behavior.
* **Hand rendering:** The first-person hand may not reproduce the intended original behavior in every situation; the exact cause requires further verification.
* **Incomplete animation parity:** Some original animation details and secondary movements are not fully reproduced.
* **Vanilla-style actions:** Eating and ordinary punching retain vanilla-style behavior rather than receiving the same custom animation treatment as supported tools.
* **Mod compatibility:** Other mods that alter first-person rendering may cause conflicts or visual differences.

Not every issue will occur in every environment, and compatibility testing is still necessary.

---

## 🛠️ Development Priorities

Future work may focus on:

1. Improving item-switching transitions.
2. Investigating and restoring correct first-person hand rendering.
3. Refining animation timing and transitions.
4. Expanding animation coverage where technically feasible.
5. Testing interactions with other Forge mods that modify first-person rendering.

These are development goals, not guarantees that every feature will be implemented.

---

## 📦 Compatibility

* **Minecraft:** 1.12.2
* **Mod Loader:** Minecraft Forge
* **Release basis:** 1.0

Use a compatible Minecraft 1.12.2 Forge installation.

---

## 📜 Project Status

This is a community legacy-port project under active development. The current release provides a functional foundation for first-person item animations but does not claim complete feature parity with modern versions of Hold My Items.

The purpose of this release is to make the available functionality usable while clearly documenting the remaining gaps.

## ❤️ Credits and Permissions

Credit should be given to the original author and any other contributors where applicable.

This project should not be considered an official release or endorsed continuation unless explicitly authorized. Redistribution must comply with the original project's applicable licensing terms and permissions.

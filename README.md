<div align="center">

# WARFARE 2027
### Next-Gen Tactical Cross-Platform, XR & Voice-Controlled First-Person Shooter

![Engine](https://shields.io)
![Pipeline](https://shields.io)
![Language](https://shields.io)
![Voice AI](https://shields.io)
![XR](https://shields.io)
![Audio](https://shields.io)
![Input](https://shields.io)
![Platforms](https://shields.io)

</div>

---

## Executive Summary
**Warfare 2027** is a flagship, tactical First-Person Shooter (FPS) engineered in **Unity 6 LTS** on the **Universal Render Pipeline (URP)**. Built with a modular AAA C# namespace architecture (`warfare2027`), the project bridges native mobile/XR performance (**Android**, **Meta Quest 3**) with browser deployment (**WebGL**, **LG 65" webOS Smart TVs**). It features hands-free **Tactical Voice Command Recognition**, full **PS4 DualShock 4** hardware integration, real-time **Wwise & FMOD** spatial acoustics, weapon redeem systems, and instant multi-language localization.

---

## Comprehensive Unity Skills & Technical Architecture

### 1. Core Engine Architecture & Cross-Platform Compatibility
* **Namespace & Modular Design (`warfare2027`):** Cleanly decoupled subsystems governed by a centralized `GameManager` handling match states, mission progression, and scene lifecycles.
* **Hardware & Graphics Abstraction:** Real-time quality scaling via `GraphicsManager`, persistent player profiles in `GameSettings`, and cross-device compatibility through `UnityCompat`.
* **Native & Mobile Optimization:** Compiled with **Android NDK** support, strict garbage-collection minimization, and URP draw-call batching for locked frame rates on mobile chipsets and Smart TV browsers.

### 2. Tactical Voice Recognition & Hands-Free Commands
* **Real-Time Voice Command Controller (`VoiceCommandController`):** Low-latency speech recognition pipeline enabling hands-free tactical execution during active combat.
* **Combat & Arsenal Voice Triggers:** Instant voice-activated weapon switching, tactical reloads, ammo resupply requests, stance changes, and loadout commands.
* **Multi-Language & Cross-Platform Speech Bridge:** Unified speech-to-action listener supporting **English**, **Arabic**, and **Russian** voice keywords across native Android microphones and Web Speech API bridges.

### 3. Tactical FPS Combat, Ballistics & Arsenal Systems
* **Precision Locomotion & Perspectives:** Physics-driven `PlayerController` paired with `FPSCamera` and Third-Person perspective switching, featuring tactical sprinting, ADS (Aim Down Sights), procedural recoil curves, and dynamic FOV.
* **Modular Arsenal & Redeem System (`WeaponSystem`):** Data-driven weapon architecture managing fire modes, reload state machines, hitmarkers, wall-block collision physics, ammo/health pickups, and weapon code redemption.
* **Vehicular & Survival Mechanics:** Integrated `VehicleSystem` for drivable combat units alongside a modular `HealthSystem` supporting armor mitigation, hitboxes, and regeneration logic.

### 4. Virtual Reality (XR) & Hardware Input Ecosystem
* **Meta Quest 3 XR Integration:** Spatial tracking, stereoscopic rendering optimization, and hands-free voice + controller interaction for standalone VR deployment.
* **Unified Input Pipeline (`PlayerInputHandler`):** Built on the **Unity New Input System** and **WebHID** for seamless hot-swapping between **PS4 DualShock 4 controllers**, voice commands, touch overlays, and keyboard/mouse.
* **Smart TV Browser Engineering:** Custom viewport scaling and controller navigation tailored for large-screen **LG webOS TV** browsers.

### 5. Spatial Audio Engineering (Wwise & FMOD)
* **Audiokinetic Wwise Integration:** Custom `AkGameObj3rdPersonCam` spatial listener positioning, platform-conditional compilation directives, and real-time acoustic occlusion.
* **FMOD Studio Middleware:** Event-driven dynamic soundscapes, layered weapon ballistics (`WeaponAudio`), surface-aware footsteps, and interactive audio mixing.

### 6. Tactical UI/UX & Multi-Language Localization
* **Combat HUD & Voice Feedback (`GameHUD`):** Diegetic and screen-space tactical interface featuring dynamic `Crosshair` dispersion, directional hitmarkers, active voice-recognition status indicators, and mission telemetry.
* **Runtime Localization Engine (`SettingsMenu`):** Instant zero-reload language switching supporting **English (EN)**, **Arabic (AR)**, and **Russian (RU)** with full RTL/LTR layout adaptation.

### 7. Multiplayer Networking & Web/Native Hybrid Stack
* **Synchronized Combat (`MultiplayerSystem`):** Low-latency player state replication, server-bridged weapon switch events, and real-time combat synchronization.
* **Web & Native Companion Engines:** Parallel battle-engine modules (`warfare-core.js`, `battle-engine.js`) and C++17 / SDL2 native prototyping utilities for rapid cross-environment testing.

### 8. Custom Editor Tooling, AI Pipeline & DevOps
* **Automated Render Pipeline Suite:** Custom Unity Editor tools (`URPAutoSetup`, `URPValidator`, `URPBootstrap`, `URPValidatorWindow`) enforcing zero shader fallbacks and automated build verification.
* **AI-Assisted Asset & Code Workflow:** Integrated **Unity MCP** (Model Context Protocol), **Unity Spark**, **Meshy 3D** AI mesh generation, and **Substance 3D** PBR texturing pipelines.
* **Mobile Linux/Termux & Git Automation:** Headless CLI project auditing, local port orchestration (`8081`), `UnityYAMLMerge` scene/prefab conflict resolution, and Asset Store publishing compliance.

---

## Supported Tactical Voice Commands

| Action | English Command | Arabic Command | Russian Command |
| :--- | :--- | :--- | :--- |
| **Reload Weapon** | `"Reload"` / `"Change Mag"` | `"تلقيم"` / `"إعادة تعبئة"` | `"Перезарядка"` |
| **Switch Primary** | `"Primary"` / `"Rifle"` | `"سلاح رئيسي"` / `"بندقية"` | `"Основное"` |
| **Switch Secondary** | `"Secondary"` / `"Pistol"` | `"مسدس"` / `"سلاح ثانوي"` | `"Пистолет"` |
| **Throw Grenade** | `"Grenade"` / `"Frag Out"` | `"قنبلة"` | `"Граната"` |
| **Heal / Medkit** | `"Heal"` / `"Medkit"` | `"علاج"` / `"إسعاف"` | `"Аптечка"` |
| **Tactical Sprint** | `"Sprint"` / `"Run"` | `"ركض"` / `"انطلق"` | `"Бег"` |
| **Toggle Crouch** | `"Crouch"` / `"Take Cover"` | `"انبطاح"` / `"احتمي"` | `"Присесть"` |

---

## Project Directory Architecture

```text
Assets/
└── Scripts/
    ├── Audio/
    │   └── VoiceCommandController.cs
    ├── Camera/
    │   ├── FPSCamera.cs
    │   └── AkGameObj3rdPersonCam.cs
    ├── Core/
    │   ├── GameManager.cs
    │   ├── GameSettings.cs
    │   ├── GraphicsManager.cs
    │   └── UnityCompat.cs
    ├── Editor/
    │   ├── URPAutoSetup.cs
    │   ├── URPBootstrap.cs
    │   ├── URPValidator.cs
    │   └── URPValidatorWindow.cs
    ├── Health/
    │   └── HealthSystem.cs
    ├── Input/
    │   └── PlayerInputHandler.cs
    ├── Multiplayer/
    │   └── MultiplayerSystem.cs
    ├── Player/
    │   └── PlayerController.cs
    ├── UI/
    │   ├── Crosshair.cs
    │   ├── GameHUD.cs
    │   └── SettingsMenu.cs
    ├── Vehicle/
    │   └── VehicleSystem.cs
    └── Weapon/
        ├── WeaponAudio.cs
        └── WeaponSystem.cs
```

---

## Toolchain & Ecosystem
* **Core Engine:** Unity 6 LTS (URP) & Unity Asset Store Publisher Pipeline
* **Voice & Speech AI:** Unity Native Microphone API, Android SpeechRecognizer & Web Speech Bridge
* **Audio Middleware:** Audiokinetic Wwise, FMOD Studio & Reaper
* **3D & PBR Art Pipeline:** Meshy AI 3D, Substance 3D Painter & Substance 3D Designer
* **Native & Web Tooling:** C# (.NET Standard 2.1), C++17 (SDL2), Android NDK, JavaScript (WebHID)
* **Environment & Automation:** Visual Studio Code, Unity MCP, Ubuntu / Termux CLI, Git & UnityYAMLMerge

---

## Build & Verification Protocol
1. **Clone Repository:**
   ```bash
   git clone <repository-url>
   ```
2. **Initialize Engine:** Open project root in **Unity Hub** using **Unity 6 LTS**.
3. **Verify Microphone & URP Settings:** Enable microphone permissions under `Player Settings` and run `Tools > URP Validator` from the Unity Editor menu to verify URP asset bindings and shader integrity.
4. **Build Target:** Open `File > Build Profiles`, select **Android (APK / Meta Quest 3)** or **WebGL (Desktop / LG Smart TV)**, and execute build.

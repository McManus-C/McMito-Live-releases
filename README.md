<h1 align="center">McMito Live</h1>

<h3 align="center">Real-time muscle NIRS acquisition, protocol control and cuff automation for the repeated-occlusion test of mitochondrial oxidative capacity, with MCMITO analysis built in</h3>

<p align="center">
  <a href="https://github.com/McManus-C/McMito-Live-releases/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/McManus-C/McMito-Live-releases?label=latest%20release&color=0e9f9f"></a>
  <a href="https://doi.org/10.5281/zenodo.23762699"><img alt="DOI" src="https://img.shields.io/badge/DOI-10.5281%2Fzenodo.23762699-blue"></a>
  <a href="https://www.mcmito.com"><img alt="Website" src="https://img.shields.io/badge/website-mcmito.com-0b3d5c"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-lightgrey">
</p>

---

## Latest release

| | |
|---|---|
| **Version** | **1.4.3** (28 October 2026) |
| **Download** | [McMitoLive_Setup_1.4.3.exe](https://github.com/McManus-C/McMito-Live-releases/releases/latest), from the *Assets* list on the release page |
| **DOI** | [10.5281/zenodo.23762699](https://doi.org/10.5281/zenodo.23762699) (all versions) |
| **Analysis engine** | [MCMITO](https://github.com/McManus-C/McMito-releases) 1.4.3, built in |
| **Website** | [www.mcmito.com](https://www.mcmito.com) |
| **Contact / licence keys** | cmcman@essex.ac.uk |

---

## What McMito Live does

McMito Live runs the repeated-occlusion NIRS test of skeletal-muscle mitochondrial oxidative capacity (Ryan et al., 2012) from one screen. It streams muscle oxygenation from a Train.Red FYER sensor and force from a Tindeq Progressor over Bluetooth, guides the operator through a protocol built from blocks, switches a Hokanson E20 rapid cuff inflator at each phase boundary through a USB relay, and records everything, with markers, into a `.mcmito` session. The session opens straight into MCMITO, the analysis platform, which runs inside McMito Live's *Analyse* tab.

The whole application runs locally on your computer. Your data never leave it.

### Capabilities

| | |
|---|---|
| **Live acquisition** | Train.Red FYER over Bluetooth (SmO₂, O₂Hb, HHb), chosen from a sensor picker that lists every unit in range, strongest first. Live plots with change from baseline, sweet-spot bands and a blood-flow-corrected HbDiff pane. Every packet is also kept in a raw device file. |
| **Protocol builder** | Rest, resting occlusion, ischaemic calibration, MVC trials, exercise stimulus, isometric holds at a % of MVC, repeated occlusion sets (released at a fixed time or at a desaturation target) and operator checkpoints. Save, load and share protocols; the exact protocol run is written into every session. |
| **Cuff automation** | Inflates and deflates a Hokanson E20 through a Devantech USB-RLY02 relay at each phase boundary, with audible cues and a full cuff event log. A Cuff-Control-Only console runs protocols without a NIRS sensor. |
| **Force** | Tindeq Progressor force gauge: MVC trials, isometric holds with a target band, per-repetition force metrics, and a participant view for a second screen showing the current stage with its timer, the next stage with its duration, and a live force bar. |
| **Physiological calibration** | Captures the SmO₂ nadir and reperfusion peak of the ischaemic calibration live, so targets and tiles can be shown as a % of the physiological range. |
| **Sessions and exports** | `.mcmito` sessions with markers, protocol, force trace and protocol events; autosave and resume after an interruption; CSV, JSON and MATLAB exports. |
| **Analysis** | MCMITO 1.4.3 is built in: blood flow correction, calibration, per-occlusion slopes, recovery-curve fitting, exercise and force dose, Excel and PDF reports. |

---

## Hardware

| Device | Status |
|---|---|
| Train.Red FYER (NIRS) | Supported |
| Tindeq Progressor 200 (force) | Supported |
| Hokanson E20 rapid cuff inflator with a Devantech USB-RLY02 relay | Supported |
| Moxy 5 (NIRS) | Experimental; not yet validated with hardware |

- One NIRS sensor at a time. Sensors are **not** paired in Windows Bluetooth settings: McMito Live scans for them itself. A Progressor that is asleep does not advertise; squeeze it to wake it before scanning.
- The relay uses Windows' built-in USB serial driver. Set its COM port under *Preferences → Hardware*; without a port the app runs a simulated cuff.

## Participant safety

McMito Live is a research aid, **not a safety system**. Cuff pressure is set on the inflator, not by the software, and software, computer, Bluetooth, USB or power faults can stop, delay or repeat a command. A trained operator must be present throughout every occlusion and able to release the cuff manually at the inflator. You are responsible for safe pressures and durations, for screening and supervising participants, and for working within your ethical approval and the manufacturers' instructions. Section 5A of the licence agreement sets this out in full.

---

## Download and install

1. Open the [latest release](https://github.com/McManus-C/McMito-Live-releases/releases/latest) and download **`McMitoLive_Setup_<version>.exe`** from the *Assets* list. (The `manifest.txt` file alongside it is used by the app's own update check; you do not need it.)
2. Run the installer, accept the licence agreement and follow the steps. McMito Live installs per user, so no administrator rights are needed, and appears in the Start menu. It can sit alongside a standalone MCMITO installation.

### Activating your licence

McMito Live needs its own licence key; an MCMITO key does not open it.

1. On first launch the activation window shows your **Machine ID**, with a *Copy* button.
2. Email the Machine ID to **cmcman@essex.ac.uk**.
3. Paste the key you receive and click **Activate**.

Each licence is tied to one computer and runs for a fixed period. The status bar warns you before it expires, and *Help → Licence…* accepts a renewal key without reinstalling.

### System requirements

- Windows 10 or 11 (64-bit) with a Bluetooth Low Energy adapter.
- A USB port for the cuff relay, if you automate the cuff.
- No Python or other dependencies; everything is bundled.

### Where your files are

- Recordings: `Documents\McMito Live\captures`
- Settings and protocols: `%USERPROFILE%\.mcmito_live`
- Log file (useful if something goes wrong): `%USERPROFILE%\.mcmito_live\logs\mcmito_live.log`
- Licence: `%LOCALAPPDATA%\MCMITO_LIVE`

None of these is inside the program folder, so updating or uninstalling keeps them.

### Updating

Use *Help → Check for updates…*. The app only installs releases published here that carry a valid signature and a matching checksum. Your licence, settings, protocols and recordings are kept.

---

## How to cite

McMito Live records the data; the analysis is MCMITO. Please cite MCMITO and the method, giving the version you used in the brackets (the DOI covers every version):

> McManus, C. (2026). *MCMITO: Near-infrared spectroscopy analysis of skeletal-muscle mitochondrial oxidative capacity* (Version 1.4.3) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.21976705

> Ryan TE, Erickson ML, Brizendine JT, Young HJ, McCully KK. Noninvasive evaluation of skeletal muscle mitochondrial capacity with near-infrared spectroscopy: correcting for blood volume changes. *Journal of Applied Physiology*. 2012;113(2):175–183. https://doi.org/10.1152/japplphysiol.00319.2012

If you use blood flow correction Method 4 (the default for McMito Live data) or the best-fit slope window, also cite:

> Beever AT, Tripp TR, Zhang J, MacInnis MJ. NIRS-derived skeletal muscle oxidative capacity is correlated with aerobic fitness and independent of sex. *Journal of Applied Physiology*. 2020;129(3):558–568. https://doi.org/10.1152/japplphysiol.00017.2020

If you describe the acquisition and cuff control, also cite McMito Live:

> McManus, C. (2026). *McMito Live: real-time muscle NIRS acquisition, protocol control and cuff automation for the repeated-occlusion test of mitochondrial oxidative capacity* (Version 1.4.3) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.23762699

---

## Licence and intended use

McMito Live is **proprietary, licensed software** provided under an End-User Licence Agreement shown during installation; a copy, `MCMITO_LIVE_EULA.txt`, is installed beside the program. This repository holds installers and update manifests only; it does not contain source code.

McMito Live is intended for **research and educational use only and is not a medical device**. It is not for the diagnosis, prevention, monitoring, prediction, prognosis, treatment or alleviation of disease, and it has not been assessed by the MHRA or any other regulatory authority.

## Changelog

### 1.4.3 — 28 October 2026

Builds in MCMITO 1.4.3 (the first update since 1.4.1; there was no public 1.4.2 of McMito Live). Recordings store the sensor's "no reading" zeros as blanks, and the raw-hex preference applies to the current session. In the Analyse tab: settings no longer revert after Compute slopes, session files open in the standalone MCMITO, the Protocol boxes drive the analysis, cuff markers can be loaded from a `.mcmito` for an imported raw device file, the per-occlusion fit figure keeps its panel size for long protocols, and the Data Cleaning controls scroll on their own. Acquisition and cuff control are unchanged. See the [release notes](https://github.com/McManus-C/McMito-Live-releases/releases/tag/v1.4.3).

### 1.4.1 — 12 October 2026

First public release. See the [release notes](https://github.com/McManus-C/McMito-Live-releases/releases/tag/v1.4.1).

---

## Contact

Chris McManus — University of Essex — cmcman@essex.ac.uk — [www.mcmito.com](https://www.mcmito.com)

© 2026 Chris McManus. All rights reserved.

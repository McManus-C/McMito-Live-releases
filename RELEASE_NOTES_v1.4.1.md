# McMito Live 1.4.1 — 12 October 2026

The first public release of McMito Live: real-time muscle NIRS acquisition, protocol control and cuff automation for the repeated-occlusion test of mitochondrial oxidative capacity, with MCMITO 1.4.1 analysis built in. Its version number matches the MCMITO release it embeds.

**Download:** `McMitoLive_Setup_1.4.1.exe` from the *Assets* list below (the `manifest.txt` file is used by the in-app updater; you do not need it).
**Licence:** McMito Live needs its own key. On first launch, copy the Machine ID from the activation window and email it to cmcman@essex.ac.uk.

---

## What is in this release

- **Live acquisition** from a Train.Red FYER over Bluetooth (SmO₂, O₂Hb, HHb), with a sensor picker, live plots, change from baseline, sweet-spot bands and a blood-flow-corrected HbDiff pane. Every packet is also kept in a raw device file.
- **Protocol builder**: rest, resting occlusion, ischaemic calibration, MVC trials, exercise stimulus, isometric holds at a % of MVC, repeated occlusion sets released at a fixed time or at a desaturation target, and operator checkpoints. Protocols can be saved and shared, and the exact protocol run is written into each session.
- **Cuff automation**: a Hokanson E20 switched through a Devantech USB-RLY02 relay at every phase boundary, with audible cues and a cuff event log; a Cuff-Control-Only console for protocols without NIRS.
- **Force**: Tindeq Progressor MVC trials and isometric holds with a target band, and a **participant view** for a second screen showing the current stage with its timer, the next stage with its duration, and a live force bar.
- **Physiological calibration** captured live, so targets and tiles can be shown as a % of the physiological range.
- **Sessions**: `.mcmito` files with markers, protocol, force trace and protocol events; autosave and resume; CSV, JSON and MATLAB exports.
- **Analysis**: MCMITO 1.4.1 in the *Analyse* tab, opening the session you have just recorded. McMito Live data open with blood flow correction **Method 4 (Beever, 2020)**, because Live records absolute O₂Hb and HHb, on which the Ryan methods do not remove blood-volume shifts. The Ryan methods remain available with a caution.
- **Licensing and updates**: machine-bound licence keys, *Help → Licence…* for renewal, and *Help → Check for updates…* for signed in-app updates.

## If you used a pre-release build

Pre-release builds were used in pilot testing. This release fixes the problems found there:

- **Force gauge dropouts.** The force trace no longer stops every 5 minutes; Tare is no longer needed to bring it back. The gauge's battery is now read when it connects and during a tare.
- **Time base.** Marker and cuff times now line up with the NIRS trace; earlier builds could drift by more than 2 s over a long session. Recordings made with earlier builds keep their original time base. Their raw device file (`*.trainred.raw.csv`) can be imported into MCMITO 1.4.1 on the session clock if you need the corrected timing.
- **Blood flow correction default.** Preferences saved by an earlier build that still hold the old Method 2 default move to Method 4 once. Method 1, Method 3 or Off, if you chose them, are kept.
- **Participant view** now shows the current stage with its timer and the next stage with its duration.
- Launching without recording no longer leaves an empty CSV file in the captures folder.
- *Check for updates* now says when nothing has been published, rather than reporting a connection problem.
- The licence agreement (`MCMITO_LIVE_EULA.txt`) is installed beside `McMitoLive.exe`.

## Participant safety

McMito Live is a research aid, not a safety system. Cuff pressure is set on the inflator, not by the software, and faults can stop, delay or repeat a command. A trained operator must be present throughout every occlusion and able to release the cuff manually. See section 5A of the licence agreement.

## Known limitations

- One NIRS sensor at a time. Moxy 5 support is experimental and has not yet been validated with hardware.
- The Train.Red battery level is shown only if the sensor reports it.
- How best to reference absolute O₂Hb and HHb before a Ryan correction is still under evaluation; Method 4 is the default meanwhile.
- Windows 10 / 11 only.

## Citation

Please cite MCMITO and the method: McManus, C. (2026). *MCMITO: Near-infrared spectroscopy analysis of skeletal-muscle mitochondrial oxidative capacity* (Version 1.4.1) [Computer software]. Zenodo. https://doi.org/<DOI> · Ryan TE et al. *J Appl Physiol* 2012;113(2):175–183 · and, for Method 4, Beever AT et al. *J Appl Physiol* 2020;129(3):558–568.

McMito Live is for research and educational use only and is not a medical device.

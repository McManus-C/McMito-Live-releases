# McMito Live 1.4.3 — 28 October 2026

McMito Live 1.4.3 builds in MCMITO 1.4.3, and its version number matches the MCMITO release it embeds. It is the first update since 1.4.1 (there was no public 1.4.2 of McMito Live), so it also brings the MCMITO 1.4.2 changes to the *Analyse* tab. Acquisition, protocol control, cuff automation and force capture are unchanged from 1.4.1.

**Download:** `McMitoLive_Setup_1.4.3.exe` from the *Assets* list below (the `manifest.txt` file is used by the in-app updater; you do not need it).
**Already on 1.4.1?** Use *Help → Check for updates…*. Your licence, settings, protocols and recordings are kept.

---

## Recordings

- **Sensor dropouts are saved as blanks.** A Train.Red FYER sends 0 for a channel it has no reading for (SmO2 while the sensor settles and when it lifts off, O2Hb / HHb for about the first second). The `.mcmito` file and the CSV, JSON and MAT exports now hold a blank there instead of 0. The raw device file (`*.raw.csv`) still records exactly what the sensor sent. Recordings made with 1.4.1 are blanked when they are opened.
- **The raw-hex preference applies straight away.** Ticking *Also keep each packet's raw bytes (hex column)* in Preferences after launch previously had no effect until the next session. It now applies to the current session as long as its raw device file has not started; once it has, the status bar says the change applies from the next session.

## Changes in the Analyse tab (MCMITO 1.4.3 and 1.4.2)

- **Analysis settings no longer revert after Compute slopes (1.4.3).** A display element that failed to draw could make the page undo your most recent setting changes and re-run *Compute* with the defaults. That roll-back is now blocked, and the failing element is logged to `%USERPROFILE%\.mcmito\frontend_errors.log` (please email it to cmcman@essex.ac.uk if you see the notice).
- **Session files open in the standalone MCMITO (1.4.2).** MCMITO 1.4.1 could not open `.mcmito` files saved by McMito Live; MCMITO 1.4.2 and later can, so a recording can be sent to someone who has only MCMITO.
- **The Protocol boxes now drive the analysis (1.4.2).** Editing *Sets*, *Occlusions / set*, *Cycle period* or *Occlusion duration* after loading a recording now updates auto-detect, the slope window, the Method 1 windows, the fit overlay and the Excel metadata. Earlier, only the marker counter changed. Markers are kept; slopes and fits computed under the previous protocol are cleared, with a message.
- **Cuff markers for a raw device file (1.4.2).** After importing a raw device file (`*.trainred.raw.csv`) in the Analyse tab, *Load cuff markers from .mcmito* takes the markers McMito Live placed at the cuff commands from the `.mcmito` saved with that recording, on the same session clock, so auto-detect is not needed.
- **Per-occlusion fit figure** keeps its panel size for long protocols (for example 2 × 17), with each set starting on a new row (1.4.2).
- **Data Cleaning controls scroll on their own**, and a fixed readout in each plot's title strip replaces the floating hover box (1.4.2).

## Compatibility

- Algorithm version 2 (unchanged). Recordings and sessions from 1.4.1 open unchanged.
- If you analysed a recording in 1.4.1 and changed the Protocol boxes after loading it, re-run that analysis after checking the Protocol boxes.

## Participant safety

McMito Live is a research aid, not a safety system. Cuff pressure is set on the inflator, not by the software, and faults can stop, delay or repeat a command. A trained operator must be present throughout every occlusion and able to release the cuff manually. See section 5A of the licence agreement.

## Citation

Please cite MCMITO and the method: McManus, C. (2026). *MCMITO: Near-infrared spectroscopy analysis of skeletal-muscle mitochondrial oxidative capacity* (Version 1.4.3) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.21976705 · Ryan TE et al. *J Appl Physiol* 2012;113(2):175–183 · and, for Method 4, Beever AT et al. *J Appl Physiol* 2020;129(3):558–568. To cite McMito Live itself: McManus, C. (2026). *McMito Live: real-time muscle NIRS acquisition, protocol control and cuff automation for the repeated-occlusion test of mitochondrial oxidative capacity* (Version 1.4.3) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.23762699 (the DOIs here cover every version).

McMito Live is for research and educational use only and is not a medical device.

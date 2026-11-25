**OSSUARY: USER GUIDE**

**PARDON OUR DUST.** This guide was put together fast from the app's own screens and notes. If a dial does something slightly different from what it says here, trust your ears and tell me.

OSSUARY is a spectral dynamics tool that runs in your browser. It smooths and tames sound frequency by frequency, and it lets you listen to exactly what it took out.

---

**1. Getting started**

This section turns it on, loads some sound and gets you hearing the effect.

1. Open the page and tap POWER to turn it on.
2. Pick an input under Sys: Test signal (Tone, Noise, Sib or Series), File…, or Mic.
3. For a file, tap File… and choose an audio file, or drop one on the page. Tap Play, and Loop if you want it to repeat.
4. Tap PRESET and pick a starting point, for example SHROUD GLUE or NIGHT WATCH.
5. Tap BYPASS (labeled DRY) to hear the original, then tap it again to hear the result.
6. Tap AUDITION until it says REMOVED to hear only what OSSUARY took out.
7. Adjust the dials on the Gate, Crypt, Shroud, Velvet, Exhume and Resurrect tabs. Switch tabs by tapping the dock at the bottom or swiping the page.
8. Tap RENDER to process the whole file and save it.

---

**2. The top controls (on every tab)**

- **PRESET:** loads a starting setting. Use [ and ] on the keyboard to step through them. The list is INIT, SHROUD GLUE, RESONANCE VEIL, MUD CRYPT, HARSH EXORCISM, RISE THE ROOT, AIR EXHUMED, FULL RITUAL, SCORCHED EARTH and NIGHT WATCH.
- **COMPARE:** two slots, A and B, to flip between two settings. Tap C on the keyboard. Copy the active slot to the other one from the Sys tab.
- **DRY / BYPASS:** hears the original with no processing. (B)
- **MATCH:** matches the loudness of the processed sound to the original, so a quieter result does not fool you into thinking it is better. It works on FINAL only. (G)
- **AUDITION:** chooses what you hear. (M)
  - FINAL: the result.
  - REMOVED: what the chain took out.
  - RECOVERED: what Exhume and Resurrect put back.
  - PERMANENT: what is gone for good.
  - PREPARED: the signal as it goes into the later stages.
- **AUDIT:** hear that choice for the whole chain (CHAIN) or for one stage: GATE, CRYPT, SHROUD or VELVET. (N)
- **ORDER:** the order the stages run in. The default is Gate, Crypt, Shroud, Velvet. (O)
- **Level meter:** shows the output level in dB.
- **The skulls:** drag a skull up or down to change a setting. Hold Shift for fine control and double-tap to reset it. Smoke is the input level, blood is what was removed and antidote is what was restored. (K)

---

**3. The stages**

One analysis feeds every stage, and each stage works bin by bin across the spectrum.

**Gate (curve EQ)**
- Draws a stereo curve whose gains feed the detectors that come after it.
- **GATE ON** switches it on. **GATE LINK** makes left and right share one curve. Turn it off to give each side its own.

**Crypt (four-band compressor)**
- Three crossovers split the sound into four bands: **XOVER 1, 2 and 3**.
- Each band has **B1 to B4 ON**, **THRESH** and **RATIO**. A band you switch off does nothing, exactly.
- **CRYPT ATK** and **CRYPT REL** set how fast it reacts and lets go.

**Shroud (spectral compressor)**
- Turns down each frequency bin separately when it gets too loud.
- **THRESHOLD**, **RATIO**, **ATTACK** and **RELEASE** work like a compressor's.
- **MAX GR** limits how much any bin can be turned down.
- **TILT** leans the effect toward the low or the high end.
- **SMOOTH** smooths the gain across neighboring bins.
- **MIX** blends the result with the original.
- **GHOST** plays what was removed.

**Velvet (resonance tamer)**
- Per-bin dynamics, with the gain smoothed per octave.
- **VEL THRESH**, **VEL RATIO**, **VEL DEPTH**, **VEL OCT SG** (how wide the smoothing is), **VEL ATK** and **VEL REL**.

**Exhume (focused restore)**
- A second pass that recovers part of what the stages above removed.
- Tap the display to aim a restore at a frequency. Drag to move it. Double-tap to remove it.
- **EXH THRESH**, **EXH RATIO**, **EXH OCT SG**, **EXH DEPTH**, **EXH ATK** and **EXH REL** shape it. **RESTORE** sets how much comes back.
- Tap a line to pin it (always restore). Tap again to veto it (never restore). Tap again for auto.

**Resurrect (harmonic restore)**
- Aim a focus on the Exhume page. Resurrect then finds its harmonics and brings them back.
- **TARGET** and **TGT WIDTH** set what it aims at and how wide that is.
- **ORDERS** is how many harmonics it looks for, **ROLL-OFF** is how quickly the higher ones fade and **TRACK** is how closely it follows the sound.

---

**4. The Loss tab**

Shows how much each stage removed, in dB against the input, plus what was recovered, what is permanent and the net. The bars are power, so recovered and permanent will not add up to removed. The waveforms do add up. That energy is not lost.

---

**5. The Sys tab**

- **Compare slots:** A and B. Copy the active one to the other.
- **Patch file:** EXPORT PATCH saves your settings and groups, with no audio. IMPORT PATCH loads one.
- **Skull:** choose its look.
- **Input:** none, a test signal, a file or the microphone.
- **Test signals:** Tone, Noise, Sib (a sibilant, "sss"-like sound) and Series. Series is 200 Hz and its harmonics plus one stray 530 Hz tone. Aim Exhume at 200 Hz, raise TARGET and use Resurrect. The stray tone should stay removed.
- **Keys:** [ ] preset, C compare, B bypass, G match, M audition, N audit stage, O order, K skull.

Presets and compare slots hold the sound. Level, bypass, audition, match and split stay where you put them.

---

**6. Files, RENDER, PRINT and TAKES**

- **RENDER:** processes the loaded file offline, faster than real time. The output is the same length as the source and lines up with it. It is a 32-bit float WAV, and the source's metadata is kept. It works for mono up to 7.1 wide.
- **PRINT:** records what you hear in AUDITION as it leaves the engine, as a 32-bit float WAV. Print REMOVED, RECOVERED and PERMANENT with bypass off, and they add up as waveforms.
- **TAKES:** the list of takes. It is shared with KAIJU-BLUE at the same web address. Takes you record in KAIJU-BLUE appear here, and a processed take goes back to KAIJU-BLUE as a new take. **CLEAR** empties the list.
- **RECALL:** brings back a processed take's settings and its original.

---

**7. GROUPS and MONITOR (surround)**

- **GROUPS:** FRONT, CENTER, LFE, SURR and BACK. Each can have its own settings. Pick a group, and the dials edit that group.
- **SHARED:** all groups use one set of settings.
- **SIDES:** the two sides of a pair can be linked or split by any amount, from SIDES LINKED to fully split.
- **ALL LINK:** groups with the same settings turn down together, so front and rear do not drift apart. It works in RENDER and in live monitoring, including when the left and right gate curves differ.
- **MONITOR:** FULL MIX or one GROUP, in STEREO or MONO. DIRECT, PHONE, SMALL, LARGE, CAR and STUDIO emulate those speakers. The monitor is never printed or rendered.

---

**8. Where it runs and what the status line says**

- Current browsers run the engine in the audio worklet. Older ones switch to backup mode, which runs on the main thread. The sound can stutter there, but RENDER stays exact.
- In backup mode the status line says: "backup mode: main thread, may stutter · render is exact".
- If the sound drops out, OSSUARY grows its buffer and then plays only the group you are editing. Messages you may see:
  - "buffer now 4096 samples" (the buffer was made bigger)
  - "now front alone" (only the front group plays live)
  - "this device cannot keep up live · RENDER is exact" (live play is not possible, but RENDER still works)
- If a browser has no Web Audio at all, nothing plays live. RENDER still works.
- Old iPhones and iPads (iOS 12 and older) load the page, but the knobs and curves cannot be dragged.
- Your groups are not kept when you reload the page. Export a patch to keep them.
- 10.2 layouts are not supported.

---

**9. License**

OSSUARY is free to use, including for paid work, and you own everything you make with it. Companies with 100 or more people or 1,000,000 USD or more in yearly revenue need a separate license. See the LICENSE file.

---

**Conclusion**

Load a sound, pick a preset, flip BYPASS and listen to REMOVED. When you can hear what is going, you can decide what stays. Take the result to RENDER or PRINT, or send it back to KAIJU-BLUE as a take.

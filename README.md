# OSSUARY

A spectral dynamics tool that runs in your browser. It smooths and tames sound frequency by frequency, and it lets you listen to exactly what it took out. One HTML file. No install, no account, no network once the page has loaded.

OSSUARY is the companion to KAIJU-BLUE. Takes you record there appear in OSSUARY's list automatically, and processed takes go back to KAIJU-BLUE as a new take.

**Open it:** https://evansciralabs.github.io/OSSUARY/ (or download `index.html` here and open it from your computer)

**User guide:** USER-GUIDE.md

## What it does

One analysis feeds a chain of stages, each working bin by bin across the spectrum:

- **GATE:** a stereo curve EQ whose gains feed the detectors. Left and right can share a curve or have their own.
- **CRYPT:** a four-band compressor with three crossovers. A band you switch off does nothing, exactly.
- **SHROUD:** a spectral compressor that works on every frequency bin separately.
- **VELVET:** a resonance tamer: per-bin dynamics, with gain smoothed per octave.
- **EXHUME:** a second pass that recovers part of what the stages above removed.
- **RESURRECT:** aim at a frequency and bring removed content back.

You can listen to the result (FINAL), to what was taken out (REMOVED), to what was recovered, and to what is permanently gone, for the whole chain or for one stage. A loss ledger shows how much each stage removed.

## Working with files

- **Inputs:** an audio file (pick or drop one), the microphone, or built-in test signals.
- **RENDER** processes a file offline, faster than real time. The output is the same length as the source and lines up with it. It is a 32-bit float WAV, and the source's BWF and iXML metadata are kept.
- **Layouts:** mono, stereo, 2.1, 3.0, quad, 4.1, 5.1, 7.1 and 7.1 wide.
- **GROUPS:** front, center, LFE, surround and back groups can each have their own settings.
- **Linking:** the two sides of a pair can be linked or split by any amount, and groups can be linked to each other. At full link, groups with the same settings are turned down together, so front and rear do not drift apart. Linking is exact in RENDER and in live monitoring, including when the left and right gate curves differ.
- **MONITOR:** hear the full mix, or one group, in stereo or mono, with phone, speaker, car and studio-monitor emulations.
- **Patch files:** export and import your settings, without any audio. RECALL brings back a processed take's settings and its original.
- **TAKES and PRINT:** a take store shared with KAIJU-BLUE, and a print of the audition stream.

## Where it runs

OSSUARY has one engine. Every way of running it uses the same code and the same maths. What changes is where the engine runs.

- **Worklet:** current browsers. Live groups and linking work for every group.
- **Backup (main thread):** browsers without AudioWorklet, or `#sp` on the address. Live groups and linking work, but the sound can stutter.
- **Render only:** no Web Audio at all. Nothing plays live; RENDER still works.
- **Rack:** inside the SRC-D suite. One stereo engine, run by the host.

RENDER works on every tier and gives the same file, bit for bit.

Minimum browsers, read from the source and from published support data (not tried on real old browsers):

- live, normal: Chrome or Edge 66, Firefox 76, Safari 14.1
- live, backup mode: Chrome 55, Firefox 59, Safari 13
- RENDER: wherever the page runs

## What has and has not been checked

Tested in headless Chrome 153 on a cloud server with no sound card. Results were judged from captured samples, never by ear.

- RENDER is byte-identical across the engine's builds for everything except the fix that made linking exact with different gate curves.
- Linked groups track to about −137 dB live and in RENDER.
- Older browsers were simulated by removing features from Chrome. The page loads and RENDER stays exact in each case.

**Not verified:** any real device, any real old browser, and how any of it sounds. If you try it on an old or slow device, I would like to hear what happened.

## Known limits

- In backup mode the sound can stutter, because the screen and the sound share one thread. OSSUARY grows its buffer and then plays only the group you are editing when it has to, and says so on the status line.
- On an old iPhone or iPad (iOS 12 and older) the page loads, but the knobs and curves cannot be dragged.
- 10.2 layouts are not supported.
- Your groups are not kept when you reload the page. Export a patch to keep them.

## Support

OSSUARY is free for small companies under the limits in the license (see License). If it is useful to you and you want to chip in, you can: https://PayPal.me/LastHitLeft/5

## License

OSSUARY is source-available under the PolyForm Small Business License 1.0.0. It is free for companies with fewer than 100 people and under 1,000,000 USD (2019 dollars, adjusted for inflation) in yearly revenue. Larger companies need a separate license from me: contact MavArtCreator@gmail.com.

Audio you make with OSSUARY is yours.

See the LICENSE file for the full terms.

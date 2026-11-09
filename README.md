# Pad Practice 🥁

A free, open-source practice trainer for electronic drum pads. Plug in your pad over USB, play along with the click, and see every hit graded live: how many milliseconds early or late it landed, whether you used the right hand, and how even your dynamics are.

Built and tested with the Roland SPD-SX PRO, and it should work with any pad or kit that sends MIDI notes over USB.

## Features

- Metronome with a one-bar count-in, 40–240 BPM
- Live timing lane showing your last 20 hits, early to late
- Drills: timing only, single strokes, double strokes, paradiddles, six-stroke rolls
- Quarter notes, eighths, triplets, and sixteenths
- Beat lessons with a 9-pad layout (three slim top pads and six large pads) that lights up which pad to hit and a step grid that grades every note
- Pad layout editor: choose the sound and the real pad (MIDI note) for each of the 9 squares, and save named layouts to switch between kits
- “Listen first” mode that plays the beat back with the pads lighting up
- Strict, normal, and relaxed timing windows (±15, ±30, ±50 ms)
- Optional auto speed-up after two clean bars
- Session stats: on-time %, rushing or dragging, spread, dynamic evenness
- Accents and ghost notes graded by how hard you hit
- Beat maker for your own beats, with share codes so others can load them
- Gap click that drops out for a bar or more to test your internal time
- Session report with insights and charts on where you rush or drag
- Tempo sync: sends MIDI clock so your pad’s click and loops follow the app
- Levels and XP for on-time notes, clean bars, finished sessions, and daily practice
- 24 drills and beats, with new ones unlocking as you level up (from rock and singles at level 1 to linear funk, a 6/8 bell groove, and blast beats)
- Daily challenge with bonus XP and a challenge streak
- 17 trophies in bronze, silver, and gold, each with bonus XP
- Progress saved in your browser, with backup download and restore to move it between devices
- Session history saved in your browser
- Guides tab with step-by-step walkthroughs for connecting and mapping your pads
- Automatic latency calibration, plus a manual latency slider
- On-screen pads with center and edge zones (rim shots on the edges), plus F/J keys for practicing without hardware
- 13 drum sounds in 7 kits (Studio, Rock, Metal, Jazz, Funk, Hip-hop, and 808 electronic), velocity-sensitive and synthesized in code with no samples

## Getting started

1. Connect your pad to a computer with USB. For the SPD-SX PRO, install Roland’s USB driver first.
2. Open the app in **Chrome** or **Edge** (Web MIDI isn’t supported in Safari or Firefox). Chrome on Android also works with a USB-OTG adapter.
3. Click **Connect pads** and allow MIDI access.
4. Click **Set right-hand pad** and hit a pad, then do the same for the left. For beat lessons, click **Learn all notes** and hit the real pad you want for each square in turn, or use **Edit layout** to change one square’s sound or pad. Save your setup under a name to switch between kits.
5. Press **Start** (or the space bar) and play along.

If steady playing always reads late, move the latency slider until it centers near zero.

Stuck? Open the **Guides** tab in the app for an illustrated walkthrough on connecting your pad, a guide to mapping your pads, a live MIDI test, and troubleshooting.

## Running locally

It’s a single HTML file with no build step. Web MIDI needs a secure context, so serve it from localhost rather than opening the file directly:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## How it works

The pad sends a MIDI note-on message (note number + velocity) for each hit. The app schedules the click with the Web Audio API, records the exact time of every click, and compares each incoming hit’s timestamp against the nearest click to get the offset in milliseconds.

## Contributing

Ideas, bug reports, and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add a beat or send a change. Some things on the wish list:

- Custom pattern editor
- Multi-pad grooves (kick, snare, hi-hat)
- Progress charts over time
- Exporting session history

Please open an issue first for larger changes so we can talk them through.

## Disclaimer

This is an independent community project and is not affiliated with, endorsed by, or sponsored by Roland Corporation. Roland and SPD-SX are trademarks of Roland Corporation.

## License

[MIT](LICENSE)

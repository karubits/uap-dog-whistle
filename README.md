# UAP "Dog Whistle" 🛸

A single-page Web Audio synth that builds the six-layer "UAP summoning" signal from a viral April 2025 post on X, and puts it next to what the science actually says. Pulse it or play it straight. Low volume, because volume does not matter in this context.

**Live site:** [whistle.uap-facts.com](https://whistle.uap-facts.com/)

## What the page does

- **Generates all six layers in the browser** with the Web Audio API, no server and no dependencies beyond Google Fonts:
  - **Schumann carrier**: a 100 Hz sine amplitude-modulated at 7.83 Hz
  - **528 Hz harmonic**: sine with a slow tremolo
  - **17 kHz ultrasonic ping**: 60 ms soft ping every 3 s
  - **Organic 2.5 kHz chirps**: clusters of 3–5 randomised upward sweeps every 10 s
  - **432 Hz ambient pad**: four detuned voices plus a 216 Hz sub through a drifting low-pass filter
  - **Breath layer**: white noise through a wandering bandpass, swelling at about 13 breaths per minute
- **Controls**: per-layer on/off and level, Straight or Pulse mode with adjustable pulse period, master volume (defaults to −14 dB), a compressor on the master bus as a hearing safeguard. Settings persist in the browser.
- **Visuals**: a live log-frequency spectrum with markers at each named frequency, activity lights for pings and chirps, an animated starfield, and a luminous orb that swells and sparks with the signal. On mouse devices the cursor is a small orb too.
- **WAV export**: 1, 3 or 10 minutes rendered offline at 48 kHz, 16-bit stereo, using the current layer mix and mode.
- **Tone by tone**: for each layer, the spiritual or esoteric claim next to the scientific or technical reality.
- **Audio versus RF**: the groups the "dog whistle" name comes from (Skywatcher, Skinwalker Ranch) describe radio-frequency emissions around 1.6 GHz, not sound. The page compares the two and marks what checks out, what is partly supported, and what is unverified.
- **References and attribution** for every source used.

## Running it

Open `index.html` in Chrome or Firefox. Phone and laptop speakers cannot reproduce 100 Hz or 17 kHz well, so use headphones or a decent speaker if you want every layer present.

To serve it locally:

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deployment

The site is static: `index.html` plus `CNAME`. The workflow in `.github/workflows/pages.yml` syntax-checks the inline script and publishes to GitHub Pages on every push to `main` that touches the site files.

For the workflow to publish, the repository's **Settings → Pages → Source** must be set to **GitHub Actions**. GitHub Pages on a free account requires the repository to be public.

## Safety

- The 17 kHz ping is inaudible to most adults but can be irritating to children and pets.
- Start quiet. High-frequency sound at high volume can damage hearing. The compressor tames peaks but is not a substitute for a sensible volume.
- Do not attempt the RF version described in the Audio versus RF section. Transmitting around 1.6 GHz can jam GPS and GLONASS receivers nearby and is illegal without a licence.

## Important notice

The recipe came from an unverified source on X. The page reproduces it as a programming and listening exercise and makes no claim that it does anything. It has no connection to Skywatcher, Skinwalker Ranch or any device they use. There is no scientific evidence that any sound, pulsed or continuous, summons anomalous phenomena.

## Credits

- **Recipe**: [post by @jasonwilde108 on X](https://x.com/jasonwilde108/status/1910816547070685522), April 2025
- **Earlier generator**: [CodePen by Ionut Stoica](https://codepen.io/ionut-stoica-the-bold/pen/MYWNQLO), shared in the [r/aliens thread](https://www.reddit.com/r/aliens/comments/1jyf331/dog_whistle_instructions/)
- **RF context**: [r/UFOs: Skywatcher's UAP "Dog Whistle"](https://www.reddit.com/r/UFOs/comments/1id5may/skywatchers_uap_dog_whistle/), NewsNation reporting, [Skywatcher's media page](https://skywatcher.ai/media), [GPS World "Spooky UAVs"](https://www.gpsworld.com/spooky-uavs/)
- **Code and research**: written with AI assistance (ChatGPT for versions 1–3, Claude for version 4). Facts in the page were checked against the sources listed in its References section.

## License

Provided as-is for educational and experimental purposes.

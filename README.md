# Thinking…

A fullscreen on-set title card effect for the short film *Thinking…*

The screen shows the word **Thinking** with a pulsing, colour-cycling ellipsis and a dense field of faint pseudo-AI reasoning text drifting behind it. After a set countdown the screen hard-cuts to a reveal message, with an audio cue and optional tension build in the final seconds.

Single self-contained HTML file. No dependencies, no build step, works offline.

**Live:** [gavinhaggis.github.io/thinking](https://gavinhaggis.github.io/thinking/)

---

## Usage

Open `index.html` in any modern browser. Press **H** to open the producer console.

The stage (what the camera sees) is always fullscreen-ready. The console never appears on screen unless you open it.

---

## Hotkeys

| Key | Action |
|---|---|
| `Space` | Begin / pause countdown |
| `R` | Reset to thinking state |
| `F` | Toggle fullscreen |
| `B` | Instant blackout |
| `H` | Show / hide producer console |

---

## Producer Console

### Playback
Set the countdown duration in `m:ss`. Hit **Begin countdown** or `Space` to start. The clock counts down; at zero the screen hard-cuts to the reveal.

### Text
- **Title** — the thinking-state word. Supports `**bold**` and `*italic*` markdown.
- **Reveal** — the message that appears at the cut. Also supports markdown.

### Type size
Independent scale sliders for the title, reveal text, and background wall text.

### Text position
X and Y offset sliders (in viewport units) for the title and reveal independently — lets you place text off-centre for a specific frame.

### Colour · thinking scene
- **Background** — stage background colour
- **Title** — title text colour and opacity
- **Wall text** — colour of the drifting reasoning fragments

### Colour · reveal scene
The hard cut switches to an entirely separate colour pair.
- **White-out preset** — white background, black text. Slams to full brightness on the cut.
- **Match thinking** — sets reveal colours to match the thinking scene for a seamless cut.

### Ellipsis palette
Four colour presets for the pulsing dots: Cool (blue/violet), Ember (orange/red), Mono (greyscale), Neon (acid).

### Ellipsis
- **Pulse** — speed of the dot cycle (120ms – 1100ms)
- **Count** — number of dots (1–8), rebuilt live
- **Size** — scale of the dots relative to the title

### Background wall
- **Density** — how frequently new reasoning fragments appear
- **Visibility** — opacity of the fragments (0–0.60)
- **Drift** — how slowly fragments rise before fading

### Drama
- **Build tension into the cut** — in the final 4 seconds the pulse accelerates, the wall thickens, and the title breathes slightly larger
- **Countdown ticks (last 3s)** — soft audio ticks on 3, 2, 1 so the operator feels the cut coming
- **Impact flash on cut** — single-frame white flash at the moment of the cut

### Audio cue
Fires at the hard cut. Four options synthesised in-browser — no audio files needed:
- **Hit** — low resonant impact
- **Chime** — three-tone bell
- **Click** — sharp transient
- **None** — silent cut

Audio arms on the first keypress or click. Test the cue before a take with the **Test cue** button.

### Stage
- **Progress hairline** — a 2px line along the bottom of the screen showing countdown progress. Off by default so nothing leaks on camera.
- **Fullscreen** / **Blackout** — also available as `F` and `B`.

---

## On-set notes

- The **cursor auto-hides** after 2.5 seconds of inactivity and reappears on any movement.
- The app requests a **screen wake-lock** when running so the display doesn't sleep during long takes. This requires a secure context (HTTPS or localhost).
- All settings **persist between reloads** via localStorage where the browser permits.
- Audio requires at least one user interaction before it will sound — pressing `Space` to start a take is enough to arm it.
- If capturing the screen, note that the audio cue plays from the machine's audio output. Route or mute it depending on whether you want it on the plate.

---

## Files

```
index.html   — the complete app, self-contained
README.md    — this file
```

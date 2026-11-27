# Dragspel (Accordion Tool)

A browser-based tool that plays melodies, bass lines, and drums from notes you type into a text box. All sound is synthesized in the browser with the Web Audio API, so no audio files are needed and nothing needs to be installed.

Languages: Swedish and English (choose in the dropdown at the top of the page).

🇸🇪 Läs den här på svenska: [README.md](README.md)

---

## Getting Started

1. Save the code as `dragspel.html`.
2. Double-click the file so it opens in a web browser (Chrome, Edge, Firefox, or Safari).
3. Click **Spela** (Play). The default melody, a riff in E minor, starts right away.

Sound starts only after you click a button. This is a browser safety rule, so if you hear nothing, click **Play** again.

---

## Parts of the Page

| Part | What it does |
|---|---|
| **Language selector** | Switches between Swedish and English. All text, instruments, and error messages change. |
| **Text box** | Where you write the notes, one line per bar. |
| **Melody** | Instrument for the upper part: Accordion, Trumpet, Harmonica, or Saxophone. |
| **Bass** | Instrument for the lower part, with the same choices. |
| **Drums** | Off, Rock 4/4, Polka, or Swing. |
| **Melody / bass / drum volume** | Sliders for balancing the mix (0 to 1.5). |
| **Tempo (BPM)** | Beats per minute. Default is 180. |
| **Bellows tremolo** | How much the volume pulses when the instrument is Accordion. Does not affect the other instruments. |
| **Repeats** | How many times the melody plays. Set 0 to loop until you stop. |
| **Pause between repeats** | Rest in beats between repeats. 0 gives a seamless loop. |
| **Play / Stop** | Starts and stops playback. |
| **Status line** | Shows the pass, bar, and chord currently playing. |

---

## How to Write Notes

### Basic Format

Each line is one bar, split into columns:

```
Bar | Chord | Melody | Bass
```

Example:

```
1 | C | C4 1 E4 1 G4 1 C5 1 | C3 1 G2 1 C3 1 G2 1
```

- **Bar** is the bar number. It is only for readability and error messages.
- **Chord** is shown in the status line during playback. It is not played.
- **Melody** is the upper part.
- **Bass** is the lower part.

Columns can be separated with `|` or with tabs. You can paste directly from a spreadsheet.

### Notes and Lengths

A note is written as a **pitch name followed by octave**, then the **length in beats**:

- `C4 1` means C in octave 4, one beat long.
- `F#3 0.5` means F# in octave 3, half a beat long.
- `Bb4 2` means B-flat in octave 4, two beats long.

Lengths are in beats, where 1 is a quarter note in 4/4:

| Length | Note value (in 4/4) |
|---|---|
| `4` | whole note |
| `2` | half note |
| `1` | quarter note |
| `0.5` | eighth note |
| `1.5` | dotted quarter note |

A rest is written as `R` followed by its length, for example `R 1` for a quarter-note rest.

Sharps are written with `#` and flats with `b`. The octave number sets which C is meant. Middle C is `C4`.

### Rules You Must Follow

1. **Melody and bass on the same line must add up to the same number of beats.** Otherwise you get an error message, for example "Bar 3: melody has 3 beats but bass has 4".
2. **Every note needs a length.** `C4 E4` is wrong, `C4 1 E4 1` is correct.
3. **In 4/4 time** each line should add up to 4. Three beats is fine if you write in 3/4, as long as both parts add up to 3.
4. **Lines without numbers are skipped.** You can write headers like `Bar | Chord | Melody | Bass` without causing problems.

### Tips for a Good Loop

- End the last bar on the tonic the first bar starts on, for example C in a piece in C major.
- If the melody ends too early or too late, add a `R` rest or adjust the length of the last note.
- If you need a pause between repeats, use the **Pause between repeats** field instead of adding rests to the notes.

---

## Instruments and Drums

- **Accordion:** Two slightly detuned sawtooth waves with bellows tremolo. The bass sounds darker and softer.
- **Trumpet:** Bright tone with vibrato and a filter that opens at the start of each note.
- **Harmonica:** Sharp, nasal tone with a little vibrato.
- **Saxophone:** Warm tone with a slow attack and vibrato.
- **Drums:** Rock 4/4, Polka, and Swing use synthesized kick, snare, and hi-hat. Off turns the drums off.

The sounds are synthetic approximations. They are recognizable as their instruments but are not recordings.

---

## Example Melodies

All examples below are public domain or original compositions. They were written from memory and may need adjusting against a music sheet. Copy the whole block into the text box and click **Play**.

### 1. Frère Jacques (French folk song, C major, 8 bars)

Good for testing the instruments. Tempo 100 to 120 BPM. Melody on Accordion or Trumpet, bass on Accordion, drums on Polka or Off.

```
1 | C | C4 1 D4 1 E4 1 C4 1 | C3 1 C3 1 C3 1 C3 1
2 | C | C4 1 D4 1 E4 1 C4 1 | C3 1 C3 1 C3 1 C3 1
3 | G | E4 1 F4 1 G4 2 | G2 1 B2 1 G2 2
4 | G | E4 1 F4 1 G4 2 | G2 1 B2 1 G2 2
5 | C | G4 0.5 A4 0.5 G4 0.5 F4 0.5 E4 1 C4 1 | C3 1 E3 1 G3 1 C3 1
6 | C | G4 0.5 A4 0.5 G4 0.5 F4 0.5 E4 1 C4 1 | C3 1 E3 1 G3 1 C3 1
7 | C | C4 1 G3 1 C4 2 | C3 1 G2 1 C3 2
8 | C | C4 1 G3 1 C4 2 | C3 1 G2 1 C3 2
```

### 2. Twinkle, Twinkle, Little Star (French folk melody, C major, 4 bars)

Simple and calm. Tempo 100 to 110 BPM. Works well with Saxophone or Harmonica on the melody and Swing drums.

```
1 | C | C4 1 C4 1 G4 1 G4 1 | C3 1 C3 1 C3 1 C3 1
2 | F | A4 1 A4 1 G4 2 | F2 1 A2 1 C3 1 A2 1
3 | G | F4 1 F4 1 E4 1 E4 1 | G2 1 B2 1 D3 1 B2 1
4 | C | D4 1 D4 1 C4 2 | C3 1 E3 1 G3 2
```

### 3. The Default Riff (original composition, E minor, 16 bars)

This is the riff preset on the page. It is written for a fast pop-punk tempo, 150 to 180 BPM, with Saxophone on the melody and Polka or Rock 4/4 drums. To use it as a starting point for your own edits, copy it from the default content of the text box in `dragspel.html`.

---

## Troubleshooting

| Problem | Solution |
|---|---|
| No sound | Click **Play** again. Check that the computer volume is on and that the volume sliders are not at 0. |
| "Bar N: melody has X beats but bass has Y" | The sums of the lengths differ between the parts on bar N. Adjust the lengths so they match. |
| "Bar N: invalid note ..." | Check the spelling. Pitch names are A to G followed by an octave, for example `F#4` or `Bb3`. |
| "Bar N: every note needs a length" | There is an even number of words, but a note is missing its length. Make sure every pitch name is followed by a number. |
| The loop stutters or drifts | Stop and start again. Lower the tempo if the computer is slow or has many tabs open. |
| The tune stops after one pass | Set **Repeats** to 0 for infinite, or to a higher number. |

---

## Limitations

- The tool does not import notes from files or sheet music. You type them in manually.
- The sounds are synthetic and do not sound like real recordings.
- Chords are shown in the status line only and are not played.
- The tool requires a modern browser with Web Audio API support.

---

## Files

- `dragspel.html` is the whole tool. It contains HTML, CSS, and JavaScript in a single file.
- `README.md` is the Swedish version of this documentation.
- `README.en.md` is this English version.

---

Created with Claude by Malmis
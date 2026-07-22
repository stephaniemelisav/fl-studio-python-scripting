# FL Studio Scripting

*[Leer esto en español](README.md)*

Custom scripts for FL Studio, written in Python. Two separate systems, each living in its own FL Studio settings folder — here we keep the "source" copy for version control on GitHub.

## Structure

```
piano-roll-scripts/       -> Piano Roll scripts (.pyscript)
midi-controller-scripts/  -> MIDI controller scripts (device_*.py)
```

## Piano Roll Scripts

Generate or modify notes directly in the Piano Roll (melodies, chords, arrangements).

- **Real FL Studio folder:** `Documents\Image-Line\FL Studio\Settings\Piano roll scripts\`
- **Extension:** `.pyscript`
- **API:** `import flpianoroll as flp` — [official manual](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_scripting_api.htm)
- **Required structure:** `createDialog()` (defines the controls) + `apply(form)` (logic that adds notes)

### Install / how to test a script

1. Copy the `.pyscript` file from this folder into `Documents\Image-Line\FL Studio\Settings\Piano roll scripts\`
2. In FL Studio, open the Piano Roll → tools menu → **Scripts** → pick the script
3. If you edit it, copy it back to the FL Studio folder and reopen the scripts menu to reload it

### Scripts

| Script | What it does |
|---|---|
| `generador-de-acordes.pyscript` | Generates a diatonic chord progression (triads or sevenths) from a root note, scale, and a degree pattern (preset or custom). |

## MIDI Controller Scripts

Tell FL Studio how to react when a key/pad/knob on a MIDI controller is pressed (play, stop, record, etc.).

- **Real FL Studio folder:** `Documents\Image-Line\FL Studio\Settings\Hardware\<device-folder>\`
- **Extension:** `.py`, the file must start with `device_`
- **API:** [official MIDI scripting manual](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/midi_scripting.htm)
- **Required structure:** first line `# name=name`, function `OnMidiMsg(event)`

### Scripts

_(none yet — next up is one for the Arturia MiniLab 3)_

## Notes

- No paid FL Studio license is needed to write/run scripts — it's a core-engine feature, not a plugin. The typical restriction on an unregistered copy is saving/exporting projects, not scripting.
- To convert hexadecimal (what FL's Debugging Log shows) to decimal (what Python expects), use any hex→dec converter.

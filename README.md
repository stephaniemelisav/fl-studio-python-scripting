# FL Studio Scripting

*[Read this in English](README.en.md)*

Scripts propios para FL Studio, hechos en Python.

## Estructura

```
piano-roll-scripts/       -> Scripts de Piano Roll (.pyscript)
midi-controller-scripts/  -> Scripts de controlador MIDI (device_*.py)
```

## Piano Roll Scripts

Generan o modifican notas directamente en el Piano Roll (melodías, acordes, arreglos).

- **Carpeta real de FL Studio:** `Documents\Image-Line\FL Studio\Settings\Piano roll scripts\`
- **Extensión:** `.pyscript`
- **API:** `import flpianoroll as flp` — [manual oficial](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_scripting_api.htm)
- **Estructura obligatoria:** `createDialog()` (define los controles) + `apply(form)` (lógica que agrega notas)

### Instalación / cómo probar un script

1. Copiá el `.pyscript` de esta carpeta a `Documents\Image-Line\FL Studio\Settings\Piano roll scripts\`
2. En FL Studio, abrí el Piano Roll → menú de herramientas → **Scripts** → elegí el script
3. Si lo editás, volvé a copiarlo a la carpeta de FL Studio y usá "Reload"/volvé a abrir el menú de scripts

### Scripts

| Script | Qué hace |
|---|---|
| `generador-de-acordes.pyscript` | Genera una progresión de acordes diatónicos (tríadas o séptimas) a partir de una nota raíz, escala y patrón de grados (predefinido o personalizado). |

## MIDI Controller Scripts

Le dicen a FL Studio cómo reaccionar cuando se presiona una tecla/pad/knob de un controlador MIDI (play, stop, grabar, etc.).

- **Carpeta real de FL Studio:** `Documents\Image-Line\FL Studio\Settings\Hardware\<carpeta-del-dispositivo>\`
- **Extensión:** `.py`, el archivo debe empezar con `device_`
- **API:** [manual oficial de MIDI scripting](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/midi_scripting.htm)
- **Estructura obligatoria:** primera línea `# name=nombre`, función `OnMidiMsg(event)`

### Scripts

_(todavía no hay ninguno acá — el próximo en la lista es para el Arturia MiniLab 3)_

## Notas

- No se necesita licencia paga de FL Studio para escribir/correr scripts — es una función del motor base, no un plugin. La única restricción típica de la versión sin registrar es guardar/exportar proyectos.
- Para pasar de hexadecimal (lo que muestra el Debugging Log de FL) a decimal (lo que espera Python), usar cualquier conversor hex→dec.

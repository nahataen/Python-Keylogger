# ⌨️ Práctica local educativa de keylogger — solo uso académico

> Registra localmente las teclas pulsadas en tu propio equipo y las guarda en `logs.txt` con usuario, fecha y hora.

## Qué hace

`keylogger.py` (34 líneas, documenta lo existente; no se añade funcionalidad) usa la librería `keyboard`: `Pressed()` reacciona a `KEY_DOWN`, forma la línea `usuario - archivo - fecha: tecla` con `getpass.getuser()` y `time.asctime()`, y la anexa con `WriteToFile()` a `logs.txt` dentro de `folder_path`. El programa se queda en espera con `keyboard.on_press(...)` + `keyboard.wait()` hasta que lo detienes. La variable `folder_path` trae una ruta de ejemplo que debes cambiar por una carpeta tuya existente.

## Estructura

```text
local-keylogger-lab/
├── keylogger.py  # WriteToFile(), Pressed(), keyboard.on_press + keyboard.wait();
│                 # escribe logs.txt en folder_path (ruta de ejemplo a ajustar)
└── README.md     # Este archivo
```

## Requisitos

- Python 3.x
- Librería `keyboard`
- Ejecutar en **tu propio equipo**; en Windows suele requerir terminal con permisos de administrador para capturar teclas globales

## Cómo correr

```bash
git clone https://github.com/nahataen/Python-Keylogger.git
cd Python-Keylogger
pip install keyboard
```

1. Edita `keylogger.py` y pon en `folder_path` una carpeta local existente (p. ej. `r"C:\Users\TuUsuario\Documents\lab"`). Crea la carpeta antes de ejecutar.
2. Ejecuta:

```bash
python keylogger.py
```

3. Pulsa teclas y revisa `logs.txt` en esa carpeta. Detén con `Ctrl + C`.

## Notas

- Práctica mínima sin panel, sin exfiltración de red ni persistencia: solo escribe un `.txt` local.
- Si `folder_path` no existe, el script falla al escribir; verifícalo antes de correr.

## ⚠️ Uso responsable

- **Exclusivamente educativo y local**: úsalo solo en tu propio equipo o en máquinas/laboratorios con consentimiento explícito por escrito.
- No lo instales en equipos ajenos ni captures credenciales o datos de terceros: puede ser ilegal (delitos contra la privacidad / acceso ilícito según tu país).
- No se aceptan contribuciones que añadan exfiltración, ocultamiento, persistencia o ejecución remota.

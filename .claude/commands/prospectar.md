---
description: Busca y califica nuevos prospectos para SerBan y genera el Excel del día
argument-hint: "[número] [sector] [país]   ej: 20 seguros México"
---

Lanza una tanda de prospección siguiendo **exactamente** el flujo de la sección 8 de `CLAUDE.md`.

Parámetros del usuario: `$ARGUMENTS`

- Si indica un **número**, ese es el objetivo de prospectos. Si no, el objetivo es 20 (mínimo 15).
- Si indica un **sector** o un **país**, céntrate en ellos sin dejar de aplicar el ICP y las exclusiones.
- Si no indica nada, reparte entre banca, seguros y energía en España, y añade algún grupo con presencia en LATAM.

Recuerda:
1. Lee primero `datos/clientes_ideales.md`, `datos/serban_contexto.md`, `datos/feedback.md`, `datos/exclusiones.csv`, todo `datos/crm/` y `salida/historico.csv`.
2. Cada señal y cada contacto llevan su URL de fuente. No inventes nada y no deduzcas emails.
3. Nada de LinkedIn automatizado ni de contactar a nadie.
4. Guarda el JSON en `salida/prospectos_<fecha de hoy>.json` y ejecuta `python3 scripts/generar_excel.py` sobre él.
5. Termina con el resumen corto de la sección 8, paso 7.

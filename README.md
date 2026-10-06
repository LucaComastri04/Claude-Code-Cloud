# Agente de prospección SerBan (Claude Code)

Agente que **encuentra y califica** empresas y contactos que encajan con el cliente ideal de SerBan
y los entrega en un **Excel** para revisarlos y cargarlos en Dynamics 365. No contacta a nadie.

## Cómo se usa

1. Abre esta carpeta con Claude Code.
2. Escribe `/prospectar` (20 prospectos de banca, seguros y energía) o, por ejemplo:
   - `/prospectar 15 seguros México`
   - `/prospectar 20 energía España`
3. El Excel aparece en `salida/prospectos_AAAA-MM-DD.xlsx`, ordenado por puntuación, con las fuentes enlazadas.

## Antes de la primera ejecución

| Archivo | Qué poner |
|---|---|
| `datos/clientes_ideales.md` | 5–10 clientes actuales ideales. Es el "entrenamiento" del agente |
| `datos/crm/` | Exportación de cuentas de Dynamics 365, para no repetir empresas que ya tenéis |
| `datos/serban_contexto.md` | Fabricantes con los que trabajáis, casos de éxito, tamaño típico de contrato |
| `datos/exclusiones.csv` | Empresas que no se deben proponer nunca |

## Para que mejore con el tiempo

Apunta en `datos/feedback.md` qué prospectos sirvieron y cuáles no. El agente lo lee en cada ejecución.

## Estructura

```
CLAUDE.md                      ← master prompt: ICP, señales, puntuación, flujo y reglas
.claude/commands/prospectar.md ← comando /prospectar
.claude/settings.json          ← permisos (web sí; LinkedIn bloqueado)
datos/                         ← tus datos de entrada
scripts/generar_excel.py       ← JSON → Excel + histórico anti-duplicados
salida/                        ← Excels e histórico (no se suben a GitHub)
```

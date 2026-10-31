# manual-tecnico

Skill de Claude Code para crear manuales visuales breves sobre un concepto de desarrollo (Zustand, reactividad, contexto, seguridad, bases de datos…). Genera de 12 a 18 diapositivas en HTML y las exporta a un PDF ligero para LinkedIn, a imágenes 9:16 para TikTok e Instagram y a una portada cuadrada. Es de la comunidad **Chamba Lab**, con **Rakim** como mascota.

> Este archivo es para personas. Claude no lo lee: sus instrucciones están en `SKILL.md`.

## Requisitos

- **Claude Code** con la skill instalada: `git clone https://github.com/Chamba-Lab/manual-tecnico.git ~/.claude/skills/manual-tecnico`.
- **Node.js** 18 o superior.
- **Playwright** (opcional): `npm i -g playwright` y luego `npx playwright install chromium`. Sin él, Claude te da los pasos para exportar el PDF a mano desde Chrome.
- **Internet**, para las fuentes, el resaltado de código y el logo de la tecnología.
- **ChatGPT** (o el generador que prefieras) para las ilustraciones.

## Primera vez: proyecto de ChatGPT

En tu primer manual, Claude te dará un bloque de instrucciones con el estilo y la descripción de Rakim. Con él:

1. Crea en ChatGPT un proyecto llamado `Rakim · Manuales` y pega ese bloque en sus instrucciones.
2. Sube como archivos del proyecto las imágenes de `assets/personaje/`.
3. En cada chat nuevo, adjúntalas también en el primer mensaje.

Así cada prompt es solo la escena y Rakim sale igual en todos los manuales.

## Cómo se usa

1. Pídele a Claude, por ejemplo, *"arma un manual de Zustand"*.
2. **Fase 1:** te entrega el esquema y de 6 a 9 prompts de imagen.
3. Crea la carpeta del manual con `imagenes/` dentro (por ejemplo `ZUSTAND/imagenes/`). Genera las imágenes en ChatGPT y guárdalas ahí, en el orden de la lista.
4. Pásale la ruta a Claude.
5. **Fase 2:** arma `manual.html`, lo revisa y exporta `manual.pdf`, `slides-9x16/` y `portada-linkedin.png`. También anota el manual en `indice.md`.

Si quieres el manual sin esperar las imágenes, pídeselo: las diapositivas sin imagen se ven como un degradado limpio y puedes agregar los archivos después.

## Qué hay dentro

| Ruta | Qué es |
|---|---|
| `SKILL.md` | Instrucciones para Claude |
| `references/` | Arco, tema visual, prompts de imagen y diagramas; Claude los lee solo cuando los necesita |
| `assets/plantilla.html` | Sistema visual y tipos de diapositiva (claro y oscuro) |
| `assets/portada-linkedin.html` | Portada cuadrada 1080×1080 |
| `assets/vertical.css` | Recomposición a 9:16 (1080×1920) para TikTok e Instagram |
| `assets/personaje/` | Referencias de Rakim para ChatGPT |
| `scripts/` | `armar.js` ensambla, `logo.js` trae el logo, `revisar.js` hace capturas (también en 9:16) y `exportar.js` genera el PDF ligero, las imágenes `slides-9x16/` y el PNG |

## Adaptarla a tu marca

- **Firma:** cambia "Chamba Lab" y el enlace en la sección *Marca de la serie* de `references/diseno.md` y en las dos plantillas de `assets/`.
- **Mascota:** reemplaza las imágenes de `assets/personaje/` y la descripción `CHARACTER` en `references/imagenes.md`.

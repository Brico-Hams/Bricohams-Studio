# Guía de marca BricoHams (colores web)

Resumen operativo del manual oficial **«BricoHams_Guia_Colores_Web_Pantone_Claro_Oscuro_con_Prompt_IA.pdf»** (v1.1, 03-11-2026). El PDF no se incluye en el repositorio; ante cualquier duda manda el documento oficial.

Esta paleta sustituye a todas las anteriores (naranja `#F7941D`/`#F26B21`/`#A64B00`, fondos oscuros azulados, azules `#89B9FF`/`#205DA8` y el par `#0A2540` + `#FF6B00`). No deben volver a usarse.

## Tokens (sRGB)

Comunes a ambos temas:

| Token | Valor | Uso |
| --- | --- | --- |
| `--brand-ink` | `#23272B` | Grafito: identidad, iconos, títulos |
| `--brand-orange` | `#F26B1D` | CTA, detalles, señalética |
| `--on-accent` | `#23272B` | Texto sobre naranja (ambos temas) |

| Token | Claro | Oscuro |
| --- | --- | --- |
| `--bg` | `#FFFFFF` | `#111518` |
| `--surface` | `#F6F7F8` | `#1C2329` |
| `--text` | `#23272B` | `#F6F8FA` |
| `--text-muted` | `#59636B` | `#BAC4CC` |
| `--border` | `#DCE1E5` | `#38434C` |
| `--link` | `#AA410B` | `#FFA06A` |
| `--focus` | `#F26B1D` | `#FFC18F` |

`index.html` añade tokens derivados (no están en el manual): `--surface-2`, `--surface-hover`, `--border-strong`, `--accent-soft` y los colores funcionales `--ok`, `--warn`, `--err` (con su fondo `*-bg`). Se eligieron para cumplir AA en cada tema y nunca sustituyen al naranja de marca en los CTA. Los alias heredados (`--fg`, `--muted`, `--panel`, `--aqua`…) apuntan a los tokens oficiales.

## Reglas

- **Contraste (WCAG 2.2 AA)**: 4,5:1 texto normal, 3:1 texto grande y componentes.
- **Botón primario**: fondo naranja `#F26B1D` con texto grafito `#23272B` en claro y oscuro. Nunca texto blanco sobre naranja.
- **Enlaces**: `#AA410B` en claro y `#FFA06A` en oscuro. El naranja `#F26B1D` no se usa como texto pequeño sobre blanco.
- **Foco**: `:focus-visible` con `outline: 3px solid var(--focus)` y separación de 3 px.
- **Tema**: claro / oscuro / sistema. El sistema sigue `prefers-color-scheme`; la elección explícita se guarda en `localStorage` (`bricohams-theme`) y se aplica como `data-theme="light|dark"` en `<html>` antes del primer pintado, sin parpadeo.
- **Logo**: solo el PNG original (`assets/logo-bricohams.png`, incrustado en `index.html`). Nunca se recolorea, filtra, invierte, deforma ni se cambia el lema «RADIOAFICIÓN · HAZLO TÚ MISMO». En modo oscuro va sobre una placa blanca discreta (`--logo-plate-bg`, `--logo-plate-pad`).
- **Tipografía**: Inter para la interfaz y Montserrat 700–800 para titulares grandes, siempre con la pila de fuentes del sistema como respaldo. No se cargan fuentes remotas: la aplicación debe funcionar sin Internet.
- **Estilo**: rejilla clara, jerarquía fuerte, tarjetas redondeadas, iconos de línea y espaciado generoso. Sin neones ni degradados llamativos.
- **Impresión**: solo Pantone 426 C (grafito) y 165 C (naranja; alternativa 158 C). Los valores Pantone no son colores de pantalla.
- **Android**: `res/values/colors.xml` (claro) y `res/values-night/colors.xml` (oscuro) con los mismos tokens; primario = naranja y `onPrimary` = grafito. Este repositorio no contiene app Android.
- **Firmware LCD monocromo**: la marca se limita al logo de arranque y a la cadena «Bricohams», sin colores.

## Tabla de contraste

Cifras citadas por el manual; el resto de pares se diseñó para AA y conviene reverificarlo con una herramienta de contraste tras cualquier cambio de tokens.

| Par | Ratio | Resultado |
| --- | --- | --- |
| Blanco sobre naranja `#F26B1D` | 3,05:1 | No cumple: prohibido |
| Naranja `#F26B1D` sobre blanco (texto pequeño) | 3,05:1 | No cumple: usar `#AA410B` |
| Naranja `#F26B1D` sobre `#111518` | 6,03:1 | Cumple |
| Grafito `#23272B` sobre naranja `#F26B1D` (botón primario) | — | Cumple AA según el manual |
| Enlace `#AA410B` sobre `#FFFFFF` (claro) | — | Cumple AA según el manual |
| Enlace `#FFA06A` sobre `#111518` (oscuro) | — | Cumple AA según el manual |
| Texto `#23272B` sobre `#FFFFFF` / `#F6F8FA` sobre `#111518` | — | Cumple AA según el manual |

## Dónde está implementado

- `index.html`: tokens en el primer bloque `:root`, capa final `<style id="brand-theme">`, script de tema en `<head>` y selector de tema en la barra superior.

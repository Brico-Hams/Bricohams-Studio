# Manual F4HWN (FH4): referencia para Studio

El **Manual de referencia completo y detallado del firmware F4HWN (FH4)**, edición
Bricohams del 8 de noviembre de 2026, explica los 68 menús de la radio, la
configuración paso a paso del bloqueo y la retroiluminación, y trae una
referencia rápida imprimible de tres páginas.

- **Guía web (5 idiomas):** <https://brico-hams.github.io/Radio-Web-install/ayuda-manual-f4hwn.html>
  ([English](https://brico-hams.github.io/Radio-Web-install/ayuda-manual-f4hwn.en.html),
  [Français](https://brico-hams.github.io/Radio-Web-install/ayuda-manual-f4hwn.fr.html),
  [Deutsch](https://brico-hams.github.io/Radio-Web-install/ayuda-manual-f4hwn.de.html),
  [Italiano](https://brico-hams.github.io/Radio-Web-install/ayuda-manual-f4hwn.it.html)).
- **Manual completo en PDF (13 páginas):** <https://brico-hams.github.io/Radio-Web-install/docs/manuals/Manual_F4HWN_FH4_Bricohams_v2.pdf>.
  Las páginas 11–13 son la referencia rápida imprimible.
- **Fuente en el repositorio:** [`docs/MANUAL-F4HWN.md`](https://github.com/Brico-Hams/Radio-Web-install/blob/main/docs/MANUAL-F4HWN.md)
  y [`docs/manuals/`](https://github.com/Brico-Hams/Radio-Web-install/tree/main/docs/manuals) en Bricohams Radio Workspace.

## Cómo usarlo con Studio

- La pestaña **Configuración** de Studio edita muchos de los ajustes que el manual
  describe (pantalla, teclas, squelch, escaneo, DTMF, bloqueo…). Busca cada ajuste
  por su **nombre corto** (`KeyLck`, `SetLck`, `BLTime`, `ChDisp`…), no por el
  número: la numeración del manual es editorial y cambia entre compilaciones.
- En la radio, pulsa **MENU** y elige **ALL** antes de seguir el manual; sin ALL
  no aparecen todos los menús.
- Las opciones disponibles dependen de la versión instalada (F4HWN Fusion 6.0 /
  6.1 y su compilación). Compruébalo en `SysInf` antes de interpretar un ajuste.
- Antes de cambiar ajustes o canales, guarda una copia recuperable de tu radio,
  como indica la sección **Seguridad y buenas prácticas** del README.

El manual es una guía independiente con la identidad gráfica de Bricohams; no es
documentación oficial de F4HWN. Fuentes técnicas citadas en el propio manual:
[repositorio F4HWN](https://github.com/armel/uv-k1-k5v3-firmware-custom) y
[controlador CHIRP F4HWN](https://github.com/armel/uv-k5-chirp-driver).

# Contribuir

Este repositorio es el juego (*Donkey Kong Country 2*, USA); el recompilador, el runtime y `snes-port` están en [`snes-recomp`](https://github.com/AlexPerez7/snes-recomp), y sus reglas generales están en su [CONTRIBUTING.md](https://github.com/AlexPerez7/snes-recomp/blob/main/CONTRIBUTING.md). Un fallo del traductor, de la PPU o del sonido va allí.

## Reglas que no se negocian

- **Nunca la ROM ni nada derivado de ella**: ni en commits, ni en issues, ni en PR (volcados, capturas con gráficos, C generado, bytes de tablas copiados). Antes de abrir un PR: `.\snes-recomp.exe scan ruta\a\dkc2_usa.sfc .` debe terminar sin error.
- **Código propio.** El C que añadas es original (clean-room). La documentación pública del juego puede dar una pista, pero toda dirección se comprueba a mano contra la ROM real.
- Mensajes de commit en español, en imperativo.

# dkc2-recomp

*Donkey Kong Country 2: Diddy's Kong Quest* (USA, Rev 1, CRC32 `4E2D90F4`) recompilado con el motor [`snes-recomp`](https://github.com/AlexPerez7/snes-recomp) (repositorio hermano `..\snes-recomp`). Este repositorio es el **juego**: su perfil, el C propio y los scripts. El motor es una herramienta externa y compartida; aquí no se copia su código (solo los binarios ya construidos en la raíz, como en `..\alttp-recomp`).

**Estado:** solo la base. Falta el mapeo HiROM en el motor y el perfil del juego (ver README.md). La ROM, HiROM de 4 MB sin coprocesador, va en `roms\dkc2_usa.sfc` (ignorada por git).

## Comandos

```
snes-port.exe roms\dkc2_usa.sfc                # cuando exista el perfil
powershell -File scripts\release.ps1           # paquete (motor de la raíz)
powershell -File scripts\update-engine.ps1     # actualiza el motor de la raíz desde ..\snes-recomp
```

## Estructura

- `games/dkc2_usa.toml`: perfil (por crear). Solo direcciones, nombres y tamaños; ningún byte del juego.
- `games/dkc2_usa/*.c`: C propio (por crear). Cada fichero nuevo se añade a la lista de `check.ps1` (por crear).
- `scripts/`: `release.ps1`, `update-engine.ps1`.

## Reglas

- Nunca la ROM ni nada derivado (C generado, volcados, capturas con gráficos): `roms/`, `out/`, `*.sfc`, `*.smc`, `*.srm`, `*.sst` están en `.gitignore`. Antes de cada push: `.\snes-recomp.exe scan roms\dkc2_usa.sfc .`.
- El C es original (clean-room). Las direcciones y tablas de saltos se comprueban a mano contra la ROM real.
- Lo que sea del traductor, la PPU, el sonido, el menú o el runtime va en `snes-recomp`; aquí solo lo específico de este juego. Cada repositorio se commitea y se sube por separado.
- Documentación y mensajes de commit en español.

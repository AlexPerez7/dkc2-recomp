# dkc2-recomp

*Donkey Kong Country 2: Diddy's Kong Quest* (USA, Rev 1) recompilado a código nativo con el motor [`snes-recomp`](https://github.com/AlexPerez7/snes-recomp). Este repositorio es el **juego**: su perfil (`games/dkc2_usa.toml`), el C propio que lo mejora y los scripts para empaquetarlo. El recompilador, el runtime y `snes-port` están en el motor.

> **Estado: sin empezar.** Solo existe la base del repositorio. El motor aún no sabe leer ROMs HiROM (la de este juego lo es), y el perfil del juego no está hecho. No hay nada que jugar todavía.

> **Aviso legal.** Este repositorio no contiene la ROM ni ningún recurso del juego (gráficos, sonido, texto, mapas), y no lo tendrá. Cada persona debe aportar su propia copia obtenida legalmente. El programa se construye en tu máquina a partir de **tu** ROM y nada derivado de ella se distribuye. Proyecto independiente y sin relación con Nintendo ni con Rare.

Licencia: [MIT](LICENSE), solo para el código de este repositorio; no da derechos sobre el juego.

## La ROM

CRC32 `4E2D90F4`: HiROM FastROM de 4 MB con RAM de batería y sin coprocesador (cabecera en `00:FFC0`, mapa `0x31`, tipo `0x02`).

## Pendiente

1. Mapeo HiROM en el motor (`snes-recomp`: `rom.rs` y el bus del runtime).
2. Perfil `games/dkc2_usa.toml`: entradas, tablas de saltos y punto `[resume]`, comprobados a mano contra la ROM.
3. `scripts/check.ps1` con pruebas de la ROM, como en [`alttp-recomp`](https://github.com/AlexPerez7/alttp-recomp).

## Comandos

```
snes-port.exe                                  # doble clic: el lanzador (cuando haya perfil)
powershell -File scripts\release.ps1           # paquete para repartir; falla si lleva ROM, .srm o C generado
powershell -File scripts\update-engine.ps1     # trae el motor más reciente de ..\snes-recomp
```

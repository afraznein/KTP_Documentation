<!-- ktp-translation
locale: es
source: KTP Cvar List.md
source-sha256: 40fe78834ec1530138f5cd67d9bdb23af61758fb5d549de38015ae272adc25e8

Records which revision of the English cvar list this translation was made from.
ktpleague.gg re-checks it on every render and warns readers when it no longer
matches. Whenever KTP Cvar List.md changes, update this translation and refresh
the hash - the workflow in .github/workflows/ opens a tracking issue for it.
-->
# Requisitos de CVAR de la Liga KTP

**Configuración de Variables de Cliente de Day of Defeat 1.3**

[![Version](https://img.shields.io/badge/Version-Season%202026-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> Todos los jugadores deben usar esta configuración de CVAR durante los partidos de KTP. Los valores fijos son obligatorios salvo que se especifique un rango. El servidor de KTP verifica y aplica estos valores automáticamente.

---

## Tabla de Contenidos

- [CVARs de Valor Fijo](#cvars-de-valor-fijo)
  - [Gráficos y Renderizado](#gráficos-y-renderizado)
  - [Audio](#audio)
  - [Movimiento y Entrada](#movimiento-y-entrada)
  - [Red y Predicción](#red-y-predicción)
  - [HUD e Interfaz](#hud-e-interfaz)
- [CVARs por Rango](#cvars-por-rango)

---

## CVARs de Valor Fijo

Estos CVARs deben estar en el valor exacto especificado. El servidor corregirá automáticamente cualquier desviación.

### Gráficos y Renderizado

| CVAR | Valor | Descripción |
|------|-------|-------------|
| `gl_clear` | `0` | Cuando está en 1, hace visibles las grietas entre texturas |
| `gl_d3dflip` | `0` | Cuando está en 1, hace visibles las grietas entre texturas |
| `gl_monolights` | `0` | Fuente de luz uniforme sin sombras (solo OpenGL) |
| `gl_overbright` | `0` | Modo de brillo máximo |
| `gl_picmip` | `0` | Nivel de mipmap de texturas. Los valores altos reducen las texturas de pared a bloques de color sólido; se fija en 0 para evitar el abuso de wallhack por contraste. **No lo cambies.** |
| `r_drawentities` | `1` | Dibujado de modelos de jugador y sprites (0=ninguno, 1=normal, 2=sin texturas, 3=hitbox, 4=hitboxes translúcidas) |
| `r_drawviewmodel` | `1` | Activa o desactiva el dibujado del modelo del arma del jugador |
| `r_dynamic` | `1` | Iluminación dinámica (reflejos de linterna, etc.) |
| `r_fullbright` | `0` | Brillo máximo solo en partidas locales |
| `r_glowshellfreq` | `2.2` | Velocidad de animación del glow shell — valor predeterminado del motor de DoD. Lo usa el brillo del portador de la bandera. Se aplica en el valor predeterminado del motor como verificación de integridad (detecta sobrescrituras por autoexec). **No lo cambies.** |
| `r_lightmap` | `0` | Renderizado por software: muestra los lightmaps (0-3) |
| `r_traceglow` | `0` | Depuración de trazado del glow shell — valor predeterminado del motor de DoD. Se aplica en el valor predeterminado como verificación de integridad. **No lo cambies.** |
| `texgamma` | `2` | Nivel de gamma de texturas |

### Audio

| CVAR | Valor | Descripción |
|------|-------|-------------|
| `s_show` | `0` | Muestra en pantalla qué sonidos se están reproduciendo |

### Movimiento y Entrada

| CVAR | Valor | Descripción |
|------|-------|-------------|
| `cl_bobcycle` | `0.8` | Con qué frecuencia oscila la vista del jugador al correr |
| `cl_bobup` | `0.5` | Cantidad de movimiento antes de que empiece la oscilación de la vista |
| `cl_pitchdown` | `89` | Ángulo máximo para mirar hacia abajo |
| `cl_pitchup` | `89` | Ángulo máximo para mirar hacia arriba |
| `cl_pitchspeed` | `225` | Velocidad de giro vertical con el teclado (grados por segundo). Fijado en el valor predeterminado de GoldSrc para evitar scripts de no-recoil basados en alias. **No lo cambies.** |
| `cl_yawspeed` | `210` | Velocidad de giro horizontal con el teclado (grados por segundo). Fijado en el valor predeterminado de GoldSrc. **No lo cambies.** |
| `cl_anglespeedkey` | `0.67` | Multiplicador aplicado a `cl_pitchspeed`/`cl_yawspeed` mientras se mantiene +speed. Fijado en el valor predeterminado de GoldSrc. **No lo cambies.** |
| `m_pitch` | `0.022` o `-0.022` | Multiplicador de sensibilidad del eje vertical del ratón. **Los jugadores con ratón invertido usan `-0.022`** — el negativo se acepta explícitamente, y un valor negativo fuera de tolerancia se corrige a `-0.022`, nunca se invierte a positivo. No tienes que renunciar al eje vertical invertido para cumplir con las reglas. |
| `m_side` | `0.8` | Multiplicador de velocidad de desplazamiento lateral del ratón. Fijado en el valor predeterminado de GoldSrc. **No lo cambies.** |

### Red y Predicción

> 📖 Para la explicación completa de estos ajustes —cómo funciona la red de GoldSrc, por qué cada valor es el que es, y cuándo es legítimo desviarse— consulta la **[Guía de Netcode de KTP](https://netcode.ktpdod.com/)**.

| CVAR | Valor | Descripción |
|------|-------|-------------|
| `rate` | `100000` | Tasa de transmisión del cliente al servidor (bytes/seg). **No lo cambies.** |

#### CVARs de red ajustables por el jugador (sin control)

Estos cvars afectan el comportamiento de tu propio cliente. KTPCvarChecker NO los controla — es tu decisión. Se muestran los valores predeterminados.

| CVAR | Predeterminado | Notas |
|------|---------|-------|
| `cl_mousegrab` | `1` | Si el motor confina el cursor del ratón a la ventana del juego. Solo del cliente — el servidor nunca lo ve, sin efecto en el juego ni en la puntería (la puntería usa entrada cruda de todos modos). Con `1`, el cursor se engancha en las esquinas del monitor y falla al hacer alt-tab o en configuraciones multimonitor en modo ventana. **Recomendado: `0` para juego en ventana o multimonitor, `1` para pantalla completa exclusiva.** (Ya no se controla desde KTPCvarChecker 7.30.) |
| `cl_lc` | `1` | Compensación de lag del lado del servidor para TUS disparos. Con `0` se desactiva el rebobinado: tienes que adelantar a los objetivos por todo tu ping. **Es una autolimitación, no un exploit.** Algunos jugadores prefieren `0` para eliminar la sensación de "disparo a través de la pared"; la mayoría lo deja en `1`. **Recomendado: 1.** |
| `cl_lw` | `1` | Predicción de armas del lado del cliente. Con `0`, las animaciones de armas pasan a depender del servidor (se siente con lag si el ping no es de LAN). Poner `0` también desactiva la compensación de lag (las comprobaciones exigen `lc=1` Y `lw=1`). **Es una autolimitación, no un exploit.** **Recomendado: 1.** |
| `cl_fixtimerate` | `7.5` | Con qué agresividad tu cliente corrige su reloj local hacia la marca de tiempo del servidor (ms de corrección permitidos por fotograma). Sin superficie competitiva — la sincronización de reloj ocurre de todos modos. El valor predeterminado es una causa conocida de **saltos en la animación del modelo de arma** en GoldSrc; si tus animaciones de arma dan tirones, bájalo (hacia `0`) para que el modelo de arma sea más fluido. **Recomendado: 7.5, salvo que veas saltos en el arma.** |
| `cl_smoothtime` | `0.1` | Cuánto tarda (en segundos) tu cliente en suavizar visualmente las correcciones de error de predicción de TU PROPIO movimiento (empujones de compañeros, retroceso, aterrizajes en bordes). Durante la ventana de suavizado, tu posición renderizada va por detrás de la del servidor — una pequeña discrepancia de puntería. `0.01` reparte la corrección a lo largo de ~un intervalo de actualización: precisión prácticamente instantánea sin saltos de un solo fotograma (la convención clásica de la liga). **Recomendado: 0.01. Los jugadores con ping alto (100 ms o más) pueden usar el predeterminado de 0.1 por comodidad — sus correcciones son mayores y más frecuentes.** |

### HUD e Interfaz

| CVAR | Valor | Descripción |
|------|-------|-------------|
| `hud_takesshots` | `1` | Guarda automáticamente una captura del marcador al final de un mapa. Se controla **únicamente en partidos competitivos** (`.ktp`, `.ktpOT`) — en `.12man`, `.scrim` y `.draft` el servidor no lo verifica ni lo corrige. |
| `cl_showevents` | `0` | Muestra eventos como el disparo de armas (los eventos están listados en dod/events/) |

---

## CVARs por Rango

Estos CVARs deben estar dentro del rango especificado. El servidor corregirá los valores fuera del rango.

| CVAR | Rango | Predeterminado | Descripción |
|------|-------|---------|-------------|
| `lightgamma` | **1.809** - **3.0** | 2.5 | Valor de gamma de iluminación. Los valores por debajo de 1.809 hacen que DoD se cierre inesperadamente |
| `cl_bob` | **0** - **0.01** | 0.005 | Cantidad de oscilación de la vista al correr |
| `cl_updaterate` | **100** - **120** | - | Actualizaciones solicitadas al servidor por segundo. El cliente limita internamente el procesamiento a **102** — los valores de 103 a 120 pasan la verificación pero no hacen nada, así que pon exactamente `102`. **Requerido por KTP.** |
| `cl_cmdrate` | **100** - **1000** | - | Veces por segundo que el cliente actualiza al servidor. Rango útil = ≤ los fps de tu cliente; ponerlo por encima de tus fps desperdicia ancho de banda. v7.25: el techo subió de 500 a 1000 para permitir probar entrada de alta resolución en clientes de 1000 fps. **Requerido por KTP.** |
| `ex_interp` | **0.01** - **0.05** | - | Tiempo de interpolación entre actualizaciones. **Pon 0.01** si tu conexión está limpia. Súbelo SOLO por pérdida de paquetes o jitter en tu propia conexión (revisa `net_graph 1`): 0.02 aguanta un único paquete perdido; 0.02-0.03 para rutas con jitter crónico; 0.03-0.05 solo para rutas de latencia genuinamente alta, que es la razón por la que el techo es 0.05 y no menos. El ping por sí solo —el tuyo o el de tus rivales— no es un motivo: la latencia retrasa el flujo de forma uniforme y la compensación de lag lo tiene en cuenta (el servidor rebobina por ping + interp, así que un interp más alto te cuesta tiempo de reacción, no registro de impactos). **Requerido por KTP.** |
| `fps_max` | **60** - **750** | - | Fotogramas por segundo máximos. **Pon 100.5**, no un 100 exacto: un 100 exacto puede quedar un pelo por debajo de 100 y perder un fotograma de vez en cuando, lo que hace que disparar se sienta entrecortado, y 100.5 le da al limitador margen para mantener un 100 estable. **Requerido por KTP.** |

---

## Referencia Rápida

### Configuración Recomendada (Copiar/Pegar)

```
rate 100000          // lo fija el servidor — cualquier otra cosa se corrige automáticamente
cl_updaterate 102    // el verdadero máximo del cliente (el cliente limita internamente a 102)
cl_cmdrate 101       // igualalo a tu fps_max — no puedes enviar más paquetes que fotogramas
ex_interp 0.01       // un intervalo de actualización de margen; ves a los enemigos lo más cerca posible de su posición real
fps_max 100.5        // un 100 estable (un 100 exacto puede caer por debajo y sentirse entrecortado); usa la tasa de refresco de tu monitor (144/240) si es mayor
cl_lc 1              // compensación de lag para tus disparos — 0 significa adelantar por todo tu ping
cl_lw 1              // predicción de armas del cliente — 0 también desactiva la compensación de lag
cl_fixtimerate 7.5   // velocidad de sincronización del reloj del cliente (predeterminado) — bájalo hacia 0 solo si las animaciones de arma dan saltos
cl_smoothtime 0.01   // corrección de error de predicción casi instantánea — el predeterminado de 0.1 es la opción cómoda para ping alto
```

Si usas un límite de fotogramas mayor a 100.5, sube `cl_cmdrate` para igualarlo (por ejemplo, `fps_max 240` → `cl_cmdrate 250`).

El razonamiento completo detrás de cada valor, además de resolución de problemas: **[Guía de Netcode de KTP](https://netcode.ktpdod.com/)**.

### Verifica tu Configuración

Para consultar tus valores de CVAR actuales dentro del juego, abre la consola (`~`) y escribe el nombre del CVAR sin ningún valor:

```
] cl_updaterate
"cl_updaterate" is "101"
```

---

## Notas Importantes

1. **Aplicación automática**: El servidor de KTP verifica y corrige automáticamente los CVARs que no cumplen
2. **cl_filterstuffcmd**: Debe estar en `0` para que el servidor pueda corregir tus CVARs
3. **Grabación**: Esta configuración no afecta tu capacidad de grabar demos ni de ejecutar KTPAntiCheat
4. **Rendimiento**: Si tienes problemas de rendimiento, contacta a un administrador de KTP antes de cambiar cualquier CVAR bloqueado

---

*Última actualización: septiembre de 2026 — auditado valor por valor contra `ktp_cvar.sma` en KTPCvarChecker **7.39**. Cada cvar controlado de esta página fue comparado con `gs_calvalues[]` / `gs_altvalues[]` en el código fuente. Eliminados el 2026-09-12: `fastsprites`, `gl_nobind`, `gl_nocolors`, `gl_playermip` y `r_luminance`. Day of Defeat no tiene estos ajustes, así que el servidor nunca pudo verificarlos y nadie fue corregido nunca por ellos; quitarlos no cambia nada para los jugadores. Cambio de recomendación el 2026-09-11: `fps_max` 100 → **100.5** (es un cambio de recomendación, no de aplicación; 7.39 lo acepta dentro de su rango de 60-750). Correcciones recientes de aplicación reflejadas aquí: **7.39** techo de `cl_bob` 0.011 → 0.01; **7.38** piso de `ex_interp` 0.009 → 0.01, tomando ahora la corrección que envía el servidor de la cadena del propio límite, de modo que ya no puede indicar un valor que luego rechaza; el techo de `ex_interp` es **0.05**, no 0.03. Dos comportamientos que esta página nunca había indicado quedan ahora escritos: `m_pitch` acepta `-0.022` para el eje vertical invertido, y `hud_takesshots` se controla únicamente en partidos competitivos. Actualización previa de julio de 2026 (referencia rápida revisada contra la configuración de la flota en vivo + KTPCvarChecker 7.30: recomendación de `cl_updaterate` corregida de 101 → 102 [verdadero tope del cliente], contexto añadido para cada ajuste, guía de `cl_lc`/`cl_lw`/`cl_fixtimerate`/`cl_smoothtime` añadida a la sección ajustable por el jugador. Actualización previa de abril de 2026: v7.26 corrigió el valor de aplicación de `r_glowshellfreq` de 0 → 2.2 para coincidir con el valor predeterminado del motor de DoD — los clientes con el valor predeterminado natural estaban siendo expulsados bajo la aplicación previa de 0 de v7.24; ese razonamiento del "0" en realidad no bloqueaba a atacantes con ESP y rompía el renderizado del brillo del portador de la bandera. v7.25 quitó cl_lc y cl_lw de la aplicación tras una auditoría del código del motor que confirmó un comportamiento de mera autolimitación; subió el techo de cl_cmdrate de 500 a 1000 para pruebas de clientes con fps altos. v7.24 había añadido 7 cvars: cl_pitchspeed / cl_yawspeed / cl_anglespeedkey / m_side para defensa de giro con teclado, gl_picmip / r_glowshellfreq / r_traceglow para defensa contra exploits visuales — la aplicación de gl_picmip sigue activa como defensa contra el wallhack por picmip.)*

*¿Preguntas? Contacta a los administradores de KTP por Discord o por el sitio web de la liga.*

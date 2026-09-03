<!-- ktp-translation
locale: es
source: KTP Ruleset.md
source-sha256: 5f160e48fdbefb97096fbeefa2edc8357980efc462432cf7ff2f4613adc028e2

Records which revision of the English ruleset this translation was made from.
ktpleague.gg re-checks it on every render and warns readers when it no longer
matches. Whenever KTP Ruleset.md changes, update this translation and refresh
the hash - the workflow in .github/workflows/ opens a tracking issue for it.
-->
# Reglas Oficiales de la Liga KTP

**Reglamento Competitivo de Day of Defeat 1.3**

[![Version](https://img.shields.io/badge/Version-Season_10_2026-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> **Nota:** Estas reglas rigen la liga competitiva KTP para el mod Half-Life: Day of Defeat. Pueden actualizarse según sea necesario (ver Regla 1.1). Se espera que todos los equipos y jugadores conozcan y cumplan estas reglas. No hacerlo puede derivar en sanciones, incluidas suspensiones y forfeits.

---

## Tabla de Contenidos

- [1. Reglas Generales, Juegos y Servidores](#1-reglas-generales-juegos-y-servidores)
- [2. Equipos, Regiones, HOME/AWAY y Reglas de Ringers](#2-equipos-regiones-homeaway-y-reglas-de-ringers)
- [3. Trampas, Sanciones y Disputas](#3-trampas-sanciones-y-disputas)
- [4. Reglas para Jugadores](#4-reglas-para-jugadores)
- [5. Reglas para Capitanes](#5-reglas-para-capitanes)

---

## 1. Reglas Generales, Juegos y Servidores

> **Resumen de la Sección:** Esta sección cubre la administración de la liga, las definiciones de términos, los requisitos de los servidores y los procedimientos generales de los partidos.

### 1.1 Modificaciones de las Reglas

KTP se reserva el derecho de modificar o actualizar cualquier regla de la liga en cualquier momento y según sea necesario. Esto incluye cambios motivados por actualizaciones del juego, nuevos lanzamientos u otros factores que se consideren necesarios para la liga. Todo cambio de regla se publicará aquí Y se anunciará públicamente (por Discord, el sitio web, etc.). Los equipos son responsables de revisar las reglas con regularidad (especialmente antes de los partidos) para asegurarse de seguir en cumplimiento. Se harán los mejores esfuerzos de buena fe para que nadie se pierda un cambio de regla.

### 1.2 Sanciones por Violaciones de las Reglas

Ante una infracción de las reglas aquí listadas o de las reglas listadas en las Reglas de la Comunidad KTP, la liga puede aplicar sanciones. Según la gravedad, puede ocurrir cualquier combinación de lo siguiente:

- Un jugador (o varios jugadores) puede ser suspendido
- Un solo juego puede perderse por forfeit
- Un partido completo puede declararse como derrota por forfeit para el equipo infractor

### 1.3 Definiciones: Juegos vs Partidos

| Término | Definición |
|------|------------|
| **Juego** | Un solo enfrentamiento entre dos equipos en un mapa, compuesto por dos mitades (los equipos cambian de bando en el entretiempo) |
| **Partido** | Puede constar de varios juegos entre los mismos equipos (p. ej., un mejor de tres puede incluir hasta tres juegos separados en mapas posiblemente distintos) |

> **Importante:** Las suspensiones normalmente se otorgan en términos de una cantidad de **juegos** (o de un período de tiempo), en lugar de partidos completos. Esta distinción es fundamental para entender la duración de las sanciones.

### 1.4 Requisitos para un Juego Válido

Para que cualquier juego oficial sea válido, deben cumplirse las siguientes condiciones:

- [ ] Se debe jugar el mapa correcto (según lo programado)
- [ ] Se debe usar la config de liga KTP correcta para ese mapa
- [ ] El juego debe realizarse en un servidor aprobado por KTP

### 1.5 Servidores Aprobados por KTP

Todos los partidos deben jugarse en un servidor que haya sido aprobado por los administradores de KTP. Para calificar como aprobado, un servidor debe cumplir los siguientes requisitos:

| Requisito | Descripción |
|-------------|-------------|
| **Servidor dedicado** | Debe ser un servidor dedicado (no listen) |
| **Registro habilitado** | El registro (logging) del servidor debe estar configurado para grabar |
| **Requisito de HLTV** | Debe haber un proxy espectador HLTV corriendo con un retraso mínimo de 120 segundos para evitar el ghosting |
| **Configuración** | El servidor y HLTV deben estar configurados con los ajustes oficiales de KTP |
| **Aprobación final** | Se requiere la aprobación de un administrador antes de que el servidor pueda usarse para partidos de KTP |

### 1.6 Acceso de los Administradores a los Servidores

Los dueños de servidores que deseen alojar partidos de la liga deben otorgar a los administradores de KTP acceso completo al servidor:

- Cualquier contraseña de HLTV
- La contraseña de rcon (consola remota) del servidor
- Acceso al panel de control del servidor
- Acceso FTP a los archivos/logs del servidor

### 1.7 Procedimiento ante Caída del Servidor

#### Caída dentro de los primeros 5 minutos de una mitad:
La mitad debe reiniciarse por completo desde el principio (marcador 0-0)

#### Caída después de los primeros 5 minutos de una mitad:
- La mitad se reiniciará con el marcador y el tiempo restante fijados en los valores que tenían al momento de la caída
- Redondear el tiempo hacia arriba al minuto completo más cercano
- El marcador deberá restaurarse manualmente mediante comandos del servidor
- **No se permiten sustituciones de jugadores** durante este reinicio a mitad del juego

> **Notificación obligatoria:** Los equipos deben informar de inmediato a un administrador de la liga cuando ocurra una caída/reinicio.

> **Nota:** Estos mismos procedimientos de caída aplican durante los períodos de tiempo extra. El umbral de 5 minutos aplica a cada mitad de tiempo extra de forma independiente.

### 1.8 Pausas Técnicas (Período de Prueba)

Cada equipo recibe 5 minutos de tiempo de pausa técnica por juego (tiempo reglamentario) para atender problemas técnicos legítimos. El tiempo de pausa reglamentario no utilizado NO se traslada al tiempo extra. Cada período de tiempo extra otorga 5 minutos nuevos de tiempo de pausa por equipo. En series al mejor de tres, cada equipo recibe 5 minutos por cada juego individual.

#### 1.8.a Mecánica de las Pausas

El plugin de partido activa automáticamente una pausa 30 segundos después de la desconexión de cualquier jugador, a menos que el equipo afectado la cancele escribiendo `.nodc` (o `.stopdc`) en el chat durante la cuenta regresiva. Los equipos también pueden iniciar pausas manuales usando comandos `.tech`. Mediante el uso del plugin, todas las pausas requieren la confirmación del equipo contrario para reanudar, seguida de una cuenta regresiva automática antes de que el juego se reanude. A los equipos no se les descuenta tiempo de pausa mientras esperan que el equipo contrario confirme la reanudación.

#### 1.8.b Problemas Técnicos Válidos

Las pausas técnicas están autorizadas únicamente para desconexiones, caídas del juego, fallas de hardware y problemas técnicos genuinos similares. Las pausas para discusiones tácticas, para esperar a jugadores atrasados o para demorar deliberadamente están prohibidas.

#### 1.8.c Requisito de Buena Fe

Ambos equipos deben actuar de buena fe al usar el sistema de pausas. Los equipos deben confirmar las reanudaciones con prontitud una vez resuelto su problema. El abuso del sistema de pausas —incluidas las pausas tácticas, demorar deliberadamente la confirmación de la reanudación o alegar problemas técnicos falsos— derivará en advertencias, suspensión del jugador o la pérdida del partido por forfeit.

#### 1.8.d Estado de Prueba

Este sistema de pausas está bajo evaluación de **PRUEBA** y puede ser modificado o incluso eliminado por completo según el uso de la comunidad, los comentarios recibidos o a discreción de los administradores. Esto podría ocurrir en cualquier momento de esta temporada.

> **Ver también:** Regla 1.7 para los procedimientos ante caída del servidor.

### 1.9 Exploits de Mapa y Posiciones Ilegales

El uso de áreas restringidas o no previstas de un mapa está estrictamente prohibido:

- Pararse sobre repisas o bordes invisibles diminutos que no están pensados para sostener jugadores
- "Pixel-walking y colgarse" (p. ej., posarse en la escalera de dod_harrington mediante un exploit)
- Ingresar a cualquier área que solo sea alcanzable usando un pixel walk

Las violaciones pueden derivar en la suspensión del jugador y/o en la pérdida por forfeit del juego o del partido.

### 1.10 Juegos Empatados y Tiempo Extra

En caso de un juego empatado, se debe jugar tiempo extra de inmediato para determinar un ganador.

**Formato del tiempo extra:**
- Dos mitades adicionales de **10 minutos cada una** (los equipos cambian de bando para la segunda mitad del tiempo extra)
- Si el empate persiste, se continúan jugando mitades adicionales de tiempo extra de 10 minutos hasta que se defina un ganador

> **Sanción:** No completar las rondas de tiempo extra requeridas resultará en que se registre una derrota para **ambos equipos**.

> **Nota:** En partidos al mejor de tres, el tiempo extra aplica a cada mapa individual si ese mapa termina empatado. Cada mapa debe producir un ganador.

### 1.11 Espectadores

No se permiten espectadores no autorizados en el servidor de juego durante partidos oficiales. Los únicos espectadores permitidos son:

- Administradores de KTP
- Transmisores oficiales (p. ej., un proxy HLTV con el retraso requerido, o casters autorizados por la liga)

### 1.12 Admisión de Equipos y Elegibilidad para Participar

KTP se reserva la discreción única y absoluta de aprobar o denegar la entrada de cualquier equipo. Se puede denegar la entrada a un equipo o removerlo por:

| Motivo | Descripción |
|--------|-------------|
| **Conducta Disruptiva** | Comportamiento destinado a provocar conflictos, interferir con el juego o violar las políticas de la liga |
| **Falta de Fiabilidad Operativa** | Patrones de forfeits, partidos no presentados, rotación excesiva del roster o comportamiento que interrumpa la programación de la liga |

### 1.13 BYEs y Puntuación de Forfeits

Un **BYE** es una semana de temporada regular en la que un equipo no tiene partido porque su división
tiene una cantidad impar de equipos. Un **forfeit** es un partido otorgado sin que se juegue.

#### 1.13.a Puntuación de un BYE

Un BYE vale el **promedio de los puntajes que los demás equipos de la división registraron esa semana**, en el
mapa de esa semana. Cada partido jugado en la división esa semana aporta dos puntajes —uno por equipo— y
al equipo con BYE se le acredita su media, tanto como puntos a favor como puntos en contra.

Solo un partido **jugado** aporta puntuaciones a ese promedio. Un partido perdido por forfeit o anulado no
tiene marcador, por lo que no aporta nada: recibe el promedio en lugar de suministrarlo. Además, un equipo
nunca forma parte de su propio promedio. Si en una semana hay un segundo BYE o un forfeit, el promedio se
calcula a partir de los partidos que esa división haya jugado realmente.

El promedio se toma **por semana**, porque cada semana se juega en un mapa y los mapas no puntúan
igual. Nunca se toma a lo largo de toda la temporada.

El promedio es una fracción y se mantiene como tal. La tabla de posiciones lo calcula con hasta cuatro decimales
y lo muestra recortado (un número entero no muestra decimales). Nunca se redondea a un número entero antes de
aplicar los desempates, ya que redondear ocho puntuaciones a puntos enteros podría reordenar una división.

*Ejemplo práctico.* Silver tiene nueve equipos, así que uno no juega cada semana. En la semana 4, en dod_harrington,
los otros ocho juegan cuatro partidos que terminan 429-243, 312-300, 500-180 y 260-411. Los ocho puntajes
promedian 329.375, así que al equipo con BYE se le acreditan 329.375 puntos a favor y 329.375 puntos en contra.

Acreditar el promedio tanto como puntos a favor como puntos en contra es deliberado: significa que un BYE
mueve la diferencia de puntos de un equipo exactamente en cero. Un BYE **no es un resultado** — no suma victoria ni derrota, y no hace que los registros sean
comparables entre equipos que han jugado una cantidad distinta de partidos.

#### 1.13.b Puntuación de un forfeit

Un partido perdido por forfeit se puntúa de la misma manera —el promedio de los puntajes que los demás equipos de la
división registraron esa semana— y se acredita **únicamente al equipo que no dio forfeit**. El equipo que dio forfeit
no recibe puntos por ese partido, ni a favor ni en contra.

Un equipo que se presentó a un partido que su rival no jugó está en la misma posición que un equipo con
BYE: no tuvo rival, sin culpa propia. El equipo que causó eso no merece el
mismo trato, y la derrota en su registro no es la totalidad de la consecuencia.

Un partido perdido por forfeit no aporta nada al promedio a partir del cual se puntúa. No tiene marcador.

Cuando ambos equipos dan forfeit, el partido se **anula** en su lugar (§1.13.c) — ninguno de los dos equipos cobra.

#### 1.13.c Cuándo queda firme cada uno

- Un **BYE** queda firme apenas se han puntuado todos los demás partidos que esa división jugó esa semana. No
  espera al resto de la temporada. Hasta entonces es provisional y se mueve con cada resultado.
- Un **forfeit** se puntúa **solo al final de la temporada regular**, una vez que quede establecido que no
  se jugará ningún partido de reposición. Hasta entonces al equipo que no dio forfeit no se le acredita nada, de modo que un encuentro
  que finalmente sí se juega nunca llevó un crédito.

Un partido **anulado** por decisión de un administrador no puntúa nada para ninguno de los dos equipos, no aporta a ningún
promedio, y no mantiene abierto un BYE ni la temporada.

### 1.14 Tabla de Posiciones y Desempates

La tabla de posiciones cuenta **únicamente los partidos de temporada regular**. Los partidos de playoffs nunca afectan la tabla de la liga. Un
partido anulado por decisión de un administrador no cuenta para ninguno de los dos equipos — ni como victoria, ni como derrota, ni en ningún total.

Los equipos se ordenan por:

1. **Registro** — más victorias, luego menos derrotas.
2. **Enfrentamiento directo** — los resultados entre los equipos que están igualados en registro (ver abajo).
3. **Diferencia de puntos** — puntos de ronda a favor menos puntos de ronda en contra a lo largo de toda la
   temporada regular.

#### 1.14.a Cómo se aplica el enfrentamiento directo

- El **grupo empatado** es todo equipo de la división con un registro idéntico. El enfrentamiento directo se aplica
  a todo el grupo a la vez — **no** es una serie de comparaciones de a pares. Comparar pares no
  es transitivo: con tres o más equipos produce una respuesta distinta según qué par se
  compare primero, y puede no producir respuesta alguna.
- El grupo se ordena según una **mini-tabla** de los partidos que esos equipos jugaron entre sí,
  contando los mismos partidos que cuenta la tabla de posiciones (temporada regular, jugados o perdidos por forfeit). Un forfeit es
  un resultado de enfrentamiento directo como cualquier otro.
- La mini-tabla se ordena **solo por registro** — más victorias en la mini-tabla, luego menos derrotas en la mini-tabla.
  **La diferencia de puntos de la mini-tabla deliberadamente no se usa**, en ningún paso. Ver §1.14.c.
- El enfrentamiento directo aplica **solo cuando cada equipo del grupo ha jugado contra al menos uno de los otros**.
  Si algún equipo empatado no ha jugado contra ninguno de ellos, el enfrentamiento directo se omite para todo el grupo y el empate
  se resuelve por diferencia de puntos. Un enfrentamiento directo no jugado nunca se trata como un registro de 0-0.
- Los equipos que sigan igualados después de la mini-tabla pasan a la diferencia de puntos. La mini-tabla se
  aplica una sola vez; la regla no recurre a un empate más pequeño dentro del grupo.

#### 1.14.b Ejemplo práctico

Dos equipos terminan 5-2. Uno está en +500 de diferencia, el otro en +100. El equipo de +100 ganó el partido
entre ambos, así que termina por delante — el enfrentamiento directo se aplica antes que la diferencia. Las columnas
visibles no pueden mostrar esto por sí solas, y por eso la página de posiciones marca una fila así y nombra
el resultado que la ubicó.

#### 1.14.b.i Equipos que siguen igualados después de los tres pasos

> **Nota de ubicación.** Esta regla está numerada bajo el §1.14.b (el ejemplo práctico) pero aplica al §1.14.a y a los desempates
> en general, no solo al ejemplo anterior. El identificador y el nivel del encabezado se dejan sin cambios a propósito: el sitio
> web genera anclajes a partir del número de regla, y ambas traducciones reflejan esta estructura línea por línea.

Si dos o más equipos permanecen exactamente igualados después del registro, el enfrentamiento directo y la diferencia de puntos, y el
orden decide una siembra de playoffs o cualquier otra consecuencia, **un administrador de KTP resuelve el orden y la
resolución se registra públicamente.** No se aplica ningún criterio automático adicional.

⛔ **El orden mostrado en la página de posiciones no es autoritativo en este caso.** El sitio rompe el
empate restante con un identificador interno únicamente para que la tabla no se reordene entre cargas de página.
Eso no tiene significado deportivo. Hasta que un administrador haya resuelto, trata esas filas como no ordenadas.

#### 1.14.c Por qué la mini-tabla ignora la diferencia de puntos

En un empate circular a tres bandas cada equipo está 1-1 dentro del grupo, así que la mini-tabla no separa a nadie
y el empate pasa a la diferencia de puntos **general**. Este es un precedente establecido de la liga: los empates a tres bandas
de Silver en las Temporadas 4, 5 y 8 se resolvieron todos de esa manera. Agregar un paso de diferencia en la mini-tabla
revertiría esos resultados. El paso está ausente a propósito — no es un descuido que haya que
ordenar más adelante.

### 1.15 Idioma y Traducciones

El texto en inglés de este reglamento es la versión oficial y rectora. Las traducciones a otros idiomas se ofrecen únicamente por conveniencia.

Cuando una traducción y el texto en inglés difieran —en redacción, en significado, o por un error u omisión de traducción— rige el texto en inglés. Todas las resoluciones, sanciones y decisiones sobre disputas se toman sobre la base de las reglas en inglés, y ninguna resolución puede apelarse alegando que una traducción decía algo distinto.

> **Importante:** Si una regla traducida resulta poco clara o parece contradecir el inglés, lee la versión en inglés o pregunta a un administrador de KTP antes de actuar según ella. Una mala interpretación de una traducción no es una defensa ante una violación de las reglas.

---

## 2. Equipos, Regiones, HOME/AWAY y Reglas de Ringers

> **Resumen de la Sección:** Esta sección cubre la composición de los equipos, la programación, la selección de servidor por región, la gestión del roster y las reglas para el uso de jugadores suplentes (ringers).

### 2.1 Composición del Equipo (Internacional vs NA)

| Tipo de Equipo | Definición |
|-----------|------------|
| **Internacional** | La mayoría de los jugadores (4 o más) radicados fuera de Norteamérica (EU, SA, etc.) |
| **Norteamericano** | Mayoría de jugadores norteamericanos |

### 2.2 Horarios Predeterminados de Programación de Partidos

#### 2.2.a Horario Predeterminado Estándar
Domingo a las 9:00 PM hora del Este (EST).

#### 2.2.b Horario Predeterminado Internacional
Cuando uno o ambos equipos tienen mayoría de jugadores de EU al este de UTC -2, el horario predeterminado del partido es el domingo a las 3:00 PM EST.

> Los horarios pueden ajustarse por el horario de verano.

### 2.3 Ventaja del Equipo Local

#### 2.3.a Partidos Estándar
El equipo listado en el calendario como equipo **HOME** tiene la elección del uso del servidor para ambas mitades, así como la elección de qué bando (Allies o Axis) tomar primero.

#### 2.3.b Partidos al Mejor de Tres (BO3)
Cada mapa se trata de forma independiente. El equipo que eligió un mapa se considera el equipo "home" para ese mapa.

### 2.4 Selección de Servidor por Región

#### 2.4.a NA vs NA — Selección de Servidor por el Equipo HOME

Para partidos entre equipos norteamericanos (sin ningún equipo Internacional involucrado), el equipo **HOME** selecciona la ubicación del servidor de juego entre las siguientes ubicaciones aprobadas por KTP:

| Ubicación | Estado |
|----------|--------|
| **Chicago** | Disponible |
| **Dallas** | Disponible |
| **Denver** | Disponible |

El equipo HOME puede proponer una ubicación alternativa de servidor aprobada por KTP que no esté listada arriba, pero esto queda sujeto a la aprobación del capitán del equipo contrario. Si el capitán contrario no aprueba la ubicación alternativa, el equipo HOME debe elegir entre las tres ubicaciones estándar listadas arriba.

> **Importante:** Los partidos nunca pueden jugarse en servidores no aprobados por KTP, sin importar que haya acuerdo mutuo.

> **Política de Prueba:** Esta política de selección de servidor por el equipo local se introduce como una prueba para evaluar su impacto en el equilibrio competitivo y la calidad de los partidos. La liga monitoreará su uso y podrá ajustar las ubicaciones disponibles, volver a la asignación neutral de servidor, o modificar el proceso de selección según los comentarios de la comunidad y los resultados competitivos.

#### 2.4.b Internacional vs Internacional

Para partidos entre equipos Internacionales (mayoría de jugadores de EU/SA según la Regla 2.1), el equipo **HOME** selecciona la ubicación del servidor de juego entre las siguientes ubicaciones aprobadas por KTP:

| Ubicación | Estado |
|----------|--------|
| **Atlanta** | Disponible |
| **New York** | Disponible |

El equipo HOME puede proponer una ubicación alternativa de servidor aprobada por KTP que no esté listada arriba. La ubicación alternativa requiere la aprobación del capitán del equipo contrario. Si el capitán contrario no la aprueba, el equipo HOME debe elegir entre las ubicaciones estándar listadas arriba.

> **Importante:** Los partidos nunca pueden jugarse en servidores no aprobados por KTP, sin importar que haya acuerdo mutuo.

#### 2.4.c NA vs EU — Selección de Servidor

Para partidos entre un equipo norteamericano y un equipo europeo (mayoría de jugadores de EU al este de UTC -2 según la Regla 2.1), el equipo **HOME** selecciona la ubicación del servidor de juego entre las siguientes ubicaciones aprobadas por KTP, con prioridad para New York:

| Ubicación | Estado |
|----------|--------|
| **New York** | Primaria |
| **Atlanta** | Solo de respaldo (si New York no está disponible) |

New York debe usarse siempre que esté disponible. Atlanta solo puede seleccionarse si no hay servidores de New York disponibles al momento de la programación o del inicio del partido. Estas ubicaciones de la Costa Este ofrecen una latencia de compromiso razonable para las conexiones transatlánticas.

El equipo HOME puede proponer una ubicación alternativa de servidor aprobada por KTP que no esté listada arriba. La ubicación alternativa requiere la aprobación del capitán del equipo contrario. Si el capitán contrario no la aprueba, el equipo HOME debe elegir entre las ubicaciones estándar listadas arriba, respetando el orden de prioridad.

> **Importante:** Los partidos nunca pueden jugarse en servidores no aprobados por KTP, sin importar que haya acuerdo mutuo.

#### 2.4.d NA vs SA — Selección de Servidor

Para partidos entre un equipo norteamericano y un equipo sudamericano (mayoría de jugadores de SA al oeste de UTC -2), el equipo **HOME** selecciona la ubicación del servidor de juego entre las siguientes ubicaciones aprobadas por KTP:

| Ubicación | Estado |
|----------|--------|
| **Atlanta** | Disponible |
| **New York** | Disponible |

Estas ubicaciones ofrecen una latencia de compromiso razonable para las conexiones sudamericanas.

El equipo HOME puede proponer una ubicación alternativa de servidor aprobada por KTP que no esté listada arriba. La ubicación alternativa requiere la aprobación del capitán del equipo contrario. Si el capitán contrario no la aprueba, el equipo HOME debe elegir entre las ubicaciones estándar listadas arriba.

> **Importante:** Los partidos nunca pueden jugarse en servidores no aprobados por KTP, sin importar que haya acuerdo mutuo.

#### 2.4.e Selección de Bando para NA vs EU

Cuando un equipo norteamericano juega contra un equipo europeo (mayoría de jugadores de EU al este de UTC -2 según la Regla 2.1), el **equipo de NA siempre elige** en qué bando (Allies o Axis) jugar primero, **anulando la ventaja del equipo local definida en la Regla 2.3.a**. Esto compensa la ventaja de programación que los equipos de EU reciben por el horario predeterminado de partido más temprano.

### 2.5 Uso de Jugadores Suspendidos

Los equipos no pueden incluir en el roster ni hacer jugar a personas que estén suspendidas por KTP. Las violaciones resultan en:
- Remoción del equipo de la liga
- Posible suspensión de todos los miembros del equipo
- Suspensión de cualquiera que preste cuentas para evadir baneos

### 2.6 Cambios de Nombre de Equipo

Un equipo puede cambiar su nombre **una vez** durante el transcurso de una temporada. Después de usar ese único cambio de nombre, el nombre del equipo queda bloqueado por el resto de la temporada.

### 2.7 Rosters y Bloqueos de Roster

| Regla | Detalles |
|------|---------|
| **Tamaño máximo del roster** | 10 jugadores |
| **Momento del bloqueo** | Fin del período de registro de equipos |
| **Después del bloqueo** | Sin cambios en el roster, el nombre del equipo, los alias de los jugadores ni los SteamIDs |
| **Excepción** | Aún pueden hacerse cambios por decisión de un administrador — ver Regla 2.7.a |

#### 2.7.a Solicitud de un Cambio de Roster

Los cambios de roster se solicitan en el sitio web de la liga (ktpleague.gg) en la configuración de tu cuenta, no por ticket de soporte.

| Cuándo | Capitán | Jugador que pide salir |
|------|---------|------------------------|
| **Registro abierto** | Edita el roster directamente; se notifica a los administradores qué cambió | Presenta una solicitud |
| **Registro cerrado, antes del bloqueo** | Presenta una solicitud; el personal la revisa | Presenta una solicitud |
| **Después del bloqueo** | El formulario del capitán se cierra — consulta a un administrador | Presenta una solicitud |

Un jugador puede pedir salir de un roster **en cualquier momento, antes o después del bloqueo**, desde la configuración de su propia cuenta. Es una solicitud en todos los casos: el jugador permanece en el roster hasta que un administrador actúe sobre ella, y una solicitud que dejaría a un equipo sin capitán no se aplica hasta que otro capitán esté en su lugar.

Cada solicitud y cada decisión quedan registradas.

### 2.7.1 Ventana de Roster de Media Temporada

Habrá una ventana de incorporación al roster a mitad de temporada, anunciada con al menos una semana de anticipación.

| División | Requisitos |
|----------|--------------|
| **División más alta** | Las incorporaciones se aprueban si hay un lugar disponible en el roster (hasta 10) |
| **Otras divisiones** | Se requiere aprobación de un administrador (preserva la integridad competitiva) |

### 2.8 No Se Pueden Eludir las Reglas por Acuerdo

Ningún acuerdo entre capitanes de equipo puede anular las reglas oficiales ni las suspensiones activas. Tales acuerdos son inválidos y constituyen una violación de las reglas.

### 2.9 Ringers

Un **ringer** es un jugador que no está en tu roster oficial y que se usa temporalmente como reemplazo. El uso de ringers requiere la aprobación del capitán del equipo contrario antes de que comience el partido.

### 2.10 Mínimos de Roster en los Partidos

| Requisito | Detalles |
|-------------|---------|
| **Jugadores del roster** | Al menos 4 de 6 jugadores deben ser del roster oficial |
| **Máximo de ringers** | Se permiten hasta 2 ringers aprobados |

### 2.11 Forfeits de Equipo y Remoción

Los equipos que den forfeit repetidamente pueden ser removidos de la liga. Más de un forfeit en una temporada puede derivar en la remoción a discreción de los administradores.

---

## 3. Trampas, Sanciones y Disputas

> **Resumen de la Sección:** Esta sección detalla qué constituye hacer trampa, el proceso de disputas, los requisitos de evidencia y las sanciones por violaciones.

### 3.1 Autoridad de los Administradores

Los administradores de la liga se reservan el derecho de imponer suspensiones, forfeits u otras sanciones según sea necesario. Todas las decisiones apuntan a preservar el juego limpio y la integridad competitiva.

### 3.2 Investigaciones y Evidencia

Los administradores de KTP pueden investigar a cualquier jugador o equipo por comportamiento sospechoso, incluyendo:
- Solicitar POV demos de jugadores al azar, y revisar los registros de KTPAntiCheat
- Realizar controles puntuales en cualquier momento

**No proporcionar los materiales solicitados puede derivar en:**
- La pérdida por forfeit del juego/partido en cuestión
- La suspensión del jugador

### 3.3 Tolerancia Cero ante las Trampas

Todo jugador que sea hallado haciendo trampa será suspendido (o baneado) de KTP, y cualquier resultado de partido influido queda sujeto a ser revertido o perdido por forfeit.

#### 3.3.a Alcance de un Baneo

Un baneo puede aplicarse a un jugador y, cuando exista evidencia de evasión del baneo, al hardware usado para evadirlo. Un baneo aplica en todos los servidores operados por KTP.

Cuando el hardware es compartido —una máquina de un local, un hogar, una computadora compartida— un baneo de hardware no debe aplicarse sin evidencia que conecte al jugador específico con la evasión. Una persona afectada por un baneo de hardware que no fue parte de la evasión puede impugnarlo bajo la Regla 3.9.a y, si la impugnación prospera, debe ser restituida.

### 3.4 Definición de Trampa

Hacer trampa incluye (entre otras cosas):
- Wallhacks (ver enemigos a través de paredes)
- Aimbots (adquisición automática de objetivos)
- Modificar ilegalmente archivos del juego
- Cualquier programa externo que otorgue una ventaja injusta
- Multiplicación de inputs — modos "Snap Tap" / cancelación por nulo SOCD, "Rapid Fire" / Turbo (auto-repetición), o cualquier bind, script o función de dispositivo que produzca más de un input a partir de una sola actuación física, acelere el disparo o eluda la estamina (ver Regla 4.6)

### 3.5 Archivos de Juego Permitidos y Prohibidos

Solo pueden usarse los archivos de juego por defecto, con estas excepciones:

#### Modificaciones Permitidas:
| Modificación | Estado |
|--------------|--------|
| HUD/UI de marcador personalizado aprobado | Permitido |
| Modelos personalizados de HLTV | Permitido |
| Modificaciones de ClientScheme.res | Permitido |
| Modificaciones de TrackerScheme.res | Permitido |
| Mira personalizada (armas que no sean de francotirador) | Permitido |
| Mira personalizada para el rifle de francotirador | **NO Permitido** |

### 3.6 Regla de Espectador Dentro del Juego (Prohibido Espectar una Vez en Vivo)

Una vez que un partido está "en vivo", ningún jugador puede usar el modo espectador. El **spec hopping** se considera hacer trampa.

**Excepciones:**
- Jugador muerto en el instante exacto de la captura total del mapa
- Jugador que queda atascado en la geometría del mapa

### 3.7 Presentación de Disputas

Las disputas deben ser presentadas por el capitán del equipo **dentro de las 24 horas** de finalizado el partido.

| Fase de la Temporada | Límite de Disputas |
|--------------|---------------|
| Temporada regular | 2 disputas por trampas |
| Postemporada (playoffs) | 1 disputa por trampas |

> **Nota:** Las disputas válidas (en las que el acusado es hallado culpable) no cuentan contra tu límite.

### 3.8 Proceso de Disputa para Jugadores Acusados

#### 3.8.a Plazo de Presentación de Evidencia
Los jugadores tienen **24 horas desde la notificación** para presentar:
- POV demos
- Cualquier otro material solicitado

#### 3.8.b Consecuencias e Investigación
- No proporcionar los archivos puede derivar en suspensión y/o forfeit
- Los administradores pueden revisar demos y registros de KTPAntiCheat de partidos previos o posteriores
- El jugador puede quedar sujeto a un escrutinio adicional en juegos futuros

### 3.9 Registros de KTPAntiCheat

Los registros de KTPAntiCheat son producidos automáticamente por el cliente y conservados por la liga; los jugadores no están obligados a presentarlos. En caso de una disputa o un control aleatorio, los jugadores deben proporcionar sus POV demos del partido en cuestión.

Cada sesión se evalúa en los servidores de KTP a partir de la evidencia presentada. Las sesiones pueden reevaluarse cuando cambian los métodos de detección, incluidas sesiones de etapas anteriores de la temporada; una reevaluación puede cambiar un resultado previo en cualquiera de las dos direcciones.

**Conservación:** Las cargas de sesiones se conservan indefinidamente para revisión de integridad, de modo que una determinación siempre pueda reexaminarse a partir de la evidencia original. La telemetría de partido se conserva por **30 días**; los registros de sesión y sus resultados se conservan durante toda la temporada. Una determinación que se apoye en telemetría solo puede reexaminarse mientras esa telemetría siga conservada.

#### 3.9.a Impugnación de una Determinación de KTPAntiCheat

Un jugador puede impugnar una determinación de KTPAntiCheat, incluida una determinación de cobertura, notificando a un administrador dentro de los **14 días** de haber sido informado de ella. Las determinaciones se reexaminan a partir de la evidencia original cuando esta sigue conservada (ver Regla 3.9).

Un jugador puede revisar sus propias sesiones cargadas en cualquier momento a través del sitio web de la liga KTP (ktpleague.gg), incluidas capturas de pantalla, archivos de configuración e inventario de dispositivos, y puede descargar su propia copia. Pueden retenerse artefactos individuales de esa copia cuando su divulgación revelaría cómo KTPAntiCheat detecta las trampas. Cuando se retiene algo, se le informa al jugador que se retuvo material, y un administrador que no haya realizado la determinación original explicará el motivo si se le solicita. El material retenido igualmente se examina en su totalidad cuando se revisa una impugnación bajo esta regla.

Un administrador que no haya realizado la determinación original revisa la impugnación. El resultado es uno de estos: determinación confirmada, determinación retirada o determinación modificada. Se le informa al jugador cuál y por qué.

Un resultado automatizado nunca es por sí solo un resultado final — una persona revisa toda determinación antes de que se aplique una sanción.

---

## 4. Reglas para Jugadores

> **Resumen de la Sección:** Esta sección detalla el registro de jugadores, los requisitos de identidad, las obligaciones de grabación, la conservación de archivos y las conductas prohibidas.

### 4.1 Registro e Identidad del Jugador

#### 4.1.a Reglas de la Comunidad y Conducta
Todos los jugadores aceptan cumplir en todo momento con las **Reglas de la Comunidad KTP**.

#### 4.1.b Registro de Alias y SteamID
- Un alias dentro del juego y una cuenta de Steam por jugador
- Se permite cambiar el alias y/o el SteamID **una vez** por temporada
- Los cambios deben informarse a los administradores de la liga

#### 4.1.c Requisitos de Identidad Dentro del Juego
- Debe usarse el SteamID registrado exacto
- Debe usarse el tag del equipo y el alias registrado del jugador
- Se permiten variaciones menores de formato (códigos de color, abreviaturas)

#### 4.1.d Verificaciones de Integridad de Archivos y CVAR
Todos los jugadores deben cumplir con las verificaciones de integridad de archivos, de CVAR y de anti-trampas. Los jugadores no deben interferir con estos sistemas ni eludirlos.

#### 4.1.e KTPAntiCheat

Todo jugador debe ejecutar la versión actual de **KTPAntiCheat** durante toda la duración de cada partido que juegue. Un partido está cubierto cuando la sesión de KTPAntiCheat del jugador está en ejecución antes de que el partido comience y sigue en ejecución hasta que termina.

Los jugadores no deben alterar, manipular ni interferir con el cliente, sus registros de sesión o sus cargas, y no deben presentar ni hacer que se presente ningún registro que no sea el suyo.

Un jugador cuyo partido no esté cubierto queda sujeto al mismo tratamiento que cualquier otra violación de la Sección 4. La reiteración en no cubrir partidos puede tratarse como evasión.

La cobertura se determina a partir de los propios registros de KTPAntiCheat. Un jugador puede impugnar una determinación de cobertura bajo la Regla 3.9.a.

Una falla técnica —una caída, una desconexión o una interrupción de KTPAntiCheat— no es una violación, siempre que el jugador la reporte a un administrador antes del siguiente partido. Los administradores pueden aceptar un partido sin cobertura a su discreción cuando la causa sea evidente.

#### 4.1.f POV Demos y Capturas de Pantalla

**POV Demos:**
- Graba una POV demo por cada mitad (dos demos por juego completo)
- Comienza a grabar antes de la primera ronda, detén la grabación cuando termine la mitad

**Captura de Pantalla Previa al Juego:**
- Toma una captura de pantalla que muestre al menos un modelo de jugador de cada equipo
- Verifica que los modelos/skins de los jugadores sean los correctos

**Capturas de Pantalla del Marcador al Final de Cada Mitad:**
- Captura el marcador al final de cada mitad
- Se usa para verificar el puntaje y la participación de los jugadores

**Permanece Hasta el Final del Juego:**
- No te desconectes hasta que el partido haya terminado por completo
- Si sufres una caída, vuelve a conectarte de inmediato

**Demos de Tiempo Extra:**
- Graba POV demos separadas para cada mitad de tiempo extra siguiendo el mismo procedimiento que en las mitades reglamentarias

#### 4.1.g Longitud y Formato del Nombre de Personaje

Todos los alias de jugador, tags de equipo y nombres completos dentro del juego deben cumplir con los siguientes requisitos técnicos para garantizar la compatibilidad con el motor del juego:

**Longitud Máxima:**
Los alias de jugador y los tags de equipo no deben exceder los 30 caracteres visibles. Los nombres completos dentro del juego (tag del equipo + alias del jugador) tampoco deben exceder los 30 caracteres visibles en total.

**Restricción del Conjunto de Caracteres:**
Solo se permiten caracteres ASCII estándar. Esto incluye:
- Letras: A-Z, a-z
- Números: 0-9
- Símbolos básicos: ! @ # $ % ^ & * ( ) - _ = + [ ] { } | \ ; : ' " , . < > ? / ~
- Espacios (aunque el espaciado excesivo no se recomienda)

**Prohibido:**
Lo siguiente no está permitido en los nombres de jugador ni en los tags de equipo:
- Caracteres UTF-8, Unicode o multibyte (p. ej., emoji, alfabetos no latinos, símbolos especiales como ™ © ®)
- Caracteres fuera del rango ASCII estándar
- Cualquier carácter que pueda causar problemas de visualización o inestabilidad del motor

**Aplicación:**
Los nombres de jugador o tags de equipo que violen estos requisitos deben cambiarse antes de jugar el partido.

### 4.2 Los VODs No Son Reemplazos Aceptables

Las grabaciones de video o los VODs de Twitch **NO** son sustitutos de las demos ni de KTPAntiCheat. Igualmente debes grabar demos dentro del juego y ejecutar KTPAntiCheat aunque estés transmitiendo.

### 4.3 Conservación de Archivos

Conserva todos los archivos del partido **durante toda la temporada**:
- POV demos de cada mitad
- Todas las capturas de pantalla requeridas

> **Nota:** No hay ningún archivo de anti-trampas que los jugadores deban conservar — los registros de KTPAntiCheat son producidos y conservados por la liga (ver Regla 3.9).

### 4.4 Impulso de Jugadores (Boosting)

El boosting está **permitido únicamente si** el área de destino es alcanzable por un solo jugador sin un impulso. Hacer boosting para acceder a áreas con fallas o no previstas es ilegal.

### 4.5 Comandos de Voz y Señales

Los comandos de voz deben usarse únicamente para la comunicación del equipo. El uso excesivo para burlarse, molestar o "neguear" a los oponentes no está permitido.

### 4.6 Asignaciones de Teclas y Funciones de Dispositivos

**Principio:** una actuación física equivale a un input dentro del juego. Un dispositivo puede cambiar *cuándo* se registra una sola tecla (su punto de actuación/reinicio); no puede multiplicar una acción física en varios inputs, auto-repetir un input, ni resolver un input por ti.

**Permitido:** Rapid Trigger y puntos de actuación ajustables — estos cambian solo *dónde*, dentro del recorrido de una tecla, se registra una sola pulsación. Una pulsación sigue siendo un input, así que el jugador sigue siendo quien limita la cadencia. ("Rapid Trigger" es el término estándar de la industria —usado por Wooting, Razer, SteelSeries, Corsair, etc.— para un punto de reinicio dinámico/continuo en teclados de efecto Hall/analógicos y en switches analógicos de mouse. Rapid Trigger está permitido tanto en teclados como en mouses. **No** es lo mismo que la auto-repetición "Rapid Fire" / "Turbo" prohibida más abajo.)

**Prohibido:**
- **Una tecla asignada a `+attack` debe emitir `+attack` y nada más.** Asignar o crear un alias de `+attack` junto con cualquier comando adicional —de forma directa, mediante un alias, o mediante una config ejecutada con exec— está prohibido.
- Asignar `+attack` o `+duck` a la rueda del mouse (acelera el disparo / elude las restricciones de estamina)
- Modos "Rapid Fire", "Turbo" o de multi-pulsación de teclado/mouse que emitan inputs repetidos a partir de una sola pulsación
- Binds de "Snap Tap" / manejo SOCD / cancelación por nulo que auto-liberan una de dos teclas de movimiento opuestas (**SOCD** es el término genérico; "Snap Tap" es el nombre de marca de Razer)

**Notas:**
- La reasignación de teclas no se ve afectada. `+attack` puede asignarse a cualquier tecla, y otros comandos pueden tener sus propias teclas. Solo está prohibido combinarlos en la tecla de disparo.
- Los comandos de fábrica no son sospechosos en sí mismos. `+lookup`, `+lookdown`, `+left`, `+right` y `centerview` vienen como valores por defecto de Half-Life y aparecen en la mayoría de las configs.
- `+jump` en la rueda sigue estando permitido (bunny-hopping).

### 4.7 Prohibición de Scripts Automatizados

Los jugadores no pueden usar scripts para automatizar:
- El ataque del jugador
- El movimiento del jugador
- Rapid-fire
- Compensación automática de retroceso
- Salto o patrones de movimiento automatizados

### 4.8 Explotación de Movimiento/Animación

Los jugadores no pueden usar señas con las manos, comandos de voz o alternancias de cvar junto con comandos de movimiento para hacer que su modelo de jugador sea más difícil de acertar. Toda táctica que deforme, haga vibrar o desalinee tu hitbox es ilegal.

### 4.9 Fallas y Exploits

Lo siguiente se considera hacer trampa:

| Exploit | Descripción |
|---------|-------------|
| **Generación de Armas** | Generar armas/munición extra para eludir las limitaciones de clase |
| **Glitch de Granadas** | Duplicar granadas o eludir las mecánicas normales |
| **Bugs de Mapa** | Atravesar paredes, meterse debajo o por encima del mapa |
| **Pixel Walking** | Usar puntos de colisión no previstos para obtener un posicionamiento injusto |
| **Wall Glitching** | Hacer que el modelo del jugador asome a través de paredes para ver o disparar al otro lado |

> **Principio general:** Todo exploit que no sea parte del juego limpio y previsto es ilegal, incluso si no está listado explícitamente.

---

## 5. Reglas para Capitanes

> **Resumen de la Sección:** Esta sección detalla las responsabilidades y requisitos específicos de los capitanes de equipo.

### 5.1 Deberes del Capitán Dentro del Juego

#### 5.1.a Marcadores Legibles
Los capitanes deben configurar los ajustes de su cliente mediante un client scheme personalizado para que los marcadores de fin de mitad sean fáciles de leer en las capturas de pantalla (alto contraste, tipografía clara).

#### 5.1.b Captura de Pantalla de RCON Status
Los capitanes deben tomar una captura de pantalla de `rcon status` por juego para comprobar los SteamIDs de los jugadores.

### 5.2 Comunicación y Disponibilidad

- Los capitanes no deben estar baneados del Discord de KTP
- Deben ser localizables y responder con prontitud a los mensajes de programación
- Si están ausentes, deben designar un capitán suplente e informar a los administradores

### 5.3 Puntualidad en los Partidos y Victorias por Forfeit

| Tiempo | Acción |
|------|--------|
| **+10 minutos** | Documentar y avisar a un administrador si no hay noticias del equipo contrario |
| **+15 minutos** | Un administrador puede declarar oficialmente la no presentación y otorgar la victoria por forfeit |

### 5.4 Programación Justa

Los capitanes deben programar con integridad:
- Ser proactivos en la comunicación
- Ofrecer varios horarios razonables
- Responder con prontitud
- Guardar registros de las comunicaciones de programación

#### 5.4.a Plazo de Programación Reglamentario

Todos los partidos de temporada regular deben completarse antes de la **medianoche que cierra el
último domingo de la temporada regular** (00:00 hora del Este del día siguiente). Un partido
que en ese plazo siga sin jugarse o sin un horario confirmado se remite al
equipo de administradores junto con todo su registro de programación — cada horario propuesto,
cada respuesta y cada recordatorio que la liga intentó entregar.

- **No hay forfeits automáticos.** El plazo marca un partido para revisión administrativa;
  nunca decide un resultado. Los administradores resuelven bajo §1.13 y §3.1, ponderando quién
  propuso horarios, quién guardó silencio y —como hecho aparte— si se pudo contactar
  siquiera a los capitanes de un equipo.
- Un equipo cuyos capitanes fueron inubicables por todos los canales que la liga tiene es un
  caso distinto al de un equipo que sí fue contactado y no respondió. El
  registro de programación muestra cuál es cuál.

### 5.5 Verificaciones de Roster y Ringers

Los capitanes deben verificar la elegibilidad de los jugadores antes de que comience el partido:
- Comprobar que los jugadores contrarios coincidan con los nombres y SteamIDs del roster
- Verificar que todos los ringers hayan sido aprobados

> **Importante:** Una vez completado un partido, no puedes disputarlo alegando un jugador no elegible si tuviste la oportunidad de detectarlo de antemano.

### 5.6 Reporte de Resultados

Los resultados se reportan en la página del partido en el sitio web de la liga (ktpleague.gg) dentro de **1 hora de finalizado el partido**. La obligación de reportar dentro de esa hora recae en el **capitán del equipo ganador**; cualquiera de los dos capitanes puede ingresar el resultado, y un capitán perdedor que lo ingrese primero cumple con la obligación.

El reporte es de dos lados. Un capitán ingresa el resultado, el capitán **contrario** lo confirma, y el resultado queda registrado —y la tabla de posiciones se mueve— solo con esa confirmación. Un capitán no puede confirmar el reporte de su propio equipo.

**Capitán que reporta:**

- [ ] Ingresa el total final de puntos de cada equipo para el partido
- [ ] Revisa el ganador que el sitio te indica de vuelta antes de enviar — un marcador invertido es el error común, y el otro capitán es la única persona que puede detectarlo

**Capitán contrario:**

- [ ] Confirma el resultado, o dispútalo con un motivo, **dentro de las 24 horas** de que se te pida

Un capitán que no esté de acuerdo con un resultado ingresado lo disputa en lugar de confirmarlo. Un resultado disputado nunca queda registrado; pasa al equipo de administradores junto con la versión de ambos capitanes.

Las capturas de pantalla **no** se cargan junto con el reporte. Los capitanes igualmente las toman (Regla 5.1.a, Regla 5.1.b), las conservan durante la temporada (Regla 4.3), y deben presentarlas cuando se les solicite — un resultado disputado se resuelve a partir de ellas.

> **Nota:** Los resultados de las series de playoffs y los forfeits son registrados por los administradores, no mediante el reporte de los capitanes. Envía los marcadores de playoffs a un administrador cuando la serie termine.

> **Si el sitio no puede recibir el reporte:** publícalo en el canal de marcadores designado del Discord de KTP dentro de esa misma hora y avísale a un administrador. Eso es un recurso alternativo ante una interrupción, no una segunda vía de reporte.

### 5.7 Vetos de Mapas en Playoffs

Los vetos se realizan únicamente para partidos de playoffs. Tienen lugar en la sala de vetos en la página del partido en el sitio web de la liga (ktpleague.gg): ambos capitanes actúan por turnos —baneos, elecciones y bandos iniciales— sobre el pool de mapas de playoffs publicado. El sitio decide de quién es el turno y rechaza una jugada ilegal, así que no hay nada que enviar en ningún otro lado.

Los capitanes deben completar el veto **al menos 72 horas antes del horario predeterminado de inicio del partido de esa ronda** (Regla 2.2). El plazo se mide desde el horario predeterminado, no desde ningún horario posterior que los dos capitanes acuerden entre sí.

> **Sanción:** Si el veto no está completo en ese plazo, los administradores realizan los pasos pendientes en nombre del equipo atrasado. Un paso realizado de esa manera se marca como acción del personal en el registro de vetos del partido, que es público.

La duración de la serie la fijan los administradores en el partido. La mayoría de los partidos de playoffs son al mejor de tres; el veto se realiza de la misma forma para un mejor de uno o un mejor de cinco.

#### 5.7.a Cuando una Ronda se Resuelve Tarde

Un partido de playoffs no tiene equipos hasta que se decide la ronda previa. Cuando ambos equipos se conocen **menos de 72 horas antes** del inicio predeterminado de la ronda, el plazo de 72 horas no pudo haberse cumplido y no se computa en contra de ninguno de los dos equipos. En su lugar, el veto vence **apenas ambos capitanes hayan tenido una oportunidad razonable de realizarlo**, y los administradores pueden realizar los pasos pendientes una vez que el partido deba jugarse por lo demás.

### 5.8 Responsabilidad del Capitán

Los capitanes son responsables de asegurar que los miembros del equipo comprendan y sigan todas las reglas. Las violaciones reiteradas del equipo pueden derivar en la suspensión del capitán por negligencia.

---

**Fin del Documento de Reglas**

*Última actualización: agosto de 2026*

*¿Preguntas? Contacta a los administradores de KTP por Discord o por el sitio web de la liga.*

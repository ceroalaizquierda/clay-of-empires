# Datos del juego

Todos los números y tablas del juego, en JSON. El prototipo web los lee al iniciar (`cargarDatos()` en
`index.html`) y la versión en Godot va a leer **los mismos archivos**: para ajustar el equilibrio se
cambia acá, no en el código.

| Archivo | Contenido |
|---|---|
| `unidades_y_edificios.json` | `tipos`: vida, velocidad, alcance, daño, cadencia, radio, altura, sprite y banderas (unidad, militar, trabajador, edificio, población, defensa, depósito, campo, recurso, `muro` con su `grosor` y `permite` = investigación que lo habilita, `material`, `arde`, `ataque`, `soloEdificios`, `rangoMin`, `area`, `despliega`…) de cada tropa, edificio, recurso y animal |
| `civilizaciones.json` | `civs`: fichas de civilización (base principal, dónde se entrena cada tropa, qué se construye, `muros` que puede dibujar, campo, base inicial, adorno, árboles, sprites); `equivalencias`: tropa propia equivalente a cada tropa de referencia, para las personalidades de la máquina |
| `economia.json` | costos y tiempos de entrenamiento, obras (costo y segundos con un aldeano; en los muros, por tramo), `mejoras` de la cosecha (lo que subirá el árbol de investigación), ritmos de recolección, carga máxima, tope de población y la economía simulada de la máquina |
| `rivales.json` | `personalidades`: las perillas de la máquina (economía, primer ataque, tamaño e intervalo de ataque, mezcla de tropas, objetivo, retirada, defensa) |
| `investigacion.json` | edades (nombre por cultura, investigaciones necesarias, costo, tiempo), sprite de la base por edad, desbloqueos por edad, edificio de cada rama por cultura y el árbol: cada investigación con rama, grupo, edad, requisitos, costo, tiempo, `doctrina` (excluyentes), `efectos` (ver `_claves`) y `desbloquea` (habilita lo que tenga ese `permite`) |
| `combate.json` | `multiplicador[ataque][material]`: cuánto daño entra según el tipo de ataque (cuerpo, flecha, boleadora, choque, piedra) y el material del blanco; `fuego`: llamas por golpe, máximo, duración y daño por segundo |
| `mapas.json` | `tamanos`: medidas y cantidades del generador de mapas (minas, bosquecitos, rebaños) |

Los nombres internos de las tropas (`enemigo` = ashigaru, `lancero` = gaucho, `jinete` = granadero) son
históricos del prototipo; el nombre que ve el jugador está en `nombre`.

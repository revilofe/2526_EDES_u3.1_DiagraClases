# Ejercicio 5: Diagrama de Clases - Juego del NIM

## Descripción del Problema

Se necesita diseñar un sistema para el juego del NIM, un juego estratégico simple pero fascinante donde varios jugadores compiten quitando palillos de una mesa, intentando no ser quien quite el último.

## Especificaciones del Cliente

### Primera Reunión - Las Reglas Básicas del Juego

**Organizador del Club de Juegos:** *"El NIM es un juego super sencillo pero muy divertido. Al principio del juego colocamos sobre la mesa varios palillos, siempre más de 20 para que la partida sea interesante. La cantidad exacta la decidimos al empezar cada partida."*

**Organizador del Club de Juegos:** *"La regla fundamental es esta: pierde el jugador que quite el último palillo. Así que nadie quiere quedarse con solo un palillo en la mesa cuando le toca jugar, ¿entiendes?"*

### Segunda Reunión - Mecánica de Turnos

**Organizador del Club de Juegos:** *"Pueden jugar 2 o más personas, no hay límite máximo. En cada turno, el jugador que le toca puede quitar 1, 2 ó 3 palillos de la mesa. No más de 3, esa es la norma. Y obviamente, al menos tiene que quitar 1, no puede pasar turno."*

**Organizador del Club de Juegos:** *"Los jugadores van por turnos. Primero juega el jugador 1, luego el jugador 2, y así sucesivamente. Cuando llegan al último jugador, vuelve a empezar el primero. Es cíclico, como un círculo de turnos."*

### Tercera Reunión - Condiciones de Victoria y Derrota

**Jugador Experto:** *"Déjame explicarte la estrategia. El objetivo es **no** ser quien quite el último palillo. Si en tu turno solo queda 1 palillo, has perdido irremediablemente porque estás obligado a quitarlo."*

**Jugador Experto:** *"Hay una estrategia ganadora matemática para este juego, pero no te la voy a contar ahora. Lo que sí te digo es que los jugadores inteligentes intentan dejar múltiplos de 4 palillos para el siguiente jugador. Pero eso es parte de la diversión, descubrir la estrategia."*

### Cuarta Reunión - Información del Sistema

**Desarrollador de Juegos:** *"El sistema debe controlar en todo momento cuántos palillos quedan en la mesa. También necesitamos saber de quién es el turno actual. Y cuando un jugador hace su movimiento, el sistema debe validar que esté quitando entre 1 y 3 palillos."*

**Desarrollador de Juegos:** *"De cada jugador necesitamos un nombre para identificarlo. Y cuando la partida termine, el sistema debe anunciar claramente quién ha perdido y, por tanto, quiénes han ganado."*

### Quinta Reunión - Implementación y Estrategia (Bonus)

**Profesor de Matemáticas:** *"Como desafío adicional, sería genial que implementaras un algoritmo con mentalidad ganadora. Si programas bien la lógica, puedes hacer que un jugador automático juegue de manera inteligente."*

**Profesor de Matemáticas:** *"Te doy una pista: después de tu turno, intenta que queden múltiplos de 4 palillos en la mesa (4, 8, 12, 16, 20...). Si lo logras consistentemente, es casi imposible que pierdas."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML
7. **Bonus**: Implementar un algoritmo de estrategia ganadora en pseudocódigo

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación correcta de clases del dominio del juego
- **CE b)** Modelado de la relación entre Juego y Jugador (agregación/composición)
- **CE c)** Gestión correcta del estado del juego (palillos restantes, turno actual)
- **CE d)** Implementación de la lógica de turnos cíclicos
- **CE e)** Validación de movimientos (1-3 palillos)
- **CE f)** Detección de condición de victoria/derrota
- **CE g)** Encapsulación apropiada de responsabilidades
- **CE h)** Bonus: Implementación de estrategia ganadora

## Pistas

- **Clases principales**: Piensa en qué entidades participan: el juego en sí, los jugadores, quizás los palillos
- **Estado del juego**: El juego debe mantener: cantidad de palillos, lista de jugadores, índice del turno actual
- **Turnos cíclicos**: Usa el operador módulo (%) para ciclar entre jugadores: `indiceActual = (indiceActual + 1) % totalJugadores`
- **Validaciones**: Verifica que el movimiento sea válido (1-3 palillos) Y que haya suficientes palillos en la mesa
- **Condición de pérdida**: Un jugador pierde cuando en su turno quita el último palillo
- **Estrategia ganadora**: Después de cada movimiento, intenta que queden múltiplos de 4 palillos
- **Diseño simple**: No sobrecomplicar - este es un juego simple con clases simples

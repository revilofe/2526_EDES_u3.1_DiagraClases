# Ejercicio 7: Diagrama de Clases - Copa Davis de Tenis

## Descripción del Problema

La Federación Internacional de Tenis necesita un sistema para gestionar la Copa Davis, una competición por equipos entre países. El sistema debe controlar equipos, jugadores, eliminatorias, partidos (individuales y dobles) y resultados.

## Especificaciones del Cliente

### Primera Reunión - Estructura General de la Competición

**Director de la Federación:** *"La Copa Davis es una competición entre equipos representando a diferentes países. Los equipos juegan varias rondas eliminatorias, y en cada eliminatoria se enfrentan dos equipos. Cada eliminatoria tiene un ganador que avanza a la siguiente ronda."*

**Director de la Federación:** *"Algo importante: cada eliminatoria se juega en la sede de uno de los dos equipos contrincantes. El equipo anfitrión tiene la ventaja de elegir la superficie donde se jugarán los partidos: puede ser césped, tierra batida o pista dura. Esto es estratégicamente importante porque algunos jugadores rinden mejor en ciertas superficies."*

### Segunda Reunión - Composición de los Equipos

**Capitán del Equipo:** *"Cada equipo puede tener un máximo de 5 jugadores registrados. No más de cinco. De cada jugador necesitamos guardar su nombre completo, su ranking mundial (un número que indica su posición), su fecha de nacimiento y su nacionalidad."*

**Capitán del Equipo:** *"Los jugadores no están permanentemente en un equipo, pueden cambiar de un año a otro. Pero en una eliminatoria específica, el equipo ya está definido con sus jugadores."*

### Tercera Reunión - Formato de los Partidos

**Responsable de Competición:** *"Cada eliminatoria consta exactamente de 5 partidos. Cuatro son partidos individuales y uno es de dobles. Los partidos individuales enfrentan a un jugador contra otro. El partido de dobles enfrenta a una pareja de un equipo contra una pareja del otro equipo."*

**Responsable de Competición:** *"Hay una restricción importante en los individuales: deben jugar al menos dos jugadores diferentes del equipo. No puede jugar el mismo jugador todos los individuales. En el dobles, obviamente juegan dos jugadores simultáneamente por cada equipo."*

### Cuarta Reunión - Calendario de la Eliminatoria

**Coordinador de Eventos:** *"La eliminatoria se desarrolla en tres días consecutivos. El primer día se juegan 2 partidos individuales. El segundo día es el partido de dobles. Y el tercer día se juegan los otros 2 partidos individuales. Es un formato fijo, siempre igual."*

**Coordinador de Eventos:** *"Los partidos se numeran del 1 al 5 para llevar el orden. Partido 1 y 2: individuales. Partido 3: dobles. Partido 4 y 5: individuales."*

### Quinta Reunión - Gestión de Resultados

**Analista Deportivo:** *"Necesitamos almacenar los resultados de cada partido. De cada partido individual queremos saber quién ganó y el marcador (sets ganados). Del dobles igual: qué pareja ganó y el marcador."*

**Analista Deportivo:** *"También necesitamos el resultado global de la eliminatoria: qué equipo ganó. Para ganar, un equipo necesita ganar al menos 3 de los 5 partidos. Es un sistema de mejor de 5."*

### Sexta Reunión - Consultas y Estadísticas

**Jefe de Estadísticas:** *"El sistema debe poder responder varias preguntas: ¿Qué jugadores participaron en una eliminatoria? ¿Cuántos partidos ganó cada jugador? ¿Qué equipo fue anfitrión? ¿En qué superficie se jugó? ¿Cuál fue el resultado final?"*

**Jefe de Estadísticas:** *"Y algo crucial: cada partido tiene un resultado específico, pero también queremos saber el resultado acumulado de la eliminatoria. Por ejemplo, después del primer día podría ser 2-0, después del dobles 2-1, etc."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad  
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML
7. **Modelar la especialización** Partido → PartidoIndividual / PartidoDobles

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación correcta de entidades deportivas
- **CE b)** Modelado de jerarquía de herencia (Partido abstracto)
- **CE c)** Relaciones N:M (Equipo-Jugador con restricción de máximo 5)
- **CE d)** Composición (Eliminatoria compuesta por Partidos)
- **CE e)** Uso de enumeraciones (Superficie, Resultado)
- **CE f)** Gestión de roles (anfitrión vs visitante)
- **CE g)** Validación de reglas de negocio (máx 5 jugadores, al menos 2 jugadores diferentes)
- **CE h)** Cálculo de resultados agregados (ganador de eliminatoria)

## Pistas

- **Clases principales**: Equipo, Jugador, Eliminatoria, Partido (abstracta), PartidoIndividual, PartidoDobles, Pareja
- **Herencia**: Partido es clase abstracta con dos especializaciones
- **Enumeraciones**: Superficie (CESPED, TIERRA_BATIDA, PISTA_DURA), ResultadoPartido (LOCAL, VISITANTE)
- **Composición fuerte**: Eliminatoria contiene exactamente 5 Partidos
- **Asociación**: Equipo tiene 1..5 Jugadores en una eliminatoria específica
- **Pareja de dobles**: Considerar si es una clase o simplemente una asociación de 2 jugadores
- **Restricciones importantes**:
  - Máximo 5 jugadores por equipo
  - En individuales, al menos 2 jugadores diferentes
  - Total 5 partidos: 4 individuales + 1 dobles
  - Gana el equipo que consigue 3 o más victorias
- **Resultado eliminatoria**: Método que cuenta partidos ganados por cada equipo

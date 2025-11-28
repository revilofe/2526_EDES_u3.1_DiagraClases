# Ejercicios UML - Estado de Procesamiento

## Orden por Complejidad (Básico → Avanzado)

### Nivel 1: BÁSICO (2-4 clases, conceptos fundamentales)
1. **[✓] eje02/eje10 - EmpresaEmpleadosCliente** - Herencia, relaciones básicas → **Ej4_DiagramaClases_GestionEmpresarial.md**
2. **[✓] eje13 - Juego NIM** - Juego simple, turnos, jugadores → **Ej5_DiagramaClases_JuegoNIM.md**
3. **[✓] eje07 - Biblioteca** - Clases, estados, relaciones básicas → **Ej6_DiagramaClases_Biblioteca.md**

### Nivel 2: INTERMEDIO (4-6 clases, conceptos moderados)
5. **[✓] eje12 - Copa Davis** - Competición, equipos, partidos, resultados → **Ej7_DiagramaClases_CopaDavis.md**
6. **[✓] eje08 - BibliotecaMulta** - Biblioteca + multas (YA CUBIERTO en Ej6) → **Ej8_DiagramaClases_BibliotecaMulta.md** (nota)
7. **[✓] eje19 - Peliculas** - Gestión catálogo, herencia, clase asociación → **Ej9_DiagramaClases_Peliculas.md**
8. **[ ] eje06 - GestionPedidos** - Sistema de pedidos (similar a Ej3 actual)
8. **[ ] eje12 - Copa Davis** - Competición, equipos, partidos, resultados
9. **[ ] eje09 - RedesOrdenadores** - Redes, nodos, conexiones

### Nivel 3: INTERMEDIO-AVANZADO (5-7 clases, patrones simples)
10. **[ ] eje05 - tamagochi** - Hardware/software, memoria, procesador, pantalla
11. **[ ] eje03 - SistemaMurciadoInteli** - Sensores, estados, monitorización
12. **[ ] eje14 - BuscaMinas** - Juego con tablero, estados, cronómetro, persistencia
13. **[ ] eje01 - Mazor-Kos** - (PDF, necesita revisión de complejidad)

### Nivel 4: AVANZADO (7+ clases, múltiples patrones)
14. **[ ] eje04 - the100** - Sistema complejo: nave, motores, sensores, IA, comunicaciones
15. **[ ] eje11 - NeoTokio** - Smart-city, geolocalización, patrullas, mensajería
16. **[ ] eje15 - C3PO** - Robot: hardware, firmware, sensores, procesamiento
17. **[ ] eje16 - Tetris&Damas** - Juegos complejos (necesita revisión del ODP)

---

## Leyenda de Estados
- **[ ]** - Pendiente de procesar
- **[▶]** - En proceso
- **[✓]** - Completado (enunciado + solución generados)
- **[⚠]** - Requiere revisión o tiene problemas

---

## Notas de Análisis por Ejercicio

### eje02 - EmpresaEmpleadosCliente
**Complejidad**: Básica
**Conceptos clave**: Herencia, relaciones 1:N, atributos derivados (edad)
**Clases estimadas**: 3-4 (Persona, Empleado, Cliente, Empresa)
**Patrones**: Ninguno
**Prioridad**: ALTA - Perfecto para comenzar

### eje10 - EmpresaEmpleadosCliente II
**Complejidad**: Básica
**Conceptos clave**: Similar al eje02, posiblemente con jerarquías
**Clases estimadas**: 3-4
**Patrones**: Ninguno
**Prioridad**: ALTA - Continuación del anterior

### eje07 - Biblioteca
**Complejidad**: Básica-Intermedia
**Conceptos clave**: Estados de objetos, enumeraciones, asociaciones simples
**Clases estimadas**: 4-5 (Libro, Autor, Lector, Préstamo, enums)
**Patrones**: Ninguno
**Prioridad**: ALTA

### eje13 - Juego NIM
**Complejidad**: Básica
**Conceptos clave**: Turnos, jugadores, estado del juego
**Clases estimadas**: 3-4 (Juego, Jugador, Tablero/Mesa)
**Patrones**: Ninguno
**Prioridad**: ALTA - Juego simple educativo

### eje08 - BibliotecaMulta
**Complejidad**: Intermedia
**Conceptos clave**: Idéntico a eje07 - Los requisitos son exactamente los mismos que Biblioteca (Ej6)
**Clases estimadas**: 6-7 (Libro, Autor, Socio, Préstamo, Multa, estados)
**Patrones**: State pattern (implícito en estados)
**Prioridad**: BAJA - Ya está cubierto por Ej6
**Nota**: El enunciado de eje08 es idéntico al sistema ya implementado en Ej6. Ambos incluyen multas, límite de 3 libros, estados, etc.

### eje19 - Peliculas
**Complejidad**: Intermedia
**Conceptos clave**: Gestión de catálogo, relaciones N:M, valoraciones (estimado)
**Clases estimadas**: 4-6 (Película, Actor, Director, Género, posiblemente Valoración)
**Patrones**: Por determinar (requiere análisis de imágenes)
**Prioridad**: MEDIA
**Nota**: Enunciado disponible solo en formato PNG. Requiere transcripción manual de la imagen para generar ejercicio completo.

### eje06 - GestionPedidos
**Complejidad**: Intermedia-Avanzada
**Conceptos clave**: Similar al Ej3 actual (pedidos, productos, clientes)
**Clases estimadas**: 6-7
**Patrones**: Posiblemente Composite
**Prioridad**: MEDIA - Ya existe ejercicio similar (Ej3)

### eje12 - Copa Davis
**Complejidad**: Intermedia
**Conceptos clave**: Competición, equipos, partidos, resultados, calendario
**Clases estimadas**: 6-7 (Equipo, Jugador, Partido, Eliminatoria, Resultado, Sede)
**Patrones**: Ninguno complejo
**Prioridad**: MEDIA

### eje09 - RedesOrdenadores
**Complejidad**: Intermedia
**Conceptos clave**: Redes, nodos, conexiones, topología
**Clases estimadas**: 5-6
**Patrones**: Composite (redes dentro de redes)
**Prioridad**: MEDIA

### eje05 - tamagochi
**Complejidad**: Intermedia-Avanzada
**Conceptos clave**: Hardware/software, memoria, procesador, interfaces, pantalla
**Clases estimadas**: 6-7 (Tamagochi, Memoria, Procesador, Coprocesador, Acelerómetro, Pantalla)
**Patrones**: Interfaces, separación hardware/software
**Prioridad**: MEDIA-BAJA

### eje03 - SistemaMurciadoInteli
**Complejidad**: Intermedia-Avanzada
**Conceptos clave**: Sensores, estados (monitorizado/listo/finalizado), alertas, valores de referencia
**Clases estimadas**: 6-7 (Sistema, Sensor, Sujeto, Alerta, Estado)
**Patrones**: State pattern, Observer pattern
**Prioridad**: MEDIA-BAJA

### eje14 - BuscaMinas
**Complejidad**: Intermedia-Avanzada
**Conceptos clave**: Tablero, casillas, estados, cronómetro, persistencia, clasificación
**Clases estimadas**: 6-8 (Juego, Tablero, Casilla, Cronómetro, Partida, Clasificación)
**Patrones**: State pattern, posible Strategy para tableros
**Prioridad**: MEDIA-BAJA

### eje01 - Mazor-Kos
**Complejidad**: Por determinar (archivo PDF)
**Conceptos clave**: Requiere lectura del PDF
**Clases estimadas**: Desconocido
**Patrones**: Desconocido
**Prioridad**: BAJA - Requiere análisis previo del PDF

### eje04 - the100
**Complejidad**: Avanzada
**Conceptos clave**: Nave espacial, múltiples sistemas (motores, sensores, control, comunicaciones), reconocimiento facial, IA, procesamiento lenguaje natural
**Clases estimadas**: 10+ (Nave, Fuselaje, CentroControl, Motor×4, Sensor×5, SistemaReconocimiento, BaseDatos, SistemaComunicaciones, Piloto, etc.)
**Patrones**: Composite, Command pattern, Observer
**Prioridad**: BAJA - Muy complejo

### eje11 - NeoTokio
**Complejidad**: Avanzada
**Conceptos clave**: Smart-city, geolocalización, sensores GPS, patrullas, delincuentes, chips, mensajería, gestión dinámica de patrullas
**Clases estimadas**: 10+ (Sistema, Delincuente, Chip, ReceptorGPS, Ciberpolicía, Patrulla, Coordinador, Mensaje, Arma, etc.)
**Patrones**: Observer, Mediator, Composite (patrullas)
**Prioridad**: BAJA - Muy complejo

### eje15 - C3PO
**Complejidad**: Avanzada
**Conceptos clave**: Robot, arquitectura hardware/software, memoria caché, procesador, persistencia, sensores múltiples, firmware, instrucciones
**Clases estimadas**: 10+ (C3PO, Caché, Procesador, Persistencia, Sensor, Vista, Oído, Ultrasonidos, InfraRojos, Sistema, etc.)
**Patrones**: Strategy (sensores intercambiables), posible Singleton (procesador)
**Prioridad**: BAJA - Muy complejo, arquitectura de sistema

### eje16 - Tetris&Damas
**Complejidad**: Avanzada (estimada)
**Conceptos clave**: Juegos complejos (necesita revisar ODP)
**Clases estimadas**: Desconocido
**Patrones**: Desconocido
**Prioridad**: BAJA - Requiere análisis del archivo ODP

---

## Orden Recomendado de Procesamiento

### FASE 1: Fundamentos (Semanas 1-2)
1. eje02 - EmpresaEmpleadosCliente
2. eje10 - EmpresaEmpleadosCliente II
3. eje13 - Juego NIM
4. eje07 - Biblioteca

### FASE 2: Consolidación (Semanas 3-4)
5. eje08 - BibliotecaMulta
6. eje12 - Copa Davis
7. eje19 - Peliculas
8. eje09 - RedesOrdenadores

### FASE 3: Profundización (Semanas 5-6)
9. eje05 - tamagochi
10. eje03 - SistemaMurciadoInteli
11. eje14 - BuscaMinas
12. eje06 - GestionPedidos (si difiere del Ej3)

### FASE 4: Avanzados (Semanas 7-8)
13. eje01 - Mazor-Kos (tras analizar PDF)
14. eje04 - the100
15. eje11 - NeoTokio
16. eje15 - C3PO
17. eje16 - Tetris&Damas (tras analizar ODP)

---

## Estadísticas

- **Total ejercicios**: 17
- **Nivel Básico**: 3 ejercicios → 3 procesados (100%) ✅
- **Nivel Intermedio**: 5 ejercicios → 3 procesados (60%) ✅
- **Nivel Intermedio-Avanzado**: 4 ejercicios → 0 procesados (0%)
- **Nivel Avanzado**: 4 ejercicios → 0 procesados (0%)
- **Procesados completamente**: 5/17 (29.4%)
- **Notas**: 1 (eje08 cubierto por Ej6)
- **Pendientes**: 11/17

---

**Última actualización**: 2025-11-25 20:45
**Último ejercicio procesado**: eje19 - Películas → Ej9 (transcrito desde imagen)
**Próximo ejercicio a procesar**: eje06 - GestionPedidos o intermedio-avanzado

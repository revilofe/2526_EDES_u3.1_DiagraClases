# Ejercicio 8: Diagrama de Clases - Biblioteca con Sistema de Multas

## Descripción del Problema

La biblioteca municipal necesita extender su sistema básico para incluir un completo sistema de gestión de multas automáticas, control estricto de préstamos y restricciones de acceso. Este ejercicio amplía el sistema básico de biblioteca (Ejercicio 6) con reglas de negocio más complejas.

## Especificaciones del Cliente

### Primera Reunión - Recordatorio del Sistema Básico

**Bibliotecaria Jefe:** *"Como recordarás, tenemos libros clasificados por tipo: novela, poesía o cuentos. Cada libro tiene un estado: disponible, prestado o retrasado. Los libros retrasados son aquellos que el socio no ha devuelto a tiempo y por los cuales será multado."*

**Bibliotecaria Jefe:** *"De los autores seguimos necesitando nombre y fecha de nacimiento para clasificarlos como contemporáneos o clásicos. Y sí, necesitamos calcular su edad automáticamente."*

### Segunda Reunión - Límites Estrictos de Préstamo

**Responsable de Préstamos:** *"La regla de oro: un socio puede tener como máximo 3 libros en préstamo simultáneamente. Ni uno más. Es imposible prestar un cuarto libro. El sistema debe bloquearlo tajantemente."*

**Responsable de Préstamos:** *"Cuando un socio intenta llevarse un libro, el sistema debe verificar dos cosas: primero, que no tenga ya 3 libros prestados; segundo, y esto es crítico, que no tenga ninguna multa activa. Si tiene multas pendientes, no puede llevarse ningún libro. Punto."*

### Tercera Reunión - Sistema de Plazos y Multas

**Gerente de la Biblioteca:** *"El plazo de préstamo es de exactamente 30 días naturales. Ni un día más, ni un día menos. Si el socio devuelve el libro el día 31 o después, se activa automáticamente el sistema de multas."*

**Gerente de la Biblioteca:** *"La penalización es clara y estricta: 3 días de multa por cada día de retraso. Si te retrasas 5 días, son 15 días de multa. Si te retrasas 10 días, son 30 días de multa. Es un sistema disuasorio efectivo."*

### Cuarta Reunión - Funcionamiento de las Multas

**Jefa de Administración:** *"Cuando un socio devuelve un libro con retraso, el sistema calcula automáticamente los días de retraso, multiplica por 3, y genera una multa con esos días. La multa tiene una fecha de inicio (el día de la devolución) y una duración en días."*

**Jefa de Administración:** *"Mientras la multa esté activa, el socio no puede llevarse ningún libro. El sistema debe verificar si la fecha actual está dentro del periodo de la multa. Solo cuando la multa expire, podrá volver a solicitar préstamos."*

### Quinta Reunión - Implementación de Operaciones

**Analista de Sistemas:** *"Necesitamos implementar dos operaciones críticas: prestar() y devolver(). La operación prestar() debe verificar tres condiciones antes de proceder:"*

1. *"El libro debe estar disponible (no prestado, no retrasado)"*
2. *"El socio no debe tener multas activas"*
3. *"El socio no debe tener ya 3 libros prestados"*

**Analista de Sistemas:** *"Si alguna condición falla, el préstamo no se realiza y el sistema debe informar el motivo. Si todo está bien, se crea el préstamo, se cambia el estado del libro a 'prestado', y se calcula la fecha límite de devolución."*

### Sexta Reunión - Devolución y Generación de Multas

**Analista de Sistemas:** *"La operación devolver() es más compleja. Primero, debe verificar que exista un préstamo activo para ese libro y ese socio. No puedes devolver un libro que no has tomado prestado."*

**Analista de Sistemas:** *"Luego, calcula si hay retraso comparando la fecha actual con la fecha límite. Si hay retraso, genera automáticamente una multa, la asocia al socio, y cambia el estado del libro a 'retrasado'. Si no hay retraso, simplemente cambia el estado a 'disponible'. En ambos casos, marca el préstamo como finalizado."*

### Séptima Reunión - Casos Especiales

**Bibliotecaria Senior:** *"Algunos casos especiales a considerar: un socio puede tener múltiples multas acumuladas si ha devuelto varios libros con retraso. Todas las multas deben cumplirse - no pueden superponerse temporalmente, se acumulan."*

**Bibliotecaria Senior:** *"También necesitamos que el sistema pueda consultar cuántos días de multa le quedan a un socio, cuántos libros tiene prestados actualmente, y si está habilitado para nuevos préstamos."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema (extensión del Ejercicio 6)
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios, especialmente prestar() y devolver()
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Implementar la lógica de validación** para todas las restricciones
7. **Crear el diagrama de clases UML** completo usando PlantUML

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Extensión correcta del modelo básico de biblioteca
- **CE b)** Implementación completa del sistema de multas automáticas
- **CE c)** Validaciones de reglas de negocio (3 libros máx, multas activas)
- **CE d)** Cálculo automático de fechas y días de retraso
- **CE e)** Gestión de estados del libro (disponible/prestado/retrasado)
- **CE f)** Métodos prestar() y devolver() con todas las validaciones
- **CE g)** Relación Socio-Multa (composición, un socio puede tener múltiples multas)
- **CE h)** Consultas de estado (días restantes de multa, libros prestados)

## Pistas

- **Este es el Ejercicio 6 extendido**: Usa la misma base pero añade complejidad en las validaciones
- **Clase Multa crítica**: Debe tener fechaInicio, diasMulta, y método estaActiva()
- **Fórmula de multa**: diasMulta = diasRetraso × 3
- **Préstamo necesita fechas**: fechaPrestamo, fechaLimite (auto-calculada +30 días), fechaDevolucion (nullable)
- **Estados del libro**: DISPONIBLE → PRESTADO → RETRASADO (si hay retraso) → DISPONIBLE
- **Validación en prestar()**:
  ```
  if (!libro.estaDisponible()) return error
  if (socio.tieneMultasActivas()) return error  
  if (socio.contarPrestamosActivos() >= 3) return error
  // Crear préstamo
  ```
- **Validación en devolver()**:
  ```
  if (!existePrestamo) return error
  diasRetraso = calcularDiasRetraso()
  if (diasRetraso > 0) {
      generar multa (diasRetraso × 3)
      libro.estado = RETRASADO
  }
  libro.estado = DISPONIBLE
  ```
- **Múltiples multas**: Un socio puede acumular varias multas si devuelve múltiples libros tarde
- **Multa activa**: Comparar LocalDate.now() con fechaInicio + diasMulta

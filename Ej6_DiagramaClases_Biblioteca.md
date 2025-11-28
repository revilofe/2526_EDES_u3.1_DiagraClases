# Ejercicio 6: Diagrama de Clases - Sistema de Biblioteca

## Descripción del Problema

Una biblioteca municipal necesita informatizar su sistema de gestión de libros y préstamos. El sistema debe controlar el catálogo de libros, los autores, los socios lectores y el estado de cada préstamo.

## Especificaciones del Cliente

### Primera Reunión - Catálogo de Libros y Autores

**Bibliotecaria Jefe:** *"Tenemos cientos de ejemplares en nuestra biblioteca. Cada libro puede ser de un tipo específico: novela, poesía o cuentos. Necesitamos clasificarlos así para las estadísticas y para que los socios busquen por género."*

**Bibliotecaria Jefe:** *"De cada autor necesitamos guardar su nombre completo y su fecha de nacimiento. ¿Para qué? Pues porque queremos poder clasificar en el futuro si son autores contemporáneos o clásicos basándonos en su edad. Necesitamos que el sistema pueda calcular la edad del autor automáticamente."*

### Segunda Reunión - Estados de los Libros

**Asistente de Biblioteca:** *"Los libros pueden estar en tres estados diferentes. Primero, **disponibles**: están en la estantería y cualquier socio puede llevárselos. Segundo, **prestados**: alguien se los ha llevado y están fuera de la biblioteca. Y tercero, **retrasados**: el socio no ha devuelto el libro en la fecha límite."*

**Asistente de Biblioteca:** *"Cuando un libro está retrasado es importante saberlo porque ese socio será multado. Pero eso es para otra reunión, ahora solo necesito que entiendas que los libros tienen estos tres estados posibles."*

### Tercera Reunión - Socios y Límites de Préstamo

**Responsable de Socios:** *"Los lectores de nuestra biblioteca son socios registrados. De cada socio guardamos su nombre, DNI y fecha de inscripción. Ahora viene algo importante: un socio puede tener prestados como máximo 3 libros simultáneamente. Ni uno más. Es una política de la biblioteca para que haya rotación."*

**Responsable de Socios:** *"Cuando un socio intenta llevarse un cuarto libro, el sistema debe impedirlo. Y cuando devuelve un libro, entonces ya puede llevarse otro. Es una regla estricta."*

### Cuarta Reunión - Préstamos y Plazos

**Gerente de la Biblioteca:** *"Los préstamos funcionan así: cuando un socio se lleva un libro, registramos la fecha de préstamo. El plazo máximo es de 30 días calendario. El sistema debe calcular automáticamente la fecha límite de devolución sumando 30 días a la fecha de préstamo."*

**Gerente de la Biblioteca:** *"Si el socio devuelve el libro después de la fecha límite, ese libro pasa a estado 'retrasado' y se genera automáticamente una multa. La multa es de 3 días por cada día de retraso. Sí, parece duro, pero funciona para que la gente devuelva a tiempo."*

### Quinta Reunión - Multas y Restricciones

**Gerente de la Biblioteca:** *"Las multas son importantes. Cuando un socio tiene una multa activa, no puede llevarse ningún libro más hasta que se cumpla el periodo de la multa. Por ejemplo, si tiene 9 días de multa, debe esperar 9 días antes de poder pedir otro préstamo."*

**Gerente de la Biblioteca:** *"El sistema debe tener dos operaciones fundamentales: prestar libro y devolver libro. Para prestar, debe verificar que el socio no tenga multas activas y que no haya alcanzado el límite de 3 libros. Para devolver, debe verificar que exista un préstamo activo de ese libro para ese socio."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML
7. **Modelar correctamente los estados** de los libros (enumeración)

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación correcta de entidades del dominio
- **CE b)** Uso de enumeraciones para tipos y estados
- **CE c)** Modelado de la relación Libro-Autor (composición/agregación)
- **CE d)** Modelado de la clase de asociación Préstamo entre Socio y Libro
- **CE e)** Implementación de reglas de negocio (límite 3 libros, multas)
- **CE f)** Cálculo de atributos derivados (edad autor, fecha límite, días de multa)
- **CE g)** Validaciones en métodos prestar y devolver
- **CE h)** Gestión correcta de estados del libro

## Pistas

- **Enumeraciones**: Usa `enum` para TipoLibro (NOVELA, POESIA, CUENTOS) y EstadoLibro (DISPONIBLE, PRESTADO, RETRASADO)
- **Clase de asociación**: El Préstamo es una relación entre Socio y Libro que tiene atributos propios (fechaPrestamo, fechaLimite)
- **Atributos derivados**: fechaLimite = fechaPrestamo + 30 días; edad = calcular desde fechaNacimiento
- **Multa**: Es una entidad separada con fechaInicio y diasMulta (3 días × días de retraso)
- **Validaciones críticas**:
  - Al prestar: socio sin multas activas Y menos de 3 libros prestados Y libro disponible
  - Al devolver: verificar que existe préstamo activo Y calcular si hay retraso
- **Relación Libro-Autor**: Un libro tiene uno o más autores (considera coautoría)
- **Cardinalidad Socio-Préstamo**: Un socio puede tener 0..3 préstamos activos simultáneamente


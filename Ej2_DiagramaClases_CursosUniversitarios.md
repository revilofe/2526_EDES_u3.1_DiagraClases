# Ejercicio 2: Diagrama de Clases - Sistema de Gestión de Cursos Universitarios

## Descripción del Problema

Una universidad necesita informatizar la gestión de sus cursos académicos. Tras varias reuniones con el cliente, se han recogido las siguientes necesidades:

## Especificaciones del Cliente

### Primera Reunión - Información General

*"Necesitamos gestionar los cursos que ofrecemos. Cada curso tiene un código único, un nombre, una descripción de qué trata y cuántos créditos ECTS vale. También necesitamos saber el nivel del curso: si es de grado, máster o doctorado."*

*"Los cursos los imparten profesores. Cada profesor tiene un identificador de empleado, su nombre completo, su email corporativo y el departamento al que pertenece. Un profesor puede impartir varios cursos, pero un curso específico solo puede ser impartido por un único profesor responsable."*

### Segunda Reunión - Estudiantes y Matrículas

*"Por supuesto, los estudiantes se matriculan en los cursos. De cada estudiante guardamos su número de expediente, nombre completo, email y la fecha en que se matriculó por primera vez en la universidad."*

*"Un estudiante puede matricularse en varios cursos, y en cada curso puede haber muchos estudiantes. Pero necesitamos saber algo importante: cuando un estudiante se matricula en un curso, queremos guardar la fecha de matrícula y la nota que ha sacado en ese curso. Al principio la nota estará vacía, claro, pero luego se actualizará."*

### Tercera Reunión - Comportamientos del Sistema

*"Los profesores necesitan poder dar clase, preparar exámenes y evaluar a los estudiantes. Los estudiantes deben poder asistir a clase, estudiar y presentarse a los exámenes."*

*"Para los cursos, necesitamos saber cuántos estudiantes están matriculados actualmente. Y para los profesores, querían tener una forma de ver qué cursos están impartiendo."*

### Cuarta Reunión - Aclaraciones sobre la Matrícula

*"Déjame aclararte lo de las matrículas. Cuando un estudiante se matricula en un curso, eso crea un registro de matrícula. Ese registro es importante porque vincula al estudiante con el curso, y en ese registro guardamos cuándo se matriculó y qué nota sacó después."*

*"Es decir, la matrícula no es solo una relación simple, es una entidad propia con sus datos. ¿Lo ves? Es como un contrato entre el estudiante y el curso."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases (asociación simple, asociación con clase de asociación, etc.)
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación de conceptos de POO (clases, atributos, métodos, visibilidad)
- **CE b)** Uso de herramientas (PlantUML) para elaborar diagramas
- **CE c)** Interpretación de especificaciones del mundo real
- **CE d)** Trazado de diagramas a partir de especificaciones narrativas
- **CE e)** Comprensión de relaciones complejas (clase de asociación)

## Pistas

- Piensa en qué información pertenece a qué clase
- Algunos datos pueden requerir una clase intermedia
- Las relaciones muchos-a-muchos con atributos propios necesitan un tratamiento especial
- Los métodos deben reflejar las acciones que cada entidad puede realizar

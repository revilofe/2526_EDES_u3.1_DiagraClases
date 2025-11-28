# Ejercicio 9: Diagrama de Clases - Sistema de Gestión de Películas

## Descripción del Problema

Una plataforma de streaming necesita informatizar su sistema de gestión de catálogo de películas. El sistema debe controlar información sobre películas, actores, directores y las relaciones entre ellos.

## Especificaciones del Cliente

### Primera Reunión - Catálogo de Películas

**Director de Contenidos:** *"Nuestra plataforma maneja un catálogo extenso de películas. De cada película necesitamos guardar información básica: el título, el año de estreno, la duración en minutos y el idioma original. Estas son las propiedades fundamentales que los usuarios consultan."*

**Director de Contenidos:** *"Cada película tiene un director único que es el responsable artístico principal. Pero aquí viene algo importante: una película puede tener múltiples actores en su reparto. Pueden ser 2, 5, 10 o más actores. Y obviamente, un actor puede participar en múltiples películas a lo largo de su carrera."*

### Segunda Reunión - Información de Personas

**Responsable de Base de Datos:** *"Tanto los actores como los directores son personas, así que comparten ciertos atributos básicos. De todos ellos necesitamos: nombre completo, fecha de nacimiento y nacionalidad. Es importante modelar esto correctamente para no duplicar información."*

**Responsable de Base de Datos:** *"Aquí está la diferencia: un director simplemente dirige películas. Pero un actor, además de actuar, tiene un papel específico en cada película. El mismo actor puede ser protagonista en una película y secundario en otra. Necesitamos guardar qué papel interpreta en cada película."*

### Tercera Reunión - Roles de los Actores

**Coordinador de Reparto:** *"Cuando un actor participa en una película, tiene un papel o personaje asignado. Por ejemplo, en 'El Padrino', Marlon Brando interpretó el papel de 'Vito Corleone'. En 'Matrix', Keanu Reeves interpretó 'Neo'. Este papel es específico de cada participación."*

**Coordinador de Reparto:** *"No confundir el papel (personaje) con el tipo de rol. El papel es el nombre del personaje: 'Harry Potter', 'Iron Man', 'Gandalf'. Es información específica de la relación actor-película, no del actor en general."*

### Cuarta Reunión - Relaciones y Consultas

**Analista de Sistemas:** *"Necesitamos poder hacer varias consultas al sistema: ¿En qué películas ha actuado este actor? ¿Qué papel interpretó en cada una? ¿Quién dirigió esta película? ¿Qué actores participaron en esta película?"*

**Analista de Sistemas:** *"También necesitamos poder listar todas las películas de un director específico. Por ejemplo, todas las películas dirigidas por Christopher Nolan o Steven Spielberg. La relación director-película es uno a muchos: un director puede dirigir varias películas."*

### Quinta Reunión - Modelado de la Participación

**Arquitecto de Software:** *"La participación de un actor en una película es una relación muchos a muchos que tiene atributos propios: el papel/personaje que interpreta. Esto es un caso clásico de clase de asociación. No es solo que el actor esté relacionado con la película, sino que esa relación tiene información específica."*

**Arquitecto de Software:** *"Piénsenlo así: Daniel Radcliffe puede estar en 50 películas, pero en cada una interpreta un personaje diferente. Ese personaje no es atributo del actor ni de la película, es atributo de la participación específica."*

### Sexta Reunión - Requisitos Funcionales

**Product Owner:** *"El sistema debe poder registrar nuevas películas con su director. Debe poder agregar actores al reparto especificando qué papel interpretan. Y debe poder consultar toda esta información de manera eficiente."*

**Product Owner:** *"También queremos poder calcular la edad de actores y directores basándonos en su fecha de nacimiento. Y necesitamos poder buscar películas por año, por director, o por actor."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Modelar la clase de asociación** para Actor-Película
7. **Crear el diagrama de clases UML** completo usando PlantUML

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación correcta de entidades del dominio cinematográfico
- **CE b)** Uso de herencia para modelar Persona → Actor/Director
- **CE c)** Modelado de relación N:M entre Actor y Película
- **CE d)** Clase de asociación Participación con atributo papel
- **CE e)** Relación 1:N entre Director y Película
- **CE f)** Atributos derivados (edad calculada desde fecha nacimiento)
- **CE g)** Cardinalidades correctas (1 director, múltiples actores)
- **CE h)** Navegabilidad bidireccional en asociaciones

## Pistas

- **Clases principales**: Película, Persona (abstracta), Actor, Director, Participación
- **Herencia**: Persona es clase base para Actor y Director
- **Clase de asociación**: Participación relaciona Actor con Película y tiene atributo "papel"
- **Cardinalidades clave**:
  - Una Película tiene 1 Director
  - Un Director puede dirigir 0..* Películas
  - Una Película tiene 1..* Actores (al menos uno)
  - Un Actor puede participar en 0..* Películas
  - Cada Participación tiene 1 Actor y 1 Película
- **Atributo "papel"**: Es parte de Participación, no de Actor ni de Película
- **Ejemplo de datos**:
  - Película: "Matrix", 1999, 136min, "Inglés"
  - Director: "Lana Wachowski"
  - Actor: "Keanu Reeves", papel: "Neo"
  - Actor: "Laurence Fishburne", papel: "Morpheus"
- **Métodos útiles**: calcularEdad(), agregarActor(), getDirector(), getPeliculasActuadas(), getPeliculasDirigidas()

---

**Archivo de origen**: `ejercicios/eje19 - Peliculas/Peliculas - Enunciado.png`
**Nivel de dificultad**: Intermedio
**Conceptos principales**: Herencia, Clase de Asociación, Relaciones N:M

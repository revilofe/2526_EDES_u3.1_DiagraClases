# Ejercicio 1: Diagrama de Clases - Sistema de Libros y Autores

## Descripción del Problema

Diseña un diagrama de clases para un sistema básico de gestión de libros y autores de una biblioteca.

## Requisitos

### Clase Autor
Representa a un autor que escribe libros.

**Propiedades:**
- `nombre`: Cadena de texto que almacena el nombre del autor (privado)
- `apellido`: Cadena de texto que almacena el apellido del autor (privado)
- `nacionalidad`: Cadena de texto que indica la nacionalidad del autor (privado)
- `fechaNacimiento`: Fecha de nacimiento del autor (privado)

**Métodos:**
- `escribir()`: Método público que simula la acción de escribir
- `getNombreCompleto()`: Método público que retorna el nombre completo del autor (campo derivado/calculado a partir de nombre + apellido)

### Clase Libro
Representa un libro que puede ser leído.

**Propiedades:**
- `titulo`: Cadena de texto con el título del libro (privado)
- `isbn`: Código ISBN del libro (privado)
- `numeroPaginas`: Número entero con la cantidad de páginas (privado)
- `precio`: Valor decimal con el precio del libro (privado)

**Métodos:**
- `leer()`: Método público que simula la acción de leer el libro
- `getTitulo()`: Método público que retorna el título del libro
- `getPrecio()`: Método público que retorna el precio del libro

### Relación entre clases

- Un **Autor** escribe **uno o varios Libros**
- Cada **Libro** es escrito por **un único Autor**
- La relación debe mostrar:
  - El rol "escribe" desde Autor hacia Libro
  - Cardinalidad apropiada en ambos extremos

### Consideraciones adicionales

- El método `getNombreCompleto()` debe estar marcado como campo derivado ({derived})
- Incluye una nota explicativa sobre el campo calculado
- Utiliza la visibilidad correcta: privado (-) para atributos, público (+) para métodos

## Tarea

Crea el diagrama de clases UML que represente este sistema siguiendo todas las especificaciones indicadas.

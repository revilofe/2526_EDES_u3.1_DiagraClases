# Ejercicio 4: Diagrama de Clases - Sistema de Gestión Empresarial

## Descripción del Problema

Una empresa de consultoría necesita desarrollar un sistema para gestionar la información de sus empleados, clientes y las empresas con las que trabajan. El sistema debe mantener datos personales, estructuras jerárquicas y relaciones comerciales entre las diferentes entidades.

## Especificaciones del Cliente

### Primera Reunión - Estructura Básica de Datos

**Director de Recursos Humanos:** *"Mira, necesitamos almacenar información básica de nuestros empleados y de nuestros clientes. De ambos grupos nos interesa guardar el nombre completo y su fecha de nacimiento. ¿Por qué la fecha de nacimiento? Pues porque necesitamos calcular su edad para varios trámites administrativos, ya sabes, temas de seguros, contratos, ese tipo de cosas."*

**Director de Recursos Humanos:** *"Ah, y algo importante: de los clientes también necesitamos su número de teléfono. Es fundamental porque constantemente necesitamos comunicarnos con ellos para proyectos, facturas, reuniones... Ya sabes cómo es esto."*

### Segunda Reunión - Jerarquía de Empleados

**Jefa de Operaciones:** *"Déjame explicarte cómo funciona nuestra estructura interna. Tenemos empleados normales y empleados responsables. Los responsables son especiales porque pueden tener a su cargo a otros empleados subordinados. Es como una cadena de mando, ¿entiendes?"*

**Jefa de Operaciones:** *"Y estos empleados responsables se dividen en categorías: tenemos supervisores, jefes de departamento, gerentes... cada categoría implica un nivel de responsabilidad diferente y, por supuesto, un rango salarial distinto. Un responsable puede tener varios subordinados, pero un subordinado solo reporta a un responsable."*

### Tercera Reunión - Aspectos Económicos

**Director Financiero:** *"Hablemos de dinero. Todos nuestros empleados, sean responsables o no, tienen un sueldo bruto asignado. Este sueldo bruto es la base sobre la cual calculamos el sueldo neto que realmente cobran, después de aplicar impuestos, deducciones, cotizaciones... el tema fiscal, vaya."*

**Director Financiero:** *"Necesito que el sistema pueda calcular automáticamente el sueldo neto a partir del bruto. Normalmente aplicamos una retención estándar del 22%, pero eso puede variar según la categoría del empleado."*

### Cuarta Reunión - Relaciones Comerciales

**Responsable de Negocio:** *"Ahora viene lo importante sobre nuestros clientes. Verás, todos nuestros clientes están asociados a al menos una empresa. No trabajamos con particulares, solo con empresas. Un cliente puede representar a varias empresas si es el caso, pero siempre tiene que pertenecer al menos a una."*

**Responsable de Negocio:** *"Las empresas tienen su nombre corporativo, su CIF, dirección fiscal... toda esa información corporativa que necesitamos para facturar y mantener la relación comercial. Y obviamente, una empresa puede tener múltiples clientes de contacto, diferentes personas según el departamento o proyecto."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases (herencia, asociación, etc.)
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación correcta de clases y sus responsabilidades
- **CE b)** Aplicación de herencia para modelar generalización/especialización (Persona → Empleado/Cliente)
- **CE c)** Uso correcto de asociaciones reflexivas (empleado responsable → empleados subordinados)
- **CE d)** Definición apropiada de atributos con tipos de datos y visibilidad
- **CE e)** Implementación de métodos derivados (cálculo de edad, cálculo de sueldo neto)
- **CE f)** Especificación correcta de cardinalidades en las relaciones
- **CE g)** Aplicación de restricciones de negocio (cliente debe pertenecer al menos a una empresa)

## Pistas

- **Herencia**: Nota que empleados y clientes comparten atributos comunes (nombre, fecha nacimiento). Esto sugiere una clase padre.
- **Atributo derivado**: La edad no debe almacenarse, sino calcularse a partir de la fecha de nacimiento.
- **Relación reflexiva**: Un empleado (responsable) puede tener relación con otros empleados (subordinados) de la misma clase.
- **Categorías**: Considera usar un tipo enumerado para las categorías de empleados responsables.
- **Cardinalidades**: Presta especial atención a "todos los clientes pertenecen **al menos** a una empresa" (1..*).
- **Método de cálculo**: El sueldo neto puede calcularse aplicando una fórmula simple: `sueldoNeto = sueldoBruto * 0.78` (restando 22% de retención).

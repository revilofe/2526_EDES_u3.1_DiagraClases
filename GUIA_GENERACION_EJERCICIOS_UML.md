# Guía para la Generación de Ejercicios de Diagramas de Clases UML

## Propósito de este Documento

Este documento proporciona instrucciones detalladas para cualquier agente de IA que desee continuar generando ejercicios de diagramas de clases siguiendo la metodología establecida en los ejercicios 2 y 3 de este repositorio.

---

## Estructura General de un Ejercicio

Cada ejercicio completo consta de **DOS archivos**:

1. **Archivo de Enunciado**: `EjN_DiagramaClases_[Tema].md`
2. **Archivo de Solución**: `EjN_DiagramaClases_[Tema]_sol.md`

Donde `N` es el número secuencial del ejercicio y `[Tema]` es un nombre descriptivo corto del dominio del problema.

---


## Fuentes de ejercicios

En la carpeta de "ejercicios", nos encontraremos distintos ejercicios en directorios con nombres como: "eje01 - Mazor-Kos" o "eje02 - EmpresaEmpleadoCliente", etc.

Estos ejercicios tienen distinto nivel de dificultad. Seria coherente ordenarlos por nivel de dificultad.

En los directorios de los ejercicios, nos encontraremos distintos archivos, en donde nos encontraremos las descripciones de los ejercicios y las soluciones.

La idea es utilizar estos archivos tanto para fuentes de "Archivo del enunciado" como "Archivo de Solución" siguiendo los pasos que se describen en este documento, pero partiendo de los archivos fuente.

en este caso, genera una lista "Eje_procesados.md" dentro de la carpeta "ejercicios", en el que primero se ordenen por orden de complejidad y luego se vayan marcando aquellos ejercicios que se vayan pasando al nuevo formato.
 
---

## FASE 1: Creación del Archivo de Enunciado

### 1.1. Estructura del Enunciado

El archivo de enunciado debe seguir esta estructura exacta:

```markdown
# Ejercicio N: Diagrama de Clases - [Título Descriptivo]

## Descripción del Problema

[Un párrafo introduciendo el contexto general del sistema a modelar]

## Especificaciones del Cliente

### Primera Reunión - [Tema de la reunión]

**[Rol del interlocutor]:** *"[Especificación en primera persona como si fuera el cliente hablando]"*

**[Rol del interlocutor]:** *"[Más especificaciones...]"*

### Segunda Reunión - [Tema de la reunión]

[Continuar con el mismo formato...]

### [Más reuniones según complejidad]

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar las clases principales** del sistema
2. **Determinar las propiedades** de cada clase y su visibilidad
3. **Definir los métodos** necesarios y su visibilidad
4. **Establecer las relaciones** entre las clases
5. **Especificar roles y cardinalidades** para cada relación
6. **Crear el diagrama de clases UML** completo usando PlantUML

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** [Criterio específico]
- **CE b)** [Criterio específico]
- **CE c)** [Criterio específico]
[etc.]

## Pistas

- [Pista 1]
- [Pista 2]
- [Pista 3]
```

### 1.2. Criterios para Escribir las Especificaciones

#### A) Formato de Reuniones
- **Número de reuniones**: Entre 3 y 6 reuniones según complejidad
- **Roles diversos**: Usar diferentes interlocutores (Responsable de Negocio, Director Financiero, Jefa de Logística, etc.)
- **Voz del cliente**: Todas las especificaciones deben estar en primera persona, como si el cliente estuviera hablando
- **Lenguaje natural**: Usar lenguaje coloquial, no técnico. El cliente no conoce UML ni POO

#### B) Progresión de Complejidad en las Reuniones
1. **Primera reunión**: Presentar las entidades principales y sus atributos básicos
2. **Segunda reunión**: Introducir relaciones simples entre entidades
3. **Tercera reunión**: Añadir complejidad (clases de asociación, cardinalidades especiales)
4. **Reuniones posteriores**: Comportamientos, restricciones, casos especiales, aclaraciones

#### C) Técnicas Narrativas
- **Usar preguntas retóricas**: *"¿Lo ves? Es como un contrato entre el estudiante y el curso."*
- **Hacer aclaraciones**: *"Déjame aclararte lo de las matrículas..."*
- **Dar ejemplos**: *"Imagina que un cliente hace un pedido grande..."*
- **Revelar información progresivamente**: No dar todos los detalles de golpe

#### D) Conceptos a Introducir Gradualmente
- Atributos de las clases principales
- Relaciones básicas (asociación simple)
- Cardinalidades
- Clases de asociación (cuando una relación tiene atributos propios)
- Restricciones de negocio
- Comportamientos y métodos
- Patrones de diseño (si es ejercicio avanzado)

### 1.3. Niveles de Complejidad

Salvo que se de una solución ya y una propuesta de ejercicio, que en cuyo caso nos restringiremos a coger la descripción y solución propuesta.

Si no hay solución:

#### **Nivel Básico** (como Ejercicio 2):
- 3-4 clases principales
- Relaciones simples (asociación, agregación)
- Una clase de asociación
- Cardinalidades estándar
- Sin patrones de diseño complejos

#### **Nivel Avanzado** (como Ejercicio 3):
- 6-8 clases principales
- Relaciones complejas (composición, herencia)
- Múltiples clases de asociación
- Patrones de diseño (Singleton, Composite, etc.)
- Restricciones de negocio explícitas
- Estados o enumeraciones

### 1.4. Dominios de Problema Sugeridos

Salvo que no se de una propuesta de ejercicio y solución.

Para futuros ejercicios, considera estos dominios:

- Sistema de biblioteca con préstamos y reservas
- Plataforma de streaming con suscripciones
- Sistema hospitalario (pacientes, doctores, citas)
- Red social (usuarios, publicaciones, comentarios)
- Sistema de reservas de hotel
- Plataforma de cursos online con certificaciones
- Sistema de gestión de proyectos software
- Aplicación de delivery de comida
- Sistema de gestión de empleados y nóminas
- Plataforma de eventos y venta de entradas

---

## FASE 2: Creación del Archivo de Solución

### 2.1. Estructura del Archivo de Solución

El archivo de solución debe seguir esta estructura:

```markdown
# Ejercicio N: Solución - [Título del Ejercicio]

## Análisis del Diseño

### 1. Clases Identificadas

#### Clase **[NombreClase1]**
[Descripción breve de la responsabilidad de la clase]

**Propiedades:**
- `-atributo: Tipo` - Descripción del atributo (visibilidad)
- [Más atributos...]

**Métodos:**
- `+metodo(): TipoRetorno` - Descripción del método (visibilidad)
- [Más métodos...]

#### Clase **[NombreClase2]**
[Repetir estructura...]

### 2. Relaciones

#### Relación 1: [Clase1] → [Clase2] ([Tipo de relación])
- **Tipo:** [Asociación/Agregación/Composición/Herencia/Clase de asociación]
- **Dirección:** [Unidireccional/Bidireccional]
- **Significado:** [Explicación en lenguaje natural]
- **Rol:** [Nombre del rol si aplica]
- **Cardinalidad:**
  - Clase1 [X] → Clase2 [Y]
  - [Explicación de la cardinalidad]
- **Implicaciones:**
  - [Implicación 1]
  - [Implicación 2]

[Repetir para cada relación...]

### 3. Roles y Cardinalidad Detallados

| Relación | Clase Origen | Rol Origen | Cardinalidad Origen | Clase Destino | Rol Destino | Cardinalidad Destino |
|----------|--------------|------------|---------------------|---------------|-------------|---------------------|
| [Nombre] | [Clase] | [rol] | [X..Y] | [Clase] | [rol] | [X..Y] |

### 4. Justificación de Decisiones de Diseño

1. **[Decisión 1]**: [Explicación y justificación]
2. **[Decisión 2]**: [Explicación y justificación]
[etc.]

## Código PlantUML

```plantuml
@startuml [NombreDelDiagrama]

class [NombreClase1] {
  -atributo1: Tipo
  -atributo2: Tipo
  +metodo1(): Tipo
  +metodo2(): Tipo
}

[Definir todas las clases...]

[Definir todas las relaciones...]

@enduml
```

## Diagrama Generado

![Diagrama de Clases - [Título]](assets/EjN_[Nombre].png)

## Implementación en Kotlin

```kotlin
[Código Kotlin completo implementando el diseño]
```

## Conceptos Clave Aplicados

1. **[Concepto 1]:** [Explicación de cómo se aplicó]
2. **[Concepto 2]:** [Explicación de cómo se aplicó]
[etc.]

## Criterios de Evaluación Cubiertos

- ✅ **CE a)** [Cómo se cumple este criterio]
- ✅ **CE b)** [Cómo se cumple este criterio]
[etc.]
```

### 2.2. Guía para Escribir el Análisis del Diseño

#### A) Clases Identificadas
- **Una sección por clase**: Cada clase debe tener su propia subsección
- **Descripción de responsabilidad**: Explicar qué representa la clase en el dominio
- **Listar todos los atributos**: Con tipo, visibilidad y descripción
- **Listar todos los métodos**: Con firma completa, visibilidad y descripción
- **Justificar visibilidades**: Explicar por qué cada elemento es público/privado

#### B) Relaciones
- **Análisis exhaustivo**: Una subsección por cada relación
- **Elementos a incluir**:
  - Tipo de relación (con justificación)
  - Dirección y navegabilidad
  - Significado semántico en lenguaje natural
  - Roles si son necesarios
  - Cardinalidades con explicación detallada
  - Implicaciones técnicas y de diseño

#### C) Tabla de Roles y Cardinalidad
- Formato tabular para referencia rápida
- Todas las relaciones en un solo vistazo
- Útil para verificación

#### D) Justificación de Decisiones
- **Explicar el porqué**: No solo el qué, sino por qué se tomó cada decisión
- **Principios aplicados**: SOLID, encapsulación, cohesión, etc.
- **Alternativas descartadas**: Si hay decisiones no obvias, mencionar otras opciones consideradas

### 2.3. Código PlantUML

#### Sintaxis Básica

**Clases:**
```plantuml
class NombreClase {
  -atributoPrivado: Tipo
  #atributoProtegido: Tipo
  +atributoPublico: Tipo
  +metodoPublico(): TipoRetorno
  -metodoPrivado(): void
}
```

**Relaciones:**
```plantuml
' Asociación simple
ClaseA --> ClaseB : relación

' Asociación con cardinalidad
ClaseA "1" --> "0..*" ClaseB : tiene

' Agregación
ClaseA o-- ClaseB

' Composición
ClaseA *-- ClaseB

' Herencia
ClasePadre <|-- ClaseHija

' Clase de asociación
ClaseA "x..y" -- "x..y" ClaseB
(ClaseA, ClaseB) .. ClaseAsociacion

' Dependencia
ClaseA ..> ClaseB
```

**Estereotipos y notas:**
```plantuml
class ProcesadorCobros <<Singleton>> {
}

note right of ClaseA
  Esta nota explica
  algo sobre ClaseA
end note
```

**Restricciones:**
```plantuml
ClaseA --> ClaseB
note on link
  {la cuenta debe pertenecer al cliente}
end note
```

### 2.4. Implementación en Kotlin

#### Directrices para el Código

1. **Completitud**: El código debe ser funcional y compilable
2. **Comentarios**: Usar KDoc para documentar clases y métodos principales
3. **Buenas prácticas**:
   - Data classes cuando sea apropiado
   - Null safety de Kotlin
   - Properties en lugar de getters/setters Java
   - Immutabilidad donde sea posible (`val` vs `var`)
4. **Ejemplo de uso**: Incluir función `main()` con ejemplo completo
5. **Validaciones**: Incluir checks con `require()` o `check()` donde haya restricciones

#### Estructura del Código

```kotlin
/**
 * [Descripción de la clase]
 */
class NombreClase(
    private val atributo1: Tipo,
    private val atributo2: Tipo
) {
    // Atributos adicionales
    private val lista = mutableListOf<Tipo>()
    
    /**
     * [Descripción del método]
     */
    fun metodo1() {
        // Implementación
    }
    
    fun metodo2(): TipoRetorno {
        // Implementación con validación
        require(condicion) { "Mensaje de error" }
        return valor
    }
}

// Ejemplo de uso, siempre.
fun main() {
    // Crear instancias
    val objeto1 = NombreClase(...)
    
    // Demostrar funcionalidad
    objeto1.metodo1()
    
    // Verificar comportamiento
    println("Resultado: ${objeto1.metodo2()}")
}
```

### 2.5. Conceptos Clave y Criterios de Evaluación

- **Conceptos Clave**: Lista numerada explicando qué conceptos de POO/UML se aplicaron y dónde
- **Criterios de Evaluación**: Checklist con ✅ mostrando cómo se cumple cada criterio del enunciado

---

## FASE 3: Generación de Imágenes del Diagrama

### 3.1. Proceso

1. **Crear el código PlantUML** completo en el archivo de solución
2. **Generar la imagen**:
   - Usar herramienta online: http://www.plantuml.com/plantuml/ a través de MCP.
   - O usar PlantUML localmente a través de MCP
   - Formato PNG recomendado
3. **Guardar en carpeta assets**: `assets/EjN_[NombreTema].png`
4. **Referenciar en el documento**: `![Diagrama de Clases - Título](assets/EjN_[NombreTema].png)`

### 3.2. Calidad del Diagrama

- **Legibilidad**: Fuente clara, tamaño adecuado
- **Organización**: Layout lógico (herencias arriba, composiciones cerca)
- **Completitud**: Todas las clases, relaciones, cardinalidades y estereotipos visibles
- **Estética**: Usar `skinparam` si es necesario para mejorar apariencia

---

## CHECKLIST FINAL

Antes de considerar completo un ejercicio, verificar:

### Archivo de Enunciado:
- [ ] Título y numeración correctos
- [ ] Descripción del problema clara
- [ ] 3-6 reuniones con especificaciones en voz del cliente
- [ ] Progresión lógica de complejidad
- [ ] Tarea claramente especificada
- [ ] Criterios de evaluación listados
- [ ] Pistas útiles incluidas

### Archivo de Solución:
- [ ] Análisis completo de todas las clases
- [ ] Análisis detallado de todas las relaciones
- [ ] Tabla de roles y cardinalidades
- [ ] Justificación de decisiones de diseño
- [ ] Código PlantUML correcto y completo
- [ ] Imagen del diagrama generada y guardada en assets
- [ ] Implementación Kotlin completa y funcional
- [ ] Ejemplo de uso en `main()`
- [ ] Conceptos clave listados
- [ ] Criterios de evaluación verificados

### Calidad General:
- [ ] Coherencia entre enunciado y solución
- [ ] Nivel de complejidad apropiado
- [ ] Lenguaje claro y educativo
- [ ] Código compilable y sin errores
- [ ] Documentación suficiente

---

## CONSEJOS ADICIONALES

### Para Agentes de IA Generadores

1. **Empatía con el cliente**: Cuando escribas las especificaciones, ponte en el papel de diferentes roles empresariales. Cada uno tiene sus preocupaciones y forma de expresarse.

2. **Progresión pedagógica**: Los ejercicios deben incrementar gradualmente en dificultad. Introduce un solo concepto nuevo por ejercicio.

3. **Realismo**: Los dominios de problema deben ser realistas y relacionables. Evita ejemplos excesivamente abstractos.

4. **Ambigüedad intencional**: En el enunciado, incluye alguna ambigüedad menor que requiera toma de decisiones de diseño. Esto es educativo.

5. **Solución canónica pero flexible**: Tu solución debe ser una respuesta válida, pero no la única posible. En la justificación, menciona alternativas.

6. **Código como documentación**: El código Kotlin debe ser tan claro que sirva como documentación adicional del diseño.

7. **Testing implícito**: El `main()` debe servir como test de integración básico, demostrando que el diseño funciona.

### Patrones Comunes a Considerar

Si se usa ún patron, hacer una introducción a este, indicando casos de uso, diseño y funcionamiento.

- **Singleton**: Para gestores globales únicos
- **Composite**: Para estructuras jerárquicas recursivas
- **Strategy**: Para algoritmos intercambiables
- **Observer**: Para notificaciones de cambios
- **Factory**: Para creación de objetos complejos
- **State**: Para comportamientos dependientes del estado

### Conceptos UML a Explorar

- Clases abstractas e interfaces
- Atributos y métodos derivados
- Visibilidad package (~)
- Atributos de clase (static) con subrayado
- Agregación compartida vs composición
- Asociaciones cualificadas
- Multiplicidad con rangos específicos

---

## EJEMPLO DE APLICACIÓN

Para ilustrar, aquí está el resumen de cómo se crearon los ejercicios 2 y 3:

### Ejercicio 2 (Nivel Básico)
- **Dominio**: Sistema universitario (familiar para estudiantes)
- **Clases**: 4 (Profesor, Curso, Estudiante, Matricula)
- **Concepto clave**: Clase de asociación (Matricula)
- **Complejidad**: Baja-Media
- **Reuniones**: 4
- **Enfoque**: Entender relaciones muchos-a-muchos con atributos

### Ejercicio 3 (Nivel Avanzado)
- **Dominio**: E-commerce (sistema real complejo)
- **Clases**: 7+ (Cliente, Cuenta, Tarjeta, Pedido, PedidoSimple, PedidoCompuesto, Producto, LineaPedido, ProcesadorCobros)
- **Conceptos clave**: Singleton, Composite, restricciones
- **Complejidad**: Alta
- **Reuniones**: 6
- **Enfoque**: Patrones de diseño y reglas de negocio complejas

---

## RECURSOS DE REFERENCIA

- **PlantUML Docs**: https://plantuml.com/class-diagram
- **UML 2.5 Specification**: https://www.omg.org/spec/UML/
- **Kotlin Style Guide**: https://kotlinlang.org/docs/coding-conventions.html

---

**Última actualización**: Noviembre 2025
**Versión**: 1.0
**Autor**: Repositorio 2526_EDES_u3_DiagraClases

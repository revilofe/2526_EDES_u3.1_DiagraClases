# Ejercicio 3: Diagrama de Clases - Sistema de Gestión de Pedidos E-Commerce

## Descripción del Problema

Una empresa de comercio electrónico necesita diseñar un sistema de gestión de pedidos completo. A continuación se presentan las transcripciones de las reuniones mantenidas con el cliente para recopilar los requisitos del sistema.

## Especificaciones del Cliente

### Primera Reunión - Gestión de Clientes y Productos

**Responsable de Negocio:** *"Lo primero es lo básico: necesitamos registrar a nuestros clientes. De cada cliente debemos guardar su nombre completo, dirección de envío, número de teléfono de contacto y su email. Esto es fundamental para poder contactar con ellos y enviarles sus pedidos."*

**Responsable de Negocio:** *"Los clientes van a realizar pedidos de productos, obviamente. Y aquí viene algo importante: cada producto tiene un stock determinado. No podemos vender lo que no tenemos, así que el sistema debe controlar esto estrictamente. Solo se pueden realizar pedidos de productos que estén en stock."*

### Segunda Reunión - Sistema de Cuentas y Pagos

**Director Financiero:** *"Cada cliente necesita tener al menos una cuenta para poder pagar sus pedidos. Aunque generalmente tendrán una sola cuenta, hay clientes que prefieren tener varias cuentas separadas, quizás una para compras personales y otra para compras profesionales. El sistema debe permitir esto."*

**Director Financiero:** *"Cada cuenta está vinculada a una tarjeta de crédito que tiene un saldo disponible. Los clientes podrán aumentar ese saldo cuando quieran, como una recarga, y obviamente el saldo disminuirá cuando realicen compras. Es como un monedero electrónico asociado a su tarjeta."*

**Director Financiero:** *"Y esto es importante: un cliente SOLO puede realizar un pedido si tiene al menos una cuenta con saldo disponible suficiente. Nada de pedidos sin fondos."*

### Tercera Reunión - Tipos de Pedidos

**Jefa de Logística:** *"Tenemos dos tipos de pedidos: simples y compuestos. Déjame explicarte..."*

**Jefa de Logística:** *"Un pedido simple es el caso normal: el cliente añade productos a su carrito y paga. Estos pedidos simples se asocian a una única cuenta de pago y tienen una limitación: pueden contener como máximo 20 productos. Pueden ser 20 unidades del mismo producto o una mezcla de diferentes productos, pero el límite es 20 ítems en total."*

**Jefa de Logística:** *"Ahora, un pedido compuesto es más complejo. Es básicamente la agrupación de dos o más pedidos. Y aquí viene lo interesante: esos pedidos que se agrupan pueden ser a su vez pedidos simples O pedidos compuestos. Es como una estructura jerárquica, ¿entiendes? Puedes tener un pedido compuesto que contenga tres pedidos simples, o un pedido compuesto que contenga dos pedidos simples y un pedido compuesto que a su vez contenga otros pedidos."*

**Jefa de Logística:** *"¿Por qué esto? Pues imagina que un cliente hace un pedido grande que requiere varios envíos desde diferentes almacenes, o que quiere agrupar compras de varios días en un único seguimiento. El pedido compuesto le da esa flexibilidad."*

### Cuarta Reunión - Restricciones y Seguridad

**Responsable de Seguridad:** *"Esto es crítico: el sistema DEBE verificar que cualquier pedido realizado por un cliente sea pagado con una cuenta que pertenezca al mismo cliente. Nada de usar cuentas de otros clientes. Es una regla de seguridad y trazabilidad fundamental."*

### Quinta Reunión - Proceso de Cobro y Estados del Pedido

**Director de Operaciones:** *"El proceso de cobro es muy específico y debe manejarlo una clase especializada. Y esto es importante: esta clase debe ser única en todo el sistema. Solo puede existir una instancia de esta clase procesadora de cobros. Es un Singleton, como lo llaman los programadores."*

**Director de Operaciones:** *"El proceso funciona así: una vez al día, el sistema ejecuta un proceso automático que revisa todos los pedidos pendientes de cobro. Para cada pedido pendiente, intenta cobrar el importe total de la cuenta de pago asociada."*

**Director de Operaciones:** *"Si una cuenta no tiene suficiente saldo para cubrir el pedido completo, se rechaza TODO el pedido. No hacemos cobros parciales. O se cobra todo o no se cobra nada."*

**Director de Operaciones:** *"Una vez que el cobro se ha realizado con éxito, el pedido pasa a estar 'listo para servir'. En ese momento se ordena su distribución al almacén. Cuando el pedido se entrega físicamente al cliente, su estado cambia a 'confirmado'. Así que tenemos varios estados: pendiente de cobro, cobrado/listo para servir, en distribución, y confirmado."*

### Sexta Reunión - Detalles Técnicos

**Desarrollador Senior (consultor técnico):** *"Déjame preguntarte algunas cosas para el diseño..."*

**Desarrollador:** *"Los productos... ¿qué información necesitamos además del stock? ¿Precio, descripción, código?"*

**Responsable de Negocio:** *"Sí, cada producto debe tener un código único identificador, un nombre, descripción y por supuesto el precio unitario. El stock ya lo mencionamos."*

**Desarrollador:** *"Y los pedidos, ¿necesitamos saber las cantidades de cada producto?"*

**Jefa de Logística:** *"¡Por supuesto! En un pedido no solo importa QUÉ productos hay, sino CUÁNTOS de cada uno. Y necesitamos saber el precio que se aplicó en ese momento, porque los precios pueden cambiar con el tiempo."*

**Desarrollador:** *"Entendido. ¿Y las cuentas necesitan algún identificador?"*

**Director Financiero:** *"Sí, cada cuenta debe tener un número de cuenta único, y obviamente el saldo actual. La tarjeta asociada necesita su número, fecha de vencimiento y el saldo disponible que puede ser diferente al saldo de la cuenta."*

## Tarea

A partir de estas especificaciones del cliente, debes:

1. **Identificar todas las clases** del sistema (pista: hay al menos 7 clases principales)
2. **Determinar las propiedades** de cada clase, sus tipos y visibilidad
3. **Definir los métodos** necesarios para cada clase y su visibilidad
4. **Identificar patrones de diseño** (Singleton, Composite, etc.)
5. **Establecer las relaciones** entre clases:
   - Asociaciones simples
   - Composición/Agregación
   - Relaciones con clase de asociación
   - Herencia/Generalización
6. **Especificar roles y cardinalidades** para cada relación
7. **Definir restricciones** (constraints) donde sea necesario
8. **Crear el diagrama de clases UML** completo usando PlantUML

## Conceptos Avanzados a Aplicar

Este ejercicio requiere aplicar:

- **Patrón Singleton**: Para la clase procesadora de cobros
- **Patrón Composite**: Para la jerarquía de pedidos (simples y compuestos)
- **Clase de Asociación**: Para relacionar pedidos con productos (líneas de pedido)
- **Restricciones UML**: Para las reglas de negocio
- **Agregación/Composición**: Para las relaciones de pertenencia
- **Generalización**: Para modelar la jerarquía de tipos de pedidos

## Criterios de Evaluación

Este ejercicio evalúa los siguientes criterios:

- **CE a)** Identificación avanzada de conceptos de POO (herencia, polimorfismo, patrones)
- **CE b)** Uso de herramientas (PlantUML) para diagramas complejos
- **CE c)** Interpretación de especificaciones complejas del mundo real
- **CE d)** Trazado de diagramas con múltiples tipos de relaciones
- **CE e)** Capacidad de generar código a partir de patrones de diseño

## Pistas

- El patrón Composite es ideal para estructuras recursivas (pedidos que contienen pedidos)
- Las líneas de pedido (producto + cantidad + precio) pueden requerir una clase intermedia
- Los estados del pedido pueden modelarse como enumeración o como atributo
- El Singleton debe indicarse con el estereotipo correspondiente
- Las restricciones se expresan con {constraint} en UML
- Piensa en qué relaciones son de composición (no puede existir el hijo sin el padre) vs agregación (relación más débil)

## Notas Adicionales

Este es un ejercicio avanzado que simula un caso real de desarrollo de software. Tómate tu tiempo para:
- Analizar cada reunión cuidadosamente
- Identificar entidades y relaciones
- Aplicar principios SOLID
- Pensar en la navegabilidad de las asociaciones
- Considerar qué operaciones son responsabilidad de cada clase

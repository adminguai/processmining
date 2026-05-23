# Conceptos de Process Mining

> **Capítulo 4 de 20** — Guía Completa de Introducción a Celonis

Definiciones, case-centric vs object-centric, objetos, eventos, relaciones.

---

**El reto:** Te han informado de que exiten grandes problemas con las entregas a tiempo. Los pedidos relacionados con el grupo de material de generadores de energía de reserva son especialmente problemáticos, lo que provoca un aumento de las quejas de los clientes.


Pasemos a los ejercicios para comprender lo que ocurre en los Centros de Datos SecureNet. Para ello, sigue los ejercicios de la página siguiente para navegar hasta la Views dedicada al Itinerario de formación Use & Interpret Views.

Conceptos clave Process Mining

**Este artículo proporciona una rápida visión general de todas las definiciones y conceptos relevantes en torno a Process Mining, incluida la diferencia entre centrado en objetos (OCPM) y centrado en casos (CCPM) Process Mining. ¿Qué es un Proceso?**

Un proceso es una serie de pasos y decisiones para completar una tarea. A menudo pasamos por alto cuántos procesos nos rodean en la vida cotidiana: desde pedir productos por Internet hasta gestionar la aprobación de facturas en el trabajo.

**Process Mining**

Cada paso de un proceso empresarial deja una huella digital en los sistemas transaccionales en forma de datos de registro de eventos. El software Process Mining funciona utilizando estos datos de registro de eventos para crear una imagen viva de cómo son los procesos reales.

**¿Qué es el process mining centrado en casos?**

Case-Centric Process Mining (CCPM) es el enfoque tradicional de Process Mining y tiene algunas cualidades definitorias en el lado del modelado de datos. Realiza el seguimiento de un único tipo de objeto, por ejemplo, un "Artículo de pedido de venta" o un "Artículo de documento de compra", a medida que avanza en un proceso. Todos los eventos, como la creación o modificación de un artículo, están vinculados a ese único objeto. Estos eventos se almacenan en un registro de eventos, que registra marcas de tiempo, actividades y el ID del caso correspondiente.

Case-Centric Process Mining añade valor a las empresas mediante

- proporcionar información sobre los procesos en función de la perspectiva del caso elegido.

- permitiendo a las empresas descubrir oportunidades de valor.

- ayudar a las empresas a rastrear el rendimiento de los procesos en relación con KPIs específicos.

- permitir a las empresas automatizar total o parcialmente las acciones en función de los datos del proceso.

Sin embargo, hay ciertos factores en el enfoque Caso-Céntrico que impiden que Process Mining alcance todo su potencial. Como sólo contempla un tipo de objeto, puede pasar por alto las interacciones entre otros objetos del mismo proceso. Por ejemplo, si un pedido contiene cinco partidas diferentes, un evento como "Pedido cancelado" podría repetirse una vez para cada partida, lo que puede dar lugar a eventos duplicados aunque el evento sólo se haya producido una vez en el nivel de la cabecera del pedido.

Construir y mantener estos Registro de eventos (Event Logs) también requiere tiempo y conocimientos técnicos. A menudo se necesitan ingenieros de datos experimentados y complejos SQL para configurar y actualizar los Data Pipelines, especialmente cuando quieres añadir nuevos Registro de eventos (Event Logs). Además, estas canalizaciones tienden a depender del sistema, por lo que podrías necesitar configuraciones separadas para diferentes sistemas fuente, lo que puede limitar la reutilización y aumentar el esfuerzo general.

Las deficiencias de Case-Centric Process Mining se abordan mediante Object-Centric Process Mining que veremos a continuación.

**¿Qué es el Process Mining centrado en objetos (Object-Centric Process Mining)?**

He aquí un breve vídeo introductorio del profesor Wil van der Aalst que explica los conceptos básicos:

Transcripción

El profesor Wil van der Aalst presenta dos aspectos principales del Object-Centric Process Mining:

- La capacidad de capturar múltiples objetos, eventos y sus relaciones.

- La capacidad de elegir dinámicamente las perspectivas adecuadas para analizar tu negocio desde cualquier ángulo.

A continuación, analicemos más de cerca muchas de las otras ventajas potenciales del process mining centrado en objetos.


**¿Qué son los objetos, los eventos y las relaciones?**

ObjetosEventosRelaciones

En el contexto del process mining, los objetos son las partes físicas y tangibles de tus procesos. Son los elementos afectados por los eventos.

En un escenario de parada en boxes, algunos ejemplos de objetos son **neumáticos, coche, conductor y personal de boxes**.

En un escenario de gestión de pedidos, los objetos son **la orden de compra, la orden de venta, la orden de producción, el envío, la factura, la recepción de mercancías**, y así sucesivamente.


**Un evento es algo que ocurre en un negocio o proceso y que afecta a uno o más objetos, ya sea creándolos o modificándolos. En el escenario de la parada en boxes, el evento " cambiar neumático" afecta a dos objetos: neumáticos y coche. En la gestión de pedidos, el evento "pedido enviado" afecta a tres objetos: envío, factura y orden de venta. Hay dos tipos de relaciones: relaciones entre objetos y relaciones entre eventos y objetos. Las relaciones muestran cuántos objetos puede conectar un objeto o un evento. Tanto las relaciones objeto a objeto como las relaciones evento a objeto pueden ser:**

- **uno a uno,**

- **de uno a muchos,**

- **de muchos a muchos Hay cierta complejidad en las relaciones. Encontrarás algunos detalles introductorios a continuación, pero no dudes en omitirlos si te parece demasiada información. Relaciones entre eventos y objetos Hay dos niveles en las relaciones entre eventos y objetos:**

- **A cuántos tipos de objetos afecta un evento**

- **Cuál es la relación del evento con los tipos específicos de objetos. En un escenario de parada en boxes:**

- **El evento «cambiar neumático» se refiere a varios tipos de objetos: neumáticos y automóviles.**

- **Un caso del evento «cambio de neumático» puede afectar a varios neumáticos. Esta es una relación de uno a muchos.**

- **Y un caso del evento «cambio de neumático» afecta a un automóvil. Esta es una relación de uno a uno. En la gestión de pedidos:**

- **El evento «pedido enviado» afecta a varios tipos de objetos: envío, factura y pedido de venta.**

- **Lo más probable es que un caso del evento «pedido enviado» tenga una relación individual con la factura y el pedido de venta, respectivamente.**

- **Sin embargo, un caso del evento podría tener una relación de uno a muchos con el envío si el pedido se divide en varios envíos. Relaciones entre objetos Puedes definir las relaciones de los objetos desde ambas perspectivas de los objetos. En un escenario de parada en boxes:**

- **Un coche se relaciona con varios neumáticos, mientras que un neumático sólo tiene un coche. Se trata de una relación de uno a muchos (1:m). En la gestión de pedidos:**

- **Un pedido de cliente puede relacionarse con varios envíos y un envío también puede relacionarse con varios pedidos. Se trata de una relación de muchos a muchos (m:n). Puntos clave Case-Centric Process Mining** se centra en perspectivas aisladas (por ejemplo, analizar sólo los neumáticos), lo que puede llevar a conclusiones inexactas, como ver ocho eventos separados para una parada en boxes en lugar de un proceso coordinado.


**Object-Centric Process Mining** combina múltiples perspectivas en "una vista 3D", lo que te permite:

- Identifica las interdependencias entre objetos.

- Desenreda los procesos complejos (los "espaguetis" 🍝 ) en ideas manejables.

- Elige perspectivas específicas en función de tus objetivos de análisis (por ejemplo, centrarte en el coche, los neumáticos o el equipo de boxes).

¿Quieres saber más sobre Object-Centric Process Mining? Entonces visita nuestro curso [**Object-Centric-Process Mining Foundations**](https://academy.celonis.com/learn/course/object-centric-process-mining-foundations-1/object-centric-process-mining-foundations/case-centric-process-mining) 📌


**Presentación del Variant Explorer**


El Variant Explorer (también "VE" para abreviar) es un componente de la View que te permite descubrir todas las formas diferentes en que fluyen los procesos empresariales dentro de tu organización. Cada una de estas formas únicas se denomina **"variante".** En otras palabras, una variante representa objetos que siguen el mismo camino y secuencia de acontecimientos dentro de tu proceso.

Revisar las Variants te permite comprender si las formas en que se ejecutan los procesos en tu organización sigue los flujos deseados.

Con el Variant Explorer puedes...

- Revisa las variantes individualmente.

- Compara múltiples variantes entre sí.

- Revisa las variantes con las métricas del proceso o los Indicadores Clave de Rendimiento (KPIs) disponibles en tu conjunto de datos

- Utiliza las distintas opciones de filtrado.

---

← [Anterior: Celonis Apps y Views](../03-apps-y-views/README.md) | [Índice](../README.md) | [Siguiente: Variant Explorer y Process Explorer](../05-variant-explorer/README.md) →

# Variant Explorer y Process Explorer

> **Capítulo 5 de 20** — Guía Completa de Introducción a Celonis

Variant Explorer, variantes, Process Explorer, animación de procesos.

---

**¿Estás preparado para sumergirte?**

¡Ensúciate las manos e interactúa Variant Explorer!

En los siguientes ejercicios prácticos, te imaginarás en el papel de **un Process Analyst** en el departamento de gestión de pedidos de SecureNet Data Centers. Como parte de tu trabajo diario, utilizarás un Celonis App para investigar y perfeccionar el proceso de gestión de pedidos, con el objetivo de aumentar la eficacia y garantizar la entrega a tiempo.

Para los ejercicios prácticos, tendrás **tres objetos clave** en tu View: (1) pedido de cliente, (2) posición de pedido de cliente y (3) entrega. Si no estás familiarizado con estos objetos, consulta sus descripciones a continuación.

Pedido de venta

Se origina a partir del "Documento de Cabecera de Pedido de Venta", que contiene un acuerdo entre un vendedor y un cliente relativo a la venta y entrega de mercancías, así como a cualquier servicio que esté asociado a estos procesos. Las distintas entradas se dividen en entidades de posición de pedido de cliente.


Articulo de Orden de Venta

Una partida en el documento de cabecera del pedido de cliente que detalla una parte específica de un acuerdo de pedido de cliente.


Entrega

Se origina a partir del "Documento de Cabecera de Entrega", que es el objeto central del proceso de entrega que proporciona información general sobre el movimiento de mercancías. Las distintas entradas se dividen en entidades separadas de Partida de Entrega.


**El reto: **Te han informado de que hay grandes problemas con las entregas a tiempo. Es posible que el ciclo de procesamiento de pedidos se ralentice por las intervenciones manuales, los frecuentes cambios de pedido, los bloqueos y las cancelaciones, que crean la tediosa Reajuste (Rework). Sin embargo, no están claras las causas profundas ni cuándo ocurren estos hechos.


**Selecciona el Tipo de Objeto**

Antes de empezar con los ejercicios de este curso, elimina cualquier filtro que pueda haber quedado del curso anterior, por favor.


Cuando trabajes con un Object-Centric Data Model (OCDM), podrás revisar varios tipos de objetos diferentes.

Si utilizas el botón Variant Explorer verías un objeto cada vez. Por tanto, el primer paso que tendrías que dar al trabajar con un objeto Variant Explorer en una View, es **elegir en qué tipo de objeto quieres profundizar**.

El OCDM con el que trabajarás en los ejercicios de este curso tiene tres tipos de objetos clave que pertenecen al proceso Order Management.

Ahora, ¡manos a la obra!

Ve a tu entorno de formación y utiliza los controles para seleccionar el tipo de objeto Sales Order.


**La Variante Más Común**

Como ya se ha dicho, el botón Variant Explorer muestra por defecto la variante más común.

Empecemos revisando la variante más común de este conjunto de datos, es decir, el mayor grupo de objetos que pasan por el mismo conjunto de eventos, siguiendo la misma secuencia. El número de objetos que pasan por cada conexión es el mismo durante todo el proceso, ya que sólo estás viendo una variante en este momento.

**¿Cuál es el porcentaje de objetos cubiertos por esta variante?**

Respuesta

79%. ¡Una gran mayoría de los pedidos de venta pasan exactamente por este conjunto y secuencia de acontecimientos!

Aquí encontrarás la respuesta. ⬇️


Cuando revises los eventos de principio a fin, verás que la mayoría de las veces en este proceso, (1) se crean cabeceras de pedido de cliente, (2) se crean posiciones de pedido de cliente y, a continuación, (3) se aprueba el pedido de cliente.

En este VE, debajo de cada encabezado de evento, verás la cantidad de veces que ha ocurrido cada evento. Ten en cuenta que, dependiendo de cómo tu Data Analyst haya configurado la View, también podrías ver otros KPIs relevantes en este área.


**¿Qué es Process Explorer?**

El Process Explorer es una poderosa herramienta, especialmente cuando adoptas un enfoque exploratorio en tu viaje de análisis de procesos. Es especialmente útil para revelar rápidamente los sucesos que ocurren más allá de los más comunes e identificar cómo se comportan e interactúan los distintos tipos de objetos. También te permite centrarte en un único suceso, por ejemplo, un suceso no deseado, para examinar los atributos asociados y las posibles causas raíz de las deficiencias de rendimiento.

¡Mira el vídeo siguiente para ver lo que puedes conseguir con el Process Explorer!

El Process Explorer que se muestra en el vídeo está conectado a un Object-Centric Data Model (OCDM), pero también puede estar construido sobre un Case-Centric Data Model (CCDM). ¡Explora las diferencias entre ambos en las pestañas siguientes!

Process Explorer conectado a un OCDMProcess Explorer conectado a un CCDM

**Process Explorer conectado a un OCDM**

El Process Explorer conectado a un OCDM se asemeja a un mapa de metro, donde las "estaciones" representan eventos y las "líneas" indican las conexiones entre ellos. Esta disposición te permite visualizar los procesos desde la perspectiva de diferentes tipos de objetos y sus flujos de proceso separados, indicados por colores diferentes.

En este ejemplo concreto, los cuatro tipos de objeto - **purchase order**, **purchase order item**, **vendor invoice** y **vendor invoice item** - comparten todos el evento "**Record Invoice Receipt**".


**Process Explorer conectado a un CCDM**

El Process Explorer conectado a un CCDM muestra sólo una perspectiva concreta de tu proceso. Este ejemplo, muestra el proceso desde la perspectiva del** purchase order item**, desde la creación de su requisition item hasta el clearing de la invoice.


Este curso y sus ejercicios interactivos utilizan un **Process Explorer** conectado a un **OCDM**. Si el tuyo funciona con un CCDM, puedes seguir el curso igualmente: las funciones principales son las mismas y la interpretación del componente funciona de forma similar.


**Panel**

Si miras a la izquierda del componente, podrás ver el panel. En el modo panel, **se tienen en cuenta tanto las conexiones directas como las indirectas entre eventos**. Es decir, si existe un camino de un evento a otro - aunque pase a través de múltiples eventos intermedios - sigue considerándose una conexión. El panel es útil para obtener un resumen general del proceso cuando el usuario está interesado en eventos concretos. En este ejemplo, puedes ver que desde el evento "Approve Sales Order", 23,6K sales orders continuaron directa e indirectamente hacia el final del proceso.


**Slider**

Si miras a la derecha del componente, puedes ver el **slider**. En el modo slider, sólo se tienen en cuenta **las conexiones directas entre un evento y otro**. El uso del slider muestra claramente el número de desviaciones del proceso, lo que facilita evaluar su impacto y priorizar las que hay que abordar. En este ejemplo, puedes ver que desde el evento "Approve Sales Order", sólo 21,6k sales orders continuaron directamente hasta el final del proceso.


**Lleva tu Exploración de Procesos al Siguiente Nivel**

Ahora que ya dominas los aspectos básicos de Process Explorer, vamos a sumergirnos en funciones avanzadas que te facilitarán y agilizarán aún más la búsqueda de insights claves. Abre las pestañas a continuación para explorar cada una de ellas.

Global SliderOcultar EventosConectar procesos multi-objetoAnimación del proceso

El **global slider** es una herramienta potente que te permite añadir y eliminar eventos y conexiones de varios tipos de objetos simultáneamente. En lugar de hacer ajustes con cada slider individual, puedes utilizar el global slider para añadir el siguiente evento más frecuente de **entre todos los tipos de objeto** a la vez. Esto te permite explorar mas rápido y obtener una visión holística de tu proceso.

Puedes seguir utilizando los sliders individuales para añadir o eliminar elementos de un tipo de objeto concreto. Los cambios que realices, ya sea con sliders globales o individuales, se reflejan entre sí, lo que te permite cambiar fácilmente de uno y otro. Añadir el siguiente evento más frecuente puede implicar que se añadan más eventos para conectar el nuevo evento al gráfico de proceso existente.


A veces, puede que no te interesen todos y cada uno de los eventos de tu proceso. Por ejemplo, algunos eventos pueden generarse automáticamente o aparecer en todos los objetos. El menú de eventos de la esquina superior derecha del Process Explorer te permite **ocultar determinados eventos** para que puedas centrarte en los que son más relevantes para ti.

Desde este menú, puedes utilizar las casillas de verificación para mostrar u ocultar cualquier evento. También puedes utilizar la barra de búsqueda para encontrar eventos concretos o utilizar los botones "Select all" y "Clear All" para gestionar tus selecciones. Una vez que hayas hecho tus elecciones, haz clic en "Update" para actualizar el gráfico del proceso.

Es importante tener en cuenta que, aunque ocultar un evento impedirá que se muestre, no filtrará los objetos asociados a dicho evento. En las próximas páginas se darán más detalles sobre el filtrado, ¡permanece atento!


Cuando añades eventos y conexiones, el Process Explorer puede volverse muy complejo. Para simplificarlo y asegurarte de que todos tus objetos estén conectados, puedes utilizar el botón "**Connected multi object Process Explorer**".

Este botón ajusta automáticamente todos tus sliders al estado mínimo necesario para conectar todos los objetos en el Process Explorer mediante eventos compartidos. Por lo tanto, si tu gráfico de procesos ya es complejo, al hacer clic en este botón se simplificará hasta este estado mínimo conectado.

Si no es posible conectar todos los objetos (por ejemplo, si un objeto no comparte eventos con otros), el botón ajustará el gráfico de proceso al estado con el menor número de objetos desconectados.


La función de **process animation** muestra visualmente cómo fluyen los objetos a través de eventos y conexiones. Al animar el proceso, es mucho más fácil seguir el flujo de tus objetos y detectar momentos críticos que interpretando un gráfico estático. La animación no está activa por defecto. Tienes dos opciones para iniciarla:

Sitúa el cursor sobre el nodo inicial de cualquier tipo de objeto para que aparezca la ventana emergente:

- Haz click en el botón Play (▶) para animar el flujo del proceso sólo para ese tipo de objeto concreto.

- Haz click en el botón Play All ( ▶▶) para animar el flujo de todos los objetos en el Process Explorer simultáneamente. Esto es útil para identificar si tus procesos multi-objeto se ejecutan de forma sincronizada.

El botón "Start Process Animation", en la esquina inferior izquierda, controla la animación una vez que está marcha:

- Pausar y Reiniciar: Utiliza este control para pausar la animación y reiniciarla en cualquier momento.

- Ajustar velocidad y tiempo: Puedes aumentar la velocidad de reproducción o avanzar directamente a un periodo de tiempo concreto que contenga un insight clave.

- Analizar momentos de alta actividad: Utiliza el menú desplegable para agrupar los casos por horas o días. Esto te proporciona una visión analítica, ya que el tamaño de la burbuja de animación refleja el número de objetos agregados: burbujas más grandes indican mayor volumen durante ese periodo.

Process Explorer y Variant Explorer en Views

- Celonis proporciona múltiples herramientas para la exploración de procesos. Dos de ellas muy potentes son Variant Explorer y Process Explorer. Ambas te muestran cómo se ejecutan realmente tus procesos utilizando datos de eventos objetivos recogidos en tiempo real de tus sistemas operativos. Pero, ¿en qué se diferencian? Eso es lo que trataremos en este artículo - ¡y al final, tenemos un pequeño concurso para ti! Permanece atento 🚀

- ¿Qué es el Variant Explorer?

- La Variant Explorer te ayuda a explorar cómo fluye un proceso concreto a través de tu organización. Si te imaginas un proceso como un viaje por carretera, cada variante del proceso es como una ruta distinta de principio a fin. Cada acontecimiento del proceso representa un punto intermedio en el camino, y las conexiones entre acontecimientos son las carreteras que conectan esos puntos intermedios. Cada viaje que hace una persona a lo largo de una ruta concreta representa cómo fluye un objeto a través del proceso. Cada vez que alguien sigue esa misma ruta, cuenta para el recuento total de esa variante específica.


- ¿Qué es Process Explorer?

- El Process Explorer te ayuda a comprender cómo interactúan los distintos acontecimientos y tipos de objetos en tu organización. En lugar de centrarse en rutas distintas (variantes), destaca los eventos y conexiones más comunes, un poco como ver toda la red de carreteras desde arriba. En lugar de mostrar cada ruta única que sigue la gente, señala las carreteras más transitadas y los puntos de paso clave. También puedes detectar rápidamente sucesos poco frecuentes y ver cómo se comportan los distintos viajeros (tipos de objetos): tal vez conducen un coche, paran a repostar o se topan con controles de velocidad.

**Bienvenido.**

Creemos que tú eres el responsable de la forma en que trabajas con Celonis y mereces cierta flexibilidad a la hora de utilizarlo. Por eso queremos capacitarte sobre las ventajas del Task Inbox y cómo utilizarlo.

El curso sigue una estructura modular. No se requieren conocimientos previos, pero podría facilitar tu progreso en el aprendizaje si conocieras los fundamentos de Celonis Apps. Te recomendamos que empieces por (alguno de) nuestros [Cursos de Celonis Apps ](https://academy.celonis.com/catalog?labels=%5B%22Feature%22%5D&values=%5B%22Apps%22%5D).

Celonis Apps son **soluciones empaquetadas** que constan de Views, Knowledge Models, y assets de automatización que proporcionan diferentes capacidades a distintos usuarios en todos los niveles de una organización. Como usuario final, la **View** (muchos la llaman "cuadro de mandos"/dashboard) es tu **cabina para actuar** cada día.

Si has trabajado con Celonis Apps antes, puede que recuerdes ejemplos de cómo es "pasar a la acción todos los días" ("take action every day"). Dependiendo de si trabajas en Accounts Payable (Cuentas por pagar), Order Management o Ventas, Celonis Apps te ayudan, por ejemplo, a procesar facturas o a ponerte en contacto con cuentas si se cumplen determinados criterios. Estas acciones suelen estar envueltas en "tasks" accesibles en cada App respectivo.


¿Qué te parece reunir todas estas tasks en un lugar centralizado? ¿E incluso trabajar en varias tasks con el mismo objetivo de tarea al mismo tiempo? Por eso hemos creado la función **Task Inbox**.

La página Task Inbox muestra tus tareas agrupadas por tipo de tarea. El único requisito previo: Que se te haya asignado una tarea.


Así que ¡a sacarle el máximo partido a Task Inbox!** En las próximas lecciones aprenderás a:**

- Diferencia entre Tasks en Views y Task Inbox

---

← [Anterior: Conceptos de Process Mining](../04-process-mining-conceptos/README.md) | [Índice](../README.md) | [Siguiente: Task Inbox y Starter Kits](../06-task-inbox-starter-kits/README.md) →

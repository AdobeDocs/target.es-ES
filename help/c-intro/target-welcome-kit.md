---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de bienvenida de Adobe Target.
title: Kit de bienvenida de Adobe Target
feature: intro
translation-type: tm+mt
source-git-commit: 0abdb598f6141edad97381bd7d457057394c2550
workflow-type: tm+mt
source-wordcount: '7755'
ht-degree: 5%

---


# Kit de bienvenida de Adobe Target

Bienvenido a Adobe Target.

## Capítulo 1: Introducción

Si hoy en día es como la mayoría de las empresas, ha modernizado sus canales de marketing digital. Ahora está buscando formas de distinguir su marca, para separarse del paquete, y al hacerlo aumentar los ingresos, las tasas de conversión y otras métricas clave del negocio. Una forma de hacerlo es optimizando y personalizando las experiencias digitales que ofrece a sus clientes mediante lo que sabe de ellos para sacar el máximo partido de sus interacciones en su sitio web, sitio móvil, aplicación móvil o cualquier otro punto de contacto de marca. Puede que incluso quiera ampliar esta optimización y personalización más allá de sus puntos de contacto digitales tradicionales a puntos de contacto como quioscos, dispositivos con Internet de las cosas (IoT), interacciones con el centro de llamadas y asistentes de voz como Alexa. Las marcas que han utilizado [!DNL Target] para probar y personalizar sus experiencias digitales han obtenido resultados increíbles.

Por ejemplo:

* Un banco importante probó y simplificó un formulario de solicitud de préstamo. Los inicios de solicitudes se triplicaron y las solicitudes se completaron en más del 50 por ciento.
* Una gran compañía de tecnología B2B personaliza las páginas de productos con recursos como guías y documentos técnicos. Los clics en recursos aumentaron más del 25 por ciento.
* Una importante compañía hotelera personalizó el contenido de su aplicación móvil. Las tasas de conversión se duplicaron en comparación con su sitio de dispositivos móviles y la aplicación superó los 1.500 millones de dólares en reservaciones.

El compromiso con sus clientes de esta manera requiere una solución que se pueda utilizar en casi cualquier punto de contacto utilizando casi cualquier fuente de datos para comprenderlos. [!DNL Adobe Target], parte de [!DNL Adobe Experience Cloud], es esa solución. [!DNL Target] le ofrece las capacidades de optimización y personalización que necesita para ofrecer a sus clientes las experiencias más relevantes y oportunas que generan más ingresos y mayor conversión.

Si está revisando este kit de bienvenida, ya ha decidido crear su programa de optimización y personalización en [!DNL Adobe Target]. Nos alegra que lo hicieras.

Ahora queremos asegurarnos de que inicios usarla de la manera correcta, de inmediato.

Para ayudarle, hemos creado este kit de bienvenida, con información, herramientas y recursos clave que le ayudarán a prepararse para la primera [!DNL Target] actividad y a iniciarla. A largo plazo, estos contenidos también proporcionan la base para crear un programa de optimización y personalización exitoso.

## Capítulo 2: Adobe Target de un vistazo

Antes de empezar a usar [!DNL Adobe Target], puede resultar útil obtener una descripción general de alto nivel de la solución. En este capítulo, conozca las funciones clave de la solución, los puntos de contacto de marca en los que puede utilizarla, las opciones de implementación, las características y flujos de trabajo importantes de la interfaz de usuario, las funciones de gobernanza y su función en general [!DNL Adobe Experience Cloud]. A menos que se indique que [!DNL Adobe Target Premium] son características, los elementos descritos en este capítulo están disponibles tanto con [!DNL Adobe Target Premium] como con [!DNL Adobe Target Standard]. For more information, see [Introduction to Target](/help/c-intro/intro.md).

### Capacidades y actividades

Las pruebas y la personalización son los dos tipos de funciones que [!DNL Target] oferta y que puede utilizar al crear una &quot;actividad&quot; en [!DNL Target]. Es posible que vea el término &quot;prueba&quot; usado indistintamente con &quot;optimización&quot; y &quot;personalización&quot; utilizado indistintamente con &quot;objetivo&quot;.

En una actividad de prueba, se compara una variación de una experiencia digital con una o varias variaciones más para descubrir que una que provoca que la mayoría de los visitantes realicen una acción deseada. [!DNL Target] oferta las siguientes funciones de prueba: Prueba A/B, prueba multivariada (MVT) y asignación automática.

Con una actividad de personalización, usted ofrece una experiencia digital adaptada a un grupo específico de visitantes o a cada visitante individual. [!DNL Target] oferta estas funciones de personalización: Segmentación de experiencias, Destinatario automático, Automated Personalization y Recommendations.

Para obtener información más detallada sobre cuándo y cómo utilizar cada función, consulte Tipos [de actividad de](/help/c-activities/target-activities-guide.md)Destinatario.

| Tipo de actividad | Detalles |
| --- | --- |
| Segmentación de experiencias (XT) | Distribuya contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por el usuario. **[!UICONTROL La segmentación]** de experiencias es valiosa para dirigir una experiencia o contenido específico a una audiencia en particular cuando se entiende que una audiencia es valiosa y tiene un buen sentido de la experiencia que resuena con ellos. [Más información](/help/c-activities/t-experience-target/experience-target.md). |
| Prueba A/B | Compare dos o más variaciones de sus experiencias o ofertas en el sitio web, u otro punto de contacto de clientes digitales para ver qué variación mejora más las medidas comerciales clave durante un período de prueba preespecificado. Las pruebas A/B son ideales para cambios de gran tamaño, como nuevos diseños de página web, distintos enfoques de la navegación del sitio o tratamientos radicalmente diferentes de elementos individuales de una experiencia digital como copiar, imágenes y botones de llamada a acción. [Más información](/help/c-activities/t-test-ab/test-ab.md). |
| Prueba multivariable (MVT) | Compare todas las combinaciones posibles de variaciones de elementos en la página o experiencia digital; por ejemplo, tres imágenes de fondo diferentes, dos variaciones de copia y dos colores de botón diferentes. MVT determina qué combinación ofrece el mejor rendimiento para una audiencia específica y qué elementos tienen el mayor impacto en los resultados. [Más información](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Asignación automática | Identifique la experiencia de mejor rendimiento entre dos o más experiencias y reasigne automáticamente más tráfico al ganador para aumentar las conversiones mientras la prueba continúa ejecutándose y aprendiendo. Utiliza Inteligencia Artificial [!DNL Adobe Sensei]. [Más información](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Destinatario<br>automático (Premium) | Aproveche Adobe Sensei AI en [!DNL Target] para determinar y ofrecer la mejor experiencia de varios a cada visitante en función de su perfil de cliente individual y del comportamiento de visitantes anteriores con perfiles similares. El Destinatario automático permite la personalización a escala. |
| Automated Personalization<br>(Premium) | Utilice algoritmos avanzados de aprendizaje automático y automatización [!DNL Adobe Sensei] para revisar diferentes combinaciones de imágenes, copias y otros elementos de una oferta y ofrecer la mejor combinación a cada visitante en función de cuál es el mejor logro para los objetivos comerciales, como mayores conversiones o ingresos por visitante. [Más información](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Recommendations<br>(Premium) | Utilice Adobe Sensei AI para sugerir automáticamente productos o contenido que pueda interesar a sus clientes en función de su actividad anterior y la de otros clientes. [Más información](/help/c-recommendations/recommendations.md). |

### Canales

Puede usar [!DNL Target] para probar y personalizar experiencias digitales prácticamente en cualquier lugar: puntos de contacto digitales tradicionales como su sitio web, sitio móvil y aplicación móvil, pero también en puntos de contacto como quioscos, correo electrónico, dispositivos IoT, consolas de juegos e incluso asistentes de voz como Alexa y Cortana. Muchos inicios de compañías usan [!DNL Target] en su sitio web. Sin embargo, investigaciones recientes indican que más personas visitan marcas desde sus dispositivos móviles. Ahora es esencial optimizar los canales móviles. Idealmente, conectará las experiencias del visitante en todos sus puntos de contacto para ofrecer una experiencia uniforme y sin problemas.

| Canal | Detalles |
| --- | --- |
| Sitio web | [!DNL Target] se puede utilizar para ejecutar actividades de prueba A/B, Multivariate Testing, segmentación de experiencias, asignación automática, Destinatario automático, Automated Personalization y Recommendations en páginas de sitios web de varias páginas, aplicaciones de una sola página (SPA) y sitios web móviles para mejorar el visitante y la participación del cliente, aumentar las conversiones y aumentar los ingresos. |
| Web móvil | [!DNL Target] se puede utilizar para ejecutar los mismos tipos de actividad que se ejecutan en el sitio web en las páginas del sitio web móvil para mejorar de forma similar el visitante y la participación del cliente, aumentar las conversiones y aumentar los ingresos. |
| Aplicación móvil | [!DNL Target] se puede utilizar para probar y personalizar experiencias de aplicaciones móviles en función del comportamiento del usuario y del contexto móvil. [!DNL Target] le permite ofrecer interacciones que atraen y convierten mediante pruebas iterativas, así como segmentación de experiencias y personalización basada en AI. Para usar [!DNL Target] en la aplicación móvil, debe utilizar el SDK de Adobe Mobile Services. |
| IoT/En todas partes | [!DNL Target] oferta una implementación del lado del servidor para que pueda utilizar las mismas funciones de prueba y personalización en actividades que utiliza en el sitio web, el sitio móvil y las aplicaciones móviles tradicionales en correos electrónicos y puntos de contacto que carecen de explorador o que no utilizan código JavaScript. Por ejemplo, para que pueda probar y personalizar quioscos, decodificadores, consolas de juegos, asistentes de voz y otros puntos de contacto no tradicionales. |

### Implementaciones

Es posible que muchos de ustedes deseen utilizar [!DNL Target] para probar y personalizar en sus diferentes puntos de contacto digitales, incluidos los puntos de contacto web y móviles tradicionales, pero también los puntos de contacto que carecen de un explorador o no utilizan código JavaScript. En algunos casos, la política interna o externa requiere que tenga niveles adicionales de control y seguridad. También puede tener procesos que necesiten ejecutarse en un servidor back-end por motivos de rendimiento. Para satisfacer esta amplia variedad de usos, le ofrecemos la posibilidad de implementar [!DNL Target] de diferentes maneras: cliente, servidor o una combinación de ambos.

| Tipo de implementación | Detalles |
| --- | --- |
| Lado del cliente | With this implementation of [!DNL Target], [!DNL Target] delivers the experiences associated with an activity directly to the client browser. El explorador decide qué experiencia mostrar y lo hace. With client-side, you can use a WYSIWYG editor, the **[!UICONTROL Visual Experience Composer]** (VEC), or a non-visual interface, the **[!UICONTROL Form-based Experience Composer]**, to create your test and personalization experiences. [Más información](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Servidor | En este tipo de implementación, un dispositivo cliente realiza una solicitud de una experiencia a través del servidor, el servidor la envía a [!DNL Target] , [!DNL Target][!DNL Target] devuelve la respuesta al servidor y el servidor decide qué experiencia se debe entregar al dispositivo cliente para que se represente. La experiencia no necesita mostrarse en un explorador; puede mostrarse en un correo electrónico o quiosco, a través de un asistente de voz o a través de otro dispositivo no visual o no basado en un explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor. [Más información](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implementación híbrida | En esta implementación, se elige el método de implementación que mejor funciona para un caso de uso determinado. Por ejemplo, puede utilizar una implementación del lado del cliente para probar una oferta en una pancarta protagonista de la página de inicio, pero también utilizar una implementación del lado del servidor para determinar los resultados de búsqueda interna que se mostrarán en un navegador del cliente, la experiencia que se mostrará en un panel de automóvil inteligente o la respuesta de voz que un asistente de voz ofrecerá. |

### Elementos de actividad

En [!DNL Target], puede crear una actividad de personalización, una actividad de optimización o una actividad que optimice su enfoque de personalización. Cada actividad tiene elementos clave: las experiencias o ofertas que está probando o personalizando, las audiencias o personas a las que está ofreciendo una experiencia, las métricas por las que mide el impacto de la actividad y los informes que muestran visualmente ese impacto.

| Tipo de elemento | Detalles |
| --- | --- |
| Experiencias | Oferta, imagen, texto, botón, vídeo, una combinación de estos elementos en una página, una página web completa o un conjunto de páginas que quizás forman un canal de compras o cualquier otra secuencia lógica de páginas. También puede ser la respuesta de un ayudante de voz, un script de servicio al cliente o incluso un sabor personalizado de una máquina de bebidas. Las experiencias se prueban o personalizan en actividades de [!DNL Target]. [Más información](/help/c-experiences/experiences.md). |
| Ofertas | Bloque de contenido que puede contener imágenes, texto, HTML, vínculos, vídeo, un botón de llamada a acción, una respuesta de asistente de voz o cualquier otro tipo de contenido. Una oferta puede ser por un descuento, envío gratuito, etc. Una oferta se puede mostrar en una página web, pero también puede experimentarse en cualquier punto de contacto del cliente, como un asistente de voz o una consola de juegos. Al probar una oferta, se mide su éxito en comparación con otras ofertas o sin oferta. [Más información](/help/c-experiences/c-manage-content/manage-content.md). |
| Audiencias | Un grupo de personas con las mismas características, como un visitante nuevo, un visitante habitual o un visitante habitual de la zona oeste. La funcionalidad Audiencia le permite segmentar contenido y experiencias diferentes para optimizar el marketing web mostrando los mensajes adecuados para la persona adecuada y en el momento adecuado. If a visitor is identified as part of a target audience, [!DNL Target] determines which experience to display, based on criteria defined during activity creation. [Más información](/help/c-target/target.md). |
| Métricas de éxito | Key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity. Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente. [Más información](/help/c-activities/r-success-metrics/success-metrics.md). |
| Informes | Información sobre el progreso y los resultados de sus actividades que le ayudan a tomar decisiones en función de sus datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una prueba, mostrar qué experiencia de oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes. [Más información](/help/c-reports/reports.md). |

### Herramientas de creación de actividades

[!DNL Target] proporciona tres formas principales de configurar las actividades de prueba y personalización, el Compositor [!UICONTROL de experiencias] visuales (VEC), el Compositor [!UICONTROL de experiencias basadas en]formularios y el Compositor [!UICONTROL de experiencias visuales de la aplicación de una]sola página (SPA). Ambos le guiarán a través del proceso de configuración de actividades en tres pasos: definir las experiencias, seleccionar o definir las audiencias y seleccionar las métricas de éxito principales y secundarias mediante las cuales medirá los resultados de la actividad.

| Herramienta | Detalles |
| --- | --- |
| Compositor de experiencias visuales (VEC) | Interfaz de usuario WYSIWYG que permite crear y probar fácilmente experiencias y ofertas personalizadas en el contexto del sitio. You can create experiences and offers for [!DNL Target] activities by dragging and dropping, swapping, and modifying the layout and content of a web page (or offer) or mobile web page. [Más información](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Compositor de experiencias basadas en formularios] | Una interfaz de creación de ofertas y experiencia no visual que resulta útil para crear experiencias que se pueden usar en pruebas A/B, segmentación de experiencias, Automated Personalization y actividades de Recommendations cuando el Compositor de experiencias visuales no está disponible o resulta práctico para su uso. Por ejemplo, puede utilizar el Compositor basado en formularios para crear experiencias y ofertas para su envío en correos electrónicos, kioscos y asistentes de voz. [Más información](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Compositor de experiencias visuales de aplicación de una sola página (SPA)] | El VEC para aplicaciones de una sola página (SPA) permite que los comerciantes creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que depender de un desarrollo continuo. El VEC se puede utilizar para crear pruebas A/B y actividades de segmentación de experiencias (XT) en marcos populares, como React y Angular. [Más información](/help/c-experiences/spa-visual-experience-composer.md). |

### Gobernanza y control

Para proporcionar a las personas adecuadas las funciones y los niveles asociados de acceso y permisos a [!DNL Target], contamos con una consola administrativa. Para los usuarios de [!UICONTROL Destinatario Premium] , la oferta de un control y una gestión más detallados se realiza con los permisos [!UICONTROL de]Enterprise.

| Herramienta | Detalles |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Añada usuarios a Adobe Target y asigne permisos de Adobe Admin Console. [Más información](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Enterprise]Permissions<br>(Premium) | Un medio de administración formal de usuarios en todo el sitio para [!DNL Target]. Add users to [!DNL Target], assign permissions based on their roles, and create workspaces for teams based on different departments, global locations, channel, and other logical groupings. Puede asignar a los usuarios las funciones Observador, Editor, Editor o Aprobador. [Más información](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

### Integraciones

[!DNL Target] se puede integrar con muchos sistemas de origen, segundo y tercero. Estas integraciones pueden ser valiosas para darle acceso a los datos de visitante y de clientes disponibles en esos sistemas para utilizarlos en la creación de audiencias para pruebas y personalización. Como parte de [!DNL Adobe Experience Cloud], [!DNL Target] se integra estrechamente con [!DNL Experience Cloud] las soluciones y sus servicios principales.

| Integración | Detalles |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] dispone de funciones integradas con otras [!DNL Adobe Experience Cloud] soluciones para personalizar las experiencias a escala. Aproveche la potencia de [!DNL Target] junto con [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), Audiencias [](/help/c-integrating-target-with-mac/mmp.md)Experience Cloud, [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) y [](/help/c-experiences/c-manage-content/aem-experience-fragments.md) Adobe Experience ManagerAEM. |
| API de destinatario (Premium) | [!UICONTROL Destinatario] oferta más de 40 API que puede utilizar para integrar Adobe Target con sistemas de origen, de segundo y de terceros. [Más información](/help/api/api-overview.md). |

### Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Desarrolle sus ideas de pruebas y personalización&quot;.

#### Prácticas recomendadas para la optimización

* **Buena estrategia**: ¿Cuál es nuestro objetivo y hipótesis? ¿Están alineados? Por ejemplo, queremos aumentar los envíos de solicitudes de préstamos, por lo que suponemos que si se reduce el número de campos en el formulario de solicitud, se logrará eso.
* **Metodología** disciplinada ¿Estamos empezando a probar en los lugares correctos? Por ejemplo: necesita ubicaciones que tengan tráfico suficiente y que afecten a las métricas que son importantes para la empresa.
* **Configuración** correcta ¿Está nuestra actividad preparada para alcanzar nuestro objetivo? Por ejemplo: si estamos tratando de aumentar los envíos de solicitudes de préstamos, deberíamos destinatario a las personas interesadas en los préstamos y medir los clics del botón &quot;Enviar&quot;.
* **Análisis** exhaustiva: ¿La actividad de la prueba se ha ejecutado hasta la finalización? ¿Qué dicen los resultados? Ejecute su actividad hasta que alcance entre el 95% y el 99% de confianza estadística. Documento por qué cree que ganó la experiencia ganadora y aplique el aprendizaje en otra parte.
* **Pruebas** iterativas: ¿Estamos aprovechando los conocimientos de actividades anteriores? Si encuentra una táctica ganadora, intente mejorarla o realice cambios que funcionen con ella para mejorar aún más la métrica de éxito.

#### Las opiniones pueden afectar negativamente a los resultados

* Opiniones que pueden afectar negativamente a su eficacia. Opinión de la persona más paga (HIPPO), actitudes, prejuicios. Por ejemplo: el director general desea reducir el tamaño del cuadro de búsqueda para dejar más espacio en cada página. Deberíamos realizar pruebas para asegurarnos de que no reduce el número de búsquedas.
* ¿Actúas con opiniones? No me gusta el aspecto de la prueba. Al cliente no le gustará en absoluto esta experiencia. Si bien la intuición es útil, las pruebas A/B han demostrado una y otra vez que no siempre se realizan correctamente.
* ¿O tiene una mentalidad de optimización? Me emociona ver qué experiencia gana. ¿Tenemos suficientes opciones para probar?

#### Los supuestos también pueden afectar negativamente a los resultados

* Supuestos que pueden afectar negativamente a su eficacia. Mentalidad de manada (así es como nuestros competidoras lo hacen). Por ejemplo, todos nuestros competidoras usan pancartas heroicas con imágenes rotativas, así que deberíamos hacerlo también.
* Suponiendo que sepamos por qué algo está funcionando o no. Suponiendo que no necesitamos probar algo. Por ejemplo, siempre se lista las habitaciones de hotel en orden de más alto a más bajo precio como predeterminado.
* ¿Estás actuando sobre suposiciones? No necesitamos probar eso, hemos comprobado los análisis. (Sí, pero puede haber más en la historia de lo que revela el análisis).
* ¿O tiene una mentalidad de optimización? Lo probamos todo.

## Capítulo 3: Desarrolle sus ideas de pruebas y personalización

Para la primera actividad, puede probar algo súper sencillo como cambiar el color o copiar en un botón de llamada a acción. Sólo para mojar los pies. Sin embargo, a más largo plazo, deseará establecer un proceso formal y repetible para presentar ideas para pruebas y actividades de personalización que ayuden a madurar el programa de optimización y personalización. Los seis pasos siguientes describen un proceso probado para hacer exactamente eso, junto con detalles sobre qué hacer en cada paso.

![Ejecución iterativa del diagrama de estrategia de optimización y personalización](/help/c-intro/assets/six-steps.png)

### Paso 1: Estrategizar

Identificar oportunidades para actividades que se alinean con los objetivos comerciales.

Haga esto mediante:

* Lluvia de ideas sobre [!DNL Target] actividades potenciales basadas en datos de rendimiento del sitio, análisis de competidoras y resultados de pruebas anteriores.
* Desarrollar ideas para actividades de revisión, comentarios y suscripción.

Por ejemplo: busque una página en el sitio con una tasa de salida hacia otro sitio alta, considere qué podría estar causando el problema y vea las formas de reducir la tasa de salida hacia otro sitio.

### Paso 2: Priorizar

Clasifique y programe actividades en base a la alineación del negocio, el nivel de esfuerzo y el impacto potencial.

Haga esto mediante:

* Clasificar actividades potenciales en base a múltiples criterios para aumentar las posibilidades de éxito y alinearse con los objetivos comerciales.
* Investigar los resultados de experiencias de prueba anteriores para determinar el potencial de las pruebas de seguimiento.
* Revisión y uso compartido de la hoja de ruta de pruebas prioritaria con los interesados internos.

Por ejemplo, dar prioridad a una actividad fácil de implementar que pueda generar buenos resultados basados en actividades similares anteriores en comparación con una que pueda generar buenos resultados, pero que requiera un esfuerzo y recursos técnicos significativos o pueda ser impulsada por los interesados.

### Paso 3: Diseño

Diseñe y desarrolle un plan de actividad con información detallada y imágenes de experiencia aprobadas.

Haga esto mediante:

* Finalización de los criterios y métricas de entrada de actividad necesarios para determinar el rendimiento de la actividad.
* Finalización y aprobación de diseños finales para experiencias de actividad.
* Documentar los requisitos de la [!DNL Target] actividad, incluidos los criterios de entrada de prueba, las métricas de sistema de informes y los cambios de experiencia.

Utilice el Planificador de Actividad, que se proporciona más adelante en el kit de bienvenida, para realizar un documento de los detalles de la actividad, incluidas las métricas que utilizará para medir el rendimiento de la actividad, como los clics en un botón de llamada a acción, los inicios de vídeo o los ingresos generados. Asegúrese de incluir capturas de pantalla o imágenes de los diseños de experiencia que tiene previsto probar o personalizar.

### Paso 4: Generar y ejecutar

Cree y ejecute la actividad dentro de [!DNL Target], desarrolle cualquier código si es necesario, realice pruebas de control de calidad e inicie la actividad.

Haga esto mediante:

* Crear una actividad, aplicar cualquier audiencia, desarrollar cualquier código si es necesario y aplicar métricas a la actividad.
* Asegurar la firma de todas las partes interesadas necesarias.
* Inicio de la actividad y revisión de métricas a la hora, a las 24 horas y periódicamente durante la actividad.

Por ejemplo, si desea destinatario de nuevos visitantes con una oferta de caja de luz con un 10 % de descuento en el primer pedido, los creativos deberán desarrollar el diseño y la copia de caja de luz, obtener la firma de los interesados en el diseño, hacer que los desarrolladores escriban el código para el diseño, realizar un control de calidad en un entorno de ensayo y, a continuación, iniciar la actividad. A continuación, debe supervisar la actividad para asegurarse de que no causa ningún impacto negativo importante.

### Paso 5: Analizar

Analice el rendimiento de la actividad y resuma los resultados de la actividad, las perspectivas y las recomendaciones.

Haga esto mediante:

* Aprovechar la análisis de datos y las optimizaciones para comprender los resultados de la actividad.
* Analizar el rendimiento de la audiencia para encontrar segmentos de visitante valiosos.
* Documentar perspectivas, resultados y recomendaciones.

Por ejemplo, puede que descubra que los visitantes que regresan prefieren una experiencia diferente a los nuevos visitantes.

### Paso 6: Actúe e itere

Lleve a cabo experiencias ganadoras para obtener valor empresarial e iterar en perspectivas.

Haga esto mediante:

* Comunicación de perspectivas, resultados y recomendaciones de actividad a los interesados.
* Obtener la aprobación de los interesados para ejecutar las recomendaciones de actividad.
* Definición y ejecución del plan para implementar la experiencia ganadora.

Por ejemplo, si la actividad de la caja de luz ha logrado aumentar las compras de visitantes por primera vez, es posible que desee mantener en funcionamiento esta actividad. Asegúrese de comunicar el valor que la prueba llevó a los accionistas y ejecutivos usando la plantilla de resumen ejecutivo incluida en el kit de bienvenida. Y consideremos cómo podemos reaplicar este aprendizaje; tal vez puedas destinatario a esos compradores nuevos con una segunda oferta para obtener más valor de cada cliente.

## Capítulo 4: Sugerencias para el uso de Destinatario

En base a nuestro trabajo con muchos [!DNL Target] usuarios, hemos observado maneras de obtener más valor de su [!DNL Target] solución. Hemos resumido estas sugerencias en las muchas sugerencias que hemos incluido en este capítulo. Aunque quizá no estés listo para usar todas estas ideas de inmediato, sigue con esta lista. Cuanta más experiencia tenga con la solución y cuanto más madure su programa, más podrá ver cómo estos consejos le ayudarán a conseguir más con [!DNL Target].

### Sugerencia 1: Profundizar la personalización aumentando el perfil de visitante con datos adicionales.

Puede personalizar las experiencias con [!DNL Target] los datos de inmediato. Pero personalice más profundamente agregando sus propios datos a la combinación. Puede aumentar el perfil con datos históricos [!DNL Adobe Analytics] y datos en tiempo real [!DNL Adobe Audience Manager]. También puede utilizar Atributos del cliente, una función del servicio principal Personas de [!DNL Adobe Experience Cloud], para introducir fácilmente datos de CRM, datos de socios de terceros y datos adquiridos por terceros en [!DNL Target].

Por ejemplo, puede asociar los datos de compra del sistema del punto de venta con un perfil de visitante. Para ello, solo tiene que crear un archivo CSV con un máximo de 200 variables sin conexión y cargarlo directamente en [!DNL Adobe Experience Cloud] un archivo mediante la carga o utilizar FTP para alojar y programar la actualización del archivo con regularidad. Una vez que los atributos del cliente se encuentren en [!DNL Adobe Experience Cloud], puede asignarlos a [!DNL Experience Cloud] soluciones como [!DNL Adobe Analytics] y [!DNL Target] dónde estarán disponibles para análisis, pruebas y personalización.

Consulte Atributos [](https://docs.adobe.com/content/help/en/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) personalizados para obtener instrucciones paso a paso.

**Es bueno saber**: Dado que [!DNL Target] es una plataforma abierta y agnóstica que funciona bien con diferentes tecnologías, puede agregar CRM o datos adquiridos de muchas maneras diferentes. Esto significa que puede elegir un método que funcione mejor para su organización.

Consulte [Métodos para obtener datos en Destinatario](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obtener más información.

### Sugerencia 2: Personalice más profundamente mezclando audiencias de Destinatario con otras audiencias de Adobe Experience Cloud.

La combinación de audiencias que viven en diferentes [!DNL Adobe Experience Cloud] soluciones puede proporcionarle una comprensión mucho más amplia de sus clientes, así como la capacidad de personalizar más profundamente. Por ejemplo, aunque [!DNL Target] proporciona datos de audiencia en tiempo real, [!DNL Adobe Analytics] proporciona datos de audiencia históricos. La combinación de ambos puede ayudarle a identificar cuándo el comportamiento de un cliente es coherente y cuándo puede haber una oportunidad para actuar en un nuevo comportamiento. Simplemente haga clic en el menú desplegable situado junto a &quot;Todos los Visitantes&quot; al crear una actividad. A continuación, marque las casillas de hasta veinte audiencias, haga clic en &quot;Combinar varias Audiencias&quot; y en &quot;Guardar&quot;.

Consulte [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md) para obtener instrucciones paso a paso.

**Es bueno saber**: [!DNL Adobe Audience Manager] Las audiencias están disponibles en [!DNL Target] forma automática. Pero compartir [!DNL Adobe Analytics] audiencias requiere un poco de configuración manual. Simplemente marque la casilla rotulada &quot;Convertir esto en una audiencia Experience Cloud&quot; durante el proceso de creación de audiencias en [!DNL Analytics]. A continuación, en [!DNL Target], haga clic en &quot;Importar audiencias de Experience Cloud&quot;.

### Sugerencia 3: Exporte datos de Destinatario para utilizarlos con herramientas de terceros.

Con los tokens de respuesta, los administradores pueden extraer datos fácilmente de [!DNL Target] y en herramientas de terceros. Esto puede resultar útil cuando desee agregar los datos a los datos recopilados en una herramienta de encuesta. Por ejemplo, si una encuesta muestra una muestra de una población con una puntuación de &quot;9&quot; en una experiencia y otra con una puntuación de &quot;4&quot; en una experiencia, puede utilizar sus datos para ver quién vio la experiencia A y quién vio la experiencia B. También puede utilizar tokens de respuesta para exportar [!DNL Target] datos al almacén de datos interno. Haga clic en &quot;Administración&quot; y, a continuación, coloque el conmutador junto al testigo de respuesta deseado en la posición ON. A continuación, cree una actividad. Los datos están listos para transferirse al proveedor externo. Puede comprobar que [!DNL Target] está exportando los datos mediante las herramientas de depuración.

Consulte los tokens de [respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Sugerencia**&#x200B;útil: Antes de que un administrador pueda activar un token de respuesta asociado a un tercero, un desarrollador debe establecer una asociación con esa compañía de terceros.

Consulte los tokens de [respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Haga esto primero**: Asegúrese de que está utilizando la versión 1.1 o posterior de at.js. Si utiliza una versión anterior, verá los tokens de respuesta, pero at.js no podrá utilizarlos.

### Sugerencia 4: Cree audiencias a partir de estas variables clave para aumentar el valor de la actividad.

Al crear audiencias para objetivos o probar promociones y ofertas, considere primero estas variables:

* Comportamiento. Patrones de visitas al sitio y patrones de compra
* Referrer. Sitios y campañas de referencia
* Temporal. Horas del día, días de la semana y factores de temporada
* Sin conexión. Patrones de visitas y compras en tiendas físicas
* Entorno. País de origen, sistema operativo, tipo de explorador

### Sugerencia 5: Proporcione a los usuarios el nivel de acceso que necesitan para realizar su trabajo.

Facilite el trabajo con los datos de su organización y mantenerlos seguros. [!DNL Target Premium] permite a los administradores controlar el nivel de acceso dado a diferentes equipos internos y externos.

Consulte Permisos [de usuario de](/help/administrating-target/c-user-management/property-channel/property-channel.md) Enterprise para obtener más información.

**Sugerencia**&#x200B;útil: Al agregar usuarios, si el nombre de un miembro del equipo no se ha agregado previamente a su organización, como puede ser el caso de un empleado de una agencia de terceros, al introducir su dirección de correo electrónico y contraseña, se activará una invitación por correo electrónico para unirse al espacio de trabajo de un equipo.

¿Usar Target Standard? Todavía puede [asignar tres niveles de acceso](/help/administrating-target/c-user-management/c-user-management/user-management.md) para los usuarios con funciones de solo lectura, editor y aprobador.

### Sugerencia 6: Descubrir el rendimiento de una oferta a lo largo de un viaje del cliente probándola en cada página del viaje.

Ver el rendimiento de una oferta, como el envío gratuito, durante un viaje del cliente que tiene lugar en varias páginas del sitio web.

Consulte actividad [de](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) varias páginas para obtener instrucciones paso a paso.

**Sugerencia**&#x200B;útil: Si cambia la dirección URL después de especificar un intervalo de páginas, se restablecerá la experiencia. Esto significa que las variaciones especificadas ya no aparecerán. Si necesita cambiar la dirección URL, recuerde redefinir la experiencia.

### Sugerencia 7: Pruebe una oferta con diferentes audiencias para descubrir si las audiencias tienen preferencias diferentes.

Con las versiones de experiencia, puede ejecutar una prueba con variaciones para tantas audiencias como desee. Por ejemplo, puede crear una publicidad tipo titular que ofrezca envío gratuito (con imágenes y variaciones de moneda para los clientes de EE.UU., Reino Unido y EE.UU.) sin tener que ejecutar pruebas para tres audiencias diferentes.

Consulte para ver las audiencias de [varias experiencias en una prueba](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) A/B y las versiones de [experiencias en Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obtener instrucciones paso a paso.

### Sugerencia 8: Ahorre tiempo replicando experiencias de actividad en páginas similares.

Cree una variación en una página web, como un nuevo color de botón, y aplíquelo automáticamente a todas las páginas que compartan la misma plantilla. Puede especificar páginas o aplicar las variaciones a todas las páginas similares del sitio web.

Consulte [Incluir la misma experiencia en páginas](/help/c-experiences/c-visual-experience-composer/temtest.md) similares para obtener instrucciones paso a paso.

### Sugerencia 9: Reduzca el desorden en la biblioteca de Audiencias mediante la creación de audiencias únicas.

Si está dirigiendo un segmento que sabe que no volverá a tener destinatarios (por ejemplo, los clientes afectados por un evento meteorológico inesperado), la creación de una audiencia de un solo uso puede ayudarle a realizar el trabajo sin agregar más desorden a la biblioteca de Audiencias. Esto facilita la búsqueda de audiencias que se usan una y otra vez.

Consulte [Creación de una audiencia](/help/c-target/creating-activity-only-audience.md) de solo actividad para obtener instrucciones paso a paso.

**Capacidad** muy solicitada: Nuestros clientes nos pidieron que pudiéramos evitar que las audiencias de un solo uso se guardaran automáticamente en la Biblioteca de Audiencias. Ahora, ya no tienen que eliminar audiencias manualmente para mantener sus bibliotecas organizadas.

### Sugerencia 10: Ejecute pruebas simples más rápido, ya que no las coloca en el proceso de control de calidad estándar.

No hay nada peor que tener una actividad lista para ir y luego esperar semanas para que complete el proceso estándar de control de calidad. Puede realizar el control de calidad de la mayoría de las actividades simplemente pasando algunos vínculos de control de calidad a compañeros para probarlos en varios exploradores. Lo más probable es que quiera realizar más pruebas de control de calidad para los esfuerzos que cambian radicalmente la función del sitio, pero en realidad debería tener menos de esas actividades y muchas más de las actividades más básicas. Añadir mejores controles de derechos para que menos personas puedan impulsar las cosas en plena vida también añade límites significativos y le permite lograr lo que necesita sin sacrificar la velocidad y la eficiencia. Otra opción es contar con un recurso de TI designado para supervisar oportunamente el proceso de control de calidad.

Consulte Control de calidad de [Actividad](/help/c-activities/c-activity-qa/activity-qa.md) para obtener instrucciones paso a paso.

### Sugerencia 11: Ejecute pruebas en páginas de mucho tráfico para que alcancen más rápidamente la relevancia estadística.

Muchos especialistas en mercadotecnia inician programas de optimización para segmentación y segmentación de audiencias sin comprobar si los niveles de tráfico y las audiencias representadas proporcionarán resultados significativos dentro del intervalo de tiempo de prueba para sus objetivos de optimización y conversión. Para evitar este error común, responda a estas preguntas con antelación:

* ¿Cuántos visitantes únicos diarios tiene la página?
* ¿Cuál es la tasa de conversión de la página?
* ¿Cuánto tiempo espera que tenga que ejecutar la prueba antes de que pueda llamarla completa con confianza?

**Sugerencia**&#x200B;útil: Utilice la calculadora [de tamaño de la](https://docs.adobe.com/content/target-microsite/testcalculator.html) muestra de Destinatario para determinar el tamaño de la muestra necesario para una prueba correcta.

### Sugerencia 12: Diseñe pruebas más sencillas para asegurarse de que puede crearlas e implementarlas.

Después de considerar todos los aspectos de cómo diseñar una prueba, un plan puede resultar muy complejo. En función de dónde se encuentre su empresa con las pruebas y de la capacidad del grupo para diseñar, codificar, ejecutar y analizar los resultados, determine si la prueba parece demasiado ambiciosa. De ser así, estar preparados para reducir su alcance y complejidad. Es mejor realizar un inicio pequeño que no realizar la prueba en absoluto. No puede proporcionar un alza impactante si nunca inicia la prueba. Es importante equilibrar las aspiraciones del equipo con las realidades de sus recursos y capacidades.

### Sugerencia 13: Desglose pruebas complejas en actividades de prueba más pequeñas para hacerlas alcanzables.

En lugar de desarrollar una prueba grande con múltiples variables y desarrollo complejo, desarrolle una serie menos compleja de pruebas más pequeñas con variables mínimas. Esto permite una comprensión más profunda del rendimiento de las pruebas en función de variables específicas. También reduce los posibles problemas técnicos derivados del desarrollo de proyectos más grandes.

![Ilustración de pruebas complejas](/help/c-intro/assets/break-complex-tasks.png)

### Sugerencia 14: Maximice el impacto de la prueba probándola más cerca del final del canal de conversión.

Realizar pruebas tan cerca de la página en la que los visitantes hacen clic en Completar compra, Enviar solicitud o bien completar una conversión tiende a ofrecer los resultados más impactantes. Los visitantes que llegan al final del canal están más cualificados, han invertido más tiempo y están listos para comprar, por lo que probar las perspectivas sobre sus preferencias y acciones puede ayudarle a realizar cambios rentables. Dado que las páginas de la ruta de compra son críticas para las tasas de conversión, las pruebas que se realicen en esas páginas deben socializarse con los principales interesados antes de publicarlas.

![Ilustración del canal de conversión](/help/c-intro/assets/conversion-funnel.png)

### Sugerencia 15: Actualice constantemente las pruebas para realizar mejoras repetitivas.

Si su hipótesis no demostró ser cierta, piense en maneras de mejorar la prueba. Recuerde que, aunque ninguna de las experiencias probadas funcionara mejor, el experimento no era una pérdida de tiempo. Una prueba exitosa no siempre significa un aumento de ingresos o conversiones. Si la prueba realmente apoyó su hipótesis, entonces usted está en camino a desarrollar una teoría general. Pero incluso cuando tenga un claro resultado ganador, no se detenga ahí. Con demasiada frecuencia, los especialistas en mercadotecnia cometen el error de probar una vez y luego recurrir a esos resultados sin comprender realmente qué llevó al éxito. En cambio, planee repetir esos resultados para averiguar por qué el favorito estaba por delante. Esto le llevará a perspectivas más profundas que puede utilizar en campañas futuras.

### Sugerencia 16: Compare pruebas y actividades de personalización para obtener ideas a fin de mejorar la segmentación.

La comparación del rendimiento de conversión de diferentes audiencias dentro de diferentes pruebas en diferentes ubicaciones puede ayudar a enfocar y refinar la estrategia de optimización de una compañía. Utilice las comparaciones de prueba para identificar qué audiencias son más valiosas de probar, qué experiencias deben recibir experiencias objetivo y qué tipos de experiencias tienen más probabilidades de generar una respuesta.

Por ejemplo, un cliente de servicios financieros ejecutó una campaña promocional para una tarjeta de crédito que incluía incentivos profesionales de evento deportivo. Mediante pruebas multivariadas factoriales parciales de sus páginas de aterrizaje, el cliente pudo equilibrar de manera óptima los mensajes sobre los beneficios de las tarjetas de crédito con incentivos deportivos para el destinatario de audiencias distintas de su base de clientes. Este enfoque permitió a la compañía aprovechar al máximo la conversión durante una ventana en la que el tiempo depende de un evento deportivo importante.

### Sugerencia 17: Haga que las pruebas sean útiles solo al iniciarlas si sabe que puede actuar con los datos.

Una prueba no tiene sentido si no está claro cómo va a actuar con los datos. Esto incluye saber cuál es la métrica de éxito clave, qué debe suceder para impulsar al ganador, cómo seguirá los resultados de la prueba y qué hará con la información de audiencia. Para una prueba rápida y exitosa, es vital que todos los grupos involucrados en la prueba (desarrolladores, creativos, especialistas en pruebas y otros) conozcan su función antes del lanzamiento de la prueba.

### Sugerencia 18: Antes de lanzar una prueba, asegúrese de que la empresa admite la promoción del ganador.

Las organizaciones de optimización exitosas creen en el concepto de prueba y entienden que sus opiniones profesionales sobre qué experiencia ganará la prueba no siempre resultan verdaderas. Determinan el ganador en base a una sólida base de datos y están ansiosos y dispuestos a impulsar la experiencia ganadora en vivo después de que los resultados estén en curso, incluso aunque no esté en línea con sus expectativas o parezca contrario a la intuición.

Por ejemplo, un cliente de servicios de salud de Adobe demostró recientemente el valor de las pruebas mostrando cómo un titular héroe que el equipo había considerado que un fragmento de slam tenía un impacto negativo en la conversión. Si su organización aún no ha adoptado completamente las pruebas, es mejor realizar primero pruebas de ámbito más simples y más pequeñas para que los cambios de los resultados de las pruebas se puedan realizar de forma incremental.

### Sugerencia 19: Comunique a todos que ha lanzado una prueba para evitar preocuparse cuando el sitio cambie.

Una de las ventajas de configurar sus actividades para utilizar parámetros de control de calidad es que puede compartir esos vínculos con todos los integrantes de su equipo. Debe informar a más personas sobre la actividad y asegurarse de que no asumen que el sitio no funciona correctamente cuando se encuentra en una variante de prueba.

Una vez finalizadas las pruebas, la comunicación de los inicios de campaña, los resultados de las pruebas y, sobre todo, las lecciones aprendidas, le ayuda a crear conciencia de los resultados de las pruebas y a despertar interés en ellos. Compartir los resultados con todos los miembros de la organización también evita volver a probar una hipótesis, educa a todos sobre lo que funciona y los ayuda a desafiar fundamentalmente sus propias ideas sobre lo que funciona basándose en lo que se ha encontrado. Es aconsejable preparar una plantilla que se utilice cada vez para compartir sus conclusiones y las lecciones clave.
A continuación, considere la posibilidad de crear un libro que se pueda compartir o un paquete de Microsoft PowerPoint que capture de forma acumulativa estos conocimientos.

### Sugerencia 20: Aproveche la funcionalidad móvil para crear actividades móviles más innovadoras.

Las experiencias de los usuarios de tabletas y smartphones deben centrarse en los controles táctiles como la interacción principal del visitante en lugar de los clics del ratón y los controles del teclado. Aproveche los controles de visualización móviles, incluidos el barrido con los dedos, el tacto, el arrastre, la pellizco y el zoom. Utilice botones sencillos y grandes para designar las interacciones y la navegación, como un carro de compras grande o un botón de reproducción de vídeo. Si diseña para la venta al por menor móvil, incorpore una visualización de productos enriquecidos optimizada para el tipo de dispositivo. Siempre busque oportunidades para cambiar el enfoque de la experiencia del usuario a visores incrustados y grandes o zoom y recorrido interactivos a pantalla completa, giro de 360 grados y funcionalidad de vídeo mejorada.

### Sugerencia 21: Ayude a los visitantes móviles a encontrar lo que desean optimizando la búsqueda móvil.

Los usuarios móviles tienen una alta calidad. La mayoría de ellos utiliza la búsqueda antes de hacer cualquier otra cosa en los sitios de comercio electrónico, lo que hace que la optimización de la búsqueda de sitios móviles sea crucial. Para mejorar la optimización del motor de búsqueda (SEO) para dispositivos móviles, utilice indicaciones de navegación explícitas para facilitar la navegación. Además, implemente la sugerencia automática y la corrección automática en los cuadros de entrada de búsqueda para resolver la dificultad de escribir con dispositivos móviles. Proporcione resultados de búsqueda relevantes y convincentes optimizados para el tamaño y la ubicación de la pantalla.

### Sugerencia 22: Alcance mejor las audiencias móviles mediante la segmentación por hora del día para campañas SEM móviles.

Conozca cómo y cuándo llegar a su audiencia y cómo administrar mejor su gasto diario en publicidad &quot;partiendo el día&quot; de sus campañas móviles en diferentes segmentos a lo largo del día.

Muchos especialistas en marketing cometen el error de no asignar suficiente presupuesto para capturar esa parte de voz en las horas en que el uso de dispositivos particulares es más pesado, dejando así muchos ingresos y posibles clientes sobre la mesa.

Por ejemplo, el uso de tabletas suele aumentar en las horas de la noche y muchos usuarios navegan mientras ven la televisión. En cambio, los usuarios de smartphones suelen acceder al contenido sobre la marcha. Los tiempos de conversión pico también varían según la industria, por lo que es importante saber cuándo es más probable que actúen los clientes únicos.

### Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Inspiración para pruebas y actividades de personalización&quot;.

#### Cuando cree sus pruebas, no decore, sea intencional.

* Controle el flujo con las rutas oculares intencionales centradas en los puntos de conversión.
* Asegúrese de que utiliza sus bienes raíces en su beneficio.
* Aproveche el enfoque de imagen para asegurarse de que las imágenes no están decoradas, pero funcionan bien.
* Reduzca el desorden, la fricción y el desenfoque con Copia simplificada.
* Asegúrese de que tiene Llamadas a acción efectivas cuando necesite que el usuario actúe.
* Añada credibilidad a través de Contenido generado por el usuario siempre que sea posible.

#### Simplifique el sitio web.

* No &quot;haga&quot; leer a los clientes. No lo harán.
* Facilite el escaneo.
* Utilice bloques de texto con viñetas.
* Asegúrese de que su copia sigue un proceso de pensamiento claro y secuencial.

#### Utilizar llamadas a acción eficaces

* Pónganse en los zapatos del cliente.
* Utilice un lenguaje orientado a la acción.
* Considere la motivación para la conversión.
* Abordar el resultado de la conversión.
* ¡Asegúrate de que se vean los CTA!

## Capítulo 5: Inspiración para pruebas y actividades de personalización.

Estas ideas de prueba y personalización, inspiradas en actividades reales manejadas por nuestros clientes que han aumentado tasas de conversión e ingresos, valen la pena probar o usar como inspiración para sus propias [!DNL Target] actividades. Incluso si la idea no es exacta para su organización, con un poco de creatividad e intercambio de ideas, considere desarrollar una actividad basada en el espíritu de la idea de la prueba o personalización.

### Idea 1: Probar la personalización del viaje del cliente.

Aumente la tasa de conversión y los ingresos mediante la creación de un viaje creativo y una experiencia de marca personalizada que resuenen con los visitantes del sitio web al tiempo que cumple los objetivos comerciales. A continuación, pruebe ese viaje personalizado comparándolo con experiencias estáticas o experiencias entregadas al azar. Para profundizar en la personalización, descubra y cree las audiencias que personaliza para usar datos de segundo y de terceros en [!DNL Adobe Audience Manager].

Después de identificar esas audiencias, realice pruebas de experiencia de usuario e investigaciones de mercado para saber qué es lo que los convence de responder, y desarrolle las experiencias que usted les destinatario en su viaje en consecuencia.

Por ejemplo, cuando un visitante que entra en una audiencia de &quot;jugador serio&quot; para una compañía de telecomunicaciones visita el sitio web de la compañía, ofrezca una experiencia que incluya copias e imágenes que resuenan con jugadores y una oferta para Internet de alta velocidad.

### Idea 2: Destinatario los visitantes por primera vez y repita los clientes de forma diferente.

Los especialistas en mercadotecnia digital reconocen intuitivamente que los clientes existentes son más valiosos que los nuevos, pero con demasiada frecuencia no dan prioridad a los programas de mercadotecnia diseñados para mantener el retorno de los clientes. Para evitar este problema común, analice las métricas de clientes repetidas para determinar el comportamiento de los clientes leales en el sitio. Utilice estas perspectivas para crear campañas de objetivo para visitantes con una o dos compras, ofreciendo incentivos que los alienten a realizar visitas adicionales al sitio.

### Idea 3: Pruebe el diseño del sitio web.

Ejecute varias pruebas del diseño del sitio web para aumentar la conversión y la participación del usuario. En primer lugar, observe las acciones clave que los visitantes están tratando de realizar y probar cosas como la ubicación diferente de Llamadas a acción (CTA) y los diferentes colores de los botones de llamada a acción que podrían facilitarles la finalización de dichas acciones.

Considere la posibilidad de simplificar el diseño eliminando ciertos elementos completamente del sitio web. Por ejemplo: pruebe a eliminar la lista tradicional de categoría de productos a la izquierda o a la derecha en la página principal (y en otras páginas) y permita que los clientes confíen en la búsqueda para encontrar productos. Si ese cambio no tiene un impacto medible en las conversiones, elimine la navegación y libere espacio para los elementos de diseño que puedan generar una participación y conversiones aún mayores.

### Idea 4: Mejore la conversión de la búsqueda con contenido de objetivo.

Los clientes potenciales que buscan en el sitio proporcionan parte del tráfico del sitio más calificado. Cuanto más enfocado y relevante sea el contenido en la página de resultados de búsqueda, más probabilidad habrá de convertir los clientes potenciales.

Considere proporcionar información contextual adicional directamente en las miniaturas de búsqueda. Al utilizar ráfagas de pegatinas de objetivo, como descuentos, disponibilidad de inventario, tamaños o colores, puede ayudar a los consumidores a encontrar rápidamente la información que necesitan para tomar decisiones de compra y actuar.

### Idea 5: Reduzca el número de toques necesarios para la conversión.

Comprender los objetivos comerciales y los KPI que intenta alcanzar con sus esfuerzos móviles. A continuación, diseñe la experiencia móvil para oferta a los clientes en el camino de menor resistencia para lograr esos objetivos. La conversión debe producirse en tres tramos, pero el objetivo es reducirla a dos tramos si es posible.

### Idea 6: No conduzcan a visitantes a un callejón sin salida.

Si los visitantes a los que Google hace referencia se envían a contenido que ha caducado o que no está en existencias, vuelva a contratarlos mediante recomendaciones para darles otra oportunidad de realizar una compra.

Por ejemplo: incluya recomendaciones en una página de detalles del producto para mostrar a los visitantes que vieron un producto fuera de existencias recomendaciones similares y personalizadas o artículos vistos recientemente en función de su comportamiento de visitante durante la sesión y su afinidad de categoría. Los usuarios pueden realizar la vista con un solo clic, lo que le ofrece otra oportunidad de participar en su sitio web o de realizar una compra.

![Ilustración de Recommendations](/help/c-intro/assets/recs-illustration.png)

### Idea 7: Incorporar tácticas económicas de comportamiento en las pruebas.

Piense en la paradoja que puede elegir al ejecutar pruebas A/B y ejecutar algunas experiencias con diferentes números de opciones. Por ejemplo, reduzca el número de opciones de suscripción y vea si esto aumenta las suscripciones generales.

Tal vez sólo cambie el orden de las opciones para elegir cuándo los clientes desean actuar. Por ejemplo, si tiene diferentes modelos de precios enumerados uno junto al otro, lista las opciones de precios de los productos de las tasas de valor más bajas a un valor más alto o viceversa, y mida el efecto de cada opción.

![Ejemplo de tácticas conductuales](/help/c-intro/assets/behavioral.png)

### Idea 8: Promocione su aplicación móvil en su sitio web.

Si su compañía está gastando recursos para desarrollar una aplicación móvil para iOS, Android u otros dispositivos, no se limite a quedarse atrás y esperar que los usuarios se toparán con su aplicación en la tienda de aplicaciones. En lugar de ello, tenga una estrategia sólida para promoverla. Pruebe diferentes enfoques para dirigir el uso y las descargas de aplicaciones. Si el sitio que no es móvil tiene un vínculo para descargar la aplicación, pruebe la eficacia de una página de aterrizaje intersticial que promocione explícitamente la aplicación cuando lleguen visitantes a la página de inicio. Configure una prueba de redireccionamiento que filtros la mitad del tráfico móvil a la página del sitio actual y la otra mitad a la página de aterrizaje intersticial.

### Idea 9: utilice las innovaciones de aplicaciones móviles.

Explore aspectos del smartphone más allá de la geolocalización, como el acelerómetro o el giróscopo. Por ejemplo, pruebe una experiencia que utilice el acelerómetro para agregar un elemento mostrado a un carro de compras agitando el teléfono. Incluso pruébelo a usuarios de diferentes marcas de dispositivos, como iOS o Android, para ver si su respuesta es diferente. Estas pruebas le permiten descubrir el nuevo comportamiento de visitante que se debe considerar utilizar en pruebas futuras.

### Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Peligros fáciles de evitar&quot;.

#### Prácticas recomendadas sobre la duración de la prueba

* Duración mínima de actividad: Ejecute una actividad de prueba durante al menos 14 días.
* Nivel mínimo de confianza de resultados: Ejecute una actividad de prueba hasta que los resultados alcancen una confianza mínima del 90 %.
* Conversión mínima por experiencia: Ejecute una actividad de prueba hasta que haya al menos 500 conversiones por experiencia.
* Coherencia en los resultados: Confirme que los resultados sean coherentes y estables visualizándolos en la vista de gráficos en [!DNL Target].

## Capítulo 6: Peligros fáciles de evitar

Lo bueno de comenzar su programa de optimización y personalización ahora es que las personas que lo han estado haciendo durante un tiempo ya han descubierto muchos de los errores que son fáciles de cometer. Al conocer estos escollos, puede evitarlos fácilmente o remediarlos.

Consulte [Diez escollos comunes de prueba A/B y cómo evitarlos](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md) para obtener información detallada. Además de las ideas presentadas en ese artículo, mantenga esta breve lista a mano para evitar o corregir estos escollos comunes de prueba y personalización.

| Escollo | Solución |
| --- | --- |
| No tener tráfico suficiente para alcanzar resultados estadísticamente significativos. | Utilice la calculadora [de tamaño de](https://docs.adobe.com/content/target-microsite/testcalculator.html) muestra de Adobe Target con antelación para comprender cuánto tiempo debe ejecutarse la prueba y, a continuación, ejecute la prueba hasta su finalización. |
| Realizar un cambio que sea demasiado pequeño o inapreciable. | Haga que el cambio sea lo suficientemente sustancial como para que pueda ser visible cuando esté a unos metros de la pantalla. |
| No poder alinear las actividades con los objetivos comerciales. | Aumentar la atención prestada a la metodología de establecimiento de prioridades y comunicar esa metodología a los interesados internos. |
| Tener poco o ningún trabajo de prueba pendiente. | Participe con los interesados internos y permita que envíen pruebas que estén alineadas con los objetivos clave del negocio. |
| Ampliación de los lanzamientos de actividad anteriores a los plazos | Mejore la documentación de las actividades e incluya detalles específicos sobre la configuración de la prueba. |
| Seleccionar datos de métricas de éxito de actividad que no ayudan a tomar decisiones. | Documento todas las métricas de prueba principales e incluya métricas adicionales para obtener perspectivas adicionales. |
| Realizar cambios durante la prueba que puedan afectar a los resultados. | Mantener un calendario de las próximas promociones y cambios en el sitio. Comunicar claramente los lanzamientos [!DNL Target] de actividad para evitar conflictos. |
| Cambiar experiencias de prueba o criterios cerca del inicio de una actividad. | Solicite la firma de los principales interesados al inicio del proceso de actividad de pruebas. |
| Concluir una actividad antes de los resultados es estadísticamente significativo. | Compruebe la duración de la prueba con la calculadora [de tamaño de la](https://docs.adobe.com/content/target-microsite/testcalculator.html)muestra de Adobe. |
| Recibir resultados negativos o planos de una [!DNL Target] actividad. | Confirme que vale la pena probar la actividad. |
| No es difícil codificar la experiencia ganadora. | Utilice los datos de actividad para mostrar el valor y obtener la compra para la codificación rígida. |
| No compartir los resultados más allá del equipo de prueba. | Amplíe las comunicaciones para incluir almuerzos y aprendizajes, desarrolle un panel de programa y programe reuniones de los interesados. |

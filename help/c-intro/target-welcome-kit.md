---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de bienvenida de Adobe Target.
title: Kit de bienvenida de Adobe Target
feature: intro
translation-type: tm+mt
source-git-commit: d3c8c328e122eaf7bf1829fc46f55ef23ad187e6
workflow-type: tm+mt
source-wordcount: '2846'
ht-degree: 15%

---


# Kit de bienvenida de Adobe Target

Bienvenido a Adobe Target. Este kit de bienvenida de Adobe Target presenta

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

---
keywords: kit de bienvenida;kit de bienvenida de target;intro;introducción;introducción a
description: Eche un vistazo general a Adobe Target. Obtenga información sobre actividades, canales, implementación, integraciones, etc. que haya disponibles.
title: ¿Dónde puedo encontrar una introducción general de Target?
feature: Información general
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2520'
ht-degree: 99%

---

# Capítulo 2: Adobe [!DNL Target] de un vistazo

Antes de comenzar a usar [!DNL Adobe Target], puede ser útil obtener un panorama general de la solución. En este capítulo, conozca las funcionalidades clave de la solución, los puntos de contacto de marca en los que puede utilizarla, las opciones de implementación, las funciones y flujos de trabajo importantes de la interfaz de usuario, las funciones de control y su función en [!DNL Adobe Experience Cloud] global. A menos que se indiquen como características de [!DNL Adobe Target Premium], los elementos descritos en este capítulo están disponibles tanto con [!DNL Adobe Target Premium] como con [!DNL Adobe Target Standard]. Para obtener más información, consulte [Introducción a Target](/help/c-intro/intro.md).

## Capacidades y actividades

Las pruebas y la personalización son los dos grandes tipos de capacidades que [!DNL Target] ofrece y que puede utilizar al crear una actividad en [!DNL Target]. Es posible que vea el término &#39;prueba&#39; usado indistintamente con &#39;optimización&#39; y el término &#39;personalización&#39; usado indistintamente con &#39;segmentación&#39;.

En una actividad de prueba, se compara una variación de una experiencia digital con una o más variaciones para descubrir cuál de ellas hace que la mayoría de los visitantes realicen la acción deseada. [!DNL Target] ofrece las siguientes capacidades de prueba: pruebas A/B, pruebas multivariable (MVT) y asignación automática.

Con una actividad de personalización, puede ofrecer una experiencia digital adaptada a un grupo específico de visitantes o a cada visitante individual. [!DNL Target] ofrece estas funciones de personalización: Experience Targeting, Segmentación automática, Automated Personalization y Recommendations.

Para obtener más información sobre cuándo y cómo utilizar cada capacidad, consulte [Tipos de actividades de Target](/help/c-activities/target-activities-guide.md).

| Tipo de actividad | Detalles |
| --- | --- |
| Prueba A/B | Compare dos o más variaciones de sus experiencias u ofertas en su sitio web u otro punto de contacto de cliente digital para ver qué variación mejora más las medidas comerciales clave durante un período de prueba previamente especificado. Las pruebas A/B son ideales para cambios de gran tamaño, como nuevos diseños de página web, distintos enfoques de la navegación en el sitio o el tratamiento totalmente diferente de los elementos individuales de una experiencia digital como copiar, imágenes y botones de llamada a la acción. [Más información](/help/c-activities/t-test-ab/test-ab.md). |
| Asignación automática | Identifique la mejor experiencia entre dos o más experiencias y reasigne automáticamente más tráfico a la opción ganadora para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. Utiliza la inteligencia artificial con tecnología [!DNL Adobe Sensei]. [Más información](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Segmentación automática<br>(Premium) | Aproveche Adobe Sensei AI en [!DNL Target] para determinar y ofrecer a cada visitante la mejor experiencia de varios visitantes en función de su perfil de cliente y del comportamiento de visitantes anteriores con perfiles similares. La segmentación automática permite la personalización a escala. [Más información](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Utilice algoritmos avanzados de aprendizaje automático y automatización con tecnología [!DNL Adobe Sensei] para revisar las diferentes combinaciones de imágenes, copias y otros elementos de una oferta y ofrecer la mejor combinación a cada visitante en función de cuál logra mejor los objetivos comerciales, como más conversiones o ingresos por visitante. [Más información](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Segmentación de experiencias (XT) | Ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por el usuario. **[!UICONTROL Experience Targeting]** es útil para dirigir una experiencia o contenido específicos a una audiencia concreta cuando se comprende que una audiencia es valiosa y se tiene una percepción correcta de cuál es la experiencia que más impacto tiene en ella. [Más información](/help/c-activities/t-experience-target/experience-target.md). |
| Multivariate Testing (MVT) | Compare todas las combinaciones posibles de variaciones de elementos en su página o experiencia digital; por ejemplo, tres imágenes de fondo diferentes, dos variaciones de copia y dos colores de botón diferentes. MVT determina qué combinación ofrece el mejor rendimiento para una audiencia específica y qué elementos tienen el mayor impacto en los resultados. [Más información](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Utilice Adobe Sensei AI para sugerir automáticamente productos o contenido que podrían interesar a sus clientes en función de su actividad anterior y la de otros clientes. [Más información](/help/c-recommendations/recommendations.md). |

## Canales

Puede utilizar [!DNL Target] para probar y personalizar experiencias digitales en casi cualquier lugar: puntos de contacto digitales tradicionales como su sitio web, sitio móvil y aplicación móvil, pero también en puntos de contacto como quioscos, correo electrónico, dispositivos IoT, consolas de juegos e incluso asistentes de voz como Alexa y Cortana. Muchas empresas empiezan a utilizar [!DNL Target] en su sitio web. Sin embargo, investigaciones recientes indican que cada vez más personas visitan las marcas desde sus dispositivos móviles. Ahora es esencial optimizar los canales móviles. Lo ideal es que conecte las experiencias del visitante en todos sus puntos de contacto para ofrecer una experiencia fluida y coherente.

| Canal | Detalles |
| --- | --- |
| Sitio web | [!DNL Target] se puede usar para ejecutar actividades de Pruebas A/B, Multivariate Testing, Segmentación de experiencias, Asignación automática, Segmentación automática, Automated Personalization y Recommendations en páginas de sitios web móviles, aplicaciones de una sola página (SPA) y de varias páginas para mejorar la participación de visitantes y clientes, aumentar las conversiones y aumentar los ingresos. |
| Web móvil | [!DNL Target] se puede usar para ejecutar los mismos tipos de actividades que se ejecutan en el sitio web en las páginas del sitio web móvil para mejorar de forma similar la participación de los visitantes y los clientes, aumentar las conversiones y aumentar los ingresos. |
| Aplicación móvil | [!DNL Target] se puede usar para probar y personalizar la experiencia de aplicaciones móviles en función del comportamiento del usuario y el contexto móvil. [!DNL Target] le permite ofrecer interacciones que atraigan y fomenten la conversión a través de pruebas iterativas, así como personalización basada en Experience Targeting y potenciada por IA. Para utilizar [!DNL Target] en la aplicación móvil, debe utilizar el SDK de Adobe Mobile Services. |
| IoT/En todas partes | [!DNL Target] ofrece una implementación del lado del servidor para que pueda utilizar las mismas capacidades de prueba y personalización en las actividades que utiliza en su sitio web, sitio móvil y aplicaciones móviles tradicionales en correos electrónicos y puntos de contacto que no tengan explorador o que no utilicen código JavaScript. Por ejemplo, para que pueda probar y personalizar quioscos, descodificadores, consolas de juegos, asistentes de voz y otros puntos de contacto no tradicionales. |

## Implementaciones

Es posible que muchos usuarios deseen utilizar [!DNL Target] para probar y personalizar sus numerosos puntos de contacto digitales, incluidos los puntos de contacto web y móviles tradicionales, pero también los puntos de contacto que carecen de explorador o no utilizan código JavaScript. En algunos casos, las directivas internas o externas requieren que tenga niveles adicionales de control y seguridad. También puede tener procesos que necesitan ejecutarse en un servidor back-end por motivos de rendimiento. Para satisfacer esta amplia variedad de usos, le ofrecemos la capacidad de implementar [!DNL Target] de diferentes maneras: del lado del cliente, del lado del servidor o una combinación de ambos.

| Tipo de implementación | Detalles |
| --- | --- |
| Lado del cliente | Con esta implementación de [!DNL Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. En el lado del cliente, puede utilizar un editor WYSIWYG, **[!UICONTROL Visual Experience Composer]** (VEC) o una interfaz no visual, **[!UICONTROL Compositor de experiencas basado en la forma]** para crear experiencias de prueba y personalización. [Más información](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Lado del servidor | En este tipo de implementación de [!DNL Target], un dispositivo cliente realiza una solicitud de una experiencia a través del servidor, el servidor envía esa solicitud a [!DNL Target], [!DNL Target] devuelve la respuesta al servidor y este toma la decisión sobre la experiencia que debe ofrecerse al dispositivo cliente para que se procese. La experiencia no necesita mostrarse en un explorador; puede mostrarse en un correo electrónico o quiosco, a través de un asistente de voz o a través de otro dispositivo no visual o no basado en un explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor. [Más información](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implementación híbrida | En esta implementación, elige el método de implementación que mejor se adapte a un caso de uso determinado. Por ejemplo, puede utilizar una implementación del lado del cliente para probar una oferta en un banner a pantalla completa en la página de inicio, pero también utilizar una implementación del lado del servidor para determinar los resultados de búsqueda interna que se mostrarán en el explorador del cliente, la experiencia que se mostrará en el salpicadero de un coche inteligente o la respuesta de voz que ofrezca un asistente de voz. |

## Elementos de actividad

En [!DNL Target], puede crear una actividad de personalización, una actividad de optimización o una actividad que optimice su enfoque de personalización. Cada actividad tiene elementos clave: las experiencias u ofertas que está probando o personalizando, las audiencias o personas a las que está entregando una experiencia, las métricas mediante las cuales mide el impacto de la actividad y los informes que muestran visualmente ese impacto.

| Tipo de elemento | Detalles |
| --- | --- |
| Experiencias | Oferta, imagen, texto, botón, vídeo, una combinación de estos elementos en una página, una página web completa o un conjunto de páginas que quizás forman un canal de compras o cualquier otra secuencia lógica de páginas. También puede ser la respuesta de un ayudante de voz, un script de servicio al cliente o incluso un sabor personalizado de una máquina de bebidas. Las experiencias se prueban o personalizan en actividades de [!DNL Target]. [Más información](/help/c-experiences/experiences.md). |
| Ofertas | Bloque de contenido que puede contener imágenes, texto, HTML, vínculos, vídeo, un botón de llamada a la acción, una respuesta del asistente de voz o cualquier otro tipo de contenido. Una oferta puede serlo por aplicar un descuento, envío gratuito, etc. Las ofertas se pueden mostrar en una página web, pero también se pueden experimentar en cualquier punto de contacto del cliente, como un asistente de voz o una consola de juegos. Al probar una oferta, se mide su éxito en comparación con otras ofertas o con la ausencia de otras ofertas. [Más información](/help/c-experiences/c-manage-content/manage-content.md). |
| Audiencias | Un grupo de personas con las mismas características, como un visitante nuevo, un visitante habitual o un visitante habitual de la zona oeste. La funcionalidad Audiencia le permite segmentar contenido y experiencias diferentes para optimizar el marketing web mostrando los mensajes adecuados para la persona adecuada y en el momento adecuado. Si un visitante se identifica como parte de una audiencia objetivo, [!DNL Target] determina qué experiencia se mostrará según los criterios definidos durante la creación de la actividad. [Más información](/help/c-target/target.md). |
| Métricas de éxito | Métricas clave de empresa que permiten determinar el éxito de una experiencia u oferta determinadas en una actividad de [!DNL Target]. Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente. [Más información](/help/c-activities/r-success-metrics/success-metrics.md). |
| Informes | Información sobre el progreso y los resultados de las actividades que le ayudan a tomar decisiones basadas en sus datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una prueba, mostrar qué experiencia de oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes. [Más información](/help/c-reports/reports.md). |

## Herramientas de creación de actividades

[!DNL Target] le proporciona tres formas principales de configurar sus actividades de prueba y personalización: [!UICONTROL Visual Experience Composer] (VEC), el [!UICONTROL Compositor de experiencias basado en la forma] y [!UICONTROL Aplicaciones de una sola página (SPA) de Visual Experience Composer]. Ambas le guían a través del proceso de configuración de la actividad en tres pasos: definir las experiencias, seleccionar o definir las audiencias y seleccionar las métricas de éxito principales y secundarias mediante las cuales se medirán los resultados de su actividad.

| Herramienta | Detalles |
| --- | --- |
| [!UICONTROL Compositor de experiencias visuales] (VEC) | Interfaz de usuario WYSIWYG que le permite crear y probar fácilmente experiencias y ofertas personalizadas en el contexto del sitio. Puede crear experiencias y ofertas para actividades de [!DNL Target] arrastrando y soltando, intercambiando y modificando el diseño y el contenido de una página web (u oferta) o de una página web móvil. [Más información](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Compositor de experiencias basadas en formularios] | Una interfaz no visual de creación de ofertas y experiencias que resulta útil para crear experiencias para utilizarlas en pruebas A/B, Segmentación de experiencias, Automated Personalization y actividades de Recommendations cuando Visual Experience Compositor no está disponible o su uso no es práctico. Por ejemplo, puede utilizar el Compositor basado en formularios para crear experiencias y ofertas para su envío en correos electrónicos, kioscos y asistentes de voz. [Más información](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Aplicaciones de una sola página (SPA) de Visual Experience Composer] | El VEC para aplicaciones de una sola página (SPA) permite que los comerciantes creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que depender de un desarrollo continuo. El VEC se puede utilizar para crear pruebas A/B y actividades de segmentación de experiencias (XT) en marcos populares, como React y Angular. [Más información](/help/c-experiences/spa-visual-experience-composer.md). |

## Gobernanza y control

Para proporcionar a las personas adecuadas las funciones adecuadas y los niveles de acceso y permisos asociados a [!DNL Target], tenemos una consola administrativa. Para los usuarios de [!UICONTROL Target Premium], ofrecemos una gestión y un control más detallados
con [!UICONTROL Permisos de empresa].

| Herramienta | Detalles |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Agregue usuarios a Adobe Target y asigne permisos de Adobe Admin Console. [Más información](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Permisos de empresa]<br>(Premium) | Un medio de administración formal de usuarios en todo el sitio para [!DNL Target]. Agregue usuarios a [!DNL Target], asigne permisos según sus funciones y cree espacios de trabajo para equipos en función de diferentes departamentos, ubicaciones globales, canales y otras agrupaciones lógicas. Puede asignar a los usuarios las funciones de Observador, Editor, Publicador o Aprobador. [Más información](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Integraciones

[!DNL Target] se puede integrar con muchos sistemas de primeras, segundas y terceras partes. Estas
integraciones pueden ser útiles para otorgarle acceso a los datos de visitantes y clientes disponibles en esos sistemas para utilizarlos en la creación de audiencias para pruebas y personalizaciones. Como parte de [!DNL Adobe Experience Cloud], [!DNL Target] se integra estrechamente con las soluciones de [!DNL Experience Cloud] y sus servicios principales.

| Integración | Detalles |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] tiene funciones integradas con otras soluciones de [!DNL Adobe Experience Cloud] para personalizar experiencias a escala. Aproveche la potencia de [!DNL Target] junto con [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Audiencias de Experience Cloud](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) y [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| API de Target (Premium) | [!UICONTROL Target] ofrece más de 40 API que puede utilizar para integrar Adobe Target con sistemas de primeras, segundas y terceras partes. [Más información](/help/api/api-overview.md). |

## Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: Desarrollo de sus ideas de pruebas y personalización.

### Prácticas recomendadas para optimización

* **Buena estrategia**: ¿Cuál es nuestro objetivo y nuestra hipótesis? ¿Van en la misma dirección? Por ejemplo, queremos aumentar los envíos de solicitudes de préstamos, por lo que suponemos que si se reduce el número de campos en el formulario de solicitud, se logrará ese aumento.
* **Metodología disciplinada** ¿Estamos empezando a probar en los lugares correctos? Por ejemplo, necesita ubicaciones que tengan tráfico suficiente y que afecten a las métricas que importan    al negocio.
* **Configuración adecuada** ¿Está configurada nuestra actividad para alcanzar nuestro objetivo? Por ejemplo, si estamos tratando de aumentar los envíos de solicitudes de préstamos, deberíamos dirigirnos a las personas interesadas en los préstamos y medir los clics del botón Enviar.
* **Análisis detallado**: ¿Se ha completado la actividad de prueba? ¿Qué dicen los resultados? Ejecute su actividad hasta que alcance entre el 95 % y el 99 % de confianza estadística. Documente por qué cree que ganó la experiencia ganadora y aplique el aprendizaje en todo lo demás.
* **Pruebas iterativas**: ¿Estamos aprovechando los conocimientos de actividades anteriores? Si encuentra una táctica ganadora, intente mejorarla o realice cambios que funcionen con ella para mejorar aún más la métrica de éxito.

### Las opiniones pueden afectar negativamente a los resultados

* Opiniones que pueden afectar negativamente a su efectividad. Opinión de la persona mejor pagada (HIPPO), actitudes, prejuicios. Por ejemplo, el director ejecutivo desea reducir el tamaño del cuadro de búsqueda para dejar más espacio en cada página. Deberíamos probarlo para asegurarnos de que no reduce el número de búsquedas.
* ¿Está actuando en función de las opiniones? No me gusta el aspecto que tiene la prueba. Al cliente no le gustará nada esta experiencia. Aunque la intuición es útil, las pruebas A/B han demostrado una y otra vez que no siempre se acierta.
* ¿O tiene mentalidad de optimización? Tengo muchas ganas de comprobar qué experiencia gana. ¿Tenemos suficientes opciones para probar?

### Las suposiciones también pueden afectar negativamente a los resultados.

* Suposiciones que pueden afectar negativamente a su eficacia. Mentalidad de rebaño (así es como lo hace la competencia). Por ejemplo, todos nuestros competidores utilizan banners de pantalla completa con imágenes rotativas, por lo que nosotros también deberíamos hacerlo.
* Suponiendo que sepamos por qué algo funciona o no funciona. Suponiendo que no necesitamos probar las cosas. Por ejemplo, las habitaciones de hotel siempre aparecen en orden de precio de mayor a menor de manera predeterminada.
* ¿Está actuando en función de las suposiciones? No es necesario probarlo, pues hemos comprobado los análisis. (Sí, pero puede haber más variables de lo que revela el análisis).
* ¿O tiene mentalidad de optimización? Lo probamos todo.

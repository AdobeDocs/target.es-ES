---
keywords: diagrama del sistema;parpadeo;at.js;implementación;biblioteca javascript;js;atjs
description: Aprenda cómo funciona la biblioteca JavaScript  [!DNL Target]  at.js, incluidos diagramas del sistema para ayudarle a comprender el flujo de trabajo a medida que se cargan las páginas.
title: ¿Cómo funciona la biblioteca Javascript at.js?
feature: at.js
role: Developer
exl-id: 2193c02a-2a85-4ae1-bfbd-40fa7b87f0a0
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 91%

---

# Cómo funciona at.js

Para implementar [!DNL Adobe Target] del lado del cliente, debe utilizar la biblioteca JavaScript at.js.

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), para crear experiencias de prueba y personalización.

## ¿Qué es at.js?

La biblioteca at.js es la nueva biblioteca de implementación para Target. La biblioteca at.js mejora los tiempos de carga de página en implementaciones web y proporciona mejores opciones de implementación en aplicaciones de una sola página. at.js es la biblioteca de implementación recomendada y se actualiza con frecuencia con nuevas capacidades. Recomendamos que todos los clientes implementen o migren a   [última versión de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

Para obtener más información, consulte [Bibliotecas de JavaScript de Target](/help/main/c-intro/how-target-works.md#libraries).

En la implementación de [!DNL Target] que puede ver a continuación, se han implementado las siguientes soluciones de [!DNL Adobe Experience Cloud]: Analytics, Target y Audience Manager. Además, se implementan los siguientes servicios principales de Experience Cloud: [!DNL Adobe Experience Platform], [!DNL Audiences] y [!DNL Visitor ID Service].

## ¿Cuál es la diferencia entre los diagramas de flujo de trabajo de at.js 1.*x* y at.js 2.x?

Consulte [Actualización de at.js 1.x a at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} para obtener más información sobre las diferencias introducidas en 2.O desde 1.*x*.

En términos generales, existen un par de diferencias entre las dos versiones:

* at.js 2 no tiene un concepto de solicitud de mbox global sino una solicitud de carga de página. La solicitud de carga de página se puede ver como una solicitud para recuperar contenido que debería aplicarse en la carga inicial de página del sitio web.
* at.js 2.x administra los conceptos de vistas, que se utilizan para las aplicaciones de una sola página (SPA). at.js 1.*x* no tiene en cuenta este concepto.

## Diagramas de at.js 2.x

Los siguientes diagramas le ayudan a comprender el flujo de trabajo de at.js 2.x con Vistas y cómo esto mejora la integración de SPA. Para obtener una mejor introducción a los conceptos utilizados en at.js 2.x, consulte [Implementación de aplicación de página única](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}.

![Flujo de Target con at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Paso | Detalles |
| --- | --- |
| 1 | La llamada devuelve el [!DNL Experience Cloud ID] si el usuario se autentica, y otra llamada sincroniza el ID del cliente. |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>at.js también se puede cargar de manera asíncrona con una opción de fragmento de ocultamiento previo implementado en la página. |
| 3 | Se solicita una carga de página que incluye todos los parámetros configurados (MCID, SDID y el ID del cliente). |
| 4 | Se ejecutan los scripts de perfiles y se incluyen en el Almacenamiento de perfiles. El Almacenamiento solicita audiencias de la Biblioteca de audiencias que cumplan los requisitos (por ejemplo, audiencias compartidas de Adobe Analytics, Gestión de público, etc.).<br>Se envían los atributos del cliente al Almacenamiento de perfiles en un procesamiento de lotes. |
| 5 | Según los parámetros de la solicitud de la URL y los datos de perfil, [!DNL Target] decide qué actividades y experiencias vuelven al visitante para la página actual y las vistas futuras. |
| 6 | El contenido dirigido se devuelve a la página, incluyendo, de manera opcional, los valores de perfil para una personalización adicional.<br>El contenido dirigido se muestra en la página actual lo más rápido posible y sin parpadeo del contenido predeterminado.<br>Contenido dirigido para vistas que se muestran como resultado de acciones del usuario en una SPA almacenada en caché en el explorador, de modo que se pueda aplicar instantáneamente sin una llamada al servidor adicional cuando se activan las vistas `triggerView()`. |
| 7 | Se envían los datos de Analytics a los servidores de recopilación de datos. |
| 8 | Se comparan los datos de Target con los datos de Analytics mediante el SDID y se procesan en el almacén de informes de Analytics.<br>Por lo tanto, los datos de Analytics se pueden visualizar tanto en Analytics como en Target mediante los informes de Analytics for Target (A4T). |

Ahora, independientemente de que se implemente `triggerView()` en la SPA, las vistas y acciones se recuperan de la caché y se muestran al usuario sin una llamada al servidor. `triggerView()` también realiza una solicitud de notificaciones al back-end [!DNL Target] para aumentar y registrar los recuentos de impresión. Para obtener más información sobre at.js para SPA con vistas, consulte [Implementación de aplicación de página única](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}.

![Flujo de Target at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Paso | Detalles |
| --- | --- |
| 1 | En la SPA, se llama a `triggerView()` para procesar la vista y aplicar acciones para modificar los elementos visuales. |
| 2 | El contenido dirigido para la vista se lee desde la caché. |
| 3 | El contenido dirigido se muestra lo más rápido posible y sin parpadeo del contenido predeterminado. |
| 4 | La solicitud de notificación se envía al Almacenamiento de perfiles de [!DNL Target] para contar al visitante en la actividad e incrementar las métricas. |
| 5 | Los datos de Analytics se envían a los servidores de recopilación de datos. |
| 6 | Se comparan los datos de Target con los datos de Analytics mediante el SDID y se procesan en el almacén de informes de Analytics. Por lo tanto, los datos de Analytics se pueden visualizar tanto en Analytics como en Target mediante los informes de A4T. |

### Vídeo: Diagrama arquitectónico de at.js 2.x

at.js 2.x mejora la compatibilidad de Adobe Target con las SPA e integra otras soluciones de Experience Cloud. Este vídeo explica cómo se vincula todo.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Consulte [Descripción del funcionamiento de at.js 2.x](https://experienceleague.adobe.com/docs/target-learn/tutorials/implementation/understanding-how-atjs-20-works.html?lang=es) para obtener más información.

## Diagrama de at.js 1.x

![Flujo de Target - at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| Paso   | Descripción | La llamada | Descripción |
|--- |--- |--- |--- |
| 1 | La llamada devuelve el [!DNL Experience Cloud ID] (MCID) si el usuario se autentica; otra llamada sincroniza el ID del cliente. | 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento. |
| 3 | Se realiza una solicitud de mbox global que incluye todos los parámetros, MCID, SDID e ID de cliente (opcional) configurados. | 4 | Se ejecutan los scripts de perfiles y se incluyen en el Almacenamiento de perfiles. El Almacenamiento solicita audiencias de la [!UICONTROL Biblioteca de audiencias] que cumplan los requisitos (por ejemplo, audiencias compartidas de [!DNL Adobe Analytics], [!DNL Audience Manager], etc.).<br>Los atributos del cliente se envían a [!DNL Profile Store] en un procesamiento de lotes. |
| 5 | Según la URL, los parámetros de mbox y los datos de perfil, [!DNL Target] decide qué actividades y experiencias vuelven al visitante. | 6 | Se devuelve el contenido dirigido a la página, incluyendo de manera opcional los valores de perfil para una personalización adicional.<br>Se muestra la experiencia lo más rápido posible sin parpadeos del contenido predeterminado. |
| 7 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. | 8 | Se comparan los datos de [!DNL Target] con los datos de [!DNL Analytics] mediante el SDID y se procesan en el almacén de informes de [!DNL Analytics].<br>[!DNL Analytics]Por lo tanto, los datos de  se pueden visualizar tanto en [!DNL Analytics] como en [!DNL Target] mediante los informes de [!DNL Analytics for Target] (A4T). |

### Vídeo: Tutorías: Sugerencias y descripción general de at.js (26 de junio de 2019)

Este vídeo es una grabación de “Horario de oficina”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Ventajas de utilizar at.js
* Configuración de at.js
* Control de parpadeo
* Depurar at.js
* Problemas conocidos
* Preguntas más frecuentes

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## Cómo procesa at.js ofertas con contenido HTML {#render}

Al procesar ofertas con contenido HTML, at.js aplica el siguiente algoritmo:

1. Las imágenes se cargan previamente (si el contenido HTML tiene etiquetas `<img>`).

1. El contenido HTML se adjunta al nodo DOM.

1. Se ejecutan scripts en línea (código delimitado por etiquetas `<script>`).

1. Los scripts remotos se cargan de forma asíncrona y se ejecutan (etiquetas `<script>` con atributos `src`).

Notas importantes:

* at.js no proporciona garantías en el orden de ejecución del script remoto, ya que estos se cargan de forma asincrónica.
* Los scripts en línea no deberían tener dependencias en scripts remotos, ya que se cargan y ejecutan más adelante.

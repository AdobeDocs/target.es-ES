---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
feature: release notes
translation-type: tm+mt
source-git-commit: 10d8f47dcca1d09654405c8382c70adc0b828e50
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 28%

---


# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Destinatario, los SDK, la biblioteca de JavaScript (at.js) y otros cambios en la plataforma, cuando corresponde.

>[!IMPORTANT]
>
>* **Fin de vida útil** de mbox.js: El 31 de marzo de 2021, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan actividades de Destinatario ejecutándose al proporcionar contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta de la asistencia que espera de Adobe.
   >
   >
* **Anuncios** de destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte [Anuncios de Destinatario](/help/r-release-notes/target-announcements.md).


Los números entre paréntesis son para uso interno de [!DNL Adobe].

## at.js 2.3.3 (13 de noviembre de 2020)

Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:

* Se ha corregido un problema relacionado con el rastreo de clics de mbox y A4T.

## Target Standard/Premium 20.10.1 (27 de octubre de 2020)

Esta versión contiene las siguientes nuevas funciones:

| Función | Detalles |
| --- | --- |
| [Toma de decisiones en el dispositivo](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | La toma de decisiones en dispositivos permite tanto a los especialistas en marketing como a los desarrolladores de productos ofrecer experimentación y personalización basada en el aprendizaje automático desde el dispositivo del usuario, en canales y con una latencia cercana a cero.<br>La velocidad y el rendimiento son importantes, tanto en la perspectiva del cliente como en la satisfacción del usuario.<br>La toma de decisiones en el dispositivo permite compilar las instrucciones de personalización y experimentación clave en los tipos de actividad Prueba A/B y Segmentación de experiencias (XT) en &quot;artefactos de optimización:&quot; objetos JSON que se cargan en dispositivos cliente mediante la CDN. Y como la toma de decisiones en dispositivos se conecta de forma nativa con [!DNL Adobe Experience Cloud] productos, [!DNL Target] los usuarios obtienen una análisis rápida y iteraciones de experiencia más rápidas.<br>Para obtener más información, consulte *Toma de decisiones [en dispositivos](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md). |

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se corrigió un problema que impedía que [!UICONTROL Intervalo de confianza de alza promedio] y [!UICONTROL Confianza] se mostraran en el sistema de informes [!DNL Auto-Target] para la fila [!UICONTROL Total]. Las mediciones se muestran correctamente para todas las experiencias individuales. (TGT-37301)
* Se ha corregido un problema que afectaba al sistema de informes [!DNL Adobe Target Premium] [!UICONTROL Destinatario automático] de los usuarios a partir del 15 de septiembre de 2:30 p.m. (PDT) hasta el 6 de octubre, 9:25 a.m. (PDT). Al ver los informes de las métricas de conversión afectadas (configurados con la opción &quot;[!UICONTROL Visualizó una página]&quot; o &quot;[!UICONTROL Se hizo clic en mbox]&quot;), las tasas de conversión se informan incorrectamente. No se conoce ningún problema de envío en este momento. Para obtener información sobre cómo volver a sincronizar y corregir el sistema de informes, consulte [sistema de informes de Destinatario automático](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) en *Problemas resueltos* en *Problemas conocidos y problemas resueltos*.
* Se añadió una columna [!UICONTROL Última actualización en] seleccionable en la tabla [!UICONTROL Búsqueda en el catálogo] y un filtro [!UICONTROL Última actualización en]. Esta mejora ahorra tiempo y esfuerzo porque no tiene que abrir cada elemento individual para ver cuándo se actualizó por última vez y puede filtrar por fecha la última vez que se actualizaron los elementos.

   ![Última actualización en la ilustración de la columna y el filtro](/help/r-release-notes/assets/column-and-filter.png)

* Se han realizado actualizaciones para ayudar a que la interfaz de usuario de Destinatario sea compatible con [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 Level A y AA Success Criteria (WCAG 2.0 AA). (TGT-34384 y TGT-24679)
* Se han realizado mejoras en la directiva de seguridad de contenido (CSP). (TGT-37035)
* Se ha introducido una forma de especificar el código de cliente como parámetro para los clientes que utilizan CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] la documentación se está trasladando a  [!DNL Experience League]. Durante el mes de octubre, todas las notas de la versión, artículos, vídeos y tutoriales se moverán de su ubicación actual en `docs.adobe.com` a [!DNL Experience League]. Este movimiento garantiza que todo el aprendizaje, la autoayuda, la habilitación y el contenido de la comunidad se proporcionen desde una sola ubicación. Cuando se produce este cambio, no hay nada que hacer, ya que todos los vínculos se redireccionarán a [!DNL Experience League]. Actualizaremos las notas de la versión cuando comience el corte.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas [ de la versión de ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)Experience Cloud. |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |

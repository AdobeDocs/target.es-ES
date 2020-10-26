---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de DNL Adobe Target.
title: Notas de evaluación de Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 02b0bd61d1ba7a591a5b61df36acc5d136e787f0
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 10%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 26 de octubre de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe nuevamente nombrado líder en el cuadrante mágico de Gartner para motores** de personalización: Una vez más, Adobe fue nombrado Líder en el tercer informe anual del Cuadrante Mágico de Gartner para Motores de Personalización, 2020. El Cuadrante mágico de Gartner para motores de personalización evaluó a los proveedores según 15 criterios que se dividen en dos categorías: integridad de la visión y capacidad de ejecución. [Lee al respecto en The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **Fin de vida útil** de mbox.js: El 18 de enero de 2021, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 18 de enero de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan actividades de Destinatario ejecutándose al proporcionar contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) At.js y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta de la asistencia que espera de Adobe.
   >
   >
* **Anuncios** de destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.10.1 (28 de octubre de 2020)

Esta versión contiene las siguientes nuevas funciones:

| Función | Detalles |
| --- | --- |
| Toma de decisiones en el dispositivo | La toma de decisiones en dispositivos permite tanto a los especialistas en marketing como a los desarrolladores de productos ofrecer experimentación y personalización basada en el aprendizaje automático desde el dispositivo del usuario, en canales y con una latencia cercana a cero.<br>La velocidad y el rendimiento son importantes, tanto en la perspectiva del cliente como en la satisfacción del usuario.<br>La toma de decisiones en el dispositivo permite compilar las instrucciones de personalización y experimentación clave en los tipos de actividad Prueba A/B y Segmentación de experiencias (XT) en &quot;artefactos de optimización:&quot; objetos JSON que se cargan en dispositivos cliente mediante la CDN. Y como la toma de decisiones en dispositivos se conecta de forma nativa con [!DNL Adobe Experience Cloud] [!DNL Target] los productos, los usuarios obtienen una análisis rápida y una experiencia más rápida de iteraciones.<br>**Regístrese ahora para un seminario web en directo.** Únase a los expertos en productos de Adobe Target para analizar cómo mover las decisiones de optimización de experiencias críticas en el dispositivo para que se ejecuten localmente con latencia cero puede abrir las puertas a nuevos casos de uso interesantes y mejorar el rendimiento del sitio para sus clientes.<ul><li>10 de noviembre de 2020</li><li>10 a.m. PT / 12 p.m. CT / 1 p.m. ET</li><li>[Registrarse aquí](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que impedía que el intervalo [!UICONTROL de confianza y la] confianza [!UICONTROL de alza promedio se mostraran en] sistema de informes para la fila [!DNL Auto-Target] Total  . Las mediciones se muestran correctamente para todas las experiencias individuales. (TGT-37301)
* Se ha corregido un problema que afectaba [!DNL Adobe Target Premium] al sistema de informes de Destinatario  automático de los usuarios desde el 15 de septiembre a las 2:30 p.m. (PDT) hasta el 6 de octubre, 9:25 a.m. (PDT). Al ver los informes de las métricas de conversión afectadas (configurados con la opción &quot;[!UICONTROL Visualizó una página]&quot; o &quot;[!UICONTROL Se hizo clic en el mbox]&quot;), las tasas de conversión se registran de manera incorrecta. No se conoce ningún problema de envío en este momento. Para obtener información sobre cómo volver a sincronizar y corregir el sistema de informes, consulte sistema de informes [de Destinatario](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) automático en Problemas ** resueltos en problemas *conocidos y problemas* resueltos.
* Se añadió una columna [!UICONTROL Última actualización] seleccionable en la tabla Búsqueda [!UICONTROL de] catálogo y un filtro [!UICONTROL Última actualización en] . Esta mejora ahorra tiempo y esfuerzo porque no tiene que abrir cada elemento individual para ver cuándo se actualizó por última vez y puede filtrar por fecha la última vez que se actualizaron los elementos.

   ![Última actualización en la ilustración de la columna y el filtro](/help/r-release-notes/assets/column-and-filter.png)

* Se han realizado actualizaciones para ayudar a que la IU de Destinatario sea compatible con las Directrices [de accesibilidad del contenido](https://www.w3.org/WAI/standards-guidelines/wcag/) web 2.0 Nivel A y los Criterios de éxito AA (WCAG 2.0 AA). (TGT-34384 y TGT-24679)
* Se han realizado mejoras en la directiva de seguridad de contenido (CSP). (TGT-37035)
* Se ha introducido una forma de especificar el código de cliente como parámetro para los clientes que utilizan CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] la documentación se está trasladando a [!DNL Experience League]. Durante el mes de octubre, todas las notas de la versión, los artículos, los vídeos y los tutoriales se moverán de su ubicación actual de `docs.adobe.com` a [!DNL Experience League]. Este movimiento garantiza que todo el aprendizaje, la autoayuda, la habilitación y el contenido de la comunidad se proporcionen desde una sola ubicación. Cuando se produce este cambio, no hay nada que hacer, ya que todos los vínculos se redireccionarán a [!DNL Experience League]. Actualizaremos las notas de la versión cuando comience el corte.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

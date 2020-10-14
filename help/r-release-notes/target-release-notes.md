---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de DNL Adobe Target.
title: Notas de evaluación de Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 8b1f98e6c05844308e63e2c32255c32d0c126cba
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 14 de octubre de 2020**

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


## Target Standard/Premium 20.10.1 (27 de octubre de 2020)

Esta versión contiene las siguientes nuevas funciones:

| Función | Detalles |
| --- | --- |
| Decisiones en el dispositivo | Las decisiones en el dispositivo permiten a los comerciantes y a los desarrolladores de productos ofrecer experimentación y personalización basada en el aprendizaje automático desde el dispositivo del usuario, en canales y con una latencia cercana a cero.<br>La velocidad y el rendimiento son importantes, tanto en la perspectiva del cliente como en la satisfacción del usuario. Las decisiones en el dispositivo permiten a los especialistas en marketing, y ahora a los desarrolladores de productos, probar y optimizar experiencias directamente desde un dispositivo de usuario, reduciendo los tiempos de decisión y carga a casi cero para las experiencias contextuales en tiempo real.<br>Las decisiones en el dispositivo le permiten compilar todas las instrucciones de personalización y experimentación en &quot;artefactos de optimización&quot;, que se cargan en dispositivos del cliente. Estos artefactos de latencia cero proporcionan a los especialistas en marketing una a una personalización, redireccionamiento del comportamiento y recomendaciones de contenido y productos en tiempo real, mientras que proporcionan a los desarrolladores y propietarios de productos acceso directo al código para probar las experiencias de usuario y los lanzamientos de productos en destinatario y fase, refinando en tiempo real. Y como las decisiones en dispositivos se conectan de forma nativa con [!DNL Adobe Experience Cloud] [!DNL Target] los productos, los usuarios obtienen una análisis rápida y una experiencia más rápida de iteraciones.<br>**Regístrese ahora para un seminario web en directo.** Únase a los expertos en productos de Adobe Target para analizar cómo mover las decisiones de optimización de experiencias críticas en el dispositivo para que se ejecuten localmente con latencia cero puede abrir las puertas a nuevos casos de uso interesantes y mejorar el rendimiento del sitio para sus clientes.<ul><li>10 de noviembre de 2020</li><li>10 a.m. PT / 12 p.m. CT / 1 p.m. ET</li><li>[Registrarse aquí](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que impedía que el intervalo [!UICONTROL de confianza y la] confianza [!UICONTROL de alza promedio se mostraran en] sistema de informes para la fila [!DNL Auto-Target] Total  . Las mediciones se muestran correctamente para todas las experiencias individuales. (TGT-37301)
* Se ha corregido un problema que afectaba [!DNL Adobe Target Premium] al sistema de informes de Destinatario  automático de los usuarios desde el 15 de septiembre a las 2:30 p.m. (PDT) hasta el 6 de octubre, 9:25 a.m. (PDT). Al ver los informes de las métricas de conversión afectadas (configurados con la opción &quot;[!UICONTROL Visualizó una página]&quot; o &quot;[!UICONTROL Se hizo clic en el mbox]&quot;), las tasas de conversión se registran de manera incorrecta. No se conoce ningún problema de envío en este momento. Para obtener información sobre cómo volver a sincronizar y corregir el sistema de informes, consulte sistema de informes [de Destinatario](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) automático en Problemas ** resueltos en problemas *conocidos y problemas* resueltos.
* Se añadió una columna [!UICONTROL Última actualización] seleccionable en la tabla Búsqueda [!UICONTROL de] catálogo y un filtro [!UICONTROL Última actualización en] . Esta mejora ahorra tiempo y esfuerzo porque no tiene que abrir cada elemento individual para ver cuándo se actualizó por última vez y puede filtrar por fecha la última vez que se actualizaron los elementos.

   ![Última actualización en la ilustración de la columna y el filtro](/help/r-release-notes/assets/column-and-filter.png)

* Se ha mejorado la navegación y la funcionalidad para los usuarios que utilizan solo el teclado.
* Etiquetas añadidas en la interfaz de usuario para ayudar a los usuarios a utilizar tecnologías de asistencia.
* Se ha mejorado el contraste de texto y color para las imágenes y el texto en la interfaz de usuario.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

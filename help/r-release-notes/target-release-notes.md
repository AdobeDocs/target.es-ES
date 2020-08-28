---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de DNL Adobe Target.
title: Notas de evaluación de Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 81b9735ea1fa6c42aa9c73565efd68a4d474622c
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 13%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 20 de agosto de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe nuevamente nombrado líder en el cuadrante mágico de Gartner para motores** de personalización: Una vez más, Adobe fue nombrado Líder en el tercer informe anual del Cuadrante Mágico de Gartner para Motores de Personalización, 2020. El Cuadrante mágico de Gartner para motores de personalización evaluó a los proveedores según 15 criterios que se dividen en dos categorías: integridad de la visión y capacidad de ejecución. [Lee al respecto en The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **Desaprobación** de mbox.js: El 18 de enero de 2021, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 18 de enero de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan actividades de Destinatario ejecutándose al proporcionar contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) At.js y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta de la asistencia que espera de Adobe.
   >
   >
* **Anuncios** de destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.9.1 (2 de septiembre de 2020)

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que provocaba que se mostraran errores al cargar las nuevas páginas de **[!UICONTROL administración]** después de cambiar de organización. (TGT-37730)
* Se ha corregido un problema de visualización que provocaba que se mostrara el código de cliente incorrecto en la página **[!UICONTROL Administración > Implementación]** . (TGT-37849)
* Se ha corregido un problema que, en ocasiones, impedía a los usuarios utilizar las funciones de edición del Compositor **[!UICONTROL de experiencias]** visuales (VEC) después de cargar correctamente el VEC. (TGT-37162)
* Se ha corregido un problema que, en ocasiones, impedía a los usuarios descargar at.js desde la página **[!UICONTROL Administración > Implementación]** después de cambiar de organización. (TGT-37668)
* Se ha corregido un problema en las actividades de **[!UICONTROL Segmentación]** de experiencias (XT) que hacía que las experiencias mostraran &quot;obteniendo resultados&quot; durante un período de tiempo prolongado. (TGT-37684)
* Se ha mejorado la navegación y la funcionalidad para los usuarios que utilizan solo el teclado. (TGT-34479 y TGT-34473)
* Etiquetas añadidas en la interfaz de usuario para ayudar a los usuarios a utilizar tecnologías de asistencia. (TGT-34480)
* Se ha mejorado el mensaje de error al eliminar una ventanilla móvil que se está utilizando en una actividad. El mensaje de error ahora es: &quot;Esta ventanilla está asociada actualmente a una o varias actividades. Debe quitar la ventanilla de esas actividades antes de poder eliminarla&quot;. (TGT-37030)
* Se ha añadido la compatibilidad en el VEC para permitir el seguimiento de clics en un selector css que coincida con más de un elemento de la página. (TGT-37323)
* Se ha corregido un problema que impedía que algunos usuarios mostraran la lista de **[!UICONTROL Actividad]** . Se mostraba el siguiente mensaje de error: &quot;No se pueden recuperar las sugerencias de URL.&quot; El error se producía para los usuarios que utilizaban retornos de carro en su Nombre (FirstName/r/n) en el sistema back-end de Adobe. (TGT-37330)
* Se ha corregido un problema que impedía que los usuarios mostraran la página de **[!UICONTROL Actividad]** si el nombre del espacio de trabajo (especificado en **[!UICONTROL Adobe Admin Console para Enterprise]**) contenía un apóstrofe. (TGT-37709)
* El botón de descarga de at.js ahora está desactivado mientras se carga para evitar que se envíen varias solicitudes si los usuarios hacen clic varias veces en el botón de descarga. [!DNL Target] (TGT-37633)
* Se ha corregido un problema que provocaba un valor modificado incorrectamente por última vez para [!DNL Recommendations] los criterios. (TGT-37666)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de DNL Adobe Target.
title: Notas de evaluación de Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 92f5953a96b92175784600d1b04a23ec4d7152ec
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 11%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 15 de septiembre de 2020**

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


## Target Standard/Premium 20.8.3 (15 de septiembre de 2020)

| Función | Detalles |
| --- | --- |
| ![Compatibilidad con Premium badge](/help/assets/premium.png) Analytics para Destinatario (A4T) para actividades de Destinatario automático | [!UICONTROL Las actividades de Destinatario] automático ahora admiten [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Esta integración le permite utilizar el algoritmo de aprendizaje automático del conjunto de Destinatario  automático para elegir una experiencia óptima para cada visitante en función de su perfil, comportamiento y contexto.<br>Si ya ha [implementado A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para su uso con actividades de Prueba A/B y de segmentación de experiencias, ¡ya está todo preparado!<br>Para obtener más información, consulte Compatibilidad [de Analytics para Destinatario (A4T) con la asignación automática y las actividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) de Destinatario automático en la creación *de* Actividades. |

## Target Standard/Premium 20.8.2 (10 de septiembre de 2020)

| Función | Detalles |
| --- | --- |
| ![Rangos de recomendaciones de control de distintivo](/help/assets/premium.png) Premium dentro de secuencias de criterios | Las secuencias de criterios ahora permiten controlar el número de ranuras ocupadas por cada criterio de recomendación, lo que le permite mezclar y hacer coincidir distintos tipos de elementos o distintas lógicas de algoritmo.<br>Consulte [Creación de secuencias](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) de criterios para obtener más información. |

## Target Standard/Premium 20.8.1 (2 de septiembre de 2020)

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que provocaba que se mostraran errores al cargar las nuevas páginas de [!UICONTROL administración] después de cambiar de organización. (TGT-37730)
* Se ha corregido un problema de visualización que provocaba que se mostrara el código de cliente incorrecto en la página [!UICONTROL Administración > Implementación] . (TGT-37849)
* Se ha corregido un problema que, en ocasiones, impedía a los usuarios utilizar las funciones de edición del Compositor [!UICONTROL de experiencias] visuales (VEC) después de cargar correctamente el VEC. (TGT-37162)
* Se ha corregido un problema que impedía que las páginas se cargaran en el VEC y en el Compositor de experiencias mejorado (EEC) aunque se instalara la extensión del asistente de VEC. Esto se debió a los cambios en Google Chrome 80+. Descargue la extensión [](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)VEC Helper actualizada. (TGT-37893)
* Se ha corregido un problema que, en ocasiones, impedía a los usuarios descargar at.js desde la página [!UICONTROL Administración > Implementación] después de cambiar de organización. (TGT-37668)
* El botón de descarga de at.js ahora está desactivado mientras se carga para evitar que se envíen varias solicitudes si los usuarios hacen clic varias veces en el botón de descarga. [!DNL Target] (TGT-37633)
* Se ha corregido un problema en las actividades de [!UICONTROL Segmentación] de experiencias (XT) que hacía que las experiencias mostraran &quot;obteniendo resultados&quot; durante un período de tiempo prolongado. (TGT-37684)
* Se ha mejorado la navegación y la funcionalidad para los usuarios que utilizan solo el teclado. (TGT-34479 y TGT-34473)
* Etiquetas añadidas en la interfaz de usuario para ayudar a los usuarios a utilizar tecnologías de asistencia. (TGT-34480)
* Se ha mejorado el mensaje de error al eliminar una ventanilla móvil que se está utilizando en una actividad. El mensaje de error ahora es: &quot;Esta ventanilla está asociada actualmente a una o varias actividades. Debe quitar la ventanilla de esas actividades antes de poder eliminarla&quot;. (TGT-37030)
* Se ha añadido la compatibilidad en el VEC para permitir el seguimiento de clics en un selector css que coincida con más de un elemento de la página. (TGT-37323)
* Se ha corregido un problema que impedía que algunos usuarios mostraran la lista de [!UICONTROL Actividad] . Se mostraba el siguiente mensaje de error: &quot;No se pueden recuperar las sugerencias de URL.&quot; El error se producía para los usuarios que utilizaban retornos de carro en su Nombre (FirstName/r/n) en el sistema back-end de Adobe. (TGT-37330)
* Se ha corregido un problema que impedía que los usuarios mostraran la página de [!UICONTROL Actividad] si el nombre del espacio de trabajo (especificado en [!UICONTROL Adobe Admin Console para Enterprise]) contenía un apóstrofe. (TGT-37709)
* Se corrigió un problema en actividades de asignación  automática al seleccionar métricas de optimización y conversión, en el cual un mensaje de error informaba incorrectamente a los usuarios de seleccionar un grupo de informes, aunque ya se hubiera especificado un grupo de informes. (TGT-37689)
* Se corrigió un problema que en ocasiones causaba que las métricas de la página [!UICONTROL Objetivos y configuración] estuvieran en blanco después de navegar a la página [!UICONTROL Objetivo] y volver a ella. (TGT-37691)
* Se ha corregido un problema que provocaba un valor modificado por última vez incorrecto para [!DNL Recommendations] los criterios. (TGT-37666)
* Se ha corregido un problema que provocaba que los ID de mbox se mostraran en la lista desplegable Mboxes en lugar de en los nombres de mbox. (TGT-37739)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

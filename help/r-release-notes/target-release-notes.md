---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target DNL.
title: Notas de la versión de evaluación de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 058828bbf3f13704d9e941563b7dab5259be6809
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 19%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 23 de junio de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!NOTE]
>
>* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Destinatario en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) At.js y Generador de habilidades [Adobe Target: Chat del desarrollador, migre el archivo mbox.js del Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.
   >
   >
* **Anuncios** de Destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.6.1 (julio de 2020, fecha exacta TBD)

Esta versión incluye las siguientes mejoras:

### Compatibilidad de Analytics para Destinatario (A4T) con actividades de Destinatario  automático

[!UICONTROL Las actividades de Destinatario] automático ahora admiten [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md).

Esta integración utiliza aprendizaje automático avanzado para seleccionar entre varias experiencias definidas por expertos en marketing de alto rendimiento para personalizar el contenido y dirigir las conversiones. La segmentación automática proporciona la experiencia más adaptada a cada visitante según su perfil de cliente individual y el comportamiento de visitantes anteriores con perfiles similares.

Si ya ha [implementado A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para su uso con actividades de prueba A/B, ¡ya está todo listo!

### [!UICONTROL Actualización de la interfaz de usuario de la sección Administración]

Hemos actualizado la sección [!UICONTROL Administración] (anteriormente [!UICONTROL Administración]) y sus páginas para que sus flujos de trabajo sean más fáciles y eficientes.

Entre los aspectos destacados se incluyen:

* **[!UICONTROL Página]del Compositor **de experiencias visuales: Esta nueva página (**[!UICONTROL Administración ]**> Compositor**[!UICONTROL de experiencias ]**visuales) permite:

   * Configuración general del VEC (especifique la dirección URL predeterminada, habilite el Compositor [!UICONTROL de experiencias]mejorado, cargue contenido mixto y genere instantáneas de experiencia en el diagrama de flujo de actividades)
   * Configurar ventanillas móviles
   * Configuración de selectores CSS

* **[!UICONTROL Página]de Sistema de informes **: Esta nueva página (**[!UICONTROL Administración ]**>**[!UICONTROL Sistema de informes ]**) permite configurar las opciones generales que se utilizarán en[!DNL Target]sistemas de informes que se apliquen a toda la[!DNL Target]cuenta.

   Las opciones de configuración disponibles son:

   * La [!DNL Adobe Experience Cloud] solución para sistema de informes
   * El huso horario que se usará para el sistema de informes
   * La divisa que se va a utilizar para el sistema de informes
   * Direcciones IP para excluir del sistema de informes
   * Si se muestra un alza estimada en los ingresos en sistemas de informes
   * Si se deben habilitar prioridades específicas

* La página [!UICONTROL Hosts] anterior se ha dividido en dos páginas nuevas:

   * [!UICONTROL Hosts]
   * [!UICONTROL Entornos]

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

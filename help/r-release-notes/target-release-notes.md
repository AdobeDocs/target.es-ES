---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target DNL.
title: Notas de la versión de evaluación de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 322b14629d420601b763fed7597c43a8458b7dbf
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 17%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 24 de junio de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!NOTE]
>
>* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan actividades de Destinatario ejecutándose al proporcionar contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) At.js y Generador de habilidades [Adobe Target: Chat del desarrollador, migre el archivo mbox.js del Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.
   >
   >
* **Anuncios** de Destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.7.1 (21 de julio de 2020). 

Esta versión incluye las siguientes mejoras:

### [!UICONTROL Actualización de la interfaz de usuario de la sección Administración]

Estamos reescribiendo gradualmente toda la [!DNL Target] interfaz de usuario con una nueva pila de tecnología para poder oferta de un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La primera sección que se actualiza es la sección [!UICONTROL Configuración] , a la que se le ha cambiado el nombre [!UICONTROL Administración].

Como parte de esta actualización, podrá realizar fácilmente muchas acciones utilizando las páginas de la sección [!UICONTROL Administración] , como:

* Descargue el archivo at.js más reciente de la ficha [!UICONTROL Implementación] (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**).
* Personalice la configuración de at.js y pueda revisar fácilmente los cambios (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**).
* Modifique la configuración mejorada del sistema de informes, como la moneda y el huso horario predeterminados, las direcciones IP que se excluirán del sistema de informes, etc. (**[!UICONTROL Administración]** > **[!UICONTROL Sistema de informes]**)
* Proteger direcciones IP de visitante por motivos de privacidad (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**)
* Vista la lista existente de usuarios por espacio de trabajo y sus funciones, antes de administrarlos en Adobe Admin Console (**[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**).
* Busque y filtre todas las tablas en la sección [!UICONTROL Administración] .

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

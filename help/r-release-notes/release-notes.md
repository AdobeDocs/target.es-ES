---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 81b9735ea1fa6c42aa9c73565efd68a4d474622c
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 30%

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Destinatario, los SDK, la biblioteca de JavaScript (at.js) y otros cambios en la plataforma, cuando corresponde.

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


Los números entre paréntesis son para uso interno de [!DNL Adobe].

## at.js 2.3.2 (24 de julio de 2020)

Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:

* Se ha corregido un error que se producía cuando un script o código añadía una propiedad predeterminada a la ventana o al documento.

## Target Standard/Premium 20.7.1 (27 de julio de 2020). 

Esta versión incluye los siguientes cambios:

### [!UICONTROL Actualización de la interfaz de usuario de la sección Administración]

Estamos reescribiendo gradualmente toda la [!DNL Target] interfaz de usuario con una nueva pila de tecnología para poder oferta de un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La primera sección que se actualiza es la sección [!UICONTROL Configuración] , a la que se le ha cambiado el nombre [!UICONTROL Administración].

Como parte de esta actualización, podrá realizar fácilmente muchas acciones utilizando las páginas de la sección [!UICONTROL Administración] , como:

* Descargue el archivo at.js más reciente de la ficha [!UICONTROL Implementación] (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**).
* Personalice la configuración de at.js y pueda revisar fácilmente los cambios (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**).
* Modifique la configuración mejorada del sistema de informes, como la moneda y el huso horario predeterminados, las direcciones IP que se excluirán del sistema de informes, etc. (**[!UICONTROL Administración]** > **[!UICONTROL Sistema de informes]**)
* Proteger direcciones IP de visitante por motivos de privacidad (**[!UICONTROL Administración]** > **[!UICONTROL Implementación]**)
* Vista la lista existente de usuarios por espacio de trabajo y sus funciones, antes de administrarlos en Adobe Admin Console (**[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**).
* Busque y filtre todas las tablas en la sección [!UICONTROL Administración] .

Para obtener más información, consulte [Administrar información general](/help/administrating-target/administrating-target.md)de Destinatario.

### Mejoras, correcciones y cambios

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que impedía que las preferencias del sitio se conservaran tras la actualización. (TGT-37239)
* Se ha corregido un problema que impedía que [!UICONTROL Insertar después] > [!UICONTROL Imagen] funcionara correctamente con imágenes de gráficos vectoriales escalables (SVG). (TGT-37242)
* Se ha corregido un problema con los usuarios con la función de [!UICONTROL Editor] que impedía eliminar actividades de borrador. (TGT-37358)
* Se ha corregido un problema que impedía a los usuarios editar una actividad cuando se seleccionaba [!UICONTROL Todos mis espacios de trabajo] . (TGT-37276)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: API de Destinatario del lado del servidor](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de la versión relacionadas con las API de servidor de Adobe Target. |
| [Notas de la versión: SDK de Node.js de Destinatario](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de la versión relacionadas con el SDK de Node.js de Adobe Target. |
| [Notas de la versión: SDK de Java de Destinatario](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de la versión relacionadas con el SDK de Java de Adobe Target. |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios en cada versión de la biblioteca JavaScript de Adobe Target at.js. |
| [Detalles de la versión de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página muestra cambios realizados a cada versión de mbox.js.<br>Tenga en cuenta que la biblioteca mbox.js ya no se está desarrollando. Todos los clientes deberían migrar de mbox.js a at.js. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas [de la versión de](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |

---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target de DNL.
title: Notas de la versión de evaluación de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 25f7ce65f4f9b863ce6ebfe0a7ff8df08e561741
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 17%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 12 de junio de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!NOTE]
>
>* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Destinatario en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Cómo funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) At.js y Generador de habilidades de [Adobe Target: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.
   >
   >
* **Anuncios** de Destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Versiones de at.js 1.8.2 y at.js 2.3.1 (15 de junio de 2020)

Se han realizado las siguientes mejoras y correcciones en las bibliotecas de [!DNL Target] at.js:

### at.js 1.8.2

* Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 1.*x* podría crear incorrectamente el dominio del servidor, lo que ocasionaba que fallara la [!DNL Target] solicitud. (TNT-35064)

### at.js 2.3.1

* Se ha hecho que la `deviceIdLifetime` configuración se pueda anular mediante [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 2.*x* podría crear incorrectamente el dominio del servidor, lo que ocasionaba que fallara la [!DNL Target] solicitud. (TNT-35065)
* Se ha corregido un problema que se producía al usar la [!DNL Target] extensión v2 y la [!DNL Launch] extensión, [!DNL Adobe Analytics] al retrasar la [!DNL Launch] [!DNL Target] [!DNL Analytics] `sendBeacon` llamada. (TNT-36407, TNT-35990, TNT-36000)

## Target Standard/Premium 20.5.1 (17 de junio de 2020). 

| Función.  / Mejora | Descripción |
| --- | --- |
| Analytics for Target (A4T) compatibilidad con actividades de asignación automática | Con la versión de junio, las pruebas de asignación automática admitirán [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md). Esta integración le permite utilizar la capacidad de edición multiarmada de la asignación automática para dirigir el tráfico a las experiencias ganadoras, mientras utiliza una métrica objetivo de Adobe Analytics y/o las funciones de sistema de informes y análisis de Adobe Analytics. Si ya ha [implementado A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para su uso con actividades de Prueba A/B y de segmentación de experiencias, ¡ya está todo preparado! |
| Función de editor | Esta nueva función es similar a la función de observador actual (puede crear actividades de vista, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para activar actividades. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

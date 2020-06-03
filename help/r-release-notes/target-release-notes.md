---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las últimas o futuras versiones de Destinatario de DNL.
title: Notas de la versión de evaluación de Adobe Destinatario
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 316c1157a4dff346f16862cfd7a04994c6a1bc7d
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 21%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 3 de junio de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!NOTE]
>
>* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Destinatario dejará de ser compatible con la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Destinatario en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Consulte *Adobe Destinatario Skill Builder: Chat para desarrolladores, migre el archivo mbox.js de Adobe Destinatario a at.js* a continuación para obtener más información.
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.
   >
   >
* **Anuncios** de Destinatario: Consulte la página de anuncios de Destinatario para obtener información sobre los próximos eventos, incluidas las sesiones del Creador de conocimientos de Destinatario, los chats para desarrolladores, los seminarios web y las sesiones de Descanso de café de Destinatario. Para obtener más información, consulte Anuncios [de Destinatario](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.5.1 (10 de junio de 2020). 

| Función.  / Mejora | Descripción |
| --- | --- |
| Analytics for Target (A4T) compatibilidad con actividades de asignación automática | Con la versión de junio, las pruebas de asignación automática admitirán [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md). Esta integración le permite utilizar la capacidad de edición multiarmada de la asignación automática para dirigir el tráfico a las experiencias ganadoras, mientras utiliza una métrica objetivo de Adobe Analytics y/o las funciones de sistema de informes y análisis de Adobe Analytics. Si ya ha [implementado A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para su uso con actividades de Prueba A/B y de segmentación de experiencias, ¡ya está todo preparado! |
| Función de editor | Esta nueva función es similar a la función de observador actual (puede crear actividades de vista, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para actividades activas. |
| Página<br>de administraciónAnteriormente, &quot;Configuración&quot;. | Se ha cambiado el nombre de la página Configuración por &quot;Administración&quot; y se ha actualizado la interfaz de usuario de todos los elementos de menú para mejorar el flujo de trabajo y la facilidad de uso.<br>Los elementos de menú disponibles incluyen:<ul><li>Compositor de experiencias visuales</li><li>Creación de informes</li><li>Configuración de Scene7</li><li>Implementación</li><li>Propiedades</li><li>Hosts</li><li>Entornos</li><li>Tokens de respuesta</li><li>Usuarios</li></ul> |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

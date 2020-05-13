---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las últimas o futuras versiones de Destinatario de DNL.
title: Notas de la versión de evaluación de Adobe Destinatario
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ae97b36e9a5aaa0394fb3b4ab1ad40b38a0c97be
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 4 de mayo de 2020**

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


## Adobe Destinatario Skill Builder: Chat del desarrollador, migrar mbox.js de Adobe Destinatario a at.js {#skill-builder}

Con la próxima desaprobación de mbox.js el 30 de agosto de 2020, David Son, administrador de productos de Adobe Destinatario, organizó recientemente un chat de desarrollador para debatir las ventajas de migrar mbox.js a at.js. Durante los próximos 30 días, puede [vista de la grabación](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)del seminario web.

## Target Standard/Premium 20.5.1 (10 de junio de 2020). 

Los detalles de esta versión se publicarán aquí.

## Cambios en la API de estado de lote de Perfil v2 (fecha TBD)

Con la versión del 4 de mayo, el estado de Lote de Perfil solo devolverá datos de error de nivel de fila a partir de ahora (no se devolverán datos de éxito). La API devolverá los ID de perfil fallidos a partir de ahora.

Las respuestas de API anteriores y nuevas son las siguientes:

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**Actualmente vemos la respuesta como:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**Después del 4 de mayo, la respuesta será:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

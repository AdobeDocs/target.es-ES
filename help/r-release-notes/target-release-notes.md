---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las últimas o futuras versiones de Destinatario de DNL.
title: Notas de la versión de evaluación de Adobe Destinatario
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e9a6545ab65cf1214977f8fa472904527c18a04d

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 24 de abril de 2020**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!NOTE]
>
>* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Destinatario dejará de ser compatible con la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Destinatario en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Consulte *Adobe Destinatario Skill Builder: Chat del desarrollador, migre el archivo mbox.js de Adobe Destinatario a at.js* a continuación para obtener información sobre cómo registrarse para un próximo chat del desarrollador sobre este tema.
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.


## Adobe Destinatario Skill Builder: Chat del desarrollador, migrar mbox.js de Adobe Destinatario a at.js {#skill-builder}

Únase a David Son, responsable de productos de Adobe Destinatario, en su presentación de las ventajas de migrar mbox.js a at.js. Obtenga información sobre las últimas actualizaciones de at.js, sus funciones mejoradas y cómo se alinean con las tendencias más grandes del panorama tecnológico, así como sobre algunos consejos prácticos para garantizar que extrae todo el valor de Destinatario al migrar de mbox.js a at.js. Los desarrolladores de Adobe Destinatario no querrán perderlo.

Martes, 5 de mayo, 8:00 - 9:00 AM (PDT)

[Regístrese aquí!](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1 (27 de abril de 2020)

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que no cumplía correctamente los requisitos de un dispositivo y un tipo de explorador para una audiencia. (TGT-36266)
* Se ha corregido un problema que impedía que los datos del informe se mostraran cuando se visualizaban en pantallas de menos de 963 píxeles de ancho. (TGT-36549)
* Se ha corregido un problema que provocaba que los informes de Personalización automática no se representaran correctamente. (TGT-36619)
* Se ha corregido un problema que permitía seleccionar métricas incompatibles en la asignación automática y en actividades de Destinatario automático que usan Analytics para Destinatario (A4t). (TGT-36646)
* Se ha corregido un problema que provocaba que determinadas opciones del Compositor de experiencias visuales (VEC) no se mostraran correctamente. (TGT-36571)
* Se ha corregido un problema en la interfaz de usuario de Destinatario que provocaba que otras previsualizaciones de oferta de Recommendations mostraran el contenido editado después de que un usuario reemplazara el contenido en una única experiencia. (TGT-36053 y TGT-36894)
* Se ha corregido un problema que impedía que algunos usuarios eliminaran elementos de un catálogo de Recomendaciones. (TGT-36455)
* Se ha corregido un problema que impedía a los usuarios guardar los criterios de Recomendaciones en una actividad de varias páginas. (TGT-36249)
* Se ha corregido un problema que provocaba que los botones de radio del origen de datos de comportamiento desaparecieran al editar los criterios por segunda vez consecutiva. (TGT-36796)
* Se corrigió un problema de visualización que ocasionaba que un algoritmo de Recomendaciones mostrara &quot;recuperando resultados&quot; durante un período prolongado. (TGT-36550 y TGT-36551)
* Se han actualizado muchas cadenas de IU traducidas en varios idiomas.

## Cambios en la API de estado de lote de Perfil v2 (4 de mayo de 2020)

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

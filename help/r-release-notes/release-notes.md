---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 8bd08463509e06673bedd0fedf9ee15e46472826
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 30%

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Destinatario, los SDK, la biblioteca de JavaScript (at.js) y otros cambios en la plataforma, cuando corresponde.

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


Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Versiones de at.js 1.8.2 y at.js 2.3.1 (15 de junio de 2020)

Se han realizado las siguientes mejoras y correcciones en las bibliotecas de [!DNL Target] at.js:

| Función.  / Mejora | Descripción |
| --- | --- |
| at.js.  1.8.2 | Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:<ul><li>Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 1.*x* podría crear incorrectamente el dominio del servidor, lo que ocasionaba que fallara la [!DNL Target] solicitud. (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| at.js 2.3.1 | Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:<ul><li>Se ha hecho que la `deviceIdLifetime` configuración se pueda anular mediante [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)</li><li>Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 2.*x* podría crear incorrectamente el dominio del servidor, lo que ocasionaba que fallara la [!DNL Target] solicitud. (TNT-35065)</li><li>Se ha corregido un problema que se producía al usar la [!DNL Target] extensión v2 y la [!DNL Launch] extensión, [!DNL Adobe Analytics] al retrasar la [!DNL Launch] [!DNL Target] [!DNL Analytics] `sendBeacon` llamada. (TNT-36407, TNT-35990, TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## Cambios en la API de estado de lote de Perfil v2 (14 de mayo de 2020)

Con la versión del 20 de mayo, el estado de Lote de Perfil solo devolverá datos de error de nivel de fila a partir de ahora (no se devolverán datos de éxito). La API devolverá los ID de perfil fallidos a partir de ahora.

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

## Target Standard/Premium 20.4.1 (6 de mayo de 2020). 

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que no cumplía correctamente los requisitos de un dispositivo y un tipo de explorador para una audiencia. (TGT-36266)
* Se ha corregido un problema que impedía que los datos del informe se mostraran cuando se visualizaban en pantallas de menos de 963 píxeles de ancho. (TGT-36549)
* Se ha corregido un problema que provocaba que los informes de Personalización automática no se representaran correctamente. (TGT-36619)
* Se ha corregido un problema que permitía que se seleccionaran métricas incompatibles en las actividades de asignación automática y Destinatario automático que usan Analytics para Destinatario (A4t). (TGT-36646)
* Se ha corregido un problema que provocaba que determinadas opciones del Compositor de experiencias visuales (VEC) no se mostraran correctamente. (TGT-36571)
* Se ha corregido un problema en la interfaz de usuario de Destinatario que provocaba que otras previsualizaciones de oferta de Recommendations mostraran el contenido editado después de que un usuario reemplazara el contenido en una única experiencia. (TGT-36053 y TGT-36894)
* Se ha corregido un problema que impedía que algunos usuarios eliminaran elementos de un catálogo de Recomendaciones. (TGT-36455)
* Se ha corregido un problema que impedía a los usuarios guardar los criterios de Recomendaciones en una actividad de varias páginas. (TGT-36249)
* Se ha corregido un problema que provocaba que los botones de radio del origen de datos de comportamiento desaparecieran al editar los criterios por segunda vez consecutiva. (TGT-36796)
* Se corrigió un problema de visualización que ocasionaba que un algoritmo de Recomendaciones mostrara &quot;recuperando resultados&quot; durante un período prolongado. (TGT-36550 y TGT-36551)
* Se han actualizado muchas cadenas de IU traducidas en varios idiomas.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: API de Destinatario del lado del servidor](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de la versión relacionadas con las API del lado del servidor de Adobe Target. |
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

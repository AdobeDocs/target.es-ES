---
keywords: Target Standard;at.js;implementation
description: La biblioteca at.js es una nueva biblioteca de implementación para Adobe Target que está diseñada tanto para implementaciones web típicas como para aplicaciones de una sola página.
title: Migrar de mbox.js a at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 96%

---


# Migrar de mbox.js a at.js{#migrate-from-mbox-js-to-at-js}

La biblioteca at.js es una nueva biblioteca de implementación para [!DNL Adobe Target] que está diseñada tanto para implementaciones web típicas como para aplicaciones de una sola página.

Entre otros beneficios, [!DNL at.js] mejora los tiempos de carga de página en implementaciones web y proporciona mejores opciones de implementación en aplicaciones de una sola página.

[!DNL at.js] reemplaza [!DNL mbox.js] por las implementaciones [!DNL Target]. La biblioteca [!DNL at.js] también incluye los componentes que se incluían en [!DNL target.js], de modo que ya no se llama a [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 con FP-11577 (o posterior) admite las implementaciones de at.js mediante su integración con los Servicios en la nube de Adobe Target. Para obtener más información, consulte [Paquetes de características](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) e [Integración con Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) en la documentación de *Adobe Experience Manager 6.2*.

## Ventajas de at.js {#benefits}

La tabla siguiente explica las diferencias entre las dos bibliotecas:

| Referencia sobre la biblioteca | Descripción |
|--- |--- |
| at.js | at.js reemplaza a mbox.js para [!DNL Target]implementaciones.<br>Entre otros beneficios, at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad, evita advertencias de document.write en Google Chrome y proporciona mejores opciones de implementación en aplicaciones de una sola página.<br>Para obtener más información, consulte [Implementación at.js](#implement). |
| mbox.js | Antes de [!DNL Target]16.3.1 (marzo de 2016), [!DNL Target] requería una llamada a mbox.js para crear el mbox global necesario [!DNL Target] para suministrar actividades, rastrear clics y rastrear la mayoría de las métricas de éxito. Este archivo contiene las bibliotecas necesarias para todas sus actividades. No es necesario que mantenga una versión del archivo para cada actividad.<br>Si ya tiene mboxes envolventes en las páginas de una implementación anterior de [!DNL Target], podrá usarlos en la nueva interfaz. El archivo mbox.js actualizado sigue siendo necesario, pero estos mboxes pueden seleccionarse para actividades y modificarse con el Compositor de experiencias visuales.<br>[!DNL Target] Standard y Premium actualizan y complementan mbox.js con una referencia a un archivo target.js. El archivo target.js se aloja en Adobe. El archivo Target.js permite editar contenido en cualquier página con el Compositor de experiencias visuales aunque la página no contenga mboxes predefinidos. Deberá hacer referencia a este archivo en todas las páginas del sitio.<br>Para obtener más información, consulte [Implementación de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante**: La biblioteca mbox.js sigue siendo compatible, pero sus características ya no se actualizarán. Todos los clientes deberían migrar a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md) |

## Implementar at.js {#implement}

Para usar [!DNL at.js], reemplace la referencia a [!DNL mbox.js] en páginas donde desea implementarla. No puede usar [!DNL mbox.js] y [!DNL at.js] en una misma página. Sin embargo, puede usar cualquiera en cada página de su sitio.

La biblioteca de [!DNL at.js] funciona para implementaciones existentes que emplean las funciones `mboxCreate()`, `mboxDefine()` y `mboxUpdate()` admite nueva funcionalidad enfocada en las implementaciones basadas en aplicaciones de una sola página.

Puede usar [!DNL at.js] en cualquier lugar donde actualmente use [!DNL mbox.js].

La biblioteca [!DNL at.js] ofrece varias mejoras con respecto a la biblioteca [!DNL mbox.js]. Algunas de ellas son:

* Comunicación completamente asincrónica mediante AJAX de dominio cruzado

   >[!IMPORTANT]
   >
   >Aunque [!DNL at.js] se comunica con los servidores de [!DNL Target] de manera asíncrona, el archivo [!DNL at.js] en sí mismo debe cargarse sincrónicamente en la sección `<head>` de la página. Idealmente, debería ser uno de los primeros scripts cargados. Una vez cargado, [!DNL at.js] ejecuta llamadas de mbox asincrónicamente mediante `XMLHttpRequest` y no bloquea el procesamiento de la página.

* No hay más bloqueos de llamadas
* No se usa.`document.write()`
* No hay ejecución inmediata de JavaScript en las respuestas de.[!DNL Target]
* Mejores tiempos de espera y gestión de errores

   * Personalizable [tiempo de espera](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) por llamada
   * No hay recargas en tiempos de espera

* Funciones diseñadas específicamente para marcos de aplicaciones de una sola página/MVC

## Vídeo de formación: at.js; prácticas recomendadas para la implementación y sus ventajas ![Distintivo de información general](/help/assets/overview.png)

Este vídeo es una grabación de “[Horario de oficina](/help/cmp-resources-and-contact-information.md)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo funciona la biblioteca at.js
* Las ventajas de at.js sobre mbox.js
* Cómo gestiona at.js el parpadeo
* Gestión de errores en at.js
* Metodologías de depuración
* Problemas conocidos y hoja de ruta

>[!VIDEO](https://video.tv.adobe.com/v/22223/)

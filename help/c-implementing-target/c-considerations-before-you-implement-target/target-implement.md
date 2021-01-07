---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Implemente Adobe Target haciendo referencia a las bibliotecas de Destinatario (at.js o mbox.js) en sus páginas web.
title: Comprender las bibliotecas JavaScript de Target
feature: Implementation
translation-type: tm+mt
source-git-commit: 362fbc25a41d73e05bcc0a4034963ee3f5fbd847
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 74%

---


# Comprender las [!DNL Target]bibliotecas JavaScript

Implemente [!DNL Target] haciendo referencia a las bibliotecas [!DNL Adobe Target] (Adobe Experience Platform Web SDK, at.js o mbox.js) en sus páginas web.

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deberían migrar de mbox.js a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Diferencias entre las bibliotecas JavaScript de Destinatario {#section_40117C78C2F84FECAC4F1BA40CC4F171}

La siguiente tabla explica las diferencias entre las bibliotecas [!DNL Target] de JavaScript:

| Referencia sobre la biblioteca | Descripción |
|--- |--- |
| Adobe Experience Platform Web SDK | El [!UICONTROL SDK web de Adobe Experience Platform] le permite interactuar con los distintos servicios de [!DNL Experience Cloud] (incluido [!DNL Target]) a través de la red perimetral de Adobe Experience. Si decide migrar a [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) en la *Guía del SDK web*. Consulte [información general de Destinatario](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) para obtener información específica de [!DNL Target]. |
| at.js  | at.js reemplaza a mbox.js para implementaciones [!DNL [!DNL Target]].<br>Entre otros beneficios, at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad, evita advertencias de document.write en Google Chrome y proporciona mejores opciones de implementación en aplicaciones de una sola página.<br>Para obtener más información, consulte [Implementación at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |
| mbox.js | Antes de [!DNL Target]16.3.1 (marzo de 2016), [!DNL Target] requería una llamada a mbox.js para crear el mbox global necesario [!DNL Target] para suministrar actividades, rastrear clics y rastrear la mayoría de las métricas de éxito. Este archivo contiene las bibliotecas necesarias para todas sus actividades. No es necesario que mantenga una versión del archivo para cada actividad.<br>Si ya tiene mboxes envolventes en las páginas de una implementación anterior de [!DNL Target], podrá usarlos en la nueva interfaz. El archivo mbox.js actualizado sigue siendo necesario, pero estos mboxes pueden seleccionarse para actividades y modificarse con el Compositor de experiencias visuales.<br>[!DNL Target] Standard y Premium actualizan y complementan mbox.js con una referencia a un archivo target.js. El archivo target.js se aloja en Adobe. El archivo Target.js permite editar contenido en cualquier página con el Compositor de experiencias visuales aunque la página no contenga mboxes predefinidos. Deberá hacer referencia a este archivo en todas las páginas del sitio.<br>Para obtener más información, consulte [Implementación de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante**: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado. Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios.<br> |

## Impacto en el tiempo de carga de página de at.js y mbox.js {#section_16630CD0FF0A498EB596A51381366A5A}

Muchos clientes y consultores quieren conocer el impacto de [!DNL at.js] y [!DNL mbox.js] en el tiempo de carga de página, especialmente en el contexto de los nuevos usuarios frente a los que regresan. Lamentablemente, es difícil medir y ofrecer números concretos sobre la influencia de [!DNL at.js] o [!DNL mbox.js] en el tiempo de carga, ya que cada cliente dispone de una implementación diferente.

No obstante, si la API de visitante está presente en la página, podemos comprender mejor cómo influyen [!DNL at.js] y [!DNL mbox.js] en este tiempo de carga.

>[!NOTE]
>
>La API de visitante y [!DNL at.js] o [!DNL mbox.js] solo afectan al tiempo de carga de página cuando utiliza el mbox global (debido a la técnica de ocultación del cuerpo). Los mboxes regionales no se ven afectados por la integración del API de visitante.

La siguiente tabla describe la secuencia de acciones para los visitantes nuevos y los habituales:

### Visitantes nuevos

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js/mbox.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript de Target:

   * Crea una instancia del objeto Visitante.
   * La biblioteca de Target intenta recuperar datos de ID de visitante de Experience Cloud.
   * Como se trata de un nuevo visitante, el API de visitante activa una solicitud entre dominios dirigida a demdex.net.
   * Una vez recuperados los datos de ID de visitante de Experience Cloud, se activa una solicitud para Target.

### Visitantes que regresan

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js/mbox.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript de Target:

   * Crea una instancia del objeto Visitante.
   * La biblioteca de Target intenta recuperar datos de ID de visitante de Experience Cloud.
   * La API de visitante recupera datos de las cookies.
   * Una vez recuperados los datos de ID de visitante de Experience Cloud, se activa una solicitud para Target.

>[!NOTE]
>
>Para los nuevos visitantes, cuando la API de visitante está presente, Target debe actuar varias veces para garantizar que las solicitudes contengan datos de ID de visitante de Experience Cloud. Para los visitantes habituales, Target actúa únicamente para recuperar el contenido personalizado.

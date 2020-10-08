---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: Implemente Target haciendo referencia a las bibliotecas de Target (at.js o mbox.js) en sus páginas web.
title: Comprender las bibliotecas JavaScript de Target
feature: implementation general
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: 05bf843e5016d33ba436f6f24f5a0d05045d5129
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# Comprender las [!DNL Target]bibliotecas JavaScript{#understand-the-target-javascript-libraries}

Implemente [!DNL Target] haciendo referencia a las [!DNL Target]bibliotecas (at.js o mbox.js) en sus páginas web.

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deberían migrar de mbox.js a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Diferencias entre las dos bibliotecas {#section_40117C78C2F84FECAC4F1BA40CC4F171}

La tabla siguiente explica las diferencias entre las dos bibliotecas:

| Referencia sobre la biblioteca | Descripción |
|--- |--- |
| at.js | at.js reemplaza a mbox.js para [!DNL Target]implementaciones.<br>Entre otros beneficios, at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad, evita advertencias de document.write en Google Chrome y proporciona mejores opciones de implementación en aplicaciones de una sola página.<br>Para obtener más información, consulte [Implementación at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |
| mbox.js | Antes de [!DNL Target]16.3.1 (marzo de 2016), [!DNL Target] requería una llamada a mbox.js para crear el mbox global necesario [!DNL Target] para suministrar actividades, rastrear clics y rastrear la mayoría de las métricas de éxito. Este archivo contiene las bibliotecas necesarias para todas sus actividades. No es necesario que mantenga una versión del archivo para cada actividad.<br>Si ya tiene mboxes envolventes en las páginas de una implementación anterior de [!DNL Target], podrá usarlos en la nueva interfaz. El archivo mbox.js actualizado sigue siendo necesario, pero estos mboxes pueden seleccionarse para actividades y modificarse con el Compositor de experiencias visuales.<br>[!DNL Target] Standard y Premium actualizan y complementan mbox.js con una referencia a un archivo target.js. El archivo target.js se aloja en Adobe. El archivo Target.js permite editar contenido en cualquier página con el Compositor de experiencias visuales aunque la página no contenga mboxes predefinidos. Deberá hacer referencia a este archivo en todas las páginas del sitio.<br>Para obtener más información, consulte [Implementación de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante**: La biblioteca mbox.js sigue siendo compatible, pero sus características ya no se actualizarán. Todos los clientes deberían migrar a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

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

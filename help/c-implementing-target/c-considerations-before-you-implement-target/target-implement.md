---
keywords: document.write;target;implementar;implementar target;dtm;at.js;adobe experience platform web skd;aep web sdk;web sdk
description: Implemente bibliotecas JavaScript de Adobe [!DNL Target] by referencing the [!DNL Target] en sus páginas web.
title: Comprender las  [!DNL Target] bibliotecas JavaScript
feature: Implementación
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 19%

---


# Comprender las [!DNL Target]bibliotecas JavaScript

Implemente [!DNL Adobe Target] haciendo referencia a las [!DNL Adobe Target] bibliotecas (Adobe Experience Platform Web SDK o at.js) en sus páginas web.

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deben migrar a at.js o al [!UICONTROL SDK web de Adobe Experience Platform] antes del 31 de marzo de 2021.

## Diferencias entre las [!DNL Target] bibliotecas JavaScript {#section_40117C78C2F84FECAC4F1BA40CC4F171}

La siguiente tabla explica las diferencias entre las bibliotecas JavaScript [!DNL Target]:

| Referencia sobre la biblioteca | Descripción |
|--- |--- |
| SDK web de Adobe Experience Platform | El [!UICONTROL SDK web de Adobe Experience Platform] le permite interactuar con los distintos servicios de [!DNL Experience Cloud] (incluido [!DNL Target]) a través de la red perimetral de Adobe Experience. Si decide migrar al [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) en la *Guía del SDK web*. |
| at.js | at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad, evita advertencias de document.write en Google Chrome y proporciona mejores opciones de implementación en aplicaciones de una sola página. |

## Impacto en el tiempo de carga de página de at.js {#section_16630CD0FF0A498EB596A51381366A5A}

Muchos clientes y consultores desean conocer el impacto de [!DNL at.js] en el tiempo de carga de página, especialmente en el contexto de los usuarios nuevos frente a los que regresan. Lamentablemente, es difícil medir y ofrecer números concretos sobre cómo [!DNL at.js] influye en el tiempo de carga de página debido a la implementación de cada cliente.

Sin embargo, si la API de visitante está presente en la página, [!DNL Target] puede comprender mejor cómo [!DNL at.js] influye en el tiempo de carga de la página.

>[!NOTE]
>
>La API de visitante y [!DNL at.js] solo afectan al tiempo de carga de página cuando utiliza el mbox global (debido a la técnica de ocultación del cuerpo). Los mboxes regionales no se ven afectados por la integración del API de visitante.

La siguiente tabla describe la secuencia de acciones para los visitantes nuevos y los habituales:

### Visitantes nuevos

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript [!DNL Target]:

   * Crea una instancia del objeto Visitante.
   * La biblioteca [!DNL Target] intenta recuperar los datos del [!UICONTROL ID de visitante del Experience Cloud].
   * Para un nuevo visitante, la API de visitante activa una solicitud entre dominios a `demdex.net`.
   * Una vez recuperados los datos de [!UICONTROL ID de visitante del Experience Cloud], se activa una solicitud a Target.

### Visitantes que regresan

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript [!DNL Target]:

   * Crea una instancia del objeto Visitante.
   * La biblioteca [!DNL Target] intenta recuperar los datos del [!UICONTROL ID de visitante del Experience Cloud].
   * La API de visitante recupera datos de las cookies.
   * Una vez que se recuperan los datos de [!UICONTROL ID de visitante del Experience Cloud], se activa una solicitud a [!DNL Target].

>[!NOTE]
>
>Para los nuevos visitantes, cuando la API de visitante está presente, [!DNL Target] pasa por alto varias veces para asegurarse de que las solicitudes [!DNL Target] contienen [!UICONTROL datos de ID de visitante de Experience Cloud]. Para los visitantes que regresan, [!DNL Target] va únicamente a [!DNL Target] para recuperar el contenido personalizado.

---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: Si utiliza una versión antigua de at.js o mbox.js, debe especificar un servidor de seguimiento de Analytics para las actividades que usan Analytics for Target (A4T).
title: Uso de un servidor de seguimiento de Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 53%

---


# Uso de un servidor de seguimiento de Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

El depurador se debería visualizar en una página donde se vaya a publicar la actividad para garantizar que se seleccione el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. From the page on which you are creating your activity, open the [!DNL Adobe Experience Cloud Debugger].

   Si no ha instalado el depurador, consulte [Instalar Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. El campo se llama *Cookies de origen* o *Cookies de terceros*, depende de la implementación. El valor del servidor de seguimiento de estará en uno de estos formatos:[!DNL Analytics]

   * (en implementaciones CNAME)
   * (en implementaciones que no sean RDC)
   * (en implementaciones de RDC)

   *Company*[!DNL Analytics] representa el nombre de la compañía de , *metrics* es un ejemplo de un valor CNAME y *d1* es un ejemplo de un centro de datos de [!DNL Analytics]
1. Copie todo el contenido del campo.
1. En la sección [!UICONTROL Configuración de informes] de la pantalla [!UICONTROL Objetivos y configuración]**[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.


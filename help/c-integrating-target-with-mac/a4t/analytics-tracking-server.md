---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Cloud debugger;reporting source
description: Si utiliza una versión antigua de at.js o mbox.js, debe especificar un servidor de seguimiento de Analytics para las actividades que usan Analytics for Target (A4T).
title: Uso de un servidor de seguimiento de Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 1957e67c8502c06be950c7dafdcc3f6878f87065
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 24%

---


# Uso de un servidor de seguimiento de Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].
>
>El [!DNL Target] equipo admite at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que está ejecutando una versión compatible. For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## Obtenga el servidor de seguimiento de análisis mediante Adobe Experience Platform Debugger

El depurador se debería visualizar en una página donde se vaya a publicar la actividad para garantizar que se seleccione el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. From the page on which you are creating your activity, open the [!DNL Adobe Experience Platform Debugger].

   Si no ha instalado el depurador, consulte [Introducción al depurador](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)de Adobe Experience Platform.

   ![](assets/Screen_DebuggerTrackServ.png)

1. Haga clic en **[!UICONTROL Analytics]** en el menú de navegación de la izquierda.

   The analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **Servidor** de seguimiento de origen: Si el nombre de host de la solicitud coincide con el dominio en el que está, entonces es un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento de origen.
   * **Servidor** de seguimiento de terceros: Normalmente, un servidor de seguimiento de terceros es `[company].sc.omtrdc.net` donde la compañía es el nombre de la compañía, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones** de CNAME: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento de origen CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud propia de CNAME para una página http (no segura).

1. Copie todo el contenido del campo.
1. En la sección **[!UICONTROL Configuración de informes]** de la pantalla **[!UICONTROL Objetivos y configuración]****[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## Obtenga el servidor de seguimiento de Analytics mediante las herramientas para desarrolladores del explorador

Las herramientas para desarrolladores deben verse en una página en la que se enviará la actividad para asegurarse de seleccionar el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que está creando la actividad, abra las herramientas para desarrolladores del explorador (en Google Chrome, haga clic en las tres elipses verticales en la esquina superior derecha > Más herramientas > Herramientas para desarrolladores).

   ![Herramientas para desarrolladores de Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. Filtre para ‘/ss’ para mostrar las solicitudes de análisis.

   ![Herramientas para desarrolladores de Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools-2.png)

   El servidor de seguimiento es el nombre de host de la solicitud.

   * **Servidor** de seguimiento de origen: Si el nombre de host de la solicitud coincide con el dominio en el que está, entonces es un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento de origen.
   * **Servidor** de seguimiento de terceros: Normalmente, un servidor de seguimiento de terceros es `[company].sc.omtrdc.net` donde la compañía es el nombre de la compañía, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones** de CNAME: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento de origen CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud propia de CNAME para una página http (no segura).


---
keywords: servidor de seguimiento de analytics;A4T;depurador de Adobe Experience Cloud;depurador de Adobe Experience Platform;fuente de informes;herramientas para desarrolladores
description: Obtenga información sobre cómo especificar un servidor de seguimiento de Analytics para actividades que usan Analytics for [!DNL Target] (A4T) si usa una versión anterior de at.js.
title: ¿Cómo se utiliza un servidor de seguimiento de Analytics?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
TQID: https://experienceleague.adobe.com/mJM5kZPQfnWodzwQ3qDKxu1e1Oq2Y53fA2LpSB4SVSc
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 675
ht-degree: 15%

---

# Usar un servidor de seguimiento [!DNL Analytics]

Si utiliza una versión anterior de at.js, debe especificar un servidor de seguimiento [!DNL Analytics] para las actividades que usan [!DNL Adobe Analytics] para [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>No es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 0.9.1 (o posterior) de at.js. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Tracking Server] en la página [!UICONTROL Goals & Settings].
>
>El equipo [!DNL Target] admite at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que dispone de una versión compatible. Para obtener más información, consulte [Detalles de la versión de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank}.

Para asegurarse de que los datos de [!DNL Target] vayan a la ubicación correcta en [!DNL Analytics], A4T requiere que se envíe un servidor de seguimiento [!DNL Analytics] en todas las llamadas a Modstats desde [!DNL Target]. Para implementaciones que usan varios servidores de seguimiento, use [!DNL Adobe Experience Platform Debugger] o las herramientas para desarrolladores del explorador para determinar el servidor de seguimiento correcto para su actividad.

## Obtener el servidor de seguimiento [!DNL Analytics] mediante [!DNL Adobe Experience Platform Debugger]

El depurador debe verse en una página en la que se publique la actividad para garantizar que se selecciona el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando su actividad, abra [!DNL Adobe Experience Platform Debugger].

   Si no ha instalado el depurador, consulte [Información general de Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html?lang=es).

1. Haga clic en **[!UICONTROL Analytics]** en el menú de navegación de la izquierda.

   ![Imagen Screen_DebuggerTrackServ](assets/Screen_DebuggerTrackServ.png)

   El servidor de seguimiento [!DNL Analytics] se encuentra en la sección [!UICONTROL Hostname] de Debugger.

   * **Servidor de seguimiento propio**: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, se trata de un servidor de seguimiento propio. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento propio.
   * **Servidor de seguimiento de terceros**: Un servidor de seguimiento de terceros suele ser `[company].sc.omtrdc.net`, donde la empresa es el nombre de la empresa, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones CNAME**: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento propio CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Reporting Settings]** de la pantalla **[!UICONTROL Goal & Settings]** de su actividad, pegue la información del servidor de seguimiento en el campo **[!UICONTROL Tracking Server]**.

   >[!NOTE]
   >
   >Seleccione [!UICONTROL Analytics as the Reporting Source] para que la actividad del campo [!UICONTROL Tracking Server] esté disponible.

## Obtenga el servidor de seguimiento [!DNL Analytics] con las herramientas para desarrolladores del explorador

Las herramientas para desarrolladores deben verse en una página a la que se envíe la actividad para garantizar que selecciona el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando la actividad, abra las herramientas para desarrolladores del explorador (en Google Chrome, haga clic en las tres elipses verticales en la esquina superior derecha > Más herramientas > Herramientas para desarrolladores).

   ![herramientas para desarrolladores de Chrome](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Haga clic en la ficha **[!UICONTROL Network]**.

1. Filtre para `/ss,` con el fin de mostrar las [!DNL Analytics] solicitudes.

   ![Herramientas para desarrolladores de Chrome con /ss search](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   El servidor de seguimiento es el nombre de host de la solicitud.

   * **Servidor de seguimiento propio**: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, se trata de un servidor de seguimiento propio. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento propio.
   * **Servidor de seguimiento de terceros**: Un servidor de seguimiento de terceros suele ser `[company].sc.omtrdc.net`, donde la empresa es el nombre de la empresa, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones CNAME**: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento propio CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Reporting Settings]** de la pantalla **[!UICONTROL Goal & Settings]** de su actividad, pegue la información del servidor de seguimiento en el campo **[!UICONTROL Tracking Server]**.

   >[!NOTE]
   >
   >Seleccione [!UICONTROL Analytics as the Reporting Source] para que la actividad del campo [!UICONTROL Tracking Server] esté disponible.

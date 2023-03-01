---
keywords: servidor de seguimiento de analytics;A4T;depurador de Adobe Experience Cloud;depurador de Adobe Experience Platform;fuente de informes;herramientas para desarrolladores
description: Obtenga información sobre cómo especificar un servidor de seguimiento de Analytics para actividades que utilizan Analytics para [!DNL Target] (A4T) si utiliza una versión anterior de at.js.
title: ¿Cómo se utiliza un servidor de seguimiento de Analytics?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 22%

---

# Utilice un [!DNL Analytics] servidor de seguimiento

Si utiliza una versión anterior de at.js, debe especificar una [!DNL Analytics] servidor de seguimiento para actividades que utilizan [!DNL Adobe Analytics] para [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>No es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 0.9.1 (o posterior) de at.js. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].
>
>El [!DNL Target] el equipo admite at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que dispone de una versión compatible. Para obtener más información, consulte [detalles de la versión de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

Para garantizar que los datos de [!DNL Target] va a la ubicación correcta en [!DNL Analytics], A4T requiere un [!DNL Analytics] Servidor de seguimiento para enviar en todas las llamadas a Modstats desde [!DNL Target]. Para implementaciones que utilizan varios servidores de seguimiento, utilice la variable [!DNL Adobe Experience Platform Debugger] o las herramientas para desarrolladores del explorador para determinar el servidor de seguimiento correcto para su actividad.

## Obtenga la [!DNL Analytics] servidor de seguimiento con [!DNL Adobe Experience Platform Debugger]

El depurador debe verse en una página en la que se publique la actividad para garantizar que se selecciona el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando la actividad, abra el [!DNL Adobe Experience Platform Debugger].

   Si no ha instalado el depurador, consulte [Información general de Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. Clic **[!UICONTROL Analytics]** en el menú de navegación izquierdo.

   ![Imagen Screen_DebuggerTrackServ](assets/Screen_DebuggerTrackServ.png)

   El [!DNL Analytics] El servidor de seguimiento de se encuentra en [!UICONTROL Hostname] de Debugger.

   * **Servidor de seguimiento propio**: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, se trata de un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento propio.
   * **Servidor de seguimiento de terceros**: Un servidor de seguimiento de terceros suele ser `[company].sc.omtrdc.net` donde la compañía es el nombre de su compañía, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones CNAME**: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento CNAME de origen para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Configuración de informes]** de la pantalla **[!UICONTROL Objetivos y configuración]****[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >Seleccionar [!UICONTROL Analytics como fuente de informes] para su actividad de [!UICONTROL Servidor de seguimiento] campo que debe estar disponible.

## Obtenga la [!DNL Analytics] servidor de seguimiento con las herramientas para desarrolladores del explorador

Las herramientas para desarrolladores deben verse en una página a la que se envíe la actividad para garantizar que selecciona el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando la actividad, abra las herramientas para desarrolladores del explorador (en Google Chrome, haga clic en las tres elipses verticales en la esquina superior derecha > Más herramientas > Herramientas para desarrolladores).

   ![Herramientas para desarrolladores Chrome](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Haga clic en **[!UICONTROL Red]** pestaña.

1. Filtrar por `/ss,` para mostrar el [!DNL Analytics] solicitudes.

   ![Herramientas para desarrolladores Chrome con búsqueda /ss](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   El servidor de seguimiento es el nombre de host de la solicitud.

   * **Servidor de seguimiento propio**: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, se trata de un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento propio.
   * **Servidor de seguimiento de terceros**: Un servidor de seguimiento de terceros suele ser `[company].sc.omtrdc.net` donde la compañía es el nombre de su compañía, pero siempre termina en `sc.omtrdc.net`.
   * **Implementaciones CNAME**: `sstats.adobe.com` es un ejemplo de un servidor de seguimiento CNAME de origen para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Configuración de informes]** de la pantalla **[!UICONTROL Objetivos y configuración]****[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >Seleccionar [!UICONTROL Analytics como fuente de informes] para su actividad de [!UICONTROL Servidor de seguimiento] campo que debe estar disponible.

---
keywords: servidor de seguimiento de analytics;A4T;Adobe Experience Cloud Debugger;Adobe Experience Platform Debugger;fuente de informes;herramientas para desarrolladores
description: 'Obtenga información sobre cómo especificar un servidor de seguimiento de Analytics para actividades que utilicen Analytics for Target (A4T) si utiliza una versión anterior de at.js o mbox.js. '
title: ¿Cómo utilizo un servidor de seguimiento de Analytics?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 20%

---


# Uso de un servidor de seguimiento de Analytics

Si utiliza una versión anterior de at.js o mbox.js, debe especificar un servidor de seguimiento de Analytics para las actividades que usan [!DNL Adobe Analytics] para [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>No es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 61 (o posterior) de mbox.js o la versión 0.9.1 (o posterior) de at.js . La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].
>
>El equipo [!DNL Target] es compatible con at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que está ejecutando una versión compatible. Para obtener más información, consulte [Detalles de la versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Para garantizar que los datos de [!DNL Target] se dirijan a la ubicación correcta en [!DNL Analytics], A4T requiere que se envíe un servidor de seguimiento de Analytics en todas las llamadas a Modstats desde [!DNL Target]. En implementaciones que usan varios servidores de seguimiento, utilice [!DNL Adobe Experience Platform Debugger] o las herramientas para desarrolladores del explorador para determinar el servidor de seguimiento correcto para su actividad.

## Obtención del servidor de seguimiento de Analytics mediante Adobe Experience Platform Debugger

El depurador debe verse en una página en la que se envíe la actividad para asegurarse de seleccionar el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando la actividad, abra [!DNL Adobe Experience Platform Debugger].

   Si no ha instalado el depurador, consulte [Introducción a Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Haga clic en **[!UICONTROL Analytics]** en el menú de navegación de la izquierda.

   El servidor de seguimiento de Analytics se encuentra en la sección [!UICONTROL Nombre de host] del depurador.

   * **Servidor** de seguimiento de origen: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, entonces es un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento de origen.
   * **Servidor** de seguimiento de terceros: Un servidor de seguimiento de terceros suele ser  `[company].sc.omtrdc.net` donde la empresa es el nombre de su empresa, pero siempre termina en  `sc.omtrdc.net`.
   * **Implementaciones** CNAME:  `sstats.adobe.com` es un ejemplo de servidor de seguimiento propio CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Configuración de informes]** de la pantalla **[!UICONTROL Objetivos y configuración]****[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >Seleccione [!UICONTROL Analytics como Fuente de informes] para la actividad del campo [!UICONTROL Servidor de seguimiento] que estará disponible.

## Obtenga el servidor de seguimiento de Analytics con las herramientas para desarrolladores del explorador

Las herramientas para desarrolladores deben verse en una página en la que se envíe la actividad para asegurarse de seleccionar el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. En la página en la que esté creando la actividad, abra las herramientas para desarrolladores del explorador (en Google Chrome, haga clic en los tres puntos verticales en la esquina superior derecha > Más herramientas > Herramientas para desarrolladores).

   ![Herramientas para desarrolladores Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Haga clic en la pestaña **[!UICONTROL Network]**.

1. Filtre por `/ss,` para mostrar las solicitudes de Analytics.

   ![Herramientas para desarrolladores Chrome con búsqueda /ss](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   El servidor de seguimiento es el nombre de host de la solicitud.

   * **Servidor** de seguimiento de origen: Si el nombre de host de la solicitud coincide con el dominio en el que se encuentra, entonces es un servidor de seguimiento de origen. Por ejemplo, si está en `adobe.com`, `adobe.com` es el servidor de seguimiento de origen.
   * **Servidor** de seguimiento de terceros: Un servidor de seguimiento de terceros suele ser  `[company].sc.omtrdc.net` donde la empresa es el nombre de su empresa, pero siempre termina en  `sc.omtrdc.net`.
   * **Implementaciones** CNAME:  `sstats.adobe.com` es un ejemplo de servidor de seguimiento propio CNAME para una solicitud https (segura). `stats.adobe.com` es un ejemplo de una solicitud de origen CNAME para una página http (no segura).

1. Copie todo el contenido del campo.

1. En la sección **[!UICONTROL Configuración de informes]** de la pantalla **[!UICONTROL Objetivos y configuración]****[!UICONTROL de la actividad, pegue la información sobre el servidor de seguimiento en el campo Servidor de seguimiento.]**

   >[!NOTE]
   >
   >Seleccione [!UICONTROL Analytics como Fuente de informes] para la actividad del campo [!UICONTROL Servidor de seguimiento] que estará disponible.


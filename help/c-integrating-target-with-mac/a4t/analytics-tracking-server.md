---
keywords: servidor de seguimiento de analytics;A4T;depurador de Adobe Experience Cloud;fuente de informes
description: Si utiliza una versión antigua de at.js o mbox.js, debe especificar un servidor de seguimiento de Analytics para las actividades que usan Analytics for Target (A4T).
title: Uso de un servidor de seguimiento de Analytics
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Uso de un servidor de seguimiento de Analytics{#use-an-analytics-tracking-server}

Si utiliza una versión antigua de at.js o mbox.js, debe especificar un servidor de seguimiento de Analytics para las actividades que usan Analytics for Target (A4T).

>[!NOTE]
>
>Si usa Adobe Analytics como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en las versiones 61 (o posterior) de mbox.js y 0.9.1 (o posterior) de at.js. La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

Para garantizar que los datos de Target lleguen a la ubicación correcta de Analytics, A4T requiere que se envíe un servidor de seguimiento de Analytics en todas las llamadas que se realicen a Modstats desde Target. En implementaciones que usan varios servidores de seguimiento, se puede utilizar Adobe Experience Cloud Debugger para determinar el servidor de seguimiento adecuado para su actividad.

El depurador se debería visualizar en una página donde se vaya a publicar la actividad para garantizar que se seleccione el servidor de seguimiento correcto. También se puede especificar un servidor de seguimiento predeterminado en cada cuenta. Póngase en contacto con el Servicio de atención al cliente para especificar o modificar el servidor predeterminado.

1. Desde la página en la que esté creando la actividad, abra Adobe Experience Cloud Debugger.

   Si no ha instalado el depurador, consulte [Instalación de Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   El servidor de seguimiento de Analytics se encuentra en la sección Imagen de SiteCatalyst del depurador. El campo se llama *Cookies de origen* o *Cookies de terceros*, depende de la implementación. El valor del servidor de seguimiento de Analytics estará en uno de estos formatos:

   * (en implementaciones CNAME)
   * (en implementaciones que no sean RDC)
   * (en implementaciones de RDC)
   *Company* representa el nombre de la compañía de Analytics, *metrics* es un ejemplo de un valor CNAME y *d1* es un ejemplo de un centro de datos de Analytics.
1. Copie todo el contenido del campo.
1. En la sección [!UICONTROL Configuración de informes] de la pantalla [!UICONTROL Objetivos y configuración]**de la actividad, pegue la información sobre el servidor de seguimiento en el campo[!UICONTROL Servidor de seguimiento.]**

   >[!NOTE]
   >
   >Tiene que seleccionar Adobe Analytics como fuente de informes en la actividad para que el campo Servidor de seguimiento esté disponible.


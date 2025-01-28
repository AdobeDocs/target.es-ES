---
keywords: crear criterios personalizados;algoritmos;criterios;criterios de recomendaciones;csv;ftp;cargar csv
description: Aprenda a cargar un archivo CSV para personalizar las recomendaciones en el Adobe  [!DNL Target] Recommendations.
title: ¿Cómo se cargan criterios personalizados en  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: ce974152-c83e-46cb-b1cd-c5e2d10c5436
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 33%

---

# Cargar criterios personalizados

Cargue un archivo CSV para personalizar las recomendaciones en [!DNL Adobe Target].

Existen varias formas de llegar a la pantalla [!UICONTROL Create New Criteria]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Cuando crea una actividad [!DNL Recommendations] con el [!UICONTROL Visual Experience Composer] (VEC), se le redirige inmediatamente a la pantalla [!UICONTROL Select Criteria] después de seleccionar un elemento en la página y hacer clic en [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] o [!UICONTROL Insert Recommendations After]. Puede seleccionar un criterio disponible o hacer clic en **[!UICONTROL Create Criteria]**. Si crea un nuevo criterio, puede guardarlo para utilizarlo con otras [!DNL Recommendations] actividades. Para obtener más información, consulte [Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una actividad [!DNL Recommendations], haga clic en un cuadro [!UICONTROL Recommendations Location] de la página y seleccione **[!UICONTROL Change Criteria]**. En la pantalla [!UICONTROL Select Criteria], haga clic en **[!UICONTROL Create Criteria]**. Puede guardar los nuevos criterios para usarlos con otras [!DNL Recommendations] actividades.

Los siguientes pasos dan por sentado que tiene acceso a la pantalla de [!UICONTROL Create New Criteria] mediante el primer método: la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Rellene la información de la sección [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la lista desplegable **[!UICONTROL Select Algorithm Type]**, seleccione **[!UICONTROL Custom Criteria]**.

1. En la lista desplegable **[!UICONTROL Algorithm]**, seleccione **[!UICONTROL Custom Algorithm]**.

   >[!NOTE]
   >
   >Los pasos anteriores hacen que la sección [!UICONTROL Upload CSV] se muestre en la parte inferior del cuadro de diálogo [!UICONTROL Create Criteria].

1. (Condicional) Rellene la información de la sección [Contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Rellene la información de la sección [Reglas de inclusión](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. En la sección **[!UICONTROL Upload CSV]**, seleccione el **[!UICONTROL Location]** de su archivo CSV.

El archivo CSV debe tener el formato correcto para que se pueda cargar. Haga clic en **[!UICONTROL Download the CSV template]** para obtener un archivo CSV con el formato correcto.

Tiene dos opciones de ubicación:

    * **FTP:** Para cargar el archivo CSV desde un servidor FTP, seleccione **[!UICONTROL FTP]** y escriba la información requerida. Puede utilizar SSL, que utiliza el protocolo FTPS para transferir el archivo CSV de forma segura.
    
    * **URL:** Para cargar el archivo CSV desde una dirección URL, seleccione **[!UICONTROL URL]** y, a continuación, escriba una dirección URL de fuente.

1. Haga clic en **[!UICONTROL Create]**.

## Consideraciones

* Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

* Las actualizaciones de criterios personalizados son “acumulativas” de forma predeterminada. Los nuevos pares de clave-valor especificados en el archivo de carga CSV sobrescribirán los pares existentes. Los pares de clave-valor existentes que no tengan claves especificadas en la carga de CSV seguirán estando disponibles para su envío y caducarán en 31 días desde la última vez que se carguen como parte del archivo CSV.

  Póngase en contacto con el servicio de atención al cliente si desea activar la configuración que descarta los resultados existentes que no están incluidos en la siguiente carga CSV. Si esta configuración está habilitada, solo están disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

* Los criterios personalizados se actualizan una vez cada 24 horas.

  Puede ver el estado de carga y sincronización de los criterios personalizados cargados para cada criterio en la página [!UICONTROL Recommendations] > [!UICONTROL Criteria]. También puede ver el estado en el cuadro de diálogo [!UICONTROL Edit] al editar criterios personalizados.

* El flujo para una carga sin errores debe ser [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* Los siguientes son posibles mensajes de error que podría recibir si [!DNL Target] encuentra un problema con la carga:

  | Mensaje de error | Detalles |
  |--- |--- |
  | Error desconocido | Indica un error técnico interno. |
  | Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, lo que reinicia el proceso de descarga del archivo. |
  | Servidor no encontrado | Proporcione una IP o un nombre de servidor que sea visible en Internet. |
  | Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
  | No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
  | No se ha encontrado el archivo | Indique el nombre de un archivo que exista en el servidor del directorio indicado. |

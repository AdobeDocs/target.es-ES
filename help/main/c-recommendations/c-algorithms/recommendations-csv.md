---
keywords: crear criterios personalizados;algoritmos;criterios;criterios de recomendaciones;csv;ftp;cargar csv
description: Aprenda a cargar un archivo CSV para personalizar las recomendaciones en Adobe [!DNL Target] Recommendations.
title: ¿Cómo se cargan criterios personalizados en  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 32%

---

# Cargar criterios personalizados

Cargue un archivo CSV para personalizar las recomendaciones en [!DNL Adobe Target].

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Cuando crea una actividad [!DNL Recommendations] con el [!UICONTROL Compositor de experiencias visuales] (VEC), se le redirige inmediatamente a la pantalla [!UICONTROL Seleccionar criterios] después de seleccionar un elemento en su página y hacer clic en [!UICONTROL Reemplazar con Recommendations], [!UICONTROL Insertar Recommendations antes] o [!UICONTROL Insertar Recommendations después]. Puede seleccionar un criterio disponible o hacer clic en **[!UICONTROL Crear criterio]**. Si crea un nuevo criterio, puede guardarlo para utilizarlo con otras [!DNL Recommendations] actividades. Para obtener más información, consulte [Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una actividad [!DNL Recommendations], haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear criterios]**. Puede guardar los nuevos criterios para usarlos con otras [!DNL Recommendations] actividades.

Los siguientes pasos dan por hecho que se accede a la pantalla [!UICONTROL Crear nuevos criterios] mediante el primer método: la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

1. Rellene la información de la sección [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la lista desplegable **[!UICONTROL Seleccionar tipo de algoritmo]**, seleccione **[!UICONTROL Criterios personalizados]**.

1. En la lista desplegable **[!UICONTROL Algoritmo]**, seleccione **[!UICONTROL Algoritmo personalizado]**.

   >[!NOTE]
   >
   >Los pasos anteriores hacen que la sección [!UICONTROL Cargar CSV] se muestre en la parte inferior del cuadro de diálogo [!UICONTROL Crear criterios].

1. (Condicional) Rellene la información de la sección [Contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Rellene la información de la sección [Reglas de inclusión](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. En la sección **[!UICONTROL Cargar CSV]**, seleccione la **[!UICONTROL ubicación]** de su archivo CSV.

   El archivo CSV debe tener el formato correcto para que se pueda cargar. Haga clic en **[!UICONTROL Descargar plantilla CSV]** para obtener un archivo CSV con el formato correcto.

   Tiene dos opciones de ubicación:

   * **FTP:** Para cargar el archivo CSV desde un servidor FTP, seleccione **[!UICONTROL FTP]** y escriba la información requerida. Puede utilizar SSL, que utiliza el protocolo FTPS para transferir el archivo CSV de forma segura.

   * **URL:** Para cargar el archivo CSV desde una dirección URL, selecciona **[!UICONTROL URL]** y después escribe una dirección URL de fuente.

1. Haga clic en **[!UICONTROL Crear]**.

## Consideraciones

* Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

* Las actualizaciones de criterios personalizados son “acumulativas” de forma predeterminada. Los nuevos pares de clave-valor especificados en el archivo de carga CSV sobrescribirán los pares existentes. Los pares de clave-valor existentes que no tengan claves especificadas en la carga de CSV seguirán estando disponibles para su envío y caducarán en 31 días desde la última vez que se carguen como parte del archivo CSV.

  Póngase en contacto con el servicio de atención al cliente si desea habilitar la configuración que descarta los resultados existentes que no están incluidos en la siguiente carga CSV. Si esta configuración está habilitada, solo están disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

* Los criterios personalizados se actualizan una vez cada 24 horas.

  Puede ver el estado de carga y sincronización de los criterios personalizados cargados para cada criterio en la página [!UICONTROL Recommendations] > [!UICONTROL Criterios]. También puede ver el estado en el cuadro de diálogo [!UICONTROL Editar] al editar criterios personalizados.

* El flujo para una carga sin errores debe ser [!UICONTROL Programada] > [!UICONTROL Descargando archivo de fuente] > [!UICONTROL Importando] > [!UICONTROL Correcta].

* Los siguientes son posibles mensajes de error que podría recibir si [!DNL Target] encuentra un problema con la carga:

  | Mensaje de error | Detalles |
  |--- |--- |
  | Error desconocido | Indica un error técnico interno. |
  | Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, lo que reinicia el proceso de descarga del archivo. |
  | Servidor no encontrado | Proporcione una IP o un nombre de servidor que sea visible en Internet. |
  | Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
  | No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
  | No se ha encontrado el archivo | Indique el nombre de un archivo que exista en el servidor del directorio indicado. |

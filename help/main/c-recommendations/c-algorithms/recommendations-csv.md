---
keywords: crear criterios personalizados;algoritmos;criterios;criterios de recomendaciones;csv;ftp;sftp;cargar csv
description: Obtenga información sobre cómo cargar un archivo CSV para personalizar recomendaciones en Adobe [!DNL Target] Recommendations.
title: Cargar criterios personalizados
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: 'https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 14%
---
# Cargar criterios personalizados {#upload-custom-criteria}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a cargar un archivo CSV de recomendaciones para crear criterios personalizados en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Los criterios personalizados utilizan un archivo CSV de recomendaciones que se ha cargado a [!DNL Target]. Esto permite que las recomendaciones que se calculan fuera de [!DNL Target] se entreguen en [!DNL Recommendations] actividades. Para obtener más información sobre cómo funcionan los criterios personalizados, consulte [La ciencia detrás de los algoritmos de recomendaciones de Target](/help/main/c-recommendations/c-algorithms/recommendations-algorithms.md).

Los criterios personalizados se crean a partir de la pantalla **[!UICONTROL Crear nuevos criterios]**. Para ver las formas de llegar a esta pantalla, consulte [Acceso a la pantalla Crear nuevos criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#access-create-criteria). Los siguientes pasos comienzan desde la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

   ![Página de criterios con el menú Crear criterios abierto, que muestra Crear criterio y Crear secuencia de criterios](../assets/criteria_create_1.png)

1. Rellene la información de la sección [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la lista desplegable **[!UICONTROL Seleccionar tipo de algoritmo]**, seleccione **[!UICONTROL Criterios personalizados]**. En la lista desplegable **[!UICONTROL Algoritmo]**, seleccione **[!UICONTROL Algoritmo personalizado]**.

   ![Sección de algoritmo de Recommendations con criterios personalizados como tipo de algoritmo y algoritmo personalizado como algoritmo](../assets/criteria_create_9.png)

1. (Condicional) Rellene la información de las secciones [Contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) y [Reglas de inclusión](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. En la sección **[!UICONTROL Cargar CSV]**, seleccione la **[!UICONTROL ubicación]** del archivo CSV.

   El archivo CSV debe tener el formato correcto para que se pueda cargar. Para obtener un archivo CSV con el formato correcto, haga clic en **[!UICONTROL Descargar la plantilla CSV]**.

   Estas son las opciones de ubicación disponibles:

   * **FTP**: Para cargar el archivo CSV desde un servidor FTP, selecciona **[!UICONTROL FTP]** y, a continuación, introduce la información requerida. Se puede utilizar SSL, que utiliza el protocolo FTPS para transferir el archivo CSV de forma segura.

   * **SFTP**: Para cargar el archivo CSV desde un servidor SFTP, seleccione **[!UICONTROL SFTP]** y, a continuación, introduzca el nombre de host o la dirección IP, el puerto (predeterminado 22), el nombre de usuario, una contraseña o una clave privada SSH, el directorio y el nombre de archivo. Para obtener más información, consulte [Configuración del servidor SFTP admitida](/help/main/c-recommendations/c-products/feeds.md#steps).

     SFTP no cambia el formato CSV de criterios personalizados. Usar el formato `# Key,Recommendation_1,...`. Un archivo CSV con el formato de un tipo de fuente diferente provoca que la importación falle.

   * **URL**: para cargar el archivo CSV desde una dirección URL, selecciona **[!UICONTROL URL]** y, a continuación, escribe una dirección URL de fuente.

     ![Cargar sección CSV con las opciones de ubicación FTP, SFTP y URL resaltadas y SFTP seleccionado](../assets/criteria_create_10.png)

1. Haga clic en **[!UICONTROL Crear]**.

## Consideraciones

* Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

* Las actualizaciones de criterios personalizados son &quot;acumulativas&quot; de forma predeterminada. Los nuevos pares de clave-valor en el archivo de carga CSV sobrescriben los pares existentes. Los pares de clave-valor existentes cuyas claves no están en la carga de CSV permanecen disponibles para su envío y caducan 31 días después de la última vez que se cargaron como parte del archivo CSV.

  Para descartar los resultados existentes que no se incluyan en la siguiente carga de CSV, póngase en contacto con Atención al cliente para habilitar la configuración correspondiente. Cuando esta configuración está habilitada, solo están disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

* Los criterios personalizados se actualizan una vez cada 24 horas.

  El estado de carga y sincronización de cada carga de criterios personalizados se muestra en la página **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**. El estado también se muestra en el cuadro de diálogo **[!UICONTROL Editar]** cuando se editan los criterios personalizados.

* El flujo para una carga sin errores es **[!UICONTROL Programada]** > **[!UICONTROL Descargando archivo de fuente]** > **[!UICONTROL Importando]** > **[!UICONTROL Correcta]**.

* Si [!DNL Target] encuentra un problema con la carga, es posible que aparezcan los siguientes mensajes de error:

  | Mensaje de error | Detalles |
  |--- |--- |
  | Error desconocido | Indica un error técnico interno. |
  | Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, lo que reinicia el proceso de descarga del archivo. |
  | Servidor no encontrado | Proporcione una IP o un nombre de host visibles en Internet. |
  | Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
  | No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
  | No se ha encontrado el archivo | Proporcione el nombre de un archivo que exista en el servidor en el directorio especificado. |

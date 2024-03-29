---
keywords: crear criterios personalizados;algoritmos;criterios;criterios de recomendaciones;csv;ftp;cargar csv
description: Obtenga información sobre cómo cargar un archivo CSV para personalizar las recomendaciones en Adobe [!DNL Target] Recommendations.
title: ¿Cómo se cargan criterios personalizados en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 39%

---

# Cargar criterios personalizados

Cargue un archivo CSV para personalizar las recomendaciones en [!DNL Adobe Target].

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En el **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** pantalla de la biblioteca, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Al crear un [!DNL Recommendations] actividad que utiliza el [!UICONTROL Compositor de experiencias visuales] (VEC), se le redirige inmediatamente al [!UICONTROL Seleccionar criterios] después de seleccionar un elemento en la página y hacer clic en [!UICONTROL Reemplazar con Recommendations], [!UICONTROL Insertar Recommendations antes], o [!UICONTROL Insertar Recommendations después]. A continuación, puede seleccionar un criterio disponible o hacer clic en **[!UICONTROL Crear criterios]**. Si crea un nuevo criterio, puede guardarlo para utilizarlo con otros [!DNL Recommendations] actividades. Para obtener más información, consulte [Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una [!DNL Recommendations]actividad, haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. En el [!UICONTROL Seleccionar criterios] , haga clic en **[!UICONTROL Crear criterios]**. Puede guardar los nuevos criterios para usarlos con otros [!DNL Recommendations] actividades.

Los siguientes pasos suponen que se accede al [!UICONTROL Crear nuevos criterios] mediante el primer método: la función **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** pantalla de la biblioteca.

1. Clic **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]**.

1. Rellene la información de la [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) sección.

   1. Desde el **[!UICONTROL Seleccionar algoritmo]** Escriba la lista desplegable y seleccione **[!UICONTROL Criterios personalizados]**.

   1. Desde el **[!UICONTROL Algoritmo]** , seleccione la opción **[!UICONTROL Algoritmo personalizado]**.

      >[!NOTE]
      >
      >Los pasos anteriores provocan el [!UICONTROL Cargar CSV] sección que se mostrará en la parte inferior de [!UICONTROL Crear nuevos criterios] Cuadro de diálogo.

1. (Condicional) Rellene la información de la [Contenido de copia](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) sección.

1. (Condicional) Rellene la información de la [Reglas de inclusión](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) sección.

1. En el **[!UICONTROL Cargar CSV]** , seleccione la **[!UICONTROL Ubicación]** del archivo CSV.

   ![Sección Cargar CSV](assets/upload-csv.png)

   El archivo CSV debe tener el formato correcto para que se pueda cargar. Haga clic en **[!UICONTROL Descargar plantilla CSV]** para obtener un archivo CSV con el formato correcto.

   Tiene dos opciones de ubicación:

   * **FTP:** para cargar el archivo CSV desde un servidor FTP, seleccione **[!UICONTROL FTP]** e introduzca la información requerida. Puede utilizar SSL, que utiliza el protocolo FTPS para transferir el archivo CSV de forma segura.
   * **URL:** Para cargar el archivo CSV desde una dirección URL, seleccione **[!UICONTROL URL]**, luego ingrese una URL de fuente.

1. Haga clic en **[!UICONTROL Guardar]**.

## Consideraciones

* Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

* Las actualizaciones de criterios personalizados son “acumulativas” de forma predeterminada. Los nuevos pares de clave-valor especificados en el archivo de carga CSV sobrescribirán los pares existentes. Los pares de clave-valor existentes que no tengan claves especificadas en la carga de CSV seguirán estando disponibles para su envío y caducarán en 31 días desde la última vez que se carguen como parte del archivo CSV.

   Póngase en contacto con el servicio de atención al cliente si desea activar la configuración que descarta los resultados existentes que no están incluidos en la siguiente carga CSV. Si esta configuración está habilitada, solo están disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

* Los criterios personalizados se actualizan una vez cada 24 horas.

   Puede ver el estado de carga y sincronización de los criterios personalizados en la parte inferior de cada tarjeta de criterios en la [!UICONTROL Recommendations] > [!UICONTROL Criterios] página. También puede ver el estado en la variable [!UICONTROL Editar] al editar criterios personalizados.

* El flujo para una carga sin errores debe ser [!UICONTROL Programado] > [!UICONTROL Descargando archivo de fuente] > [!UICONTROL Importando] > [!UICONTROL Correcto].

* Los siguientes son posibles mensajes de error que podría recibir si [!DNL Target] encuentra un problema con la carga:

   | Mensaje de error | Detalles |
   |--- |--- |
   | Error desconocido | Indica un error técnico interno. |
   | Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, que reinicia el proceso de descarga del archivo. |
   | Servidor no encontrado | Proporcione una IP o un nombre de servidor que sea visible en Internet. |
   | Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
   | No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
   | No se ha encontrado el archivo | Indique el nombre de un archivo que exista en el servidor del directorio indicado. |

## Vídeo de formación: Crear criterios en Recommendations (12:33) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la siguiente información (los detalles sobre cómo cargar criterios personalizados comienzan a las 11:43):

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)

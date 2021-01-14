---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Cargue un archivo CSV para personalizar las recomendaciones.
title: Cargar criterios personalizados
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) Cargar criterios personalizados{#upload-custom-criteria}

Cargue un archivo CSV para personalizar las recomendaciones.

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Al crear una actividad [!DNL Recommendations] mediante el [!UICONTROL Compositor de experiencias visuales] (VEC), se le dirigirá inmediatamente a la pantalla [!UICONTROL Seleccionar criterios] después de seleccionar un elemento en la página y hacer clic en [!UICONTROL Reemplazar con Recommendations], [!UICONTROL Insertar Recommendations antes de] o [!UICONTROL Insertar Después de]. Luego puede seleccionar un criterio disponible o puede hacer clic en **[!UICONTROL Crear criterios]**. Si crea un nuevo criterio, tiene la opción de guardar los criterios para usarlos con otras [!DNL Recommendations] actividades. Para obtener más información, consulte [Creación de una actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una [!DNL Recommendations]actividad, haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear criterios]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!DNL Recommendations].

Los siguientes pasos suponen que accede a la pantalla [!UICONTROL Crear nuevos criterios] mediante el primer método: la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Cargar criterios personalizados]**.

1. Rellene la información de la sección [Información básica](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Rellene la información de la sección [Fuente de datos](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source).

1. Rellene la información de la sección [Contenido](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Rellene la información de la sección [Similitud de contenido](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

1. (Condicional) Rellene la información de la sección [Reglas de inclusión](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. (Condicional) Rellene la información de la sección [Ponderación de atributos](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting).

1. En la sección **[!UICONTROL Cargar CSV]**, seleccione la **[!UICONTROL Ubicación]** del archivo CSV.

   ![Cargar sección CSV](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   El archivo CSV debe tener el formato correcto para que se pueda cargar. Haga clic en **[!UICONTROL Descargar plantilla CSV]** para obtener un archivo CSV con el formato correcto.

   Tiene dos opciones de ubicación:

   * **FTP:** para cargar el archivo CSV desde un servidor FTP, seleccione **[!UICONTROL FTP]** e introduzca la información requerida. Tiene la opción de usar SSL, que emplea el protocolo FTPS para transferir el archivo CSV de forma segura.
   * **URL:** para cargar el archivo CSV desde una URL, seleccione  **[!UICONTROL URL]** y, a continuación, introduzca una URL de fuente.

1. Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

Las actualizaciones de criterios personalizados son “acumulativas” de forma predeterminada. Los nuevos pares de clave-valor especificados en el archivo de carga CSV sobrescribirán los pares existentes. Los pares de clave-valor existentes que no tengan claves especificadas en la carga de CSV seguirán estando disponibles para su envío y caducarán en 31 días desde la última vez que se carguen como parte del archivo CSV.

Póngase en contacto con el servicio de atención al cliente si desea activar la configuración que descarta los resultados existentes que no están incluidos en la siguiente carga CSV. Si esta opción está activada, solo estarán disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

Los criterios personalizados se actualizan una vez cada 24 horas.

Puede ver el estado de carga y sincronización de los criterios personalizados en la parte inferior de cada tarjeta de criterios, en la página Recommendations > Criterios. También puede ver el estado en el cuadro de diálogo de edición al editar los criterios personalizados.

El flujo de una carga sin errores debería ser Programado > Descargando el archivo de fuente > Importando > Correcto.

Los siguientes son posibles mensajes de error que puede recibir si [!DNL Target] encuentra un problema con la carga:

| Mensaje de error | Detalles |
|--- |--- |
| Error desconocido | Indica un error técnico interno. |
| Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, que reiniciará el proceso de descarga del archivo. |
| Servidor no encontrado | Proporcione una IP o un nombre de servidor que sea visible en Internet. |
| Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
| No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
| No se ha encontrado el archivo | Indique el nombre de un archivo que exista en el servidor del directorio indicado. |

## Vídeo de formación: Crear criterios en Recommendations (12:33)  ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la siguiente información (los detalles sobre la carga de criterios personalizados comienzan a las 11:43):

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
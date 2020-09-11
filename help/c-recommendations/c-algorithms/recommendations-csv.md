---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Cargue un archivo CSV para personalizar las recomendaciones.
title: Cargar criterios personalizados
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 66b3c42181daf582c9b3bee1f83a2229b823c5c3
workflow-type: tm+mt
source-wordcount: '1873'
ht-degree: 66%

---


# ![PREMIUM](/help/assets/premium.png) Cargar criterios personalizados{#upload-custom-criteria}

Cargue un archivo CSV para personalizar las recomendaciones.

## Acceso a la pantalla Crear nuevo criterio

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Al crear una [!DNL Recommendations] actividad con el Compositor [!UICONTROL de experiencias] visuales (VEC), se le dirigirá inmediatamente a la pantalla [!UICONTROL Seleccionar criterios] después de seleccionar un elemento en la página y hacer clic en [!UICONTROL Reemplazar con Recommendations], [!UICONTROL Insertar Recommendations antes]o Insertar Recommendations después. Luego puede seleccionar un criterio disponible o puede hacer clic en **[!UICONTROL Crear criterio]**. Si crea un nuevo criterio, tiene la opción de guardar los criterios para usarlos con otras [!DNL Recommendations] actividades. For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una [!DNL Recommendations]actividad, haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!DNL Recommendations].

Los pasos siguientes suponen que accede a la pantalla [!UICONTROL Crear nuevo criterio] mediante el primer método: la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** .

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Cargar criterios]** personalizados.

1. Configure la información en las siguientes secciones.

## Información básica   {#info}

1. Escriba un **[!UICONTROL Nombre de criterio]**.

   Es el nombre “interno” que se usa para describir los criterios. Por ejemplo, quizá use el nombre “Productos con más margen” para los criterios, pero es probable que no quiera que ese título se muestre al público. Consulte el paso siguiente para establecer el título que se presenta al público.

   ![Sección Información básica](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Escriba un **[!UICONTROL Título]** que se mostrará a la audiencia para que aparezca en la página para todas las recomendaciones que usen este criterio.

   Por ejemplo, una idea es mostrar “Las personas que han visto esto también vieron” o “Productos similares” cuando use estos criterios para mostrar recomendaciones.

1. Escriba una breve **[!UICONTROL Descripción]** del criterio.

   La descripción debería ayudarle a identificar los criterios y podría incluir información sobre el propósito de los mismos.

1. Seleccione un **[!UICONTROL Segmento de mercado vertical]**:

   * [!UICONTROL Venta minorista/Comercio electrónico]
   * [!UICONTROL Generación de vanguardia/B2B/Servicios financieros]
   * [!UICONTROL Medios/Publicación]

   Otras opciones de criterios cambiarán según el sector que seleccione.

1. Seleccione un **[!UICONTROL Tipo de página]**.

   Puede seleccionar varios tipos de página.

   En conjunto, el sector y los tipos de página se usan para categorizar los criterios guardados, facilitando su reutilización para otras actividades de [!DNL Recommendations].

1. Seleccione una **[!UICONTROL Clave de recomendación]**.

   Para obtener más información sobre cómo basar los criterios en una clave, consulte [Basar la recomendación en una clave de recomendación](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. Seleccione la **[!UICONTROL Lógica de recomendación]**.

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](../../c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

## Contenido {#content}

Content rules determine what happens if the number of recommended items does not fill your [recommendations design](/help/c-recommendations/c-design-overview/design-overview.md). Es posible que algunos criterios de [!DNL Recommendations] devuelvan menos recomendaciones que las que exige el diseño. Por ejemplo, si el diseño tiene ranuras para cuatro artículos, pero los criterios hacen que solo se recomienden dos artículos, puede dejar las ranuras restantes vacías o puede utilizar las recomendaciones de copia de seguridad para rellenar las ranuras adicionales.

![Sección Contenido](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Opcional) Deslice el conmutador Representación **[!UICONTROL de diseño]** parcial a la posición &quot;activado&quot;.

   Se rellenarán tantas ranuras como sea posible, pero la plantilla de diseño puede incluir espacio en blanco para las ranuras restantes. Si esta opción está deshabilitada y no hay suficiente contenido para llenar todas las ranuras disponibles, no se mostrarán las recomendaciones y se mostrará el contenido predeterminado.

   Active esta opción si desea que las recomendaciones se proporcionen con ranuras en blanco. Utilice las recomendaciones de copia de seguridad si desea que las ranuras de recomendación se llenen con contenido basado en sus criterios con ranuras vacías llenas de contenido popular o similar del sitio, como se explica en el paso siguiente.

1. (Opcional) Deslice el conmutador **[!UICONTROL Mostrar copia de seguridad de Recommendations]** a la posición &quot;activado&quot;.

   Llene los espacios vacíos restantes del diseño con una selección aleatoria de los productos más vistos de todo el sitio.

   El uso de recomendaciones de copia de seguridad garantiza que el diseño de la recomendación llene todos los espacios disponibles. Supongamos que tiene un diseño de 4 x 1, como se ilustra a continuación:

   ![Diseño de 4 x 1](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supongamos que los criterios hacen que solo se recomienden dos elementos. Si activa la opción Representación [!UICONTROL de diseño] parcial, las dos primeras ranuras se rellenan, pero las dos restantes permanecen vacías. Sin embargo, si activa la opción [!UICONTROL Mostrar copia de seguridad de Recommendations] , las dos primeras ranuras se rellenan según los criterios especificados y las dos ranuras restantes se rellenan según las recomendaciones de copia de seguridad.

   La siguiente matriz muestra el resultado que observará al utilizar las opciones Representación [!UICONTROL de diseño] parcial y [!UICONTROL Copia de seguridad de Recommendations] :

   | Procesamiento de diseño parcial | Recomendaciones de copia de seguridad | Resultado |
   |--- |--- |--- |
   | Deshabilitado | Deshabilitado | Si se devuelven menos recomendaciones que las que llama el diseño, el diseño de recomendaciones se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |
   | Habilitado | Deshabilitado | Se procesa el diseño, pero puede incluir espacio en blanco si se devuelven menos recomendaciones que las que llama el diseño. |
   | Habilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, se procesa parcialmente el diseño.<br>Si el criterio no devuelve ninguna recomendación, y las reglas de inclusión restringen las recomendaciones de copia de seguridad a cero, el diseño se reemplaza por el Contenido predeterminado. |
   | Deshabilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, el diseño se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |

   Para obtener más información, consulte [Uso de una recomendación](/help/c-recommendations/c-algorithms/backup-recs.md)de copia de seguridad.

1. (Condicional) Si seleccionó **[!UICONTROL Mostrar copia de seguridad de Recommendations]** en el paso anterior, puede activar **[!UICONTROL Aplicar reglas de inclusión a las recomendaciones]** de copia de seguridad.

   Las reglas de inclusión determinan qué artículos se incluyen en las recomendaciones. Las opciones disponibles dependen del sector.

   For more details, see [Specify inclusion rules](#inclusion) below.

1. (Opcional) Deslice el botón **[!UICONTROL Recomendar artículos]** comprados anteriormente a la posición &quot;activado&quot;.

   Esta configuración se basa en `productPurchasedId`. El comportamiento predeterminado es no recomendar artículos comprados previamente. En la mayoría de los casos, no desea promocionar artículos que un cliente haya comprado recientemente. Es útil si vende artículos que la gente suele comprar solo una vez como, por ejemplo, canoas. Si vende artículos que las personas vuelven a comprar repetidamente, como champú u otros artículos personales, debe activar esta opción.

## Reglas de inclusión {#inclusion}

Existen varias opciones que le ayudan a reducir el número de artículos que aparecen en las recomendaciones. Puede utilizar reglas de exclusión al crear criterios o promociones.

![Reglas de inclusión](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Las reglas de inclusión son opcionales, pero definir estos detalles permite controlar mejor los artículos que aparecen en las recomendaciones. Cada detalle que se configure reduce un poco más los criterios de visualización.

Por ejemplo, puede que desee mostrar únicamente los zapatos de mujer que tengan un precio entre 25 y 45 dólares y de los que haya más de 50 pares disponibles en el inventario. También puede ponderar cada atributo para que los artículos que son más importantes para su negocio tengan más posibilidades de aparecer.

Otro ejemplo: puede elegir mostrar ofertas de trabajo solo a quienes visiten su sitio desde determinadas ciudades, o tengan una determinada titulación universitaria.

Las opciones de reglas de inclusión varían por sector. De forma predeterminada, las reglas de inclusión se aplican a recomendaciones de copia de seguridad.

>[!IMPORTANT]
>
>Debería usar las reglas de inclusión con cautela. Estos filtros son útiles si, por ejemplo, su organización ha establecido reglas que exigen que una marca no se recomiende al mismo tiempo que se está viendo otra marca. Sin embargo, esta función tiene un coste de oportunidad, ya que posiblemente pueda perder un porcentaje de alza al restringir la presentación de algunos elementos que normalmente se mostrarían con los criterios de la actividad.

Las reglas de inclusión se unen mediante Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Para crear una regla de inclusión sencilla, como se mencionó, previamente, que muestre únicamente zapatos de mujer de entre 25 y 45 dólares y de los que haya más de 50 pares en el inventario, siga los pasos siguientes:

1. Establezca un rango de precios para los productos que desea recomendar.
1. Defina la cantidad mínima en inventario para los productos que desea recomendar.
1. Configure la recomendación para que únicamente muestre los artículos cuando cumplan determinados criterios.

   ![](assets/Recs_InclusionRules.png)

   Puede especificar que los artículos se incluyan solamente cuando uno de los atributos de la lista cumpla o no una o varias condiciones especificadas.

   Los evaluadores que hay disponibles dependen del valor que elija en la primera lista desplegable. Puede listar varios elementos. Estos artículos se evaluarán con O.

   Si hay varias reglas, se combinan con una Y.

   >[!NOTE]
   >
   >Esta opción limita los artículos mostrados en la recomendación. No afecta a las páginas en las que aparece la recomendación. Para limitar dónde se muestra la recomendación, seleccione las páginas en el Compositor de experiencias visuales.

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Cargar CSV

1. Seleccione la **[!UICONTROL Ubicación]** del archivo CSV.

   ![Cargar sección CSV](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   El archivo CSV debe tener el formato correcto para que se pueda cargar. Haga clic en **[!UICONTROL Descargar plantilla CSV]** para obtener un archivo CSV con el formato correcto.

   Tiene dos opciones de ubicación:

   * **FTP:** para cargar el archivo CSV desde un servidor FTP, seleccione **[!UICONTROL FTP]** e introduzca la información requerida. Tiene la opción de usar SSL, que emplea el protocolo FTPS para transferir el archivo CSV de forma segura.
   * **URL:** Para cargar el archivo CSV desde una URL, seleccione **[!UICONTROL URL]** y, a continuación, introduzca una URL de fuente.

1. Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Las entidades de criterios personalizados (filas) pueden contener 1000 artículos recomendados (columnas).

Las actualizaciones de criterios personalizados son “acumulativas” de forma predeterminada. Los nuevos pares de clave-valor especificados en el archivo de carga CSV sobrescribirán los pares existentes. Los pares de clave-valor existentes que no tengan claves especificadas en la carga de CSV seguirán estando disponibles para su envío y caducarán en 31 días desde la última vez que se carguen como parte del archivo CSV.

Póngase en contacto con el servicio de atención al cliente si desea activar la configuración que descarta los resultados existentes que no están incluidos en la siguiente carga CSV. Si esta opción está activada, solo estarán disponibles para su envío las claves presentes en el archivo CSV personalizado. Esta configuración se aplica a todos los criterios personalizados.

Los criterios personalizados se actualizan una vez cada 24 horas.

Puede ver el estado de carga y sincronización de los criterios personalizados en la parte inferior de cada tarjeta de criterios, en la página Recommendations > Criterios. También puede ver el estado en el cuadro de diálogo de edición al editar los criterios personalizados.

El flujo de una carga sin errores debería ser Programado > Descargando el archivo de fuente > Importando > Correcto.

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| Mensaje de error | Detalles |
|--- |--- |
| Error desconocido | Indica un error técnico interno. |
| Error de análisis | Probablemente exista un problema con el formato del archivo fuente. Corrija el formato del archivo y vuelva a guardar el algoritmo, que reiniciará el proceso de descarga del archivo. |
| Servidor no encontrado | Proporcione una IP o un nombre de servidor que sea visible en Internet. |
| Error de credenciales | Proporcione un usuario y una contraseña válidos para una cuenta activa en el servidor. |
| No se ha encontrado el directorio | Indique un directorio que exista en el servidor. |
| No se ha encontrado el archivo | Indique el nombre de un archivo que exista en el servidor del directorio indicado. |

## Vídeo de formación: Crear criterios en Recommendations (12:33) ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la siguiente información (los detalles sobre la carga de criterios personalizados comienzan a las 11:43):

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
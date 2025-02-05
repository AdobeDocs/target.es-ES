---
keywords: fuente de recommendations;fuente;SAINT;ftp;csv;clasificaciones;clasificaciones de analytics
description: Descubra cómo las fuentes importan entidades en  [!DNL Adobe Target] [!DNL Recommendations] mediante archivos CSV, el formato de fuente  [!DNL Google Product Search] y  [!DNL Analytics] clasificaciones de productos.
title: ¿Cómo se usa [!UICONTROL Feeds] en  [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2417'
ht-degree: 38%

---

# Fuentes

Utilice fuentes para obtener entidades importadas en [!DNL Adobe Target] [!DNL Recommendations]. Las entidades se pueden enviar mediante archivos CSV, el formato de fuente [!DNL Google Product Search] y [!DNL Adobe Analytics] clasificaciones de productos.

## Resumen de fuentes {#concept_D1E9C7347C5D4583AA69B02E79607890}

Las fuentes le permiten pasar [Entidades](/help/main/c-recommendations/c-products/products.md) o ampliar los datos de mbox con información que no está disponible en la página o que no es seguro enviar directamente desde la página. Por ejemplo, margen, Coste de productos vendidos (COGS), etc.

Las fuentes también le permiten pasar información detallada del elemento a [!DNL Recommendations], como el ID del producto, la categoría, el nombre, el mensaje y otros atributos.

Puede seleccionar las columnas de su archivo de clasificaciones de productos [!DNL Target] o del archivo [!DNL Google Product Search] que desea enviar al servidor [!DNL Recommendations].

Estos datos sobre cada elemento se pueden utilizar para lo siguiente:

* Mostrar valores en diseños
* Definir reglas de inclusión de criterios
* Ordenar elementos en diferentes colecciones
* Aplicación de exclusiones a recomendaciones

Las descripciones de los elementos se pueden pasar a [!DNL Target] mediante fuentes o mboxes. Si [!DNL Target] recopila datos mediante una fuente de entidades y un mbox, prevalecerán los datos más recientes. Normalmente, los datos más recientes proceden de un mbox, ya que su visualización es más frecuente. En el caso improbable de que los datos de una fuente de entidades y los datos de un mbox se visiten al mismo tiempo, se utilizarán los datos del mbox.

La lista [!UICONTROL Feeds] ( **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]**) proporciona información sobre cualquier fuente que haya creado.

La página [!UICONTROL Feeds] contiene las siguientes columnas:

* **Nombre**: El nombre de la fuente especificada durante la creación. Para editar el nombre de una fuente, debe editar la propia fuente. Al guardar la fuente con el nuevo nombre, se actualiza.
* **Estado**: [Estado actual de la fuente](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0).
* **Tipo**: los tipos incluyen [CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA), [[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF) y [Clasificaciones de Analytics](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A).
* **Elementos**: Muestra el número de elementos de la fuente.
* **Programación**: Muestra la programación de actualización de la fuente: [!UICONTROL Daily], [!UICONTROL Weekly], [!DNL Every 2 Weeks] o [!UICONTROL Never].
* **Última actualización**: muestra la fecha y la hora en que la fuente se actualizó por última vez y el nombre de la persona que actualizó la fuente.

Haga clic en el icono [!UICONTROL Customize Table] ( ![Personalizar icono de tabla](/help/main/assets/icons/ColumnSetting.svg) ) para seleccionar o anular la selección de las columnas que desee mostrar.

Haga clic en el icono [!UICONTROL Information] ( ![icono de información](/help/main/assets/icons/InfoOutline.svg) ) para mostrar una tarjeta que muestre la última fecha de carga y la dirección URL de la fuente.

Haga clic en el icono [!UICONTROL More Actions] ( ![icono de más acciones](/help/main/assets/icons/MoreSmallList.svg) ) para obtener acceso a las siguientes acciones: [!UICONTROL Deactivate], [!DNL Edit], [!UICONTROL Copy] y [!UICONTROL Delete].

>[!IMPORTANT]
>
>Las entidades y atributos de entidad cargados caducan al cabo de 61 días. Esto implica lo siguiente:
>
>* La fuente debe ejecutarse al menos una vez al mes para garantizar que el contenido del catálogo no caduque.
>* Al eliminar un elemento del archivo de fuentes, no se elimina del catálogo. Para quitar el elemento del catálogo, elimínelo manualmente mediante la interfaz de usuario o la API de [!DNL Target]. O bien, modifique los atributos del artículo (como el inventario) para asegurarse de que el artículo se excluye de la consideración.

## Tipos de Source

Las entidades se pueden enviar mediante archivos CSV, el formato de fuente [!DNL Google Product Search] y [!DNL Adobe Analytics] clasificaciones de productos.

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

Puede crear un archivo .csv utilizando el formato de carga CSV propiedad de [!DNL Adobe]. El archivo contiene información de visualización sobre los atributos reservados y personalizados para sus productos. Para cargar atributos específicos de su implementación, reemplace `CustomN` en la fila del encabezado con el nombre del atributo que desea utilizar. En el ejemplo siguiente, `entity.Custom1` ha sido reemplazado por `entity.availability`. A continuación, puede subir de forma masiva el archivo al servidor de [!DNL Recommendations].

El uso del formato .csv tiene las siguientes ventajas con respecto al formato de fuente [!DNL Google]:

* El formato .csv no requiere asignaciones de campos.
* El formato .csv admite atributos de varios valores (consulte el ejemplo siguiente).
* El formato .csv admite hasta 100 atributos personalizados. Si necesita más de 100 atributos personalizados, puede crear un segundo archivo de fuente con un conjunto diferente de atributos personalizados específicos.

Utilice el método de carga masiva para enviar información de visualización si no tiene mboxes en la página o si desea complementar la información de visualización con elementos que no están disponibles en el sitio. Por ejemplo, es posible que desee enviar la información del inventario de que no esté publicada en el sitio.

Cualquier dato cargado con el archivo .csv, fuente de producto de Google o fuente de clasificación de producto [!DNL Analytics] sobrescribe el valor de atributo de entidad existente en la base de datos. Si envía información de precios mediante solicitudes mbox y, a continuación, envía valores de precios diferentes en el archivo, los valores del archivo sobrescriben los valores establecidos en la solicitud mbox. Una excepción a esto es el atributo de entidad `categoryId` donde los valores de categoría se anexan en lugar de sobrescribirse hasta el límite de 250 caracteres.

>[!IMPORTANT]
>
>No escriba los valores entre comillas dobles (&quot;) en el archivo .csv a menos que sean deliberadas. Si coloca los valores entre comillas dobles, debe escaparlos escribiendo otro par de comillas dobles. Las comillas dobles sin escape evitan que la fuente de recomendaciones no se cargue correctamente.

Por ejemplo, la sintaxis siguiente es incorrecta:

```
"Apples "Bananas" Grapes"",
```

La sintaxis correcta sería esta:

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>No se puede sobrescribir un valor existente con un valor en blanco. Pase otro valor en su lugar para sobrescribir el valor existente. En el caso de un precio de venta, una solución común es pasar un &quot;NULL&quot; real o algún otro mensaje. A continuación, puede escribir una regla de plantilla para excluir los artículos con el valor en cuestión.

El producto está disponible en la interfaz de administración de aproximadamente dos horas después de cargar su entidad correctamente.

El siguiente es un código de muestra de un archivo .csv:

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

El tipo de fuente [!DNL Google Product Search] usa el formato [!DNL Google]. Es distinto del formato de carga CSV propiedad de [!DNL Adobe].

Si ya tiene un(a) [!DNL Google Product Feed], puede utilizarlo como archivo de importación.

>[!NOTE]
>
>No es necesario usar los datos de [!DNL Google]. [!DNL Recommendations] usa el mismo formato que [!DNL Google]. Puede usar este método para cargar los datos que tenga y utilizar las funciones de programación disponibles. Sin embargo, debe conservar los nombres de atributo predefinidos de [!DNL Google] al configurar el archivo.

La mayoría de los comerciantes cargan productos en [!DNL Google], por lo que cuando un visitante usa la búsqueda de productos de [!DNL Google], se muestran sus productos. [!DNL Recommendations] sigue exactamente la especificación [!DNL Google] para las fuentes de entidades. Las fuentes de entidad se pueden enviar a [!DNL Recommendations] a través de .xml, .txt o .tsv, y pueden usar los [atributos definidos por Google](https://support.google.com/merchants/answer/188494?hl=en&amp;topic=2473824&amp;ctx=topic#US). Los resultados se pueden buscar en [[!DNL Google] páginas de compras](https://www.google.com/prdhp).

>[!NOTE]
>
>Se debe permitir el método POST en el servidor que hospeda el contenido de la fuente [!DNL Google].

Dado que los usuarios de [!DNL Recommendations] ya configuraron las fuentes .xml o .txt para enviarlas a [!DNL Google] a través de una dirección URL o un FTP, las fuentes de entidades aceptan esos datos de productos y los utilizan para generar el catálogo de recomendaciones. Especifique si la fuente existe y si el servidor de Recommendations recupera los datos.

Si usa [!DNL Google Product Search] para la carga de fuente de entidades, aún debe tener un mbox de página de producto en la página si desea mostrar recomendaciones o rastrear vistas de productos para la entrega de algoritmos basados en vistas.

[!DNL Google] fuentes no admiten varios valores para un atributo personalizado.

La fuente se ejecuta en el momento en que la guarda y activa. Se ejecuta en el momento en que se guarda la fuente y, a continuación, todos los días una hora después.

El siguiente es un ejemplo de código para un archivo .xml de fuente [!DNL Google Product Search]:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

El siguiente es un ejemplo de código para un archivo .tsv de fuente [!DNL Google Product Search]:

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### Clasificaciones de productos de [!DNL Analytics] {#section_79E430D2C75443BEBC9AA0916A337E0A}

La clasificación de producto [!DNL Adobe Analytics] es la única clasificación disponible para Recommendations. Para obtener más información acerca de este archivo de clasificación, consulte [Acerca de las clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html) en la guía de *Componentes de Analytics*. Es posible que su implementación actual de no incluya toda la información que necesita en Recommendations. Por lo tanto, si desea agregar información a su archivo de clasificaciones, consulte esta guía del usuario.

>[!IMPORTANT]
>
>Antes de importar datos de entidad en [!DNL Recommendations] mediante [!DNL Analytics] clasificaciones de productos, tenga en cuenta que este no es el método preferido.
>
> Tenga en cuenta las siguientes advertencias:
>
>* Las actualizaciones de los atributos de la entidad incurren en un retraso adicional de hasta 24 horas.
>* [!DNL Target] solo admite [!UICONTROL Product Classifications]. La SKU del producto [!DNL Analytics] debe asignarse al mismo nivel que [!DNL Recommendations] `entity.id`. Las clasificaciones personalizadas [!DNL Analytics] se pueden diseñar con [!UICONTROL Adobe Consulting Services]. Póngase en contacto con el Administrador de cuentas si tiene alguna pregunta.

## Crear fuente   {#steps}

Cree una fuente para incluir información sobre sus productos o servicios en [!DNL Recommendations].

1. Desde la interfaz [!DNL Target], haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**.

1. Elija un nombre descriptivo para la fuente.
1. Seleccione un(a) **[!UICONTROL Source Type]**.

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   Para obtener información acerca de los tipos de fuentes [!UICONTROL CSV] y [!UICONTROL Google Product Feed], vea [Información general de fuentes](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890). También puede [descargar una guía de CSV como modelo](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) para ayudarle a dar formato a la fuente correctamente.

1. (Condicional) Si seleccionó **[!UICONTROL CSV]** o **[!UICONTROL Google Product Feed]**, especifique la ubicación donde se puede obtener acceso a la fuente.

   * **FTP**: Si ha seleccionado la ubicación FTP, indique los datos del servidor FTP, las credenciales de inicio de sesión, el nombre de archivo y el directorio de FTP. Puede utilizar FTP con SSL (FTPS) para que las cargas sean más seguras.

     Configuración del servidor FTP admitida:

      * FTP y FTPS deben estar configurados para utilizar FTP pasivo.
      * En FTPS, configure el servidor para que acepte conexiones de FTPS explícitas.
      * SFTP no es compatible.
      * Puede especificar manualmente un puerto en el que iniciar la conexión (por ejemplo, `ftp://ftp.yoursite.com:2121`). Si no especifica un puerto, se utilizará el puerto FTP o FTPS predeterminado.

   * **URL**: Si selecciona [!UICONTROL URL], especifique la URL.

1. (Condicional) Si seleccionó **[!UICONTROL Analytics Classifications]**, elija el grupo de informes en la lista desplegable.

1. Haga clic en la flecha **[!UICONTROL Next]** para mostrar las opciones de [!UICONTROL Schedule].

1. Seleccione una opción de actualización:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never]: no programar una actualización. Seleccione esta opción si no quiere que se ejecute esta fuente.

1. Especifique a qué hora desea que se ejecute la fuente.

   Esta opción está basada en la zona horaria establecida en el navegador. Si quiere usar una hora de otra zona horaria, tiene que calcularla según su propia zona horaria.

1. Haga clic en la flecha **[!UICONTROL Next]** para mostrar las opciones de [!UICONTROL Mapping] y, a continuación, especifique cómo desea asignar los datos a las definiciones de [!DNL Target].

1. (Opcional) Si quiere que la fuente pertenezca a un entorno (grupo de hosts), seleccione el grupo de hosts.

   De manera predeterminada, la fuente pertenece a todos los grupos de hosts. De este modo se garantiza que los elementos de la fuente estén disponibles en cualquier entorno. Para obtener más información, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

1. Haga clic en **[!UICONTROL Save]**.

Después de crear o editar una fuente, esta se ejecuta inmediatamente. A continuación, la fuente se actualiza según los parámetros que haya establecido. La información tarda un poco en estar disponible. Primero es necesario sincronizar la fuente, después debe procesarse e indizarse para poder publicarla y ponerla a disposición del público. El estado actual aparece en [Estado de fuente](/help/main/c-recommendations/c-products/feeds.md#status) en la lista [!UICONTROL Feeds]. Puede cerrar [!DNL Target] antes de que el proceso se haya completado y el proceso seguirá su curso.

Mientras la indización está en curso, se muestran los encabezados de la fuente y los productos antes de indizar los valores individuales. Esto le permite buscar y ver productos para poder crear colecciones, exclusiones, diseños y actividades antes de completar la indexación.

Cuando el estado indica “Correcto”, significa que el archivo se ha encontrado y se ha analizado correctamente. La información no está disponible para su uso en [!DNL Recommendations] hasta que se indexa el archivo. La tarea de indexación puede tardar bastante, en función del tamaño del archivo. Si el proceso falla, significa que no se encontró el archivo. Por ejemplo: ha utilizado una dirección URL incorrecta, la información de FTP era incorrecta o había un error de análisis.

## Estados e indicadores de alimentación   {#concept_E475986720D1400999868B3DFD14A7A0}

Información sobre los posibles estados de alimentación y sus indicadores.

### Estados de las fuentes {#status}

Estos son los posibles estados de una fuente:

| Estado | Descripción |
|--- |--- |
| [!UICONTROL Syncing] | Los detalles de configuración de fuente se están guardando en [!DNL Target]. |
| [!UICONTROL Sync Failed] | No se pudieron guardar los detalles de configuración de fuente en [!DNL Target]. Inténtelo de nuevo. |
| [!UICONTROL No Feed Run] | Ha creado una fuente, pero no se ha programado (la frecuencia se establece en Nunca). |
| Programado para *fecha y hora* | La fuente no se ha ejecutado, pero está programada para ejecutarse en la fecha y la hora establecidas. |
| [!UICONTROL Waiting for Download] | [!DNL Target] se está preparando para descargar el archivo de fuente. |
| [!UICONTROL Downloading Feed File] | [!DNL Target] está descargando el archivo de fuente. |
| [!UICONTROL Importing Items] | [!DNL Target] está importando elementos del archivo de fuente. |
| Fuente importada correctamente a las *horas* | [!DNL Target] ha importado el archivo de fuente en su sistema de entrega de contenido. Se han realizado cambios en los atributos del elemento en el sistema de entrega de contenido, y estos se reflejarán próximamente en las recomendaciones enviadas. Si no ve los cambios esperados, inténtelo de nuevo y actualice la página que contenga recomendaciones.<br>Notas:<ul><li>Si los cambios realizados en los atributos de un elemento resultan en la exclusión de un elemento de las recomendaciones, la exclusión se refleja inmediatamente. Si se agrega un elemento nuevo o los cambios en los atributos hacen que el elemento *ya no se excluya* de las recomendaciones, esto no se reflejará hasta la siguiente actualización del algoritmo, que se producirá en un plazo de 24 horas.</li><li>Cuando se muestra este estado, es posible que las actualizaciones no se reflejen todavía en la interfaz de usuario de [!UICONTROL Catalog Search]. Aparece un estado separado en [!UICONTROL Catalog Search] que indica la última vez que se actualizó el catálogo en el que se puede buscar.</li></ul> |
| [!UICONTROL Failed to Index] | Se ha producido un error en la operación de indexación. Inténtelo de nuevo. |
| [!UICONTROL Server Not Found] | Las ubicaciones FTP o URL no son válidas o bien no se pueden encontrar. |

Para actualizar una fuente (por ejemplo, para realizar cambios en la configuración o el archivo de la fuente), ábrala, realice los cambios que desee y haga clic en **[!UICONTROL Save]**.

>[!IMPORTANT]
>
>Las entidades cargadas caducan al cabo de 61 días. Esto significa que el archivo de fuentes debe cargarse al menos cada 60 días para evitar interrupciones en las actividades de Recommendations. Si un elemento no se incluye en un archivo de fuentes (u otro método de actualización de entidad) al menos una vez cada 60 días, [!DNL Target] deduce que el elemento ya no es relevante y lo elimina del catálogo.

### Indicadores de estado de fuente   {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

Los siguientes indicadores de estado de fuente se muestran en la columna [!UICONTROL Status]:

| Indicador de estado | Descripción |
|--- |--- |
| Indicador de estado verde | Cuando una fuente termina de indexarse correctamente, aparece un punto de estado verde que indica que la fuente tiene un estado correcto. |
| Indicador de estado amarillo | Cuando una fuente o índice de fuente tiene un retraso de un 25 % de la frecuencia de la fuente, se muestra un punto de estado amarillo. Por ejemplo, el punto amarillo aparece en una fuente configurada para ejecutarse a diario si el índice aún no se ha completado pasadas seis horas de la hora programada. Nota: Una vez que el estado de la fuente es &quot;Esperando a la cola de índice&quot;, los valores recién actualizados ya están disponibles para su publicación y el procesamiento de criterios. |
| Indicador de estado blanco | Cuando una fuente no está programada, un punto de estado blanco indica que aún no se ha ejecutado. |
| Indicador de estado rojo | Si la fuente no puede cargar datos en el servidor, se muestra un indicador de estado rojo. |

Veamos los siguientes ejemplos:

**Ejemplo 1:**

* Día uno: procesos diarios de alimentación a las 9:00 a.m. PST.
* Día dos: son las 15:30 y la fuente no se ha ejecutado desde ayer a las 9:00

El estado tendría que ser amarillo, ya que el índice se debe de haber ejecutado, más o menos, hace 6 horas y media. 6,5 horas + 24 es un 127 % del plazo de la fuente.

**Ejemplo 2:**

* 1 de enero: procesos mensuales de alimentación a las 9:00 a.m. PST.
* 3 de febrero: son las 10:00 a.m. y la fuente no ha funcionado durante un mes, un día y una hora atrás.

El estado tendría que ser amarillo, ya que el índice se debe de haber ejecutado, más o menos, hace un día y una hora. Aunque esto es solo [31 + (1/25)]/30 = 1,03 % de la configuración de frecuencia, se ha superado el retraso máximo de un día.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Explicación de las fuentes en Recommendations (3:01) ![distintivo de información general](/help/main/assets/overview.png)

Este vídeo contiene la información siguiente:

* Explicación del objetivo de las fuentes
* Explicación del valor de las fuentes

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### Crear una fuente (6:44) ![Insignia de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Configuración de una fuente
* Qué tipo de fuente utilizar

>[!VIDEO](https://video.tv.adobe.com/v/27696)

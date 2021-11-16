---
keywords: administración de la relación con los clientes;servicio de registro de clientes;crs;crm;mbox3rdpartyid;atributos del cliente;segmentación;csv;crm;personas de adobe experience cloud
description: Aprenda a utilizar los datos de clientes empresariales de una base de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en [!DNL Adobe Target].
title: ¿Qué son los atributos del cliente y cómo se utilizan?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 19b012a0fcbf5195b12990f0a634a90597850899
workflow-type: tm+mt
source-wordcount: '1571'
ht-degree: 35%

---

# [no definido](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)

Información sobre el uso de datos de clientes empresariales de las bases de datos de Administración de la relación con los clientes (CRM) para la segmentación de contenido en [!DNL Adobe Target] mediante los atributos del cliente en la variable [!DNL Adobe Enterprise Cloud People] servicio.

Los datos de clientes empresariales recopilados a través de múltiples fuentes y almacenados dentro de bases de datos CRM pueden utilizarse en [!DNL Target] para ofrecer de forma estratégica el contenido más relevante para los clientes, centrándose específicamente en los clientes que regresan. Audiencias y atributos del cliente en la variable [!DNL People] (antes Profiles and Audiences) aúna la recopilación y el análisis de datos con las pruebas y la optimización, lo que permite utilizar los datos y las perspectivas.

## Información general sobre Atributos del cliente {#section_B4099971FA4B48598294C56EAE86B45A}

[Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) en el [!DNL People] forma parte del [!DNL Adobe Experience Cloud] y proporciona a las empresas una herramienta para trasladar los datos de sus clientes al [!DNL Experience Cloud] plataforma.

Los datos introducidos en [!DNL Experience Cloud] están disponibles para todos los flujos de trabajo de [!DNL Experience Cloud]. [!DNL Target] utiliza estos datos para segmentar a los clientes que regresan en función de los atributos. [!DNL Adobe Analytics] consume estos atributos, que pueden entonces utilizarse para el análisis y la segmentación.

![ejemplo de crs](/help/c-target/c-visitor-profile/assets/crs.png)

Tenga en cuenta lo siguiente al trabajar con Atributos del cliente y [!DNL Target]:

* Debe cumplir algunos requisitos previos para poder usar la variable [!UICONTROL Atributos del cliente] en la función [!DNL People] servicio. Para obtener más información, consulte &quot;Requisitos previos para cargar atributos del cliente&quot; en [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) en el *Documentación de administración y servicios de Experience Cloud*.
* Tenga en cuenta las limitaciones relacionadas con las cargas de archivos, tal como se documentan en [Acerca del archivo de datos y las fuentes de datos para los Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en) en el *Guía de componentes de la interfaz central del Experience Cloud*. Como práctica recomendada:

   * Cargue archivos grandes únicos (dentro del [límites especificados](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en)). Los archivos grandes únicos son preferibles a los archivos más pequeños.
   * Si debe dividir la carga en varios archivos, asegúrese de que los archivos se procesen completamente antes de enviar nuevos archivos. Asegúrese de que cada archivo de un lote se procese completamente antes de enviar el siguiente lote.

* [!DNL Adobe] no garantiza que el 100% de los datos de atributos del cliente (perfil del visitante) de las bases de datos CRM se incorporen al [!DNL Experience Cloud] y, por lo tanto, estar disponible para su uso como objetivo en [!DNL Target]. En el diseño actual, existe la posibilidad de que no se incorpore un pequeño porcentaje de datos (hasta el 0,1% de los lotes de producción grandes).
* La duración de los datos de atributos del cliente importados desde la variable [!DNL Experience Cloud] a [!DNL Target] depende de la duración del perfil del visitante, que es de 14 días de forma predeterminada. Para obtener más información, consulte [Duración del perfil del visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si la variable `vst.*` son los únicos que identifican al visitante, el perfil &quot;autenticado&quot; existente no se recuperará mientras `authState` no está AUTENTICADO (0). El perfil solo entra en juego si `authState` se cambia a AUTENTICADO (1).

   Por ejemplo, si la variable `vst.myDataSource.id` se usa para identificar al visitante (donde `myDataSource` es el alias de la fuente de datos) y no hay ningún MCID ni ID de terceros, utilizando el parámetro `vst.myDataSource.authState=0` no recupera el perfil que se podría haber creado mediante una importación de Atributos del cliente. Si el comportamiento deseado es recuperar el perfil autenticado, la variable `vst.myDataSource.authState` debe tener el valor de 1 (AUTHENTICATED).

* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

## Acceso a los Atributos del cliente en el servicio People

1. En el [!DNL Adobe Experience Cloud], haga clic en el icono de menú ( ![icono de menú](/help/c-target/c-visitor-profile/assets/menu-icon.png) ) y haga clic en **[!UICONTROL People]**.

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. Haga clic en el **[!UICONTROL Atributos del cliente]** pestaña .

   ![Ficha Atributos del cliente](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Flujo de trabajo de atributos del cliente para [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete los siguientes pasos para usar datos CRM en [!DNL Target], como se muestra abajo:

![flujo de trabajo crm](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Puede encontrar instrucciones detalladas para completar cada una de las siguientes tareas en [Crear un origen de atributos del cliente y cargar el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) en el *Documentación de administración y servicios de Experience Cloud*.

1. Cree un archivo de datos.

   Exporte datos de los clientes de su CRM al formato CSV para crear un archivo .csv. También puede crear un archivo zip o gzip para su carga. Asegúrese de que la primera fila del archivo CSV sea el encabezado y que todas las filas (datos del cliente) tengan el mismo número de entradas.

   La siguiente ilustración muestra un archivo de datos de clientes empresariales de muestra:

   ![muestra de crs](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   La siguiente ilustración muestra un archivo .csv de cliente empresarial de muestra:

   ![ejemplo de csv](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Cree un origen de atributos y cargar el archivo de datos.

   Especifique un nombre y descripción de la fuente de datos y el ID de alias. El ID de alias es un ID único que se usa en el código Atributo del cliente en `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >El nombre de la fuente de datos y el nombre del atributo no pueden contener un punto.

   El archivo de datos debe cumplir los requisitos de carga de archivos y no debe superar los 100 MB. Si el archivo es demasiado grande o tiene datos que deben cargarse de forma recurrente, puede crear FTP con los archivos en su lugar.

   * **HTTPS:** Puede arrastrar y soltar el archivo de datos .csv o hacer clic en **[!UICONTROL Examinar]** para cargar desde el sistema de archivos.
   * **FTP:** Haga clic en el vínculo FTP para [cargar el archivo a través de FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). El primer paso es proporcionar una contraseña para el servidor FTP de Adobe. Especifique la contraseña y haga clic en **[!UICONTROL Listo]**.

   Ahora, transfiera su archivo CSV/ZIP/GZIP al servidor FTP. Una vez completada la transferencia de archivos, cree un archivo con el mismo nombre y una `.fin` extensión. Transfiera este archivo vacío al servidor. Esto indica un Fin de transferencia y la variable [!DNL Experience Cloud] comienza a procesar el archivo de datos.

1. Valide el esquema.

   El proceso de validación le permite asignar nombres para mostrar y descripciones en atributos cargados (cadenas, números enteros, números y demás). Asigne cada atributo a su tipo de datos, su nombre en pantalla y su descripción.

   Haga clic en **[!UICONTROL Guardar]** una vez completada la validación del esquema. El tiempo de carga del archivo varía en función del tamaño.

   ![Validar esquema](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Cargar esquema](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Configure suscripciones y activar el origen de atributos.

   Haga clic en **[!UICONTROL Agregar suscripción]** y, a continuación, seleccione la solución para suscribirse a estos atributos. [Configurar suscripciones](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) configura el flujo de datos entre [!DNL Experience Cloud] y soluciones. Activar el origen de atributos permite el flujo de datos a las soluciones suscritas. Los registros de cliente que ha cargado concuerdan con las señales de ID entrantes de su sitio web o aplicación.

   ![Configurar solución](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Activar](/help/c-target/c-visitor-profile/assets/activate.png)

   Mientras realiza este paso, tenga en cuenta las siguientes limitaciones:

   * El tamaño máximo de archivo para cada carga con el método HTTP es de 100 MB.
   * El tamaño máximo de archivo para cada carga con el método FTP es de 4 GB.
   * Número de atributos a los que puede suscribirse: 5 de [!DNL Target Standard] y 200 de [!DNL Target Premium].

## Utilice los atributos del cliente en [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Puede utilizar los atributos del cliente en [!DNL Target] de los siguientes modos:

### Creación de audiencias de segmentación

En [!DNL Target], puede seleccionar un atributo del cliente en la sección Perfil del visitante cuando cree una audiencia.  Todos los atributos del cliente tienen el prefijo &lt;data_source_name> en la lista. Combine estos atributos según sea necesario con otros atributos de datos para crear audiencias.

![Audiencia de Target](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Creación de scripts de perfil mediante tokens

Se puede hacer referencia a los atributos del cliente en las secuencias de comandos de perfil con el formato `crs.get('<Datasource Name>.<Attribute name>')`.

Este script de perfil puede usarse directamente en ofertas para enviar atributos que pertenecen al visitante actual.

### Uso de mbox3rdPartyID en su sitio web para una correcta implementación y utilización

Pass `mbox3rdPartyId` como parámetro del mbox global dentro del `targetPageParams()` método. El valor de `mbox3rdPartyId` debe establecerse en el ID de cliente que estaba presente en el archivo de datos CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso del servicio Experience Cloud ID.

Si utiliza el servicio de ID de Experience Cloud, debe establecer un ID de cliente y un estado de autenticación para utilizar los atributos del cliente en la segmentación. Para obtener más información, consulte [ID de cliente y estado de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) en el *Ayuda del servicio de ID de Experience Cloud*.

Para obtener más información sobre el uso de atributos del cliente en [!DNL Target], consulte los siguientes recursos:

* [Crear un origen de atributos del cliente y cargar el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) en el *Documentación de administración y servicios de Experience Cloud*

## Problemas que los clientes encuentran con frecuencia {#section_BE0F70E563F64294B17087DE2BC1E74C}

Podría encontrar los siguientes problemas al trabajar con atributos del cliente y [!DNL Target].

>[!NOTE]
>
>Los problemas 1 y 2 causan aproximadamente el 60% de los problemas en esta área. El problema 3 causa aproximadamente el 30% de los problemas. El problema 4 causa aproximadamente el 5% de los problemas. El 5 % restante corresponde a otros problemas diversos.

### Problema 1: Los atributos del cliente se eliminan porque el perfil es demasiado grande

No hay límite de caracteres para un campo particular en el perfil del usuario, pero si el perfil supera los 64 K, se trunca eliminando los atributos más antiguos hasta que vuelve a quedar por debajo de los 64 K.

### Problema 2: Los atributos no aparecen en la biblioteca de audiencias de [!DNL Target], incluso después de varios días

Suele deberse a un problema de conexión de Pipeline. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 3: La entrega no funciona en función del atributo

El perfil todavía no se ha actualizado en el perímetro. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 4: Problemas de implementación

Tenga en cuenta los siguientes problemas de implementación:

* El ID de visitante no se pasó correctamente. El ID se pasó `mboxMCGVID` en lugar de `setCustomerId`.
* El ID de visitante se pasó correctamente, pero el estado de AUTENTICACIÓN no se estableció en Autenticado.
* `mbox3rdPartyId` no se pasó correctamente.

### Problema 5: `mboxUpdate` no se realizó correctamente

`mboxUpdate` no se realizó correctamente con `mbox3rdPartyId`.

### Problema 6: Los atributos del cliente no se importan en [!DNL Target]

Si no encuentra los datos de Atributos del cliente en Target, asegúrese de que la importación se produjo en el último *x* días en los que *x* es el objetivo [Duración del perfil del visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 días de forma predeterminada).

## Vídeo de formación: Carga de datos sin conexión mediante atributos del cliente ![Distintivo del tutorial](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Este vídeo muestra cómo importar sin conexión datos de CRM, centro de ayuda, punto de venta y otros datos de marketing en la [!DNL Experience Cloud People] y asociarlo a los visitantes mediante sus ID conocidos.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)

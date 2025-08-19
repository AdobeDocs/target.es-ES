---
keywords: administración de la relación con los clientes;servicio de registro de clientes;crs;crm;mbox3rdpartyid;atributos del cliente;segmentación;csv;crm;adobe experience cloud people
description: Aprenda a utilizar los datos de clientes empresariales de una base de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en  [!DNL Adobe Target].
title: ¿Qué son los atributos del cliente y cómo se utilizan?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 31%

---

# Atributos del cliente

Información sobre el uso de datos de clientes empresariales en bases de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en [!DNL Adobe Target] mediante el uso de atributos de cliente en el servicio [!DNL Adobe Enterprise Cloud People].

Los datos de clientes empresariales recopilados a través de múltiples fuentes y almacenados dentro de bases de datos CRM se pueden usar en [!DNL Target] para ofrecer de forma estratégica el contenido más relevante para los clientes, centrándose específicamente en los clientes que regresan. Audiencias y atributos del cliente en el servicio [!DNL People] (antes conocido como Perfiles y audiencias) combina la recopilación y el análisis de datos con las pruebas y la optimización, lo que permite llevar a cabo acciones con los datos y las perspectivas.

## Resumen de atributos del cliente {#section_B4099971FA4B48598294C56EAE86B45A}

[Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=es) en el servicio [!DNL People] forma parte de [!DNL Adobe Experience Cloud] y proporciona a las empresas una herramienta para insertar los datos de sus clientes en la plataforma [!DNL Experience Cloud].

Los datos introducidos en [!DNL Experience Cloud] están disponibles para todos los flujos de trabajo de [!DNL Experience Cloud]. [!DNL Target] utiliza estos datos para segmentar a los clientes que regresan en función de los atributos. [!DNL Adobe Analytics] consume estos atributos, que pueden entonces utilizarse para el análisis y la segmentación.

![ejemplo de crs](/help/main/c-target/c-visitor-profile/assets/crs.png)

Tenga en cuenta lo siguiente al trabajar con atributos del cliente y [!DNL Target]:

* Deben cumplirse algunos requisitos previos para poder usar la característica [!UICONTROL Customer attributes] en el servicio [!DNL People]. Para obtener más información, consulte &quot;Requisitos previos para cargar atributos del cliente&quot; en [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es#section_BD38693AFBF34926BA28E964963B4EA0) en la *documentación de servicios y administración de Experience Cloud*.
* Tenga en cuenta las limitaciones relacionadas con las cargas de archivos, como se documenta en [Acerca del archivo de datos y las fuentes de datos para los Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=es) en la *Guía de componentes de la interfaz central de Experience Cloud*. Como práctica recomendada:

   * Cargar archivos grandes únicos (dentro de los [límites especificados](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=es)). Se prefieren archivos grandes únicos sobre varios archivos más pequeños.
   * Si debe dividir la carga en varios archivos, asegúrese de que los archivos se procesen completamente antes de enviar los nuevos archivos. Asegúrese de que cada archivo de un lote se procesa completamente antes de enviar el siguiente archivo del lote.

* [!DNL Adobe] no garantiza que el 100% de los datos de atributos del cliente (perfil del visitante) procedentes de bases de datos CRM se incorporarán a [!DNL Experience Cloud] y, por lo tanto, estarán disponibles para su uso como destino en [!DNL Target]. En el diseño actual, existe la posibilidad de que no se incorpore un pequeño porcentaje de datos (hasta el 0,1 % de los lotes de producción grandes).
* La duración de los datos de atributos del cliente importados de [!DNL Experience Cloud] a [!DNL Target] depende de la duración del perfil del visitante, que es de 14 días de forma predeterminada. Para obtener más información, consulte [Duración del perfil del visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si los parámetros `vst.*` son los únicos que identifican al visitante, el perfil &quot;autenticado&quot; existente no se recuperará mientras `authState` no esté autenticado (0). El perfil entra en juego solamente si `authState` se cambia a AUTHENTICATED (1).

  Por ejemplo, si el parámetro `vst.myDataSource.id` se usa para identificar al visitante (donde `myDataSource` es el alias del origen de datos) y no hay ningún MCID ni ID de terceros, al usar el parámetro `vst.myDataSource.authState=0` no se recupera el perfil que podría haberse creado mediante una importación de Atributos del cliente. Si el comportamiento deseado es recuperar el perfil autenticado, `vst.myDataSource.authState` debe tener el valor de 1 (AUTHENTICATED).

* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

## Acceder a Atributos del cliente en el servicio People

1. En [!DNL Adobe Experience Cloud], haga clic en el icono de menú ( ![icono de menú](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ) y, a continuación, haga clic en **[!UICONTROL People]**.

   ![People](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Haga clic en la ficha **[!UICONTROL Customer Attributes]**.

   ![Ficha Atributos del cliente](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Flujo de trabajo de atributos del cliente para [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete los siguientes pasos para usar datos CRM en [!DNL Target], como se muestra abajo:

![flujo de trabajo crm](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

Encontrará instrucciones detalladas para completar cada una de las tareas siguientes en [Crear un origen de atributos del cliente y cargar el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=es) en la *documentación de servicios y administración de Experience Cloud*.

1. Cree un archivo de datos.

   Exporte datos de clientes desde su CRM al formato CSV para crear un archivo .csv. También puede crear un archivo zip o gzip para su carga. Asegúrese de que la primera fila del archivo CSV sea el encabezado y que todas las filas (datos del cliente) tengan el mismo número de entradas.

   La siguiente ilustración muestra un ejemplo de archivo de datos de cliente empresarial:

   ![muestra de crs](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   La siguiente ilustración muestra un ejemplo de archivo .csv de cliente empresarial:

   ![muestra de csv](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Cree un origen de atributos y cargar el archivo de datos.

   Especifique un nombre y descripción de la fuente de datos y el ID de alias. El identificador de alias es un identificador único que se utilizará en el código de atributo del cliente en `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >El nombre de la fuente de datos y el nombre del atributo no pueden contener un punto.

   El archivo de datos debe cumplir con los requisitos de carga de archivos y no debe superar los 100 MB. Si el archivo es demasiado grande o tiene datos que deben cargarse de forma recurrente, puede enviarlos por FTP.

   * **HTTPS:** Puede arrastrar y soltar el archivo de datos .csv o hacer clic en **[!UICONTROL Browse]** para cargar desde su sistema de archivos.
   * **FTP:** Haga clic en el vínculo FTP para [cargar el archivo a través de FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html?lang=es). El primer paso es proporcionar una contraseña para el servidor FTP de Adobe. Especifique la contraseña y haga clic en **[!UICONTROL Done]**.

   Ahora, transfiera su archivo CSV/ZIP/GZIP al servidor FTP. Una vez completada la transferencia de archivos, cree un archivo con el mismo nombre y una extensión `.fin`. Transfiera este archivo vacío al servidor. Esto indica un final de la transferencia y [!DNL Experience Cloud] comienza a procesar el archivo de datos.

1. Valide el esquema.

   El proceso de validación le permite asignar nombres para mostrar y descripciones en atributos cargados (cadenas, números enteros, números y demás). Asigne cada atributo a su tipo de datos, su nombre en pantalla y su descripción.

   Haga clic en **[!UICONTROL Save]** una vez completada la validación del esquema. El tiempo de carga del archivo varía en función del tamaño.

   ![Validar esquema](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Cargar esquema](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Configure suscripciones y activar el origen de atributos.

   Haga clic en **[!UICONTROL Add Subscription]** y, a continuación, seleccione la solución para suscribirse a estos atributos. [Configurar suscripciones](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html?lang=es) configura el flujo de datos entre [!DNL Experience Cloud] y las soluciones. Activar el origen de atributos permite el flujo de datos a las soluciones suscritas. Los registros de cliente que ha cargado concuerdan con las señales de ID entrantes de su sitio web o aplicación.

   ![Configurar solución](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Activar](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Mientras realiza este paso, tenga en cuenta las siguientes limitaciones:

   * El tamaño máximo de archivo para cada carga con el método HTTP es de 100 MB.
   * El tamaño máximo de archivo para cada carga con el método FTP es de 4 GB.
   * Número de atributos a los que puede suscribirse: 5 de [!DNL Target Standard] y 200 de [!DNL Target Premium].

## Usar atributos del cliente en [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Puede utilizar los atributos del cliente en [!DNL Target] de los siguientes modos:

### Creación de audiencias de segmentación

En [!DNL Target], puede seleccionar un atributo del cliente en la sección [!UICONTROL Visitor Profile] al crear una audiencia. Todos los atributos del cliente tienen el prefijo &lt;data_source_name> en la lista. Combine estos atributos según sea necesario con otros atributos de datos para crear audiencias.

![Audiencia de Target](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Creación de scripts de perfil mediante tokens

Se puede hacer referencia a los atributos del cliente en las secuencias de comandos de perfil con el formato `crs.get('<Datasource Name>.<Attribute name>')`.

Este script de perfil puede usarse directamente en ofertas para enviar atributos que pertenecen al visitante actual.

### Uso de mbox3rdPartyID en su sitio web para una correcta implementación y utilización

Pase `mbox3rdPartyId` como parámetro al mbox global dentro del método `targetPageParams()`. El valor de `mbox3rdPartyId` debe establecerse en el ID de cliente presente en el archivo de datos CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso del servicio Experience Cloud ID.

Si utiliza el servicio de Experience Cloud ID, debe establecer un ID de cliente y un estado de autenticación para utilizar los atributos del cliente en la segmentación. Para obtener más información, consulte [ID de cliente y estado de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es) en la *Ayuda del servicio de Experience Cloud ID*.

Para obtener más información sobre el uso de atributos del cliente en [!DNL Target], consulte los siguientes recursos:

* [Cree un origen de atributo de cliente y cargue el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html?lang=es) en la *documentación de servicios y administración de Experience Cloud*

## Problemas que los clientes encuentran con frecuencia {#section_BE0F70E563F64294B17087DE2BC1E74C}

Podría encontrar los siguientes problemas al trabajar con atributos del cliente y [!DNL Target].

>[!NOTE]
>
>Los problemas 1 y 2 causan aproximadamente el 60 % de los problemas en esta área. El número 3 causa aproximadamente el 30% de los problemas. El problema 4 causa aproximadamente el 5 % de los problemas. El 5 % restante corresponde a otros problemas diversos.

### Problema 1: Los atributos del cliente se eliminan porque el perfil es demasiado grande

No hay límite de caracteres para un campo particular en el perfil del usuario, pero si el perfil supera los 64 K, se trunca eliminando los atributos más antiguos hasta que vuelve a quedar por debajo de los 64 K.

### Problema 2: Los atributos no aparecen en la biblioteca de audiencias en [!DNL Target], ni siquiera después de varios días

Suele deberse a un problema de conexión de Pipeline. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 3: La entrega no funciona según el atributo

El perfil todavía no se ha actualizado en el perímetro. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 4: Problemas de implementación

Tenga en cuenta los siguientes problemas de implementación:

* El ID de visitante no se pasó correctamente. Se pasó el identificador en `mboxMCGVID` en lugar de `setCustomerId`.
* El ID de visitante se pasó correctamente, pero el estado de AUTENTICACIÓN no se estableció en Autenticado.
* `mbox3rdPartyId` no se pasó correctamente.

### Problema 5: `mboxUpdate` no se realizó correctamente

`mboxUpdate` no se realizó correctamente con `mbox3rdPartyId`.

### Problema 6: Los atributos del cliente no se importan en [!DNL Target]

Si no encuentra los datos de Atributos del cliente en Target, asegúrese de que la importación se produjo en los últimos *x* días, donde *x* es el valor de [Duración del perfil del visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) de Target (14 días de forma predeterminada).

## Vídeo de formación: Cargar datos sin conexión mediante atributos del cliente ![Distintivo de tutorial](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Este vídeo muestra cómo se importan sin conexión datos de CRM, servicio de asistencia, punto de venta y otros datos de marketing al servicio [!DNL Experience Cloud People] y cómo dichos datos se asocian a los visitantes mediante sus identificadores conocidos.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)

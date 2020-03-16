---
keywords: customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm
description: Información sobre el uso de datos de clientes empresariales en una base de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en Adobe Target mediante el uso de Atributos del cliente en el servicio principal Perfiles y audiencias de Adobe.
title: Atributos del cliente en Adobe Target
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 7c8705e45b84fb7d49f93e1f3a25392a8d2758a6

---


# Atributos del cliente {#customer-attributes}

Information about using enterprise customer data from a customer relationship management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud] core service.

Los datos de clientes empresariales obtenidos a través de múltiples fuentes y almacenados dentro de una base de datos CRM pueden usarse en [!DNL Target] para ofrecer de forma estratégica el contenido más relevante para los clientes, centrándose específicamente en los clientes que regresan. El servicio principal [!DNL Audiences] (conocido anteriormente como Perfiles y audiencias) combina la recopilación y el análisis de datos con las pruebas y la optimización ofreciendo datos e información procesables.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

The Audiences core service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. Los datos introducidos en [!DNL Experience Cloud] están disponibles para todos los flujos de trabajo de [!DNL Experience Cloud]. [!DNL Target] utiliza estos datos para dirigirse a clientes que regresan en función de los atributos. [!DNL Adobe Analytics] consume estos atributos, que pueden entonces utilizarse para el análisis y la segmentación.

![](assets/crs.png)

Tenga en cuenta lo siguiente al trabajar con Atributos del cliente y [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL Audiences] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the *Experience Cloud Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] (cualquier versión) o [!DNL mbox.js] versión 58 o posterior.

* Adobe does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. En el diseño actual, existe la posibilidad de que un pequeño porcentaje de datos se quede sin introducir.
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. Para obtener más información, consulte   [Duración del perfil del visitante](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will only come into play if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. Si el comportamiento deseado pasa por recuperar el perfil autenticado, `vst.myDataSource.authState` debe tener el valor de 1 (AUTHENTICATED).

* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete los siguientes pasos para usar datos CRM en [!DNL Target], como se muestra abajo:

![](assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Product Documentation*.

1. Cree un archivo de datos.

   Exporte datos de los clientes de su CRM al formato CSV para crear un archivo .csv. También puede crear un archivo zip o gzip para su carga. Asegúrese de que la primera fila del archivo CSV sea el encabezado y que todas las filas (datos del cliente) tengan el mismo número de entradas.

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. Cree un origen de atributos y cargar el archivo de datos.

   Especifique un nombre y descripción de la fuente de datos y el ID de alias. El ID de alias es un ID exclusivo que se usa en el código Atributo del cliente en `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >El nombre de la fuente de datos y el nombre del atributo no pueden contener un punto.

   Puede cargarse archivos de datos de hasta 100 MB con el método HTTP. Los archivos de más de 100 MB, hasta 4 GB, se pueden cargar mediante FTP.

   * **HTTPS:** Puede arrastrar y soltar el archivo de datos .csv o hacer clic en **[!UICONTROL Examinar]** para cargarlo desde el sistema de archivos.
   * **FTP:** Haga clic en el vínculo FTP para [cargar el archivo a través de FTP](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). El primer paso es proporcionar una contraseña para el servidor FTP de Adobe. Specify the password, then click **[!UICONTROL Done]**.

      Ahora, transfiera su archivo CSV/ZIP/GZIP al servidor FTP. Una vez que la transferencia de archivos se haya realizado correctamente, cree un nuevo archivo con el mismo nombre y la misma extensión .fin. Transfiera este archivo vacío al servidor. This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. Valide el esquema.

   El proceso de validación le permite asignar nombres para mostrar y descripciones en atributos cargados (cadenas, números enteros, números y demás). Asigne cada atributo a su tipo de datos, su nombre en pantalla y su descripción.

   Click **[!UICONTROL Save]** after the schema validation is complete. El tiempo de carga del archivo varía en función del tamaño.

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. Configure suscripciones y activar el origen de atributos.

   Haga clic en **[!UICONTROL Agregar suscripción]** y, a continuación, seleccione la solución para suscribirse a estos atributos. [Configurar suscripciones](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) configura el flujo de datos entre las soluciones [!DNL Experience Cloud] y. Activar el origen de atributos permite el flujo de datos a las soluciones suscritas. Los registros de cliente que ha cargado concuerdan con las señales de ID entrantes de su sitio web o aplicación.

   ![](assets/solution.png)

   ![](assets/activate.PNG)

   Mientras realiza este paso, tenga en cuenta las siguientes limitaciones:

   * El tamaño máximo de archivo para cada carga con el método HTTP es de 100 MB.
   * El tamaño máximo de archivo para cada carga con el método FTP es de 4 GB.
   * Número de atributos a los que puede suscribirse: 5 de [!DNL Target Standard] y 200 de [!DNL Target Premium].

## Utilizar los atributos del cliente en Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Puede utilizar los atributos del cliente en [!DNL Target] de los siguientes modos:

### Creación de audiencias de segmentación

En [!DNL Target], puede seleccionar un atributo del cliente en la sección Perfil del visitante cuando cree una audiencia.  Todos los atributos del cliente tienen el prefijo &lt;data_source_name> en la lista. Combine estos atributos según sea necesario con otros atributos de datos para crear audiencias.

![Audiencia de Target](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Creación de scripts de perfil mediante tokens

Se puede hacer referencia a los atributos del cliente en las secuencias de comandos de perfil con el formato `crs.get('<Datasource Name>.<Attribute name>')`.

Este script de perfil puede usarse directamente en ofertas para enviar atributos que pertenecen al visitante actual.

### Uso de mbox3rdPartyID en su sitio web para una correcta implementación y utilización

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso del servicio Experience Cloud ID.

Si está utilizando el servicio de Experience Cloud ID, necesita establecer un ID de cliente y un estado de autenticación para poder usar atributos del cliente en la segmentación. For more information, see [Customer IDs and Authentication State](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

Para obtener más información sobre el uso de atributos del cliente en [!DNL Target], consulte los siguientes recursos:

* [Cree un origen de atributos de cliente y cargue el archivo](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) de datos en la documentación del producto de *Experience Cloud*
* [Atributos del cliente: cuanto más sabe, mejor se relaciona](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) en el *blog Digital Marketing*

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

Podría encontrar los siguientes problemas al trabajar con atributos del cliente y [!DNL Target]:

| Problema | Detalles |
|--- |--- |
| Los atributos del cliente se eliminan porque el perfil es demasiado grande | No hay límite de caracteres para un campo particular en el perfil del usuario, pero si el perfil supera los 64 K, se trunca eliminando los atributos más antiguos hasta que vuelve a quedar por debajo de los 64 K. |
| Los atributos no aparecen en la biblioteca de audiencias de [!DNL Target], ni siquiera después de varios días | Suele deberse a un problema de conexión de Pipeline. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente. |
| La entrega no funciona basada en el atributo | El perfil todavía no se ha actualizado en el perímetro. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente. |
| Problemas de implementación | Tenga en cuenta los siguientes problemas de implementación:<ul><li>El ID de visitante no se pasó correctamente. The ID was passed in `mboxMCGVID` instead of `setCustomerId`.</li><li>El ID de visitante se pasó correctamente, pero el estado de AUTENTICACIÓN no se estableció en Autenticado.</li><li>`mbox3rdPartyId` no se pasó correctamente.</li> |
| `mboxUpdate` no se realizó correctamente. | `mboxUpdate` no se realizó correctamente con `mbox3rdPartyId`. |
| Los atributos de cliente no se importan en Target | If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default). |

Los problemas de las filas 1 y 2 suponen aproximadamente el 60 % del total en esta área. La fila 3 supone aproximadamente el 30 % de los problemas. El problema en la fila 4 supone aproximadamente el 5 % del total. El 5 % restante corresponde a otros problemas diversos.

## Vídeo de formación: Carga de datos sin conexión mediante atributos del cliente {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8} Distintivo ![de tutoriales](/help/assets/tutorial.png)

En este vídeo se muestra cómo importar datos de CRM sin conexión, asistencia técnica, puntos de venta y otros datos de marketing en el servicio Personas de Experience Cloud y cómo asociarlos con visitantes que utilizan sus ID conocidos.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)

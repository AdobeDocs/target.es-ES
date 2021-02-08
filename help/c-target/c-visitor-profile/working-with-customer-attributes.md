---
keywords: administración de la relación con los clientes;servicio de registros de clientes;crs;crm;mbox3rdpartyid;atributos del cliente;segmentación;csv;crm;adobe experience cloud people
description: Obtenga información sobre cómo utilizar datos de clientes empresariales de una base de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en Adobe Target.
title: ¿Qué son los atributos del cliente y cómo se utilizan?
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 40%

---


# Atributos del cliente

Información sobre el uso de datos de clientes empresariales de bases de datos de administración de la relación con los clientes (CRM) para la segmentación de contenido en [!DNL Adobe Target] mediante el uso de atributos del cliente en el servicio [!DNL Adobe Enterprise Cloud People].

Los datos de clientes empresariales recopilados a través de múltiples fuentes y almacenados dentro de bases de datos CRM se pueden utilizar en [!DNL Target] para ofrecer estratégicamente el contenido más relevante a los clientes, centrándose específicamente en los clientes que regresan. Audiencias y atributos del cliente en el servicio [!DNL People] (anteriormente Perfiles y Audiencias) aúna la recopilación de datos y la análisis con las pruebas y la optimización, lo que hace que los datos y las perspectivas sean procesables.

## Información general sobre los atributos del cliente {#section_B4099971FA4B48598294C56EAE86B45A}

[Los ](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) atributos del cliente en el  [!DNL People] servicio forman parte del mismo  [!DNL Adobe Experience Cloud] y proporcionan a las empresas una herramienta para insertar los datos de sus clientes en la  [!DNL Experience Cloud] plataforma.

Los datos introducidos en [!DNL Experience Cloud] están disponibles para todos los flujos de trabajo de [!DNL Experience Cloud]. [!DNL Target] utiliza estos datos para dirigirse a clientes que regresan en función de los atributos. [!DNL Adobe Analytics] consume estos atributos, que pueden entonces utilizarse para el análisis y la segmentación.

![ejemplo de crs](/help/c-target/c-visitor-profile/assets/crs.png)

Tenga en cuenta lo siguiente al trabajar con Atributos del cliente y [!DNL Target]:

* Hay algunos requisitos previos que debe cumplir para poder utilizar la función [!UICONTROL Atributos del cliente] en el servicio [!DNL People]. Para obtener más información, consulte &quot;Requisitos previos para cargar atributos del cliente&quot; en [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) en la *documentación de Experience Cloud Services and Administration*.

   >[!NOTE]
   >
   >[!DNL at.js] (cualquier versión) o  [!DNL mbox.js] versión 58 o posterior.

* [!DNL Adobe] no garantiza que el 100 % de los datos de atributos del cliente (perfil de visitante) de las bases de datos CRM se incorporarán al  [!DNL Experience Cloud] y, por lo tanto, estarán disponibles para su uso como objetivo en  [!DNL Target]. En nuestro diseño actual, existe la posibilidad de que un pequeño porcentaje de datos (hasta el 0,1% de los lotes de producción grandes) no se incorporen.
* La duración de los datos de atributos del cliente importados de [!DNL Experience Cloud] a [!DNL Target] depende de la duración del perfil de visitante, que es de 14 días de manera predeterminada. Para obtener más información, consulte   [Duración del perfil del visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si los parámetros `vst.*` son lo único que identifica el visitante, no se recuperará el perfil &quot;autenticado&quot; existente siempre y cuando `authState` no esté AUTENTICADO (0). El perfil solo entrará en juego si `authState` se cambia a AUTENTICADO (1).

   Por ejemplo, si el parámetro `vst.myDataSource.id` se utiliza para identificar el visitante (donde `myDataSource` es el alias de la fuente de datos) y no hay ningún MCID o ID de terceros, el uso del parámetro `vst.myDataSource.authState=0` no recuperará el perfil que podría haberse creado mediante una importación de Atributos del cliente. Si el comportamiento deseado es recuperar el perfil autenticado, `vst.myDataSource.authState` debe tener el valor 1 (AUTENTICADO).

* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

## Acceso a los atributos del cliente en el servicio Personas

1. En [!DNL Adobe Experience Cloud], haga clic en el icono de menú ( ![icono de menú](/help/c-target/c-visitor-profile/assets/menu-icon.png) ) y luego haga clic en **[!UICONTROL Personas]**.

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. Haga clic en la ficha **[!UICONTROL Atributos del cliente]**.

   ![Ficha Atributos del cliente](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Flujo de trabajo de atributos del cliente para Destinatario {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete los siguientes pasos para usar datos CRM en [!DNL Target], como se muestra abajo:

![flujo de trabajo crm](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Encontrará instrucciones detalladas para completar cada una de las siguientes tareas en [Cree un origen de atributos del cliente y cargue el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) en la *documentación de Experience Cloud y administración*.

1. Cree un archivo de datos.

   Exporte datos de los clientes de su CRM al formato CSV para crear un archivo .csv. También puede crear un archivo zip o gzip para su carga. Asegúrese de que la primera fila del archivo CSV sea el encabezado y que todas las filas (datos del cliente) tengan el mismo número de entradas.

   La siguiente ilustración muestra un archivo de datos de clientes empresariales de muestra:

   ![muestra de crs](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   La siguiente ilustración muestra un archivo .csv de ejemplo de cliente empresarial:

   ![muestra de csv](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Cree un origen de atributos y cargar el archivo de datos.

   Especifique un nombre y descripción de la fuente de datos y el ID de alias. El ID de alias es un ID exclusivo que se usa en el código Atributo del cliente en `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >El nombre de la fuente de datos y el nombre del atributo no pueden contener un punto.

   El archivo de datos debe cumplir los requisitos de carga de archivos y no debe superar los 100 MB. Si el archivo es demasiado grande o tiene datos que deberán cargarse de forma recurrente, puede enviar sus archivos por FTP.

   * **HTTPS:** Puede arrastrar y soltar el archivo de datos .csv o hacer clic en  **** Examinar para cargar desde el sistema de archivos.
   * **FTP:** haga clic en el vínculo FTP para  [cargar el archivo a través de FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). El primer paso es proporcionar una contraseña para el servidor FTP de Adobe. Especifique la contraseña y haga clic en **[!UICONTROL Finalizado]**.

   Ahora, transfiera su archivo CSV/ZIP/GZIP al servidor FTP. Una vez que la transferencia de archivos se haya realizado correctamente, cree un nuevo archivo con el mismo nombre y la misma extensión .fin. Transfiera este archivo vacío al servidor. Esto indica un Fin de transferencia y los inicios [!DNL Experience Cloud] para procesar el archivo de datos.

1. Valide el esquema.

   El proceso de validación le permite asignar nombres para mostrar y descripciones en atributos cargados (cadenas, números enteros, números y demás). Asigne cada atributo a su tipo de datos, su nombre en pantalla y su descripción.

   Haga clic en **[!UICONTROL Guardar]** después de completar la validación del esquema. El tiempo de carga del archivo varía en función del tamaño.

   ![Validar esquema](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Cargar esquema](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Configure suscripciones y activar el origen de atributos.

   Haga clic en **[!UICONTROL Agregar suscripción]** y, a continuación, seleccione la solución para suscribirse a estos atributos. [Configurar ](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) suscripciones configura el flujo de datos entre las soluciones  [!DNL Experience Cloud] y. Activar el origen de atributos permite el flujo de datos a las soluciones suscritas. Los registros de cliente que ha cargado concuerdan con las señales de ID entrantes de su sitio web o aplicación.

   ![Configurar solución](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Activar](/help/c-target/c-visitor-profile/assets/activate.png)

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

Pase `mbox3rdPartyId` como parámetro al mbox global dentro del método `targetPageParams()`. El valor de `mbox3rdPartyId` debe establecerse en el ID de cliente que estaba presente en el archivo de datos CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso del servicio Experience Cloud ID.

Si está utilizando el servicio de Experience Cloud ID, necesita establecer un ID de cliente y un estado de autenticación para poder usar atributos del cliente en la segmentación. Para obtener más información, consulte [ID de cliente y estado de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) en la *Ayuda del servicio de ID de Experience Cloud*.

Para obtener más información sobre el uso de atributos del cliente en [!DNL Target], consulte los siguientes recursos:

* [Cree un origen de atributos de cliente y cargue el ](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) archivo de datos en la documentación de  *Experience Cloud Services y Administration*
* [Atributos del cliente: cuanto más sabe, mejor se relaciona](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) en el *blog Digital Marketing*

## Problemas con los que se encuentran frecuentemente los clientes {#section_BE0F70E563F64294B17087DE2BC1E74C}

Podría encontrar los siguientes problemas al trabajar con atributos del cliente y [!DNL Target].

>[!NOTE]
>
>Los problemas 1 y 2 causan aproximadamente el 60% de los problemas en esta área. El problema 3 causa aproximadamente el 30% de los problemas. El problema 4 causa aproximadamente el 5 % de los problemas. El 5 % restante corresponde a otros problemas diversos.

### Problema 1: Los atributos del cliente se eliminan porque el perfil es demasiado grande

No hay límite de caracteres para un campo particular en el perfil del usuario, pero si el perfil supera los 64 K, se trunca eliminando los atributos más antiguos hasta que vuelve a quedar por debajo de los 64 K.

### Problema 2: Los atributos no aparecen en la biblioteca de Audiencias en [!DNL Target], incluso después de varios días

Suele deberse a un problema de conexión de Pipeline. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 3: Envío no funciona según el atributo

El perfil todavía no se ha actualizado en el perímetro. Como solución, pida a su equipo de Atributos del cliente que vuelva a publicar la fuente.

### Problema 4: Problemas de implementación

Tenga en cuenta los siguientes problemas de implementación:

* El ID de visitante no se pasó correctamente. El ID se pasó en `mboxMCGVID` en lugar de `setCustomerId`.
* El ID de visitante se pasó correctamente, pero el estado de AUTENTICACIÓN no se estableció en Autenticado.
* `mbox3rdPartyId` no se pasó correctamente.

### Problema 5: `mboxUpdate` no se realizó correctamente

`mboxUpdate` no se realizó correctamente con `mbox3rdPartyId`.

### Problema 6: Los atributos del cliente no se importan en [!DNL Target]

Si no encuentra los datos de Atributos del cliente en Destinatario, asegúrese de que la importación se produjo en los últimos *x* días en los que *x* es el valor de Destinatario [duración del Perfil del Visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 días de forma predeterminada).

## Vídeo de capacitación: Cargar datos sin conexión mediante Atributos del cliente ![distintivo del tutorial](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Este vídeo muestra cómo importar datos de CRM sin conexión, asistencia técnica, puntos de venta y otros datos de marketing en el servicio [!DNL Experience Cloud People] y asociarlos con visitantes mediante sus ID conocidos.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)

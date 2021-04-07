---
keywords: implementar;implementación;configurar;configuración;parámetro de página;tomcat;codificación url;atributo de perfil de página;parámetro mbox;atributos de perfil en página;atributo de perfil en script;API de actualización de perfiles en lote;API de actualización de archivo único;atributos del cliente;proveedores de datos;proveedor de datos
description: Obtenga datos en Target (parámetros de página, atributos de perfil, atributos de perfil de secuencia de comandos, proveedores de datos, API de actualización de perfiles único y en bloque, atributos del cliente).
title: ¿Cómo se obtienen los datos en Target?
feature: Implementación
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 84%

---

# Información general sobre métodos

Información sobre los distintos métodos que puede utilizar para obtener datos en [!DNL Adobe Target].

Los métodos disponibles incluyen:

| Método | Detalles |
| --- | --- |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>Parámetros de página (también denominados “parámetros de mbox”)  | Los parámetros de página son pares de nombre-valor pasados directamente a través del código de página que no se almacenan en el perfil del visitante para un uso futuro.<br>Los parámetros de página son útiles para enviar a Target datos de página adicionales que no es necesario que se almacenen con el perfil del visitante para un uso de segmentación futuro. Estos valores, en cambio, se utilizan para describir la página o la acción realizada por el usuario en la página específica. |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>Atributos de perfil en página (también denominados “atributos de perfil en mbox”) | Los atributos de perfil en página son pares de nombre-valor pasados directamente a través del código de página que se almacenan en el perfil del visitante para un uso futuro.<br>Los atributos de perfil en página permiten que los datos específicos del usuario se almacenen en el perfil de Target para una posterior segmentación. |
| [Atributos de perfil en script](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Los atributos de perfil en script son pares de nombre-valor definidos en la solución de Target. El valor se determina a partir de la ejecución de un fragmento JavaScript en el servidor de Target por llamada de servidor.<br>Los usuarios escriben pequeños fragmentos de código que se ejecutan mediante una llamada de mbox y antes de que el visitante se evalúe por audiencia y abono a la actividad. |
| [Proveedores de datos](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Los proveedores de datos son una funcionalidad que le permite pasar fácilmente datos de terceros a Target. |
| API de actualización de perfiles en lote | A través de la API, envíe un archivo .csv a Target que incluya actualizaciones de perfil de visitantes para muchos visitantes. Cada perfil de visitante se puede actualizar con varios atributos de perfil en página con una llamada. |
| API de actualización de perfil único | Casi idéntico a la API de actualización de perfiles en lote, pero un perfil de visitante se actualiza a la vez, en línea en la llamada de API en lugar de con un archivo .csv. |
| Atributos del cliente | Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target. |







## API de actualización de perfiles en lote {#section_92AB4820A5624C669D9A1F1B6220D4FA}

A través de la API, envíe un archivo .csv a Target que incluya actualizaciones de perfil de visitantes para muchos visitantes. Cada perfil de visitante se puede actualizar con varios atributos de perfil en página con una llamada.

Esta opción es muy similar a los atributos de cliente con algunas diferencias:

* Los atributos de cliente utilizan una carga FTP, mientras que la API de actualización de perfiles en lote de Target utiliza una API HTTP POST.
* Los datos de atributos del cliente se pueden compartir con Analytics. La actualización de perfiles en lote solo se puede usar en Target.
* La compatibilidad de los atributos del cliente para crear un perfil para un usuario Target todavía no se ha constatado. La API de actualización de perfiles en lote solo actualiza los perfiles de Target existentes.
* Los atributos del cliente requieren el uso del Experience Cloud ID (ECID). La API de actualización de perfiles en lote requiere el ID de TNT o el `mbox3rdPartyId`.
* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

### Formato

El archivo .csv debe hacer referencia a cada visitante a través de su PCID de Target o mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite. Todos los atributos o valores del perfil se crean y actualizan a través de la API. En la documentación de la API encontrará detalles sobre el formato.

### Casos de uso de ejemplo

Su CRM u otro sistema interno almacena datos valiosos sobre sus visitantes que le interesa actualizar sistemáticamente en Target sin exponer los datos de perfil en la implementación de su página.

### Beneficios del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

### Advertencias

El tamaño del archivo en lote debe ser inferior a 50 MB. Además, el número total de filas no puede superar las 500 000 filas por carga.

No hay ningún límite en el número de filas que puede cargar en lotes consecutivos en un período de 24 horas. Sin embargo, el proceso de ingestión puede acelerarse durante el horario laboral para garantizar que otros procesos se ejecuten de forma eficaz.

Las [actualizaciones de llamadas en lote V2](https://developers.adobetarget.com/api/#updating-profiles) consecutivas   sin llamadas mbox intermedias para los mismos ID de terceros ignoran las propiedades actualizadas en la primera actualización de la llamada en lote.

### Ejemplos de código

Consulte [Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles).

### Vínculos a información relevante

[Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)

## API de actualización de perfil único {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Casi idéntico a la API de actualización de perfiles en lote, pero un perfil de visitante se actualiza a la vez, en línea en la llamada de API en lugar de con un archivo .csv.

### Formato

El visitante se debe identificar a través del valor mboxPC de Target o del valor mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite.

### Casos de uso de ejemplo

Quiere actualizar Target en tiempo real cuando un visitante realiza alguna acción que no sea en Internet, como contactar con un centro telefónico de atención al cliente, financiar un crédito, usar una tarjeta de fidelidad en una tienda, ir a un quiosco, etc.

### Beneficios del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

### Advertencias

Límite de 1 000 000 (1 millón) de llamadas a la API por período de 24 horas

Solo se actualiza el perfil. No se puede crear un perfil para un usuario potencial que Target todavía tiene que ver.

### Ejemplos de código

Se admiten GET y POST.   `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Vínculos a información relevante

[Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)

## Atributos del cliente {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target.

Los clientes de Target Standard pueden utilizar 5 atributos; los clientes de Target Premium pueden utilizar 200 atributos.

### Formato

Se carga un archivo .csv con Experience Cloud IDs (ECID) y pares de atributos nombre-valor a través de FTP o manualmente en la IU de Experience Cloud.

### Casos de uso de ejemplo

Su CRM u otros sistemas internos almacenan información valiosa que le interesa compartir con Adobe Experience Cloud, incluidos Target y Analytics.

### Beneficios del método

Al cargar datos del cliente se crea una entrada de perfil para cada visitante en Target, aunque Target todavía no haya visto el visitante.

Los mismos datos están disponibles automáticamente en Target y Analytics.

FTP puede ser un método de implementación más sencillo que la API.

### Advertencias

Los clientes de Target Standard pueden utilizar 5 atributos; los clientes de Target Premium pueden utilizar 200 atributos.

Los valores solo se pueden actualizar a través de Atributos del cliente, no en la página.

Se requiere la implementación del Experience Cloud ID (ECID).

### Ejemplos de código

Puede encontrar más información en [Crear un origen de atributos del cliente y cargar el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Vínculos a información relevante

[Creación de un origen de atributos del cliente y carga del archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

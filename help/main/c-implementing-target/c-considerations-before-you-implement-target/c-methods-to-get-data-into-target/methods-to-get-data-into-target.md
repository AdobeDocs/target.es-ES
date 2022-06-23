---
keywords: implementar;implementación;configurar;configuración;parámetro de página;tomcat;codificación url;atributo de perfil de página;parámetro mbox;atributos de perfil en página;atributo de perfil en script;API de actualización de perfiles en lote;API de actualización de archivo único;atributos del cliente;proveedores de datos;proveedor de datos
description: Obtener datos en [!DNL Target] (parámetros de página, atributos de perfil, atributos de perfil de secuencia de comandos, proveedores de datos, API de actualización de perfiles únicos y masivos, atributos del cliente).
title: ¿Cómo se obtienen los datos en Target?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 56%

---

# Información general sobre métodos

Información sobre los distintos métodos que se pueden usar para obtener datos en [!DNL Adobe Target].

Los métodos disponibles incluyen:

| Método | Detalles |
| --- | --- |
| [Parámetros de página](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/page-parameters/)<br>(También denominados &quot;parámetros de mbox&quot;) | Los parámetros de página son pares de nombre-valor pasados directamente a través del código de página que no se almacenan en el perfil del visitante para un uso futuro.<br>Los parámetros de página son útiles para enviar datos de página a Target que no es necesario almacenar con el perfil del visitante para un uso de segmentación futuro. Estos valores, en cambio, se utilizan para describir la página o la acción realizada por el usuario en la página específica. |
| [Atributos de perfil en página](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/in-page-profile-attributes/)<br>(También denominados &quot;atributos de perfil en mbox&quot;) | Los atributos de perfil en página son pares de nombre-valor pasados directamente a través del código de página que se almacenan en el perfil del visitante para un uso futuro.<br>Los atributos de perfil en página permiten que los datos específicos del usuario se almacenen en el perfil de Target para una posterior segmentación. |
| [Atributos de perfil en script](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/script-profile-attributes/) | Los atributos de perfil en script son pares de nombre-valor definidos en la solución de Target. El valor se determina a partir de la ejecución de un fragmento JavaScript en el servidor de Target por llamada de servidor.<br>Los usuarios escriben pequeños fragmentos de código que se ejecutan mediante una llamada de mbox y antes de que el visitante se evalúe por audiencia y abono a la actividad. |
| [Proveedores de datos](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/data-providers/) | Los proveedores de datos permiten pasar fácilmente datos de terceros a Target. |
| [API de actualización de perfiles en lote](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/bulk-profile-update-api/) | A través de la API, envíe un archivo .csv a Target que incluya actualizaciones de perfil de visitantes para muchos visitantes. Cada perfil de visitante se puede actualizar con varios atributos de perfil en página con una llamada. |
| [API de actualización de perfil único](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/single-profile-update-api/) | Casi idéntico a la API de actualización de perfiles en lote, pero un perfil de visitante se actualiza a la vez, en línea en la llamada de API en lugar de con un archivo .csv. |
| [Atributos del cliente](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/) | Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, utilice los datos en Adobe Analytics y Adobe Target. |













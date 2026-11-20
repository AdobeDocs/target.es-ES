---
keywords: control de calidad;lado del servidor;vista previa;vínculos de vista previa
description: Aprenda a utilizar las direcciones URL de control de calidad [!DNL Target] de Adobe con entrega de servidor para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentar audiencias de manera opcional y crear informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.
title: Use ¿Puedo realizar el control de calidad de la actividad con la entrega del lado del servidor?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# Usar el control de calidad de la actividad con entrega de servidor {#qa-server-side}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a pasar parámetros de control de calidad de la actividad en una llamada [!DNL Adobe Target] del lado del servidor para que pueda probar actividades cuando `pageUrl` no esté disponible.

>[!ENDSHADEBOX]

La implementación estándar del control de calidad de la actividad admite pasar `qa_mode` parámetros a través de `pageUrl` parámetros. Este método es conveniente para las llamadas estándar/ajax [!DNL Target]. Sin embargo, no es adecuado para llamadas de servidor a servidor, como una implementación de Mobile SDK, en la que `pageUrl` no está disponible. En estos casos, pase los parámetros de control de calidad en la propia solicitud, que mantiene los mismos vínculos de vista previa, objetivos de audiencia opcionales e informes de control de calidad que se segmentan a partir de datos de actividades activas.

El siguiente ejemplo de código muestra el control de calidad de la actividad en una llamada del servidor:

```json
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

En la tabla siguiente se describen los parámetros de una solicitud del lado del servidor:

| Parámetro | Tipo | Valor predeterminado | Descripción |
|--- |--- |--- |--- |
| token | Token cifrado | Ninguno. No puede estar vacío. | Una entidad cifrada que contiene la lista de identificadores de actividad que se pueden ejecutar en el control de calidad de la actividad.<br>Reglas de validación: el token debe ser un token cifrado que pertenezca al cliente especificado en la solicitud [!DNL Target]. Todas las actividades especificadas en el token deben pertenecer al cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica si los destinos de paso de entrada para actividades de control de calidad se evalúan o se consideran coincidentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica si las actividades de control de calidad se ejecutan de forma aislada o se evalúan como actividades activas para el entorno actual. |
| evaluateAsTrueAudienceIds | Lista de ID | Lista vacía | Lista de ID de audiencia que siempre se evalúan como verdaderos en el ámbito de la solicitud [!DNL Target]. |
| evaluateAsFalseAudienceIds | Lista de ID | Lista vacía | Lista de ID de audiencia que siempre se evalúan como false en el ámbito de la solicitud [!DNL Target]. |
| activityIndex | Número entero | Null. No puede estar vacío. | Índice de actividad en el token cifrado. Si `activityIndex` es nulo o está fuera de los límites de las actividades en el token, se omite. El índice comienza con 1.<br>Reglas de validación: se requiere al menos un índice de actividad y debe hacer referencia a una actividad especificada en el token. |
| experienceIndex | Número entero | Null | Cuando se especifica, selecciona una experiencia por índice en la definición de la actividad. Si no se especifica o está fuera de los límites, vuelve a la estrategia de selector de experiencia de la actividad. El índice comienza con 1.<br>Reglas de validación: el valor puede ser nulo o debe hacer referencia a una experiencia en la actividad. |

---
keywords: control de calidad;lado del servidor;vista previa;vínculos de vista previa
description: Use direcciones URL de control de calidad con entrega de servidor para realizar sencillos controles de calidad de las actividades integrales con vínculos de vista previa invariables, segmentar audiencias de manera opcional y crear informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.
title: Usar el control de calidad de la actividad con entrega de servidor
topic: Advanced,Standard,Classic
uuid: c1875243-e37f-4205-9e6b-6e96cadf4a7f
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Usar el control de calidad de la actividad con entrega de servidor{#use-activity-qa-with-server-side-delivery}

Use direcciones URL de control de calidad con entrega de servidor para realizar sencillos controles de calidad de las actividades integrales con vínculos de vista previa invariables, segmentar audiencias de manera opcional y crear informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.

La implementación estándar del control de calidad de la actividad admite pasar parámetros `qa_mode` mediante parámetros mbox de `pageUrl`. Este enfoque es conveniente para las llamadas mbox standard/ajax. Sin embargo, para las llamadas de servidor a servidor, este no es el mejor enfoque para un caso de SDK móvil cuando `pageUrl` no está disponible.

El siguiente ejemplo de código muestra el control de calidad de la actividad en una llamada del servidor:

```
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

La siguiente tabla explica los detalles de una solicitud del servidor:

| Parámetro | Tipo | Valor predeterminado | Descripción |
|--- |--- |--- |--- |
| token | Token cifrado | Ninguna.<br>No puede estar vacío. | Una entidad cifrada que contiene la lista de ID de actividad que se pueden ejecutar en el control de calidad de la actividad.<br>Reglas de validación: debe ser un token cifrado que pertenezca al cliente especificado en la solicitud de mbox. Todas las actividades especificadas en el token deben pertenecer al cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica si los objetivos de paso de entrada para actividades de control de calidad deben evaluarse o si deben considerarse como coincidentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica si las actividades de control de calidad deben ejecutarse de forma aislada o si deben evaluarse como actividades activas para el entorno actual. |
| evaluateAsTrueAudienceIds | Lista de ID | Lista vacía. | Lista de ID de audiencia que siempre deben evaluarse como verdaderas en el alcance de la solicitud de mbox. |
| evaluateAsFalseAudienceIds | Lista de ID | Lista vacía. | Lista de ID de audiencia que siempre deben evaluarse como falsas en el alcance de la solicitud de mbox. |
| activityIndex | Número entero | Nulo.<br>No puede estar vacío. | Índice de actividad en el token cifrado. Si activityIndex está fuera de los límites de la actividad en el token o si es nulo, se ignorará. El índice empieza con 1.<br>Reglas de validación: deben ser al menos un índice de actividad y deben hacer referencia a una actividad especificada en el token. |
| experienceIndex | Número entero | Nulo. | Cuando se especifica, selecciona una experiencia por índice en la definición de la actividad. Si no se especifica o está fuera de los límites, se recurrirá a la estrategia de selección de experiencia de la actividad. El índice empieza con 1  Reglas de validación: pueden ser nulas o deben hacer referencia a una experiencia en la actividad. |
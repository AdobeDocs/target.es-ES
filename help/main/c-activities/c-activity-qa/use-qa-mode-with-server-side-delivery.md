---
keywords: control de calidad;lado del servidor;vista previa;vínculos de vista previa
description: Aprenda a utilizar Adobe [!DNL Target] URL de control de calidad con entrega de servidor para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias y realización de informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.
title: ¿Puedo realizar un control de calidad de la actividad con entrega de servidor?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 70%

---

# Usar el control de calidad de la actividad con entrega de servidor

Use direcciones URL de control de calidad con entrega de servidor en [!DNL Adobe Target] para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias e informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.

La implementación estándar del control de calidad de la actividad admite pasar parámetros `qa_mode` mediante parámetros de `pageUrl`. Este enfoque es conveniente para standard/ajax [!DNL Target] llamadas a . Sin embargo, para las llamadas de servidor a servidor, este no es el mejor enfoque para un caso de SDK móvil cuando `pageUrl` no está disponible.

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

La siguiente tabla explica los detalles de una solicitud del servidor:

| Parámetro | Tipo | Valor predeterminado | Descripción |
|--- |--- |--- |--- |
| token | Token cifrado | Ninguna.<br>No puede estar vacío. | Una entidad cifrada que contiene la lista de ID de actividad que se pueden ejecutar en el control de calidad de la actividad.<br>[!DNL Target]Reglas de validación: debe ser un token cifrado que pertenezca al cliente especificado en la solicitud de Todas las actividades especificadas en el token deben pertenecer al cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica si los objetivos de paso de entrada para actividades de control de calidad deben evaluarse o si deben considerarse como coincidentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica si las actividades de control de calidad deben ejecutarse de forma aislada o si deben evaluarse como actividades activas para el entorno actual. |
| evaluateAsTrueAudienceIds | Lista de ID | Lista vacía. | Lista de ID de audiencia que siempre deben evaluarse como verdaderas en el ámbito del [!DNL Target] solicitud. |
| evaluateAsFalseAudienceIds | Lista de ID | Lista vacía. | Lista de ID de audiencia que siempre deben evaluarse como falsas en el ámbito del [!DNL Target] solicitud. |
| activityIndex | Número entero | Nulo.<br>No puede estar vacío. | Índice de actividad en el token cifrado. Si activityIndex está fuera de los límites de la actividad en el token o si es nulo, se ignorará. El índice empieza con 1.<br>Reglas de validación: deben ser al menos un índice de actividad y deben hacer referencia a una actividad especificada en el token. |
| experienceIndex | Número entero | Nulo. | Cuando se especifica, selecciona una experiencia por índice en la definición de la actividad. Si no se especifica o está fuera de los límites, se recurrirá a la estrategia de selección de experiencia de la actividad. El índice empieza con 1  Reglas de validación: pueden ser nulas o deben hacer referencia a una experiencia en la actividad. |

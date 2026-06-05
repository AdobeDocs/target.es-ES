---
keywords: preguntas frecuentes;faq;analytics para target;a4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action;códigos de evento
description: Encuentre respuestas a preguntas sobre clasificaciones y uso de [!UICONTROL Analytics for Target] (A4T).
title: ¿Dónde puedo encontrar información sobre las clasificaciones de con A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
TQID: https://experienceleague.adobe.com/-BIklVbPaO9QGmnjN0eQdbLFXGA7c2sR-3s6OUli8BM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 25%

---

# Clasificaciones: Preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## Después de usar el [!UICONTROL Importador de clasificaciones] para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

+++Respuesta
Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=es) de las herramientas de administración. La variable se denomina &quot;TNT&quot; en la lista de exportación. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos del flujo de navegación de [!DNL Adobe]. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

Para las actividades estándar de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT), el formato de la cadena TNT es el siguiente:

```
activityID:experienceID:targettype|event
```

Para las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática], el formato de la cadena TNT es el siguiente:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` y `algorithmId` son identificadores internos utilizados por las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 3-32766 representa el ID de la métrica de éxito de Analytics.
* Evento = 32767 representa una conversión de actividad.
* Event -1 o 65535 representa que el usuario se ha eliminado de la actividad o experiencia. Esta situación suele ocurrir cuando el visitante se convierte. El visitante se libera de la experiencia y ahora está disponible para clasificarse para cualquier otra experiencia.

Puede importar el archivo de clasificación con frecuencia desde la interfaz de usuario con una [importación del explorador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=es) o una [importación de FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=es). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

+++

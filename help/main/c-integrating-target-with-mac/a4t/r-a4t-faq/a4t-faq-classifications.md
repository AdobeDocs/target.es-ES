---
keywords: preguntas frecuentes;faq;analytics para target;a4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action;códigos de evento
description: Encuentre respuestas a preguntas sobre clasificaciones y uso de [!UICONTROL Analytics for Target] (A4T).
title: ¿Dónde puedo encontrar información sobre las clasificaciones de con A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 30%

---

# Clasificaciones: Preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## Después de usar [!UICONTROL Classifications Importer] para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

+++Respuesta
Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) de las herramientas de administración. La variable se denomina &quot;TNT&quot; en la lista de exportación. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos del flujo de navegación de [!DNL Adobe]. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

Para las actividades estándar [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] (XT), el formato de la cadena TNT es el siguiente:

```
activityID:experienceID:targettype|event
```

Para las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target], el formato de la cadena TNT es:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` y `algorithmId` son identificadores internos utilizados por las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 3-32766 representa el ID de la métrica de éxito de Analytics.
* Evento = 32767 representa una conversión de actividad.
* Event -1 o 65535 representa que el usuario se ha eliminado de la actividad o experiencia. Esta situación suele ocurrir cuando el visitante se convierte. El visitante se libera de la experiencia y ahora está disponible para clasificarse para cualquier otra experiencia.

Puede importar el archivo de clasificación con frecuencia desde la interfaz de usuario con una [importación del explorador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) o una [importación de FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

+++

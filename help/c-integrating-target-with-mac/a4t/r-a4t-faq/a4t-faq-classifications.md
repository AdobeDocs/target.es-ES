---
keywords: preguntas frecuentes;faq;analytics para target;a4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action;códigos de evento
description: Encuentre respuestas a preguntas sobre clasificaciones y uso de [!UICONTROL Analytics for Target] (A4T).
title: ¿Dónde puedo encontrar información sobre las clasificaciones con A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: e81a27bc321fa83cc1b2449e5df32edfa37d5198
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# Clasificaciones: Preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## Después de usar el [!UICONTROL Importador de clasificaciones] para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) de las herramientas de administración. En la lista de exportación, la variable se llama “TNT”. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda resulta útil para los clientes que reciben la fuente de datos del flujo de navegación de [!DNL Adobe]. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

Para las actividades estándar [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT), el formato de la cadena TNT es:

```
activityID:experienceID:targettype|event
```

Para las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática], el formato de la cadena TNT es:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` =  `targettype` y  `algorithmId` son identificadores internos utilizados por las actividades de  [!UICONTROL Asignación ] automática y  [!UICONTROL Segmentación ] automática.
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 3-32766 representa el id de métrica de éxito de Analytics.
* Evento = 32767 representa una conversión de actividad.
* El evento -1 o 65535 representa que el usuario se elimina de la actividad o experiencia. Esta situación suele ocurrir cuando el visitante se convierte. El visitante es liberado de la experiencia y ahora está disponible para cumplir los requisitos de cualquier otra experiencia.

Puede importar el archivo de clasificación con frecuencia desde la interfaz de usuario mediante una [importación del explorador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) o una [importación de FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

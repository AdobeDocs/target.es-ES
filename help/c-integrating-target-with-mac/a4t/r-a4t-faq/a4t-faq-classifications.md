---
keywords: FAQ;preguntas más frecuentes;preguntas frecuentes;Analytics para Target;A4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action
description: Encuentre respuestas a preguntas sobre clasificaciones y uso de Analytics para actividades [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] .
title: ¿Dónde puedo encontrar información sobre las clasificaciones con A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 59%

---

# Clasificaciones: Preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## Tras usar el importador de clasificaciones para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) de las herramientas de administración. En la lista de exportación, la variable se llama “TNT”. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos secuencias de clic de Adobe. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

El formato de cadena de la variable TNT es `activityID:experienceID:targettype|event`.

* targettype = 0 (control/aleatorio) o 1 (segmentado) para las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 3-32766 representa el id de métrica de éxito de Analytics.
* Evento = 32767 representa una conversión de actividad.

Puede importar el archivo de clasificación con frecuencia desde la interfaz de usuario mediante una [importación del explorador](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) o una [importación de FTP](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

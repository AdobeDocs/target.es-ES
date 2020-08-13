---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de Analytics como fuente de informes para Target (A4T).
title: 'Clasificaciones: Preguntas más frecuentes sobre A4T'
feature: a4t troubleshooting
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 66%

---


# Clasificaciones: Preguntas más frecuentes sobre A4T{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Tras usar el importador de clasificaciones para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html) de las herramientas de administración. En la lista de exportación, la variable se llama “TNT”. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos secuencias de clic de Adobe. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

El formato de cadena de la variable TNT es `activityID:experienceID:targettype|event`.

* targettype = 0 (control/aleatorio) o 1 (objetivo) para actividades de asignación  automática y Destinatario  automático.
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 32767 representa una conversión de actividad.

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

---
keywords: FAQ;preguntas más frecuentes;preguntas frecuentes;Analytics para Target;A4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action
description: Encuentre respuestas a preguntas sobre las clasificaciones y el uso de Analytics para Destinatario (A4T). A4T le permite utilizar sistema de informes de Analytics para actividades de Destinatario.
title: ¿Dónde puedo encontrar información sobre las clasificaciones con A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 55%

---


# Clasificaciones: Preguntas más frecuentes sobre A4T{#classifications-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de [!DNL Analytics] como fuente de sistema de informes para [!DNL Target] (A4T).

## Tras usar el importador de clasificaciones para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) de las herramientas de administración. En la lista de exportación, la variable se llama “TNT”. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos secuencias de clic de Adobe. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

El formato de cadena de la variable TNT es `activityID:experienceID:targettype|event`.

* targettype = 0 (control/aleatorio) o 1 (objetivo) para actividades [!UICONTROL de asignación automática] y [!UICONTROL de Destinatario automático].
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 3-32766 representa la identificación de la métrica de éxito de análisis.
* Evento = 32767 representa una conversión de actividad.

Puede importar el archivo de clasificación con frecuencia desde la interfaz de usuario mediante una [importación del explorador](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) o una [importación por FTP](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

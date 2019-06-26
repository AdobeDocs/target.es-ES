---
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de Analytics como fuente de informes para Target (A4T).
keywords: FAQ;preguntas más frecuentes;preguntas frecuentes;Analytics para Target;A4T;clasificaciones;clasificación;importador de clasificaciones;post-tnt-action
seo-description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de Analytics como fuente de informes para Target (A4T).
seo-title: 'Clasificaciones: Preguntas más frecuentes sobre A4T'
solution: Target
title: 'Clasificaciones: Preguntas más frecuentes sobre A4T'
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Clasificaciones: Preguntas más frecuentes sobre A4T{#classifications-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las clasificaciones y el uso de Analytics como fuente de informes para Target (A4T).

## Tras usar el importador de clasificaciones para descargar clasificaciones, ¿cómo relaciono el valor post-tnt-action con el nombre de una actividad? {#section_6045DAC488B248418F430E663C38D001}

Puede descargarse la clasificación para la cadena A4T/TNT del [importador de clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) de las herramientas de administración. En la lista de exportación, la variable se llama “TNT”. Los datos incluidos incluyen los nombres descriptivos de actividades, experiencias, etc.

Este archivo de búsqueda es útil para los clientes que reciben la fuente de datos secuencias de clic de Adobe. El archivo proporciona nombres descriptivos para las columnas `post_tnt` y `post_tnt_action`.

El formato de cadena de la variable TNT es `activityID:experienceID:targettype|event`.

* targettype siempre será 0 para A4T.
* Evento = 0 representa una entrada en la experiencia.
* Evento = 1 representa una visita en la experiencia.
* Evento = 2 representa una impresión de actividad.
* Evento = 32767 representa una conversión de actividad.

Puede descargarse el archivo de clasificaciones frecuentemente desde la interfaz de usuario mediante una [exportación de navegador](https://marketing.adobe.com/resources/help/en_US/reference/browser_export.html) o una [exportación de FTP](https://marketing.adobe.com/resources/help/en_US/reference/ftp_export.html). También puede incluir servicios de ingeniería para obtener el archivo como una tabla de búsqueda con una fuente de datos de secuencias de clic.

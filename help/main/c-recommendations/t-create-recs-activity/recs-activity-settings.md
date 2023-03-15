---
keywords: Recommendations;Configuración;nombre;objetivo;prioridad;duración;configuración de informes;otros metadatos
description: Obtenga información sobre cómo configurar los ajustes utilizados para describir y controlar una actividad de Recommendations en Adobe Target.
title: ¿Cómo configuro la configuración de actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 84%

---

# Configuración de actividades de Recommendations

Información sobre la configuración que puede utilizar para describir y controlar una [!UICONTROL Recommendations] actividad en [!DNL Adobe Target].

![Página Objetivos y configuración de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

En las siguientes secciones se describen las configuraciones disponibles para una actividad de [!UICONTROL Recommendations].

## Nombre

Asigne un nombre descriptivo que le ayude, tanto a usted como a su equipo, a identificar la actividad.

No se permite usar los caracteres siguientes en el nombre de una actividad:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

Si especifica el nombre de una actividad de [!UICONTROL Recommendations] que ya existe para otra actividad de [!UICONTROL Recommendations Classic], la nueva actividad se vuelve a sincronizar con otro nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. Este nuevo nombre se muestra en ambas [!DNL Target Standard/Premium] y [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Describa el objetivo de la actividad.

## Prioridad

Ajuste el control deslizante para determinar el nivel de prioridad.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

## Duración

Establezca la duración de la actividad.

La actividad se puede iniciar cuando se activa, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## Configuración de informes. 

* **Fuente de informes:** Seleccione la fuente de informes: [!DNL Adobe Target] o [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md). No cambie la fuente de informes después de que la actividad se active. Cambiar la fuente de informes después de una actividad causa un informe incoherente.
* **Métrica de objetivo:** Asigne un nombre al objetivo y seleccione la métrica de éxito que determina si la actividad tiene éxito.
* **Métricas adicionales:** Configure métricas de éxito adicionales para usarlas en sus informes.
* **Audiencias para creación de informes:** Defina las audiencias que se pueden usar cuando filtre los informes.

## Otros metadatos

Escriba notas sobre la actividad.

## Vídeo de formación: Configuración de actividades (3:02) ![Distintivo del tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)

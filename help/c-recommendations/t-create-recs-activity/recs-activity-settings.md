---
keywords: Recommendations;Settings;name;objective;priority;duration;reporting settings;other metadata
description: Se pueden utilizar varios ajustes para describir y controlar una actividad de Recommendations en Adobe Target.
title: Configuración de actividades de Recommendations en Adobe Target
feature: recs creation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 89%

---


# ![PREMIUM](/help/assets/premium.png) Configuración de actividades de Recommendations{#recommendations-activity-settings}

Information about the settings you can use to describe and control a [!UICONTROL Recommendations] activity in [!DNL Adobe Target].

![Página Objetivos y configuración de Recommendations](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

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

Si especifica el nombre de una actividad de [!UICONTROL Recommendations] que ya existe para otra actividad de [!UICONTROL Recommendations Classic], la nueva actividad se vuelve a sincronizar con otro nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. This new name is displayed in both [!DNL Target Standard/Premium] and [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Describa el objetivo de la actividad.

## Prioridad

Ajuste el control deslizante para determinar el nivel de prioridad.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

## Duración

Establezca la duración de la actividad.

La actividad se puede iniciar cuando se activa, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## Configuración de informes. 

* **Origen de sistema de informes:** Seleccione el origen del sistema de informes: [!DNL Adobe Target] o [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). No cambie la fuente de informes después de que la actividad se active. Cambiar la fuente de informes después de una actividad causa un informe incoherente.
* **Métrica de objetivo:** Asigne un nombre al objetivo y seleccione la métrica de éxito que determina si la actividad tiene éxito.
* **Métricas adicionales:** Configure métricas de éxito adicionales para usarlas en sus informes.
* **Audiencias para creación de informes:** Defina las audiencias que se pueden usar cuando filtre los informes.

## Otros metadatos

Escriba notas sobre la actividad.

## Vídeo de capacitación: Distintivo de ![tutorial de configuración de actividad (3:02)](/help/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)
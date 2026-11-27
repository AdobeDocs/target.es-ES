---
keywords: Recommendations;Configuración;nombre;objetivo;prioridad;duración;configuración de informes;otros metadatos
description: Obtenga información sobre cómo configurar los ajustes utilizados para describir y controlar una actividad de Recommendations en Adobe Target.
title: ¿Cómo configuro la configuración de actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 13%
---
# Configuración de actividades de Recommendations {#recs-activity-settings}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información acerca de la configuración que describe y controla una actividad de [!DNL Recommendations] en [!DNL Adobe Target].

>[!ENDSHADEBOX]

La configuración de actividad identifica una actividad [!DNL Recommendations], controla cuándo y dónde se muestra y define cómo se generan los informes de sus resultados.

## Nombre

Haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ) y, a continuación, haga clic en **[!UICONTROL Cambiar nombre]** para asignar a la actividad un nombre descriptivo que ayude a identificarla.

No se permiten los siguientes caracteres en el nombre de una actividad: `/`, `?`, `#`, `:`, `=`, `+`, `-` y `@`.

Si el nombre de una actividad [!DNL Recommendations] ya existe para otra actividad en [!UICONTROL Recommendations Classic], la nueva actividad se vuelve a sincronizar con un nombre nuevo. El nuevo nombre es el nombre original con una marca de tiempo adjunta, para que sea único. Se muestra en [!DNL Target Standard/Premium] y en [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Describa el objetivo de la actividad.

## Prioridad

Ajuste el control deslizante para establecer el nivel de prioridad.

La prioridad se utiliza cuando se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

## Duración

Establezca la duración de la actividad.

La actividad se puede iniciar cuando se activa o en una fecha y hora específicas. Del mismo modo, puede finalizar cuando se desactiva o en una fecha y hora específicas.

El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria es la configurada en el explorador. Para utilizar una zona horaria diferente, establezca el explorador en esa zona horaria y reinicie el explorador.

## Configuración de informes.

La siguiente configuración define cómo se informan los resultados de la actividad.

* **[!UICONTROL Source de informes]:** Especifica la solución de la que se recopilan los datos: [!DNL Adobe Target], [!DNL Adobe Analytics] o [!DNL Adobe Customer Journey Analytics].

  Si se especifica una solución de generación de informes en [configuración de la cuenta](/help/main/administrating-target/reporting.md), se usa esa solución y esta configuración no es visible. La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

  **[!DNL Adobe Analytics]**: vea [[!DNL Adobe Analytics] como fuente de informes de [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para ver las diferencias entre las soluciones de informes y las ventajas de cada una. Para seleccionar el grupo de informes [!DNL Analytics] y el servidor de seguimiento, consulte [Informes de Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

  **[!DNL Adobe Customer Journey Analytics]**: vea [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].

* **[!UICONTROL Métrica de objetivo]:** Selecciona la métrica de éxito que determina si la actividad es exitosa.
* **[!UICONTROL Métricas adicionales]:** Configura métricas de éxito adicionales para los informes.
* **[!UICONTROL Audiencias para informes]:** Define audiencias que se pueden usar para filtrar los informes.

## Otros metadatos

Introduzca notas sobre la actividad.

## Vídeo de formación: Configuración de actividades (3:02) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo trata sobre la siguiente configuración de la actividad:

* Introduzca un objetivo para la actividad.
* Defina el nivel de prioridad de la actividad.
* Programar las horas de inicio y finalización.
* Añada audiencias para los informes con el fin de crear filtros de informes.
* Introduzca notas para la actividad.

>[!VIDEO](https://video.tv.adobe.com/v/17381)

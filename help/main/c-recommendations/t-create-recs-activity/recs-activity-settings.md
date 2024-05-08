---
keywords: Recommendations;Configuración;nombre;objetivo;prioridad;duración;configuración de informes;otros metadatos
description: Obtenga información sobre cómo definir la configuración utilizada para describir y controlar una actividad de Recommendations en Adobe Target.
title: ¿Cómo configuro los ajustes de actividad de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 48%

---

# Configuración de actividades de Recommendations

Información sobre la configuración que puede utilizar para describir y controlar una [!UICONTROL Recommendations] actividad en [!DNL Adobe Target].

![Página Objetivos y configuración de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

Las secciones siguientes describen la configuración disponible para un [!UICONTROL Recommendations] actividad.

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

Si especifica un [!UICONTROL Recommendations] nombre de actividad que ya existe para otra actividad en [!UICONTROL Recommendations Classic], la nueva actividad se vuelve a sincronizar con un nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. Ese nuevo nombre se muestra en [!DNL Target Standard/Premium] y en [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Describa el objetivo de la actividad.

## Prioridad

Ajuste el control deslizante para determinar el nivel de prioridad.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

## Duración

Establezca la duración de la actividad.

La actividad se puede iniciar cuando se activa, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## Configuración de informes. 

* **Fuente de informes:** Especifique de qué datos de solución se recopilan:

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  Si se especifica una solución de creación de informes en su [configuración de cuenta](/help/main/administrating-target/reporting.md), se utiliza la solución especificada y esta configuración no es visible.

  La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

  **[!DNL Adobe Analytics]**: consulte [[!DNL Adobe Analytics] como fuente de informes para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de creación de informes y las ventajas de cada una.

  Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T), seleccione un [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad. Para ello, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  [!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente de los resultados. Aparece un servidor de seguimiento predeterminado en la [!UICONTROL Tracking Server] field. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

  **[!DNL Adobe Customer Journey Analytics]**: consulte [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].

* **Métrica de objetivo:** Asigne un nombre al objetivo y seleccione la métrica de éxito que determina si la actividad tiene éxito.
* **Métricas adicionales:** Configure métricas de éxito adicionales para usarlas en sus informes.
* **Audiencias para creación de informes:** Defina las audiencias que se pueden usar cuando filtre los informes.

## Otros metadatos

Escriba notas sobre la actividad.

## Vídeo de formación: Configuración de actividades (3:02) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)

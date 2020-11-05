---
keywords: Goal &Settings;objective;priority;duration
description: Use Configuración de actividades para administrar el objetivo, la prioridad y la duración de las actividades.
title: Configuración de actividades
feature: activities
subtopic: Multivariate Test
topic: Standard
uuid: d317e63a-ba1f-4c0e-ab90-c6181b8b45fd
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 90%

---


# Configuración de actividades{#activity-settings}

Use Configuración de actividades para administrar el objetivo, la prioridad y la duración de las actividades.

1. Introduzca notas sobre el objetivo de la actividad.

   Escriba la información sobre la actividad que sea útil tener disponible para el equipo. Arrastre para modificar el tamaño del campo [!UICONTROL Objetivo].
1. Establezca la prioridad de actividades.

   La interfaz de usuario y las opciones de [!UICONTROL Prioridad] varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

   La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

   If this option is not enabled in [!UICONTROL Administration] > [!UICONTROL Reporting] (the default), specify a priority: Low, Medium, or High.

   To enable fine-grained priorities, click [!UICONTROL Administration] > [!UICONTROL Reporting], then toggle the [!UICONTROL Enable Fine-Grained Priorities] option to the &quot;On&quot; position.

   Si esta opción está habilitada, indique un valor entre 0 y 999:

   * 0 = Bajo
   * 999 = Alto

   En las actividades creadas en versiones anteriores de [!DNL Target Standard/Premium], el nivel bajo de prioridad se convierte en 0; el medio, en 5; y el alto, en 10. Si lo necesita, puede ajustar estos valores.

   >[!NOTE]
   >
   >Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a establecer todas las prioridades en 0, 5 y 10.

1. Establezca la duración de la actividad.

   Puede activar y desactivar manualmente la actividad o especificar una fecha y una hora para la entrega de la actividad. El control de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

   >[!NOTE]
   >
   >Programar una actividad permite controlar el lapso de tiempo de entrega de la actividad; sin embargo, la actividad debe activarse de forma explícita antes de entregarse de acuerdo con la programación especificada.

La página [!UICONTROL Objetivo y configuración] incluye configuración adicional que varía según el tipo de actividad que está creando. Para obtener más información sobre esta configuración, consulte el tipo de actividad:

* [Prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Prueba multivariable](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Vídeo de formación: Configuración de actividades ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

   >[!VIDEO](https://video.tv.adobe.com/v/17381)

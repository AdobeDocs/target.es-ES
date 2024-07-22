---
keywords: Objetivo y configuración;objetivo;prioridad;duración
description: Aprenda a usar la Configuración de actividades en Adobe [!DNL Target] para administrar el objetivo, la prioridad y la duración de las actividades.
title: ¿Cómo Se Especifica La Configuración De La Actividad?
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 74%

---

# Configuración de actividades

Use [!UICONTROL Activity Settings] en [!DNL Adobe Target] para administrar el objetivo, la prioridad y la duración de las actividades.

1. Introduzca notas sobre el objetivo de la actividad.

   Escriba la información sobre la actividad que sea útil tener disponible para el equipo. Arrastre para cambiar el tamaño del campo [!UICONTROL Objective].
1. Establezca la prioridad de actividades.

   La interfaz de usuario y las opciones de [!UICONTROL Priority] varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

   La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

   Si esta opción no está habilitada en [!UICONTROL Administration] > [!UICONTROL Reporting] (la predeterminada), indique un nivel de prioridad: bajo, Medium o alto.

   Para habilitar prioridades específicas, haga clic en [!UICONTROL Administration] > [!UICONTROL Reporting] y luego coloque la opción [!UICONTROL Enable Fine-Grained Priorities] en la posición &quot;Activado&quot;.

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

La página [!UICONTROL Goal & Settings] incluye configuraciones adicionales que varían según el tipo de actividad que esté creando. Para obtener más información sobre esta configuración, consulte el tipo de actividad:

* [Prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Personalización automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Vídeo de formación: Configuración de actividades ![Insignia de tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

  >[!VIDEO](https://video.tv.adobe.com/v/17381)

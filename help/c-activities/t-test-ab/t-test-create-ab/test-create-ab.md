---
keywords: Create A/B;A/B test;A/B activity;new a/b activity
description: Use el Compositor de experiencias visuales de Target para crear la prueba directamente en una página con Target habilitado y para modificar partes de la página en Target.
title: Crear una prueba A/B
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 99%

---


# Crear una prueba A/B{#create-an-a-b-test}

Use el Compositor de experiencias visuales de Target para crear la prueba directamente en una página con Target habilitado y para modificar partes de la página en Target.

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Recommendations] es una funcionalidad de [Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) y la [Guía de actividades de Target](/help/c-activities/target-activities-guide.md).

   ![Crear una actividad de prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [!UICONTROL [Elegir lugar de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md) de la ilustración anterior es una [función de Target Premium](/help/c-intro/intro.md). Su organización tiene una licencia de Target Standard si no ve esta opción.]

1. (Condicional) Si es [cliente de Target Premium](/help/c-intro/intro.md#premium), elija un [espacio de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique la [URL de la actividad](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) y haga clic en **[!UICONTROL Siguiente]**.

   Si la cuenta se configura con una dirección URL predeterminada esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección.

   Se abre el [!UICONTROL Compositor de experiencias visuales] con la página especificada en la dirección URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![Campo Nombre](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   No se permite usar los caracteres siguientes en el nombre de una actividad:

   | Carácter | Descripción |
   |--- |--- |
   | `/` | Barra oblicua |
   | `?` | Signo de interrogación |
   | `#` | Signo de número |
   | `:` | Dos puntos |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

1. Cree experiencias nuevas cambiando los elementos de la página.

   El [!UICONTROL Compositor de experiencias visuales] muestra dos fichas en la parte izquierda después de crear una actividad nueva: Experiencia A, que es la de control, y Experiencia B. Nos vamos a centrar en la ficha Experiencia B, que podemos modificar si es necesario. Experiencia B es la experiencia alternativa que se puede añadir a la prueba. Se pueden añadir varias experiencias a la prueba. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte  [Añadir experiencia](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar Experiencia B, empiece con el paso 3.

1. Haga clic en **[!UICONTROL Segmentación]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.
1. En el cuadro [!UICONTROL Audiencia], haga clic en el icono de edición y luego [seleccione la audiencia](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) de su actividad.

   De manera predeterminada, la audiencia se establece en Todos los visitantes.

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. La audiencia seleccionada se mostrará en un diagrama junto con las experiencias que haya añadido a la actividad.

   Elija el método de asignación de tráfico que desee:

   * **[!UICONTROL Manual (predeterminado)]**: Especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Consulte [Asignación automática del tráfico](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Asignación automática para experiencias personalizadas]**: Target utilizará algoritmos avanzados de aprendizaje automático para ofrecer automáticamente la mejor experiencia a los visitantes objetivo y, de ese modo, maximizar sus objetivos. Para obtener más información, consulte [Segmentación automática para optimizar](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).
   También puede hacer clic en **[!UICONTROL Agregar experiencia]** para agregar otra experiencia a la actividad.

1. Cuando esté satisfecho con las elecciones de audiencias y experiencias, haga clic en **[!UICONTROL Siguiente]** para ir al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.

   ![Configuración de actividades A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Haga clic en **[!UICONTROL Guardar]**.

Después de crear la actividad, la ficha Información general muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de formación: Creación de la prueba A/B (8:36). ![Insignia de tutorial](/help/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Crear una actividad A/B en Adobe Target
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)

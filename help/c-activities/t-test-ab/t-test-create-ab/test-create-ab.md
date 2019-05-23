---
description: Use el Compositor de experiencias visuales de Target para crear la prueba directamente en una página con Target habilitado y para modificar partes de la página en Target.
keywords: Crear A/B;prueba A/B;actividad A/B;nueva actividad a/b
seo-description: Use el Compositor de experiencias visuales de Target para crear la prueba directamente en una página con Target habilitado y para modificar partes de la página en Target.
seo-title: Crear una prueba A/B
solution: Target
title: Crear una prueba A/B
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: 5405e95cf516f973b69834ac114a1e351cd3040a

---


# Crear una prueba A/B{#create-an-a-b-test}

Use el Compositor de experiencias visuales de Target para crear la prueba directamente en una página con Target habilitado y para modificar partes de la página en Target.

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** &gt; **[!UICONTROL Test A/B]**.

   ![](assets/ab_select.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista.

   Para obtener información sobre los distintos tipos de actividades, consulte   [Actividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

   ![](assets/ab_newactivityurl.png)

1. Seleccione **[!UICONTROL Compositor de experiencias visuales]** si es necesario.

   Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione esa opción. Consulte [Compositor de experiencias basadas en formularios](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).
1. Especifique la URL [de la actividad](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)y haga clic **[!UICONTROL en Crear]**.

   Si la cuenta se configura con una dirección URL predeterminada, esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección.

   Se abre el [!UICONTROL Compositor de experiencias visuales] con la página especificada en la dirección URL.

   ![](assets/vec.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![](assets/ab_newname.png)

   No se permite usar los caracteres siguientes en el nombre de una actividad:

   | Carácter | Descripción |
   |--- |--- |
   | `/` | Barra oblicua |
   | `?` | Signo de interrogación |
   | `#` | Signo de número  |
   | `:` | Dos puntos |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

1. Cree experiencias nuevas cambiando los elementos de la página.

   El [!UICONTROL Compositor de experiencias visuales] muestra dos fichas en la parte izquierda después de crear una actividad nueva: Experiencia A, que es la de control, y Experiencia B. Nos vamos a centrar en la ficha Experiencia B, que podemos modificar si es necesario. Experiencia B es la experiencia alternativa que se puede añadir a la prueba. Se pueden añadir varias experiencias a la prueba. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte   [Añadir experiencia](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar Experiencia B, empiece con el paso 3.

1. Haga clic en **[!UICONTROL Target]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![](assets/ab_flow.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.
1. En el cuadro [!UICONTROL Audiencia], haga clic en el icono de edición y luego [seleccione la audiencia](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) de su actividad.

   De manera predeterminada, la audiencia se establece en Todos los visitantes. 1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![](assets/audperc.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.
1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. La audiencia seleccionada se mostrará en un diagrama junto con las experiencias que haya añadido a la actividad. 

   Si selecciona **[!UICONTROL Manual]**, especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   Si selecciona **[!UICONTROL Asignar automáticamente a la mejor experiencia]**, la mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Consulte [Asignación automática del tráfico](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   Si selecciona **[!UICONTROL Asignación automática para la optimización]**, Target utilizará algoritmos avanzados de aprendizaje automático para ofrecer automáticamente la mejor experiencia a los visitantes objetivo y, de ese modo, maximizar sus objetivos.

   >[!NOTE]
   >
   >La opción “Primera impresión” está activada para algunos clientes en esta versión, para probar y recibir comentarios.

   Para obtener más información, consulte [Segmentación automática para optimizar](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

   También puede hacer clic en **[!UICONTROL Agregar experiencia]para agregar otra experiencia a la actividad.**
1. Cuando esté satisfecho con las elecciones de audiencias y experiencias, haga clic en **[!UICONTROL Siguiente]** para ir al tercer paso del flujo de trabajo guiado de tres pasos.
1. Especifique los [objetivos y la configuración](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.

   ![](assets/ab_settings.png)

1. Haga clic en **[!UICONTROL Guardar]**.

Después de crear la actividad, la ficha Información general muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de formación: Creación de la prueba A/B (8:36).

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Crear una actividad A/B en Adobe Target
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)

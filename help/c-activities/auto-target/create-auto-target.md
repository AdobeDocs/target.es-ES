---
keywords: Create auto-target;A/B test;auto-target activity;new a/b activity;auto target;auto-target for personalized experiences;personalized
description: Utilice el Compositor de experiencias visuales en Adobe Target para crear la actividad de prueba A/B de asignación automática directamente en una página con Destinatario habilitado y para modificar partes de la página dentro de Destinatario.
title: Creación de una actividad de Destinatario automático
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: fb4f43eef067a24f58ab8b53a7c8aa9c09392c9e
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 59%

---


# ![PREMIUM](/help/assets/premium.png) Crear una actividad de Destinatario automático

Utilice el Compositor [!UICONTROL de experiencias] visuales (VEC) en [!DNL Adobe Target] para crear la actividad de prueba  A/B de Destinatario [!UICONTROL automático directamente en una página] habilitada y para modificar partes de la página dentro de [!DNL Target][!DNL Target].

>[!NOTE]
>
>Además de la actividad de prueba  A/B de Destinatario [!UICONTROL automático (analizada en este artículo),] proporciona dos tipos adicionales de actividades de prueba [!DNL Target]  A/B: [!UICONTROL Manual (predeterminado)] y asignación [!UICONTROL automática].
>
>Consulte [Tipos de actividades](/help/c-activities/t-test-ab/test-ab.md#types) de prueba A/B en la descripción general *de la prueba* A/B.

Para crear una actividad de Destinatario  automático:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Destinatario] automático y [!UICONTROL Recommendations] son funciones [de](/help/c-intro/intro.md#premium)Destinatario Premium.
   >
   >Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](/help/c-activities/activities.md) y la [Guía de actividades de Target](/help/c-activities/target-activities-guide.md).

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Crear Actividad de prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del Compositor [!UICONTROL de experiencias basadas en]formularios, [!DNL Target] oferta el VEC de la aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [[!UICONTROL Elegir lugar de trabajo]](/help/administrating-target/c-user-management/property-channel/property-channel.md) de la ilustración anterior es una [función de Target Premium](/help/c-intro/intro.md). Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. Elija un [espacio de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique la [URL de la actividad](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) y haga clic en **[!UICONTROL Siguiente]**.

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

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte  [Añadir experiencia](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar Experiencia B, empiece con el paso 3.

1. Haga clic en **[!UICONTROL Segmentación]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.

1. En el cuadro [!UICONTROL Audiencia] , haga clic en el icono de edición (tres elipses verticales), haga clic en **[!UICONTROL Reemplazar Audiencia]** y, a continuación, [seleccione la audiencia](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para la actividad.

   By default, the audience is set to [!UICONTROL All Visitors].

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. La audiencia seleccionada se mostrará en un diagrama junto con las experiencias que haya añadido a la actividad.

   Elija el método de asignación de tráfico que desee. Para crear una actividad de Destinatario  automático, seleccione destinatario **[!UICONTROL automático para experiencias]** personalizadas.

   Los tres tipos de asignación de tráfico se describen a continuación:

   * **[!UICONTROL Manual (predeterminado)]**: Especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%. For more information, see [Create an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. For more information, see [Auto-Allocate overview](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Destinatario automático para experiencias]** personalizadas: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando varias experiencias de alto rendimiento definidas por expertos en marketing y, a continuación, ofreciendo la experiencia más adaptada a los visitantes en función de sus perfiles de cliente individuales y los comportamientos anteriores de visitantes similares.
   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. Especifique los [objetivos y la configuración](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   ![Configuración de actividades A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Haga clic en **[!UICONTROL Guardar y cerrar]** o en **[!UICONTROL Guardar]**.

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Cree una actividad de prueba [!UICONTROL A/] B en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
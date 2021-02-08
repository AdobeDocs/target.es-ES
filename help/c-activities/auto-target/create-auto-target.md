---
keywords: Crear destinatario automático;Prueba A/B;actividad de destinatario automático;nueva actividad a/b;destinatario automático;destinatario automático para experiencias personalizadas;personalización
description: Descubra cómo usar el Compositor de experiencias visuales (VEC) en Adobe Target para crear su actividad de prueba A/B de Destinatario automático directamente en una página con Destinatario habilitado.
title: ¿Cómo se crea una Actividad de Destinatario automático?
feature: Auto-Target
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 58%

---


# ![](/help/assets/premium.png) PREMIUMCrear una actividad de Destinatario automático

Utilice el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear la actividad [!UICONTROL Destinatario automático] [!UICONTROL Prueba A/B] directamente en una página habilitada para [!DNL Target] y para modificar partes de la página dentro de [!DNL Target].

>[!NOTE]
>
>La [!UICONTROL segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/c-intro/intro.md).
>
>Además de la actividad [!UICONTROL Destinatario automático] [!UICONTROL Prueba A/B] (analizada en este artículo), [!DNL Target] proporciona dos tipos adicionales de actividades [!UICONTROL Prueba A/B]: [!UICONTROL Manual (predeterminado)] y [!UICONTROL Asignación automática].
>
>Consulte [Tipos de actividades de prueba A/B](/help/c-activities/t-test-ab/test-ab.md#types) en *Información general de la prueba A/B*.

Para crear una actividad [!UICONTROL Destinatario automático]:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Destinatario automático] y [!UICONTROL Recommendations] son [características de Destinatario Premium](/help/c-intro/intro.md#premium).
   >
   >Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](/help/c-activities/activities.md) y la [Guía de actividades de Target](/help/c-activities/target-activities-guide.md).

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Crear Actividad de prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   Si prefiere utilizar el [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] oferta el VEC de la aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [[!UICONTROL Elegir lugar de trabajo]](/help/administrating-target/c-user-management/property-channel/property-channel.md) de la ilustración anterior es una [función de Target Premium](/help/c-intro/intro.md). Su organización tiene una licencia [!UICONTROL de Target Standard] si no ve esta opción.

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

1. En el cuadro [!UICONTROL Audiencia], haga clic en el icono de edición (tres elipses verticales), haga clic en **[!UICONTROL Reemplazar Audiencia]** y, a continuación, [seleccione la audiencia](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para la actividad.

   De forma predeterminada, la audiencia se establece en [!UICONTROL Todos los Visitantes].

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. La audiencia seleccionada se mostrará en un diagrama junto con las experiencias que haya añadido a la actividad.

   Elija el método de asignación de tráfico que desee. Para crear una actividad [!UICONTROL Destinatario automático], seleccione **[!UICONTROL destinatario automático para experiencias personalizadas]**.

   Los tres tipos de asignación de tráfico se describen a continuación:

   * **[!UICONTROL Manual (predeterminado)]**: Especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%. Para obtener más información, consulte [Creación de una prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [Información general de asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Destinatario automático para experiencias]** personalizadas:  [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando varias experiencias de alto rendimiento definidas por expertos en marketing y, a continuación, ofreciendo la experiencia más adaptada a los visitantes en función de sus perfiles de cliente individuales y los comportamientos anteriores de visitantes similares.
   También puede hacer clic en **[!UICONTROL Añadir]** para agregar otra experiencia a la actividad.

1. Cuando esté satisfecho con las opciones de audiencia, experiencia y asignación de tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   ![Configuración de actividades A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >Si desea utilizar [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, consulte la información importante en [Compatibilidad de A4T para la asignación automática y actividades de Destinatario automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Haga clic en **[!UICONTROL Guardar y cerrar]** o **[!UICONTROL Guardar]**.

Después de crear la actividad, la ficha [!UICONTROL Información general] muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de capacitación: Creación de pruebas A/B (8:36) ![Distintivo de tutorial](/help/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Cree una actividad [!UICONTROL Prueba A/B] en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
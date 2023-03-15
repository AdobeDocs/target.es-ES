---
keywords: Crear segmentación automática;prueba A/B;actividad de segmentación automática;nueva actividad a/b;segmentación automática;segmentación automática para experiencias personalizadas;personalizada;optimización
description: Aprenda a usar el Compositor de experiencias visuales (VEC) en Adobe [!DNL Target] para crear su actividad de prueba A/B de segmentación automática directamente en un [!DNL Target]-habilitada.
title: ¿Cómo creo una actividad de segmentación automática?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 50%

---

# Creación de una actividad de segmentación automática

Utilice la variable [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear su [!UICONTROL Segmentación automática] [!UICONTROL Prueba A/B] actividad directamente en un [!DNL Target]-página habilitada y para modificar partes de la página en [!DNL Target].

>[!NOTE]
>
>La [!UICONTROL segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>Además del [!UICONTROL Segmentación automática] [!UICONTROL Prueba A/B] actividad (analizada en este artículo), [!DNL Target] proporciona otros dos tipos de [!UICONTROL Prueba A/B] actividades: [!UICONTROL Manual (predeterminado)] y [!UICONTROL Asignación automática].
>
>Consulte [Tipos de actividades de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) en *Información general sobre la prueba A/B*.

Para crear un [!UICONTROL Segmentación automática] actividad:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Segmentación automática] y [!UICONTROL Recommendations] are [Funciones de Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](/help/main/c-activities/activities.md) y la [Guía de actividades de Target](/help/main/c-activities/target-activities-guide.md).

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Crear actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   Si prefiere usar la variable [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el VEC de aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [[!UICONTROL Elegir lugar de trabajo]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de la ilustración anterior es una [función de Target Premium](/help/main/c-intro/intro.md). Su organización tiene un [!UICONTROL Target Standard] licencia si no ve esta opción.

1. Elija un [workspace](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique la [URL de la actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) y haga clic en **[!UICONTROL Siguiente]**.

   Si la cuenta se configura con una dirección URL predeterminada esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección.

   Se abre el [!UICONTROL Compositor de experiencias visuales] con la página especificada en la dirección URL.

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![Campo Nombre](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

1. Cree experiencias cambiando los elementos de la página.

   La variable [!UICONTROL Compositor de experiencias visuales] muestra dos pestañas en el lado izquierdo después de crear una actividad: Experiencia A y Experiencia B. Experiencia A es la experiencia de control. El enfoque está en la ficha Experiencia B, que puede modificar como desee. Experiencia B es la experiencia alternativa que se puede añadir a la prueba. Se pueden añadir varias experiencias a la prueba. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte  [Añadir experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar Experiencia B, empiece con el paso 3.

1. Haga clic en **[!UICONTROL Segmentación]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.

1. En el [!UICONTROL Audiencia] , haga clic en el icono de edición (tres elipses verticales) y haga clic en **[!UICONTROL Reemplazar audiencia]**, luego [seleccionar la audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para su actividad.

   De forma predeterminada, la audiencia está configurada en [!UICONTROL Todos los visitantes].

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. La audiencia seleccionada se mostrará en un diagrama junto con las experiencias que haya añadido a la actividad.

   Elija el método de asignación de tráfico que desee. Para crear un [!UICONTROL Segmentación automática] actividad, seleccione **[!UICONTROL Segmentación automática para experiencias personalizadas]**.

   A continuación se describen los tres tipos de asignación de tráfico:

   * **[!UICONTROL Manual (predeterminado)]**: Especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%. Para obtener más información, consulte [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [Información general de asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Segmentación automática para experiencias personalizadas]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing, y sirviendo la experiencia más adaptada a los visitantes en función de sus perfiles de cliente y del comportamiento pasado de visitantes similares.
   También puede hacer clic en **[!UICONTROL Agregar]** para agregar otra experiencia a la actividad.

1. Cuando esté satisfecho con las opciones de audiencia, experiencia y asignación de tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   ![Configuración de actividades A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >Si desea utilizar [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, consulte información importante en [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Haga clic en **[!UICONTROL Guardar y cerrar]** o **[!UICONTROL Guardar]**.

Después de crear la actividad, la variable [!UICONTROL Información general] muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de formación: Creación de pruebas A/B (8:36) ![Distintivo del tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Cree un [!UICONTROL Prueba A/B] actividad en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)

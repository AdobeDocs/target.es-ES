---
keywords: crear asignación automática;prueba A/B;actividad de asignación automática;nueva actividad a/b;asignación automática;asignación automática a la mejor experiencia;asignar;asignación automática
description: Aprenda a utilizar el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear un [!UICONTROL Asignación automática] Actividad de prueba A/B.
title: ¿Cómo se crea un [!UICONTROL Asignación automática] ¿Actividad?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 49%

---

# Crear un [!UICONTROL Asignación automática] actividad

Utilice el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear su [!UICONTROL Asignación automática] [!UICONTROL Prueba A/B] actividad directamente en una [!DNL Target]página habilitada para y para modificar partes de la página en [!DNL Target].

Además de las [!UICONTROL Asignación automática] [!UICONTROL Prueba A/B] actividad (que se analiza en este artículo), [!DNL Target] proporciona dos tipos adicionales de [!UICONTROL Prueba A/B] actividades: [!UICONTROL Manual (predeterminado)] y [!UICONTROL Segmentación automática]. Consulte [Tipos de actividades de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) in *Información general sobre las pruebas A/B*.

Para crear un [!UICONTROL Asignación automática] actividad:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Recommendations] es una funcionalidad de [Target Premium](/help/main/c-intro/intro.md#premium). Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](/help/main/c-activities/activities.md) y la [Guía de actividades de Target](/help/main/c-activities/target-activities-guide.md).

1. En el **[!UICONTROL Crear actividad de prueba A/B]** , seleccione **[!UICONTROL Visual]**, si es necesario.

   Si prefiere usar la variable [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el VEC de aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si es [cliente de Target Premium](/help/main/c-intro/intro.md#premium), elija un [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique la URL [de la actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) y haga clic **[!UICONTROL en Crear]**.

   Si la cuenta se configura con una dirección URL predeterminada esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

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

   El [!UICONTROL Compositor de experiencias visuales] muestra dos fichas en la parte izquierda después de crear una actividad nueva: Experiencia A, que es la de control, y Experiencia B. Se centra en la pestaña Experiencia B, que puede modificar según desee. Experiencia B es la experiencia alternativa que se puede añadir a la prueba. Se pueden añadir varias experiencias a la prueba. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte  [Añadir experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar Experiencia B, empiece con el paso 2.

1. Haga clic en **[!UICONTROL Segmentación]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.

1. En el [!UICONTROL Audiencia] , haga clic en el icono editar (los puntos suspensivos verticales) y, a continuación, haga clic en **[!UICONTROL Reemplazar audiencia]**, entonces [seleccionar la audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para su actividad de.

   De forma predeterminada, la audiencia se establece en [!UICONTROL Todos los visitantes].

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure el método de asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. Se muestra un diagrama con la audiencia seleccionada y las experiencias que ha añadido a la actividad.

   Elija el método de asignación de tráfico que desee. Para crear un [!UICONTROL Asignación automática] actividad, seleccione **[!UICONTROL Asignación automática a la mejor experiencia]**.

   A continuación se describen los tres tipos de asignación de tráfico:

   * **[!UICONTROL Manual (predeterminado)]**: especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%. Para obtener más información, consulte [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento.

   * **[!UICONTROL Segmentación automática para experiencias personalizadas]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más adaptadas a los visitantes en función de sus perfiles de cliente y del comportamiento pasado de visitantes similares. Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   También puede hacer clic en **[!UICONTROL Añadir]** para añadir otra experiencia a la actividad.

1. Cuando esté satisfecho con las opciones de asignación de audiencia, experiencia y tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   >[!NOTE]
   >
   >Si desea utilizar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, consulte información importante en [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clic **[!UICONTROL Guardar y cerrar]** o **[!UICONTROL Guardar]**.

Después de crear la actividad, las variables [!UICONTROL Información general] La pestaña muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de formación: Creación de la prueba A/B (8:36).

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Crear un [!UICONTROL Prueba A/B] actividad en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)

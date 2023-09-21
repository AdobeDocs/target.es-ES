---
keywords: Crear A/B;prueba A/B;actividad A/B;nueva actividad a/b;crear a/b
description: Aprenda a utilizar el Compositor de experiencias visuales (VEC) en Adobe [!DNL Target] para crear su actividad de prueba A/B directamente en una [!DNL Target]página habilitada para.
title: ¿Cómo se crea una prueba A/B?
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 44%

---

# Crear una prueba A/B

Utilice el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear su [!UICONTROL Prueba A/B] actividad directamente en una [!DNL Target]página habilitada para y para modificar partes de la página en [!DNL Target].

>[!NOTE]
>
>Además del manual (predeterminado) [!UICONTROL Prueba A/B] actividad (que se analiza en este artículo), [!DNL Target] proporciona dos tipos adicionales de [!UICONTROL Prueba A/B] actividades: [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
>
>Consulte [Tipos de actividades de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) in *Información general sobre las pruebas A/B*.

Para crear un manual [!UICONTROL Prueba A/B] actividad:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![Lista desplegable Crear actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Recommendations] es una funcionalidad de [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obtener información sobre los distintos tipos de actividades, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) y la [Guía de actividades de Target](/help/main/c-activities/target-activities-guide.md).

1. En el cuadro de diálogo Crear actividad de prueba A/B, seleccione **[!UICONTROL Visual (predeterminado)]**, si es necesario.

   Si prefiere usar la variable [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el VEC de aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si es un [Cliente de Target Premium](/help/main/c-intro/intro.md#premium), desde el **[!UICONTROL Elija Workspace]** , elija una de las opciones [workspace](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   El [[!UICONTROL Elegir lugar de trabajo]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) en la ilustración anterior es una [Target Premium](/help/main/c-intro/intro.md) función y podría no mostrarse si su organización tiene un [!UICONTROL Target Standard] licencia.

1. En el **[!UICONTROL Introducir URL de actividad]** , especifique su [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md), luego haga clic en **[!UICONTROL Crear]**.

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

   Se abre el [!UICONTROL Compositor de experiencias visuales] con la página especificada en la dirección URL.

1. Clic **[!UICONTROL Actividad sin título]** en la parte superior del VEC, especifique un nombre para la actividad en el espacio proporcionado.

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

   El nombre de la actividad no puede contener ninguna de estas secuencias de caracteres:

   | Secuencia de caracteres | Descripción |
   |--- |--- |
   | ;= | Punto y coma, igual a |
   | ;+ | Punto y coma, más |
   | ;- | Punto y coma, menos |
   | ;@ | Punto y coma, signo de arroba |
   | ,= | Coma, igual a |
   | ,+ | Coma, más |
   | ,- | Coma, menos |
   | ,@ | Coma, Signo de arroba |
   | `[`&quot; | Corchete de apertura, comillas dobles |
   | &quot;`]` | Comillas tipográficas dobles, cerrar corchete |

1. Cree experiencias nuevas cambiando los elementos de la página.

   El [!UICONTROL Compositor de experiencias visuales] muestra dos fichas en la parte izquierda después de crear una actividad nueva: Experiencia A, que es la de control, y Experiencia B. Se centra en la pestaña Experiencia B, que puede modificar según desee. La Experiencia B es la experiencia alternativa que puede añadir a su prueba. Se pueden añadir varias experiencias a la prueba. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Si desea más información sobre cómo añadir y modificar experiencias en el [!UICONTROL Compositor de experiencias visuales], consulte  [Añadir experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar Experiencia B, empiece con el paso 2.

1. Haga clic en **[!UICONTROL Segmentación]**, en la parte superior del [!UICONTROL Compositor de experiencias visuales], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.

1. En el **[!UICONTROL Audiencia]** , haga clic en el icono editar (los puntos suspensivos verticales) y, a continuación, haga clic en **[!UICONTROL Reemplazar audiencia]**, entonces [seleccionar la audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para su actividad de.

   De forma predeterminada, la audiencia se establece en [!UICONTROL Todos los visitantes].

1. Elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Porcentaje de audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Configure la asignación de tráfico.

   Se pueden mostrar varias experiencias a la misma audiencia. Se muestra un diagrama con la audiencia seleccionada y las experiencias que añadió a la actividad.

   Elija el método de asignación de tráfico que desee:

   * **[!UICONTROL Manual (predeterminado)]**: especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [[!UICONTROL Asignación automática] descripción general](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Segmentación automática para experiencias personalizadas]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más adaptadas a los visitantes en función de sus perfiles de cliente y del comportamiento pasado de visitantes similares. Para obtener más información, consulte [Información general sobre la segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   También puede hacer clic en **[!UICONTROL Añadir]** para añadir otra experiencia a la actividad.

1. Cuando esté satisfecho con las opciones de asignación de audiencia, experiencia y tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

1. Clic **[!UICONTROL Guardar y cerrar]** o **[!UICONTROL Guardar]**.

Después de crear la actividad, las variables [!UICONTROL Información general] La pestaña muestra información sobre la actividad, incluido un diagrama de la actividad.

## Vídeo de formación: Creación de pruebas A/B (8:36). ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Crear un [!UICONTROL Prueba A/B] actividad en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)

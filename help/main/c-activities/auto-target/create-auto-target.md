---
keywords: Crear segmentación automática;prueba A/B;actividad de segmentación automática;nueva actividad a/b;segmentación automática;segmentación automática para experiencias personalizadas;personalizado;optimización
description: Aprenda a utilizar el [!UICONTROL Visual Experience Composer] (VEC) para crear una actividad de prueba A/B de [!UICONTROL Auto-Target].
title: ¿Cómo creo una actividad de [!UICONTROL Auto-Target]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 19%

---

# Crear una actividad [!UICONTROL Auto-Target]

Use el [!UICONTROL Visual Experience Composer] (VEC) en [!DNL Adobe Target] para crear su actividad [!UICONTROL Auto-Target] [!UICONTROL A/B Test] directamente en una página habilitada para [!DNL Target] y para modificar partes de la página en [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).

Para crear una actividad [!UICONTROL Auto-Target]:

1. En la lista **[!UICONTROL Activities]**, haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

1. En el cuadro de diálogo [!UICONTROL Create A/B Test Activity], seleccione **[!UICONTROL Visual]**, si es necesario.

   Si prefiere usar [!UICONTROL Form-Based Experience Composer], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Form-Based Experience Composer], [!DNL Target] ofrece el VEC [!UICONTROL Single Page Application]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si eres [cliente de Target Premium](/help/main/c-intro/intro.md#premium), en la lista desplegable **[!UICONTROL Choose Workspace]**, elige [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   La opción [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) es una característica de [Target Premium](/help/main/c-intro/intro.md) y es posible que no se muestre si su organización tiene una licencia de [!UICONTROL Target Standard].

1. En el cuadro **[!UICONTROL Enter Activity URL]**, especifique la [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

1. Haga clic en **[!UICONTROL Create]**.

   Se abre [!UICONTROL Visual Experience Composer] y se muestra la página especificada en la dirección URL.

1. Haga clic en el icono **[!UICONTROL Rename]** ( ![Cambiar nombre del icono](/help/main/assets/icons/MoreSmallListVert.svg) ), haga clic en **[!UICONTROL Rename]**, especifique un nombre para la actividad y, a continuación, haga clic en **[!UICONTROL Save]**.

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

1. Cree nuevas experiencias cambiando los elementos de la página.

   [!UICONTROL Visual Experience Composer] muestra dos fichas en el lado izquierdo después de crear una nueva actividad: [!UICONTROL Experience A] y [!UICONTROL Experience B]. [!UICONTROL Experience A] es la experiencia de control. Se encuentra enfocado en la ficha [!UICONTROL Experience B], la cual puede modificar según desee. [!UICONTROL Experience B] es la experiencia alternativa que puede agregar a la prueba. Para agregar varias experiencias a la prueba, haga clic en el icono [!UICONTROL Add] ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) en la parte superior del panel [!UICONTROL Experiences]. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Para obtener más información sobre cómo agregar y modificar experiencias en [!UICONTROL Visual Experience Composer], consulte [Agregar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar Experiencia B, empiece con el paso 2.

1. Haga clic en **[!UICONTROL Targeting]**, en la parte superior de [!UICONTROL Visual Experience Composer], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL All Visitors]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL All Visitors] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Replace]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo [!UICONTROL Add Audience], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Assign Audience]**.

      Puede hacer clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Si necesita crear una audiencia nueva que no esté ya en [!UICONTROL Audience Library], haga clic en **Crear audiencia**. Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

      * **[!UICONTROL Audience Library]**: cree una audiencia bajo demanda que se guarde en [!UICONTROL Audience Library] y que pueda reutilizarse en otras actividades
      * **[!UICONTROL This activity only]**: cree una [audiencia específica de actividad](/help/main/c-target/creating-activity-only-audience.md) que no se haya guardado en [!UICONTROL Audience Library] y que solo se pueda usar en la actividad actual

   1. Haga clic en **[!UICONTROL Visitor Percentage]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Haga clic en el control **[!UICONTROL Traffic Allocation]** y, a continuación, elija el método de asignación de tráfico que desee en el panel derecho. En este escenario, haga clic en **[!UICONTROL Auto-Taget for personalized experiences]**.

   ![Configuración del método de asignación de tráfico](/help/main/c-activities/assets/auto-target.png)

   Los métodos de asignación de tráfico disponibles son los siguientes:

   * **[!UICONTROL Manual (Default)]**: especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   * **[!UICONTROL Auto-Allocate to best experience]**: la mayoría de los visitantes de la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, vea [[!UICONTROL Auto-Allocate] información general](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones al identificar varias experiencias de alto rendimiento definidas por expertos en marketing; a continuación, ofrece a los visitantes la experiencia más adaptada en función de sus perfiles de cliente individuales y de los comportamientos pasados de visitantes similares. Para obtener más información, consulte [Información general sobre la segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Haga clic en **[!UICONTROL Experiences]** en el panel derecho y, a continuación, especifique la asignación de tráfico que desee para cada experiencia.

1. Cuando esté satisfecho con las opciones de asignación de audiencia, experiencia y tráfico, haga clic en **[!UICONTROL Next]** para ir al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   >[!NOTE]
   >
   >Si desea usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, vea información importante en [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Haga clic en **[!UICONTROL Save & Close]** o **[!UICONTROL Save]**.

Después de crear la actividad, la ficha [!UICONTROL Overview] muestra información sobre la actividad, incluido un diagrama de la actividad.

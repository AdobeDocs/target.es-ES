---
keywords: Crear segmentación automática;prueba A/B;actividad de segmentación automática;nueva actividad a/b;segmentación automática;segmentación automática para experiencias personalizadas;personalizado;optimización
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) para crear una actividad de prueba A/B de [!UICONTROL Segmentación automática].
title: ¿Cómo creo una actividad de [!UICONTROL Segmentación automática]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
TQID: https://experienceleague.adobe.com/qbt-h-4C4uVz6r6xmwKmSeU-RuBdWikmtDQq40dBq9k
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1062
ht-degree: 17%

---

# Crear una actividad [!UICONTROL de segmentación automática]

Use el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear su actividad de [!UICONTROL Segmentación automática] [!UICONTROL Prueba A/B] directamente en una página habilitada para [!DNL Target] y para modificar partes de la página en [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).

Para crear una actividad de [!UICONTROL Segmentación automática]:

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

1. En el cuadro de diálogo [!UICONTROL Crear actividad de prueba A/B], seleccione **[!UICONTROL Visual]**, si es necesario.

   Si prefiere usar el [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el VEC de [!UICONTROL aplicación de una sola página]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si eres [cliente de Target Premium](/help/main/c-intro/intro.md#premium), en la lista desplegable **[!UICONTROL Elegir Workspace]**, elige [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   La opción [[!UICONTROL Elegir lugar de trabajo]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) es una característica de [Target Premium](/help/main/c-intro/intro.md) y podría no mostrarse si su organización tiene una licencia de [!UICONTROL Target Standard].

1. En el cuadro **[!UICONTROL Introducir URL de actividad]**, especifique la [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

1. Haga clic en **[!UICONTROL Crear]**.

   Se abre el [!UICONTROL Compositor de experiencias visuales] con la página especificada en la dirección URL.

1. Haga clic en el icono **[!UICONTROL Rename]** ( ![Rename icon](/help/main/assets/icons/MoreSmallListVert.svg) ), haga clic en **[!UICONTROL Rename]**, especifique un nombre para la actividad y, a continuación, haga clic en **[!UICONTROL Guardar]**.

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

   El [!UICONTROL Compositor de experiencias visuales] muestra dos pestañas a la izquierda después de crear una nueva actividad: la [!UICONTROL Experiencia A] y la [!UICONTROL Experiencia B]. La [!UICONTROL Experiencia A] es la experiencia de control. Se centra en la ficha [!UICONTROL Experiencia B], que puede modificar según desee. [!UICONTROL Experiencia B] es la experiencia alternativa que puedes agregar a tu prueba. Para agregar varias experiencias a la prueba, haz clic en el icono [!UICONTROL Agregar] ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) en la parte superior del panel [!UICONTROL Experiencias]. También podemos eliminar Experiencia A de la actividad si no queremos incluir una experiencia de sitio predeterminada como opción.

   Para obtener más información sobre cómo agregar y modificar experiencias en [!UICONTROL Compositor de experiencias visuales], consulte [Agregar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar Experiencia B, empiece con el paso 2.

1. Haga clic en **[!UICONTROL Segmentación]** en la parte superior de [!UICONTROL Compositor de experiencias visuales] para pasar al siguiente paso en el flujo de trabajo guiado de tres pasos.

   Se abrirá el diagrama de flujo.

   ![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL Todos los visitantes]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL Todos los visitantes] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo [!UICONTROL Agregar audiencia], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Asignar audiencia]**.

      Puede hacer clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Si necesita crear una audiencia nueva que no esté ya en la [!UICONTROL Biblioteca de audiencias], haga clic en **Crear audiencia**. Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

      * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la [!UICONTROL Biblioteca de audiencias] y que pueda reutilizarse en otras actividades
      * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la [!UICONTROL Biblioteca de audiencias] y que solo se puede usar en la actividad actual

   1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que quiere que participen de la actividad.

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % del público de California.

1. Haga clic en el control **[!UICONTROL Asignación de tráfico]** y, a continuación, elija el método de asignación de tráfico que desee en el panel derecho. En este escenario, haga clic en **[!UICONTROL Segmentación automática para experiencias personalizadas]**.

   ![Configuración del método de asignación de tráfico](/help/main/c-activities/assets/auto-target.png)

   Los métodos de asignación de tráfico disponibles son los siguientes:

   * **[!UICONTROL Manual (predeterminado)]**: especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad son dirigidos automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [[!UICONTROL Información general sobre la asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Segmentación automática para experiencias personalizadas]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones al identificar varias experiencias de alto rendimiento definidas por expertos en marketing; a continuación, ofrece a los visitantes la experiencia más adaptada en función de su perfil de cliente y del comportamiento pasado de visitantes similares. Para obtener más información, consulte [Información general sobre la segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Haga clic en **[!UICONTROL Experiencias]** en el panel derecho y, a continuación, especifique la asignación de tráfico que desee para cada experiencia.

1. Cuando esté satisfecho con las opciones de asignación de audiencia, experiencia y tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad.

   >[!NOTE]
   >
   >Si desea usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, vea información importante en [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Haz clic en **[!UICONTROL Guardar y cerrar]** o en **[!UICONTROL Guardar]**.

Después de crear la actividad, la ficha [!UICONTROL Información general] muestra información sobre la actividad, incluido un diagrama de la actividad.

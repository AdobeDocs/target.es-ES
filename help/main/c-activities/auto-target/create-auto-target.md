---
keywords: Crear segmentación automática;prueba A/B;actividad de segmentación automática;nueva actividad a/b;segmentación automática;segmentación automática para experiencias personalizadas;personalizado;optimización
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) para crear una actividad de prueba A/B de [!UICONTROL Segmentación automática].
title: ¿Cómo creo una actividad de [!UICONTROL Segmentación automática]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
TQID: 'https://experienceleague.adobe.com/qbt-h-4C4uVz6r6xmwKmSeU-RuBdWikmtDQq40dBq9k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 9f1aaf5c0b172b4bbe89266800708881306e4592
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 12%
---
# Crear una actividad [!UICONTROL de segmentación automática] {#create-auto-target-activity}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear una actividad de **[!UICONTROL Segmentación automática]** en el **[!UICONTROL Compositor de experiencias visuales]** (VEC). Puede crear sus experiencias, establecer objetivos y elegir el método de asignación de tráfico de segmentación automática y, a continuación, configurar los objetivos y la configuración.

>[!ENDSHADEBOX]

Use el **[!UICONTROL Compositor de experiencias visuales]** (VEC) en [!DNL Adobe Target] para crear su actividad de **[!UICONTROL Segmentación automática]** **[!UICONTROL Prueba A/B]** directamente en una página habilitada para [!DNL Target] y para modificar partes de la página en [!DNL Target].

>[!NOTE]
>
>**[!UICONTROL Segmentación automática]** está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).

La actividad sigue el flujo de trabajo guiado de tres pasos del VEC:

1. [Creación de experiencias](#build-experiences)
1. [Establecimiento de objetivos y asignación de tráfico](#set-targeting)
1. [Configurar objetivos y opciones](#configure-goals-and-settings)

## Paso 1: Crear experiencias {#build-experiences}

Cree la actividad y, a continuación, diseñe las experiencias alternativas que desee probar con el control.

### Creación de la actividad {#create-activity}

Abra la página que desee probar en el **[!UICONTROL Compositor de experiencias visuales]** y asigne un nombre a la actividad.

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba A/B]**.

   ![](../assets/create-ab-1.png)

1. En el cuadro de diálogo **[!UICONTROL Crear actividad de prueba A/B]**, elija su Compositor de experiencias:

   * **[!UICONTROL Visual]**.
   * **[!UICONTROL Compositor de experiencias basadas en formularios]**, consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del **[!UICONTROL Compositor de experiencias basadas en formularios]**, [!DNL Target] ofrece el VEC de **[!UICONTROL aplicación de una sola página]**. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si eres [cliente de Target Premium](/help/main/c-intro/intro.md#premium), en la lista desplegable **[!UICONTROL Elegir Workspace]**, elige [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. En el cuadro **[!UICONTROL Introducir URL de actividad]**, especifique la [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

1. Haga clic en **[!UICONTROL Crear]**. Se abre el **[!UICONTROL Compositor de experiencias visuales]** con la página especificada en la dirección URL.

1. Para asignar un nombre a la actividad, haz clic en el icono **[!UICONTROL Editar]** ( ![Editar icono](/help/main/assets/icons/Edit.svg) ), especifica un nombre descriptivo para la actividad y luego haz clic en **[!UICONTROL Guardar]**.

   {{activity-name-rules}}

   ![](../assets/create-ab-2.png)

### Diseño de las experiencias {#design-experiences}

Cree nuevas experiencias cambiando los elementos de la página.

Después de crear una actividad nueva, **[!UICONTROL Compositor de experiencias visuales]** muestra dos fichas a la izquierda: Experiencia A y Experiencia B.

* **Experiencia A** es la experiencia de control. Puede eliminarla si no desea incluir una experiencia de sitio predeterminada como opción.
* **Experiencia B** es la experiencia alternativa que agregaste a tu prueba. Se centra en esta pestaña, que puede modificar según desee.

Para agregar más experiencias a la prueba, haz clic en el icono **[!UICONTROL Agregar]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ).

![](../assets/create-ab-3.png)

Para obtener más información sobre cómo agregar y modificar experiencias en **[!UICONTROL Compositor de experiencias visuales]**, consulte [Agregar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#ab-add-experience).

## Paso 2: Establecer el objetivo y la asignación de tráfico {#set-targeting}

Después de obtener acceso al menú **[!UICONTROL Segmentación]**, se abre el diagrama de flujo.

![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

El diagrama de flujo le guía a través de la asignación de una audiencia y su porcentaje de tráfico, la selección del método de asignación de tráfico y la especificación de la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL Todos los visitantes]** para seleccionar otra audiencia para la actividad.

   La audiencia **[!UICONTROL Todos los visitantes]** está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda. Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % del público de California.

   +++ Pasos para seleccionar una audiencia diferente

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo **[!UICONTROL Agregar audiencia]**, [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Asignar audiencia]**.

      Para crear una audiencia que combine varias audiencias, haga clic en **[!UICONTROL Combinar audiencias]**. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Para crear una audiencia nueva que no esté ya en la **[!UICONTROL Biblioteca de audiencias]**, haga clic en **[!UICONTROL Crear audiencia]**. En [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), elija una de las siguientes opciones:

      * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la **[!UICONTROL Biblioteca de audiencias]** y pueda reutilizarse en otras actividades.
      * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la **[!UICONTROL Biblioteca de audiencias]** y que solo se puede usar en la actividad actual.

   1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que quiere que participen de la actividad.

   +++

1. Haga clic en el control **[!UICONTROL Asignación de tráfico]** y, a continuación, elija el método de asignación de tráfico que desee en el panel derecho. En este escenario, haga clic en **[!UICONTROL Segmentación automática para experiencias personalizadas]**.

   ![Configuración del método de asignación de tráfico](/help/main/c-activities/assets/auto-target.png)

   +++ Métodos de asignación de tráfico

   | Método | Qué hace |
   |---|---|
   | **[!UICONTROL Manual (predeterminado)]** | Especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%. |
   | **[!UICONTROL Asignación automática a la mejor experiencia]** | La mayoría de los participantes en la actividad se dirigen automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [**[!UICONTROL Información general sobre la asignación automática &#x200B;]**](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4). |
   | **[!UICONTROL Segmentación automática para experiencias personalizadas]** | [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones al identificar varias experiencias de alto rendimiento definidas por expertos en marketing; a continuación, ofrece a los visitantes la experiencia más adaptada en función de sus perfiles de cliente y del comportamiento pasado de visitantes similares. Para obtener más información, consulte [Información general sobre la segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

   +++

1. Haga clic en **[!UICONTROL Experiencias]** en el panel derecho y, a continuación, especifique la asignación de tráfico que desee para cada experiencia.

1. Cuando esté satisfecho con las opciones de asignación de audiencia, experiencia y tráfico, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

## Paso 3: Configurar los objetivos y la configuración {#configure-goals-and-settings}

En la página **[!UICONTROL Objetivos y configuración]**, le dices a [!DNL Target] cómo medir la actividad. La configuración disponible depende de si usa [!DNL Target] o [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) para la actividad. Revise las secciones de la página y configure lo que necesite.

   | Sección | Lo que ha configurado |
   |---|---|
   | **[!UICONTROL Configuración de actividades]** | Un objetivo opcional, **[!UICONTROL Priority]** (se usa cuando varias actividades comparten una ubicación y una audiencia) y **[!UICONTROL Duration]** (fechas de inicio y finalización). |
   | **[!UICONTROL Configuración de informes]** | La fuente de informes, la métrica del objetivo (por ejemplo, una métrica de **[!UICONTROL Conversión]**), las métricas adicionales, las audiencias para informes y la metodología estadística. |
   | **[!UICONTROL Configuración avanzada]** | Dependencias entre métricas de éxito, lo que sucede después de que un visitante alcanza la métrica de objetivo y cómo se incrementa el recuento. |
   | **[!UICONTROL Otros metadatos]** | Notas sobre la actividad que son útiles para usted o para otros integrantes del equipo. |

   >[!NOTE]
   >
   >Si desea usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) con esta actividad, vea información importante en [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Haz clic en **[!UICONTROL Guardar y cerrar]** o en **[!UICONTROL Guardar]**.

Después de crear la actividad, la ficha **[!UICONTROL Información general]** muestra información sobre la actividad, incluido un diagrama de la actividad.

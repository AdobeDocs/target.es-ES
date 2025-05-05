---
keywords: mvt; prueba multivariable; crear prueba multivariable; creación de prueba multivariable; crear mvt; creación de mvt, procedimiento de mvt; procedimiento de prueba multivariable
description: Aprenda a usar el [!UICONTROL Visual Experience Composer] (VEC) en  [!DNL Adobe Target] para crear un [!UICONTROL Multivariate Test] (MVT).
title: ¿Cómo creo un(a) [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: be118753eed999ce24d547c90ac9d195cce7e9e9
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 26%

---

# Crear una prueba multivariable

El [!UICONTROL Visual Experience Composer] (VEC) de [!DNL Adobe Target] facilita la creación de [!UICONTROL Multivariate Test] y la modificación de partes de la página en [!DNL Target].

El editor de apuntar y hacer clic [!DNL Target] le permite elegir cualquier ubicación y agregar varias ofertas.

[!UICONTROL Multivariate Test] (MVT) toma un informe centrado en una página. Es decir, la prueba se ejecuta en una determinada dirección URL, con las experiencias que diseño para esa página.

1. Haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   >[!NOTE]
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/main/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

1. (Condicional) Elija el tipo de entrega: [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email] o [!UICONTROL Other/API].

1. (Condicional) Si es cliente de [Target Premium](/help/main/c-intro/intro.md#premium), [elija un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique la dirección URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) para la página que desea probar y haga clic en **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >Utilice una dirección URL completa, incluido HTTP o HTTPS del principio.

   Si aparece un mensaje pidiendo que habilite el navegador para contenido mixto, siga las instrucciones del mensaje. Después de habilitar el navegador para contenido mixto, vuelva a comenzar por el Paso 1.

   Se abre [!UICONTROL Visual Experience Composer].

1. &#x200B;
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

1. [Cree las ofertas en cada ubicación](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Puede añadir los siguientes tipos de oferta:

   * HTML
   * Imagen
   * Texto

1. Haga clic en **[!UICONTROL Preview]** para [obtener una vista previa de sus experiencias](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Haga clic en el icono **[!UICONTROL Show Experiences]** ( ![icono Mostrar experiencias](/help/main/assets/icons/WebPages.svg) ) para mostrar la lista de todas las experiencias en el cuadro izquierdo.

1. Haga clic en una experiencia específica en la lista para verla.

1. (Condicional) Para excluir una o más experiencias de la actividad, haga clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar experiencias](/help/main/assets/icons/Experience.svg) ) para mostrar el cuadro de diálogo [!UICONTROL Manage Experiences].

1. (Condicional) En el cuadro de diálogo [!UICONTROL Manage Experiences], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a la experiencia que desea excluir y, a continuación, haga clic en **[!UICONTROL Exclude]**.

   Puede elegir excluir una experiencia que muestre variaciones que entran en conflicto o una experiencia que no esté equilibrada desde el punto de vista estético.

1. (Condicional) Para excluir varias experiencias, seleccione las casillas de verificación de las experiencias que desee y haga clic en **[!UICONTROL Exclude]**.

1. [Utilice el estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para probar la viabilidad de su plan de prueba.

1. Haga clic en **[!UICONTROL Next]** para avanzar a la página [!UICONTROL Targeting].

   El paso **Segmentación** le resultará familiar si ha utilizado otros tipos de actividad de [!DNL Target]. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que ven cada experiencia.

   El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL All Visitors]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL All Visitors] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Replace]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo [!UICONTROL Add Audience], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Assign Audience]**.

      Puede hacer clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Si necesita crear una audiencia nueva que no esté ya en [!UICONTROL Audience Library], haga clic en **Crear audiencia**. Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

      * **[!UICONTROL Audience Library]**: cree una audiencia bajo demanda que se guarde en [!UICONTROL Audience Library] y que pueda reutilizarse en otras actividades.
      * **[!UICONTROL This activity only]**: cree una [audiencia específica de actividad](/help/main/c-target/creating-activity-only-audience.md) que no se haya guardado en [!UICONTROL Audience Library] y que solo se pueda usar en la actividad actual.

   1. Haga clic en **[!UICONTROL Visitor Percentage]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. [Revise el resumen de la prueba](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), realice los cambios que desee y luego haga clic en **[!UICONTROL Next]**.

1. [Especifique los objetivos y la configuración](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la prueba.

1. Haga clic en **[!UICONTROL Save and Close]** para crear la actividad.

## Vídeo de formación: Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se muestra cómo planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)

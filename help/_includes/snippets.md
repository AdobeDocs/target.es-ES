---
source-git-commit: 87c0d2aa67d54dcbc2963be63d2d7ad9c02b6aa9
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 5%
---
# Fragmentos

## Funciones de Target Premium {#premium-note}

>[!NOTE]
>
>Esta funcionalidad está disponible como parte de la licencia [Target Premium](/help/main/c-intro/intro.md#premium). Esta funcionalidad no está disponible en [!DNL Target Standard].

## Actualización de permisos de Target {#permissions-update}

>[!IMPORTANT]
>
>Los usuarios de [!DNL Target] con derechos de [!UICONTROL Administrador de productos] y [!UICONTROL Administrador de sistemas] pueden editar toda la configuración en las páginas de [!UICONTROL Administración], independientemente de su rol en [!DNL Target]. Los usuarios sin estos permisos tienen acceso de solo lectura a esta configuración.

## IU de Target actualizada {#updated-ui}

>[!NOTE]
>
>Como novedad en 2025, [!DNL Target] introdujo una interfaz de usuario actualizada y [!UICONTROL Compositor de experiencias visuales] (VEC). Haga clic en los siguientes vínculos para obtener más información:
>
>* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Actividades], [!UICONTROL Recommendations] y [!UICONTROL Compositor de experiencias visuales] (VEC).
>
>* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para la [!UICONTROL Biblioteca de ofertas].
>
>* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.
>
>* [[!UICONTROL Cambios del Compositor de experiencias visuales]](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.
>
>* [[!UICONTROL Compositor de experiencias visuales] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario de VEC actualizada y sus opciones.
>
>* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y el [!UICONTROL Compositor de experiencias visuales] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la obsolescencia de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a sacar el máximo partido a la IU actualizada.

## Reglas de nombre de actividad {#activity-name-rules}

El nombre de la actividad no puede empezar por `=`, `+`, `-` ni `@`. El nombre de la actividad tampoco puede contener ninguna de las siguientes secuencias de caracteres: `;=`, `;+`, `;-`, `;@`, `,=`, `,+`, `,-`, `,@`, `["` o `"]`.

## Seleccione una audiencia en el paso Segmentación {#audience-selection-steps}

1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.

1. En el cuadro de diálogo **[!UICONTROL Agregar audiencia]**, [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Asignar audiencia]**.

   Para crear una audiencia que combine varias audiencias, haga clic en **[!UICONTROL Combinar audiencias]**. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

   Para crear una audiencia nueva que no esté ya en la [!UICONTROL Biblioteca de audiencias], haga clic en **[!UICONTROL Crear audiencia]**. En [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), elija una de las siguientes opciones:

   * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la [!UICONTROL Biblioteca de audiencias] y pueda reutilizarse en otras actividades.
   * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la [!UICONTROL Biblioteca de audiencias] y que solo se puede usar en la actividad actual.

1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que quiere que participen de la actividad.



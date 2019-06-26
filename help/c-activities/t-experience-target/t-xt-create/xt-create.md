---
description: Use el Compositor de experiencias visuales para crear una actividad de segmentación de experiencias en una página con Target habilitado y para modificar partes de la página en Target.
seo-description: Use el Compositor de experiencias visuales para crear una actividad de segmentación de experiencias (XT) en una página con Target habilitado y modificar partes de la página en Adobe Target.
seo-title: Crear una actividad de segmentación de experiencias
solution: Target
subtopic: Prueba multivariable
title: Crear una actividad de segmentación de experiencias
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Crear una actividad de segmentación de experiencias{#create-an-experience-targeting-activity}

Use the [!UICONTROL Visual Experience Composer] (VEC) to create an [!UICONTROL Experience Targeting] (XT) activity on a Target-enabled page and to modify portions of the page within [!DNL Adobe Target].

Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

Experience Targeting, including [geo-targeting](/help/c-target/c-audiences/c-target-rules/geo.md), is valuable for defining rules that target a specific experience or content to a particular audience. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias.

For more information about Experience Targeting, a use-case scenario, and training videos, see [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**Para crear una actividad XT:**

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** &gt; **[!UICONTROL Segmentación de experiencias]**.

   ![Crear actividad &gt; Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Los tipos de actividades disponibles dependen de su cuenta de Target. Algunos tipos de actividades podrían no aparecer en su lista. For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Cuadro de diálogo Crear actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >Además del Compositor de experiencias visuales y el Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Su organización tiene una licencia de Target Standard si no ve esta opción.]

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   If your account is [configured with a default URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), that URL appears by default. Si es necesario, puede cambiar de la dirección predeterminada a otra URL.

   Se abre el VEC, mostrando la página especificada en la URL.

   ![Actividad de segmentación de experiencias dentro del VEC](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![Campo Nombre](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Cree nuevas experiencias dirigidas a distintas audiencias.

   For step-by-step instructions, see [Add experience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique los [objetivos y la configuración](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.
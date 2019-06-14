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
source-git-commit: dcddbf8c1a4f406fdbfb00b9deaa75113aa7b624

---


# Crear una actividad de segmentación de experiencias{#create-an-experience-targeting-activity}

Use el [!UICONTROL Compositor de experiencias visuales] (VEC) para crear una [!UICONTROL actividad de segmentación] de experiencias (XT) en una página con Target habilitado y modificar partes de la página dentro [!DNL Adobe Target]de.

Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

Segmentación de experiencias, incluida [la segmentación geográfica](/help/c-target/c-audiences/c-target-rules/geo.md), es útil para definir reglas dirigidas a una experiencia o contenido específicos para una audiencia concreta. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias.

Para obtener más información sobre segmentación de experiencias, casos de uso y vídeos de formación, consulte [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md).

**Para crear una actividad XT:**

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** &gt; **[!UICONTROL Segmentación de experiencias]**.

   ![Crear actividad &gt; Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Los tipos de actividades disponibles dependen de su cuenta de Target. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, Personalización [!UICONTROL automatizada] es una función [de Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles y [!DNL Target] sus diferencias, consulte [Actividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad necesita sus necesidades.

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Cuadro de diálogo Crear actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione esa opción. Consulte [Compositor de experiencias basadas en formularios](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).

   >[!NOTE]
   >
   >Además del Compositor de experiencias visuales y el Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

1. Especifique la URL [de la actividad](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)y haga clic **[!UICONTROL en Siguiente]**.

   Si su cuenta está [configurada con una dirección URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)predeterminada, esa dirección URL aparece de forma predeterminada. Si es necesario, puede cambiar de la dirección predeterminada a otra URL.

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

   Para obtener instrucciones paso a paso, consulte [Añadir experiencia](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique los [objetivos y la configuración](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.
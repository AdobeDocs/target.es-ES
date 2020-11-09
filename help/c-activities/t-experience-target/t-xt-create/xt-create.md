---
description: Use el Compositor de experiencias visuales para crear una actividad de segmentación de experiencias (XT) en una página con Target habilitado y para modificar partes de la página en Adobe Target.
title: Crear una actividad de segmentación de experiencias
feature: xt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# Crear una actividad de segmentación de experiencias{#create-an-experience-targeting-activity}

Use el [!UICONTROL Compositor de experiencias visuales] para crear una actividad de [!UICONTROL segmentación de experiencias] (XT) en una página con habilitado y para modificar partes de la página en [!DNL Adobe Target].

Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

La segmentación de experiencias, incluyendo [Segmentación geográfica](/help/c-target/c-audiences/c-target-rules/geo.md), sirve para definir reglas que dirigen un contenido o experiencia determinados a una audiencia concreta. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias.

Para obtener más información sobre la segmentación de experiencias, casos de uso y vídeos de formación, consulte [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md).

**Para crear una actividad XT:**

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Segmentación de experiencias]**.

   ![Crear actividad > Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Los tipos de actividades disponibles dependen de su cuenta de Target. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Automated Personalization] es una funcionalidad de [Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Cuadro de diálogo Crear actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [!UICONTROL Elegir lugar de trabajo] de la ilustración anterior es una [función de Target Premium](/help/c-intro/intro.md). Su organización tiene una licencia de Target Standard si no ve esta opción.

1. (Condicional) Si es cliente de Target Premium, [elija un espacio de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique la [URL de la actividad](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) y haga clic en **[!UICONTROL Siguiente]**.

   Si la cuenta se [configura con una dirección URL predeterminada](/help/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección, si es necesario.

   Se abre el VEC y muestra la página especificada en la dirección URL.

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

1. Especifique los [objetivos y la configuración](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.
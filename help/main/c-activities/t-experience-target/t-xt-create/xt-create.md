---
keywords: Segmentación de experiencias;xt;create
description: Aprenda a utilizar el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear un [!UICONTROL Segmentación de experiencias] Actividad (XT).
title: ¿Cómo se crea un [!UICONTROL Segmentación de experiencias] ¿Actividad?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 51%

---

# Crear un [!UICONTROL Segmentación de experiencias] Actividad (XT)

Utilice el [!UICONTROL Compositor de experiencias visuales] (VEC) para crear un [!UICONTROL Segmentación de experiencias] Actividad (XT) en una [!DNL Target]página habilitada para y para modificar partes de la página en [!DNL Adobe Target].

[!UICONTROL Segmentación de experiencias] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

La segmentación de experiencias, incluyendo [Segmentación geográfica](/help/main/c-target/c-audiences/c-target-rules/geo.md), sirve para definir reglas que dirigen un contenido o experiencia determinados a una audiencia concreta. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias.

Para obtener más información acerca de [!UICONTROL Segmentación de experiencias], un caso de uso y vídeos de formación, consulte [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md).

**Para crear un [!UICONTROL Segmentación de experiencias] actividad:**

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Segmentación de experiencias]**.

   ![Crear actividad > Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Automated Personalization] es una funcionalidad de [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/main/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   Si prefiere usar la variable [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione [!UICONTROL Form].

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el VEC de aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información sobre la resolución de problemas del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si es un [!DNL Target Premium] cliente, [elija un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   El [!UICONTROL Elegir lugar de trabajo] La opción es una [Target Premium](/help/main/c-intro/intro.md) función. Si su organización tiene un [!DNL Target Standard] licencia si no ve esta opción.

1. Especifique la URL [de la actividad](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) y haga clic **[!UICONTROL en Crear]**.

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección, si es necesario.

   Se abre el VEC y muestra la página especificada en la dirección URL.

   ![Actividad de segmentación de experiencias dentro del VEC](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![Campo Nombre](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Cree nuevas experiencias dirigidas a diferentes audiencias.

   Para obtener instrucciones paso a paso, consulte [Añadir experiencia](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique los [objetivos y la configuración](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.

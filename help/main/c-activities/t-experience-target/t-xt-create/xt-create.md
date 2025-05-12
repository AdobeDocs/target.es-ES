---
keywords: Segmentación de experiencias;xt;create
description: Aprenda a usar el [!UICONTROL Visual Experience Composer] (VEC) en  [!DNL Adobe Target] para crear una actividad de [!UICONTROL Experience Targeting] (XT).
title: ¿Cómo creo una actividad de [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 9cc1eb4c5c95ea51bc0a1fc9e89b245a18c9914b
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 33%

---

# Crear una actividad [!UICONTROL Experience Targeting] (XT)

Use [!UICONTROL Visual Experience Composer] (VEC) para crear una actividad [!UICONTROL Experience Targeting] (XT) en una página habilitada para [!DNL Target] y para modificar partes de la página en [!DNL Adobe Target].

[!UICONTROL Experience Targeting] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

[!UICONTROL Experience Targeting], incluido [targeting geográfico](/help/main/c-target/c-audiences/c-target-rules/geo.md), sirve para definir reglas que dirigen un contenido o experiencia determinados a una audiencia concreta. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias.

Para obtener más información sobre [!UICONTROL Experience Targeting], un caso de uso y vídeos de aprendizaje, consulte [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md).

**Para crear una actividad [!UICONTROL Experience Targeting]:**

1. En la lista [!UICONTROL Activities], haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**.

   >[!NOTE]
   >
   >Nota: los tipos de actividades disponibles dependen de su cuenta de [!DNL Target]. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, [!UICONTROL Automated Personalization] es una [característica de Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/main/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

1. Seleccione **[!UICONTROL Visual]**, si es necesario.

   Si prefiere usar el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione [!UICONTROL Form].

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Form-Based Experience Composer], [!DNL Target] ofrece el VEC de aplicación de una sola página. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Si es cliente de [!DNL Target Premium], [elija un área de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   La opción [!UICONTROL Choose Workplace] es una característica de [Target Premium](/help/main/c-intro/intro.md). Si su organización tiene una licencia de [!DNL Target Standard] si no ve esta opción.

1. Especifique la [URL de actividad](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) y haga clic en **[!UICONTROL Create]**.

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección, si es necesario.

   Se abre el VEC y muestra la página especificada en la dirección URL.

1. Para asignar un nombre a la actividad, haga clic en el icono **[!UICONTROL Edit]** ( ![Editar icono](/help/main/assets/icons/Edit.svg) ) junto a &quot;[!UICONTROL Untitled Activity]&quot;, especifique un nombre descriptivo para la actividad y haga clic en **[!UICONTROL Save]**.

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

---
keywords: prioridad;crear experiencia;prioridad;experiencia;audiencia;experiencia;convertir experiencias;compositor de experiencias visuales;visual experience composer
description: Descubra cómo los visitantes pueden cambiar entre experiencias en un [!DNL Adobe Target] [!UICONTROL Segmentación de experiencias] (XT) a medida que evolucionan sus perfiles.
title: ¿Pueden los visitantes cambiar de experiencia en un [!UICONTROL Segmentación de experiencias] ¿Actividad?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 44%

---

# Cambiar experiencias en [!UICONTROL Segmentación de experiencias]

Con [!UICONTROL Segmentación de experiencias], puede controlar qué experiencia ven los visitantes a medida que evolucionan sus perfiles.

La siguiente lista presenta solo algunos casos en los que los perfiles de los visitantes pueden evolucionar y es posible que desee presentar contenido diferente en función de esos cambios:

| Escenario | Detalles |
|--- |--- |
| Ubicación geográfica | Mientras que los visitantes viajan por negocios o por ocio, es posible que accedan a su sitio web o aplicación móvil desde diferentes ubicaciones geográficas. |
| Estado del cliente | Los visitantes pueden considerarse potenciales antes de crear una cuenta o comprar un producto. |
| Afinidad de la categoría | La [afinidad de categoría](/help/main/c-target/c-visitor-profile/category-affinity.md) función en [!DNL Target] captura automáticamente las categorías que ven los visitantes y luego calcula la afinidad de los visitantes por la categoría con fines de segmentación. Por ejemplo, a los visitantes que vieron varios artículos en su sitio web sobre un tema en particular se les presenta contenido relacionado con ese tema. |
| Día de la semana | Conforme se aproxime el fin de semana, es posible que quiera mostrar a los visitantes contenidos sobre películas, lugares en los que cenar u otras formas de entretenimiento. |

Para usar estas capacidades en [!DNL Target]Sin embargo, es importante comprender la siguiente información a medida que trabaja con [!UICONTROL Segmentación de experiencias] actividades:

* **La prioridad la controla el orden de las experiencias, de arriba abajo.** Si un visitante cumple los requisitos de más de dos audiencias, recibirá contenido de la experiencia de prioridad más alta.
* **Los visitantes cambian de experiencia en un [!UICONTROL Segmentación de experiencias] actividad si empiezan a cumplir los requisitos para la audiencia de una experiencia de prioridad superior.**

  Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Alemania, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante cambia a la Experiencia B (visitantes alemanes).

  ![Prioridad de EE. UU. > Alemania](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Los visitantes también cambian de experiencia si dejan de cumplir los requisitos de su audiencia actual y empiezan a cumplir los requisitos para una experiencia de prioridad inferior.**
* **Si los visitantes dejan de cumplir los requisitos para su experiencia actual y no cumplen los requisitos para otra experiencia, ven el contenido predeterminado.**

  Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Francia, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Francia, este visitante permanece en la experiencia original.

  ![Prioridad de EE. UU. > Alemania](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Se puede utilizar una experiencia segmentada a &quot;Todos los visitantes&quot; como la última experiencia de la [!UICONTROL Segmentación de experiencias] actividad para &quot;captar&quot; a visitantes que no cumplen los requisitos de ninguna otra experiencia. Si una experiencia segmentada a &quot;Todos los visitantes&quot; no es la última del pedido, se evaluarán otras experiencias segmentadas que aparezcan por debajo de esta experiencia.**

  Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Alemania, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante permanece en la Experiencia A (visitantes estadounidenses).

  ![Prioridad de EE. UU. > Todos los visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  Si no desea que ocurra esto, puede crear una audiencia nueva que esté definida de forma explícita como audiencia contraria a la de destino, como se muestra en el siguiente ejemplo:

  ![Prioridad de EE. UU. > No EE. UU.](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Con una experiencia única [!UICONTROL Segmentación de experiencias] actividad, los visitantes permanecen en una experiencia aunque dejen de cumplir los requisitos para la audiencia que les asigne dicha experiencia.**

  Si no desea que ocurra esto, podría crear otra experiencia dirigida a la audiencia contraria (por ejemplo, “No Estados Unidos” en oposición a “Estados Unidos”)..

  Como otra opción, puede crear un [!UICONTROL Prueba A/B] actividad dirigida a la audiencia deseada con una asignación del tráfico del 100 %, como se muestra a continuación:

  ![Experiencia de prioridad 1](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **[!DNL Target]La prioridad de las experiencias la define su orden (de arriba a abajo) al mostrarse en la interfaz de usuario de .**

  Es importante tener esto en cuenta cuando es posible que un visitante cumpla los requisitos de más de una de sus audiencias. Por ejemplo, si tiene dos experiencias, una dirigida a &quot;Estados Unidos&quot; y otra a &quot;Nueva York&quot;, un visitante en Nueva York cumple los requisitos para ambas audiencias. Por lo tanto, debe asegurarse de que la experiencia &quot;Nueva York&quot; se define antes que &quot;Estados Unidos&quot; en la [!DNL Target] IU. Esta práctica garantiza que la experiencia más dirigida, &quot;Nueva York&quot;, tenga mayor prioridad, como se muestra en el siguiente ejemplo:

  ![Prioridad NY > EE. UU.](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)

---
keywords: prioridad;crear experiencia;prioridad;experiencia;audiencia;experiencia;convertir experiencias;compositor de experiencias visuales;visual experience composer
description: Descubra cómo los visitantes pueden cambiar entre experiencias en una actividad de Adobe Target Experience Targeting (XT) a medida que evolucionan sus perfiles.
title: ¿Pueden los Visitantes cambiar experiencias en una Actividad de segmentación de experiencias?
feature: Experience Targeting
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 96%

---


# Cambiar experiencias en segmentación de experiencias

Información sobre cómo los visitantes pueden cambiar entre experiencias en una actividad de Segmentación de experiencias (XT) conforme evolucionan sus perfiles.

>[!NOTE]
>
>**21 de septiembre de 2017**
>
>Con la versión del 21 de septiembre de 2017, Target cambió el modo en que se coloca a los usuarios en experiencias en las actividades de segmentación de experiencias (XT; pruebas de página de aterrizaje en Target Classic). Para todas las actividades nuevas y existentes, los usuarios deben satisfacer las reglas de segmentación de experiencias en todos los aspectos para seguir viendo el contenido de la experiencia y ser contabilizados en los informes. Anteriormente, aunque un usuario dejara de cumplir los requisitos de cualquier experiencia, seguía viendo el contenido de la última experiencia para la que estuvo cualificado y se lo contabilizaba en sus informes.
>
>Este cambio se produjo automáticamente como parte de la versión para todas las actividades existentes y para cualquier actividad creada posteriormente. Si prefiere el método antiguo (el anterior al 21 de septiembre), puede crear audiencias empleando scripts de perfil, de modo que el usuario solo deba satisfacer una vez una condición para poder seguir perteneciendo a esa audiencia en el futuro. A continuación, utilice esas audiencias para cada experiencia de la actividad.

Con la Segmentación de experiencias, puede controlar la experiencia que ve cada visitante conforme evoluciona su perfil. La siguiente lista muestra solo algunas situaciones en las que los perfiles de los visitantes pueden evolucionar y es posible que quiera presentar contenido diferente:

| Situación | Detalles |
|--- |--- |
| Ubicación geográfica | Mientras que los visitantes viajan por negocios o por ocio, es posible que accedan a su sitio web o aplicación móvil desde diferentes ubicaciones geográficas. |
| Estado del cliente | Los visitantes pueden considerarse potenciales antes de crear una cuenta o comprar un producto. |
| Afinidad de la categoría | La [función de afinidad de la categoría](/help/c-target/c-visitor-profile/category-affinity.md) en Target captura automáticamente las categorías que visitan los usuarios y calcula la afinidad de los usuarios por la categoría para fines de segmentación. Por ejemplo, a los visitantes que hayan visto varios artículos en su sitio web sobre un tema en particular se les podría presentar contenido relacionado con este tema. |
| Día de la semana | Conforme se aproxime el fin de semana, es posible que quiera mostrar a los visitantes contenidos sobre películas, lugares en los que cenar u otras formas de entretenimiento. |

Para aprovechar estas capacidades en [!DNL Target], es importante entender la siguiente información cuando trabaje con actividades de XT:

* **La prioridad la controla el orden de las experiencias, de arriba abajo.** Si un visitante cumple los requisitos de más de dos audiencias, recibe el contenido de la experiencia con mayor prioridad.
* **Los visitantes cambiarán de experiencia en una actividad XT si empiezan a cumplir los requisitos de audiencia para obtener una experiencia de prioridad superior.**

   Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Alemania, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante cambia a la Experiencia B (visitantes alemanes).

   ![Prioridad de EE. UU. > Alemania](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **También cambiarán de experiencia si dejan de cumplir los requisitos de su audiencia actual, pero cumplen los de una experiencia de prioridad inferior.**
* **Si los visitantes dejan de cumplir los requisitos para su experiencia actual y no cumplen los de ninguna otra, verán el contenido predeterminado.**

   Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Francia, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Francia, este visitante permanecerá en la experiencia original.

   ![Prioridad de EE. UU. > Alemania](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Se puede utilizar una experiencia segmentada a “Todos los visitantes” como la última experiencia de la actividad de segmentación de experiencias para “captar” a los visitantes que no han participado de otras experiencias. Si una experiencia segmentada a “Todos los visitantes” no es la última del pedido, se evaluarán otras experiencias segmentadas que aparezcan por debajo de esta experiencia.**

   Por ejemplo, en la siguiente configuración de actividad, un visitante visitó su página web desde los Estados Unidos y viajó a Alemania, desde donde visitó de nuevo su página web. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante permanecerá en la Experiencia A (visitantes estadounidenses).

   ![Prioridad de EE. UU. > Todos los visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   Si no desea que ocurra esto, puede crear una audiencia nueva que esté definida de forma explícita como audiencia contraria a la de destino, como se muestra en el siguiente ejemplo:

   ![Prioridad de EE. UU. > No EE. UU.](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Con una actividad de XT de una sola experiencia, los visitantes permanecerán en una experiencia aunque dejen de cumplir los requisitos para la audiencia que les asigne dicha experiencia.**

   Si no desea que ocurra esto, podría crear otra experiencia dirigida a la audiencia contraria (por ejemplo, “No Estados Unidos” en oposición a “Estados Unidos”)..

   También tiene la opción de crear una actividad A/B dirigida a su audiencia deseada con una asignación del tráfico del 100 %, como se muestra a continuación:

   ![Experiencia de prioridad 1](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **La prioridad de las experiencias la define su orden (de arriba a abajo) al mostrarse en la interfaz de usuario de Target.**

   Es importante tener esto en cuenta cuando es posible que un visitante cumpla los requisitos de más de una de sus audiencias. Por ejemplo, si tiene dos experiencias, una dirigida a “Estados Unidos” y otra a “Nueva York”, un visitante en Nueva York cumpliría los requisitos para ambas audiencias. Por lo tanto, debe asegurarse de que la experiencia “Nueva York” se define antes que “Estados Unidos” en la interfaz de usuario de Target. De este modo se asegura de que la experiencia más dirigida, “Nueva York”, tenga mayor prioridad, como se muestra en el siguiente ejemplo:

   ![Prioridad NY > EE. UU.](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)


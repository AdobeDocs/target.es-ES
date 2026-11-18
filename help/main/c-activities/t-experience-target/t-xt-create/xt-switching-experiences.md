---
keywords: prioridad;crear experiencia;prioridad;experiencia;público;experiencia;convertir experiencias;compositor de experiencias visuales;visual experience composer
description: Descubra cómo los visitantes pueden cambiar entre experiencias en una actividad [!DNL Adobe Target] [!UICONTROL Segmentación de experiencias] (XT) a medida que evolucionan sus perfiles.
title: ¿Pueden los visitantes cambiar de experiencia en una actividad de [!UICONTROL segmentación de experiencias]?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
TQID: 'https://experienceleague.adobe.com/4bBukCristluFUClhewMcSsNMTPjLjXEqM1QyyropKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
    internal-label: Experience target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aaa094f4f36b6088ca180637d8054b6d5ff59d60
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 20%
---
# Cambiando experiencias en [!UICONTROL segmentación de experiencias] {#switching-experiences}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo funciona la prioridad en una actividad de **[!UICONTROL Segmentación de experiencias]** y cuándo los visitantes cambian de experiencia a medida que evolucionan sus perfiles.

>[!ENDSHADEBOX]

Con **[!UICONTROL Segmentación de experiencias]**, puede controlar qué experiencia ven los visitantes a medida que evolucionan sus perfiles. El perfil de un visitante puede cambiar de varias formas y es posible que desee presentar contenido diferente en función de esos cambios. En la tabla siguiente se muestran algunos ejemplos:

| Escenario | Detalles |
|--- |--- |
| Ubicación geográfica | Mientras que los visitantes viajan por negocios o por ocio, es posible que accedan a su sitio web o aplicación móvil desde diferentes ubicaciones geográficas. |
| Estado del cliente | Los visitantes pueden considerarse potenciales antes de crear una cuenta o comprar un producto. |
| Afinidad de la categoría | La característica [afinidad de la categoría](/help/main/c-target/c-visitor-profile/category-affinity.md) en [!DNL Target] captura automáticamente las categorías que ven los visitantes y luego calcula la afinidad de los visitantes por cada categoría con fines de segmentación. Por ejemplo, a los visitantes que vieron varios artículos en su sitio web sobre un tema en particular se les presenta contenido relacionado con ese tema. |
| Día de la semana | Conforme se aproxime el fin de semana, es posible que quiera mostrar a los visitantes contenidos sobre películas, lugares en los que cenar u otras formas de entretenimiento. |

Para usar estas capacidades en [!DNL Target], es importante entender la siguiente información cuando trabaje con actividades de **[!UICONTROL Segmentación de experiencias]**.

## Cómo se atienden los visitantes {#how-visitors-are-served}

El orden de las experiencias en la interfaz de usuario de [!DNL Target], de arriba abajo, controla su prioridad, por lo que debe definir la experiencia más segmentada antes que la más amplia. La siguiente tabla resume lo que los visitantes ven en cada situación.

| Situación | Lo que ve el visitante |
|--- |--- |
| El visitante cumple los requisitos de más de una audiencia. | El contenido de la experiencia que tiene la prioridad más alta. |
| El visitante empieza a cumplir los requisitos para la audiencia de una experiencia de prioridad superior. | El visitante cambia a la experiencia de prioridad superior. |
| El visitante deja de cumplir los requisitos de la audiencia actual y comienza a cumplir los requisitos para una experiencia de prioridad inferior. | El visitante cambia a la experiencia de prioridad inferior. |
| El visitante deja de cumplir los requisitos para la experiencia actual y no cumple los requisitos para otra experiencia. | Contenido predeterminado. |
| El visitante no cumple los requisitos de ninguna otra experiencia y la última experiencia está dirigida a &quot;Todos los visitantes&quot;. | La experiencia &quot;Todos los visitantes&quot; Esta experiencia &quot;captura&quot; a los visitantes que no cumplen los requisitos para ninguna otra experiencia. |
| Una experiencia segmentada a &quot;Todos los visitantes&quot; no es la última del pedido. | Las experiencias segmentadas que aparezcan por debajo de la experiencia &quot;Todos los visitantes&quot; se seguirán evaluando. |
| La actividad tiene una sola experiencia y el visitante deja de cumplir los requisitos para su audiencia. | El visitante permanece en la experiencia. |

## Ejemplos {#examples}

Los siguientes ejemplos ilustran estas situaciones.

### Prioridad: Nueva York y Estados Unidos

Si tiene dos experiencias, una dirigida a &quot;Estados Unidos&quot; y otra a &quot;Nueva York&quot;, un visitante ubicado en Nueva York cumple los requisitos para ambas audiencias. Por lo tanto, debe definir la experiencia &quot;Nueva York&quot; antes que &quot;Estados Unidos&quot; en la interfaz de usuario de [!DNL Target]. Esta práctica garantiza que la experiencia más dirigida, &quot;Nueva York&quot;, tenga mayor prioridad, como se muestra en el siguiente ejemplo:

![Prioridad NY > EE. UU.](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)

### Cambio a una experiencia de mayor prioridad: Estados Unidos a Alemania

En la siguiente configuración de actividad, un visitante accedió a su sitio web desde Estados Unidos y luego viajó a Alemania y visitó su sitio web una segunda vez. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante cambia a la Experiencia B (visitantes alemanes).

![Prioridad de EE. UU. > Alemania](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Dejando la audiencia: Estados Unidos a Francia

En la siguiente configuración de actividad, un visitante accedió a su sitio web desde Estados Unidos y luego viajó a Francia y visitó su sitio web una segunda vez. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Francia, este visitante permanece en la experiencia original.

![Prioridad EE.UU. > Alemania, visitante de Francia](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Experiencia segmentada a todos los visitantes

En la siguiente configuración de actividad, un visitante accedió a su sitio web desde Estados Unidos y luego viajó a Alemania y visitó su sitio web una segunda vez. En la primera visita, el visitante cumplía los requisitos para la Experiencia A (visitantes estadounidenses). Tras ver su sitio web desde Alemania, este visitante permanece en la Experiencia A (visitantes estadounidenses).

![Prioridad de EE. UU. > Todos los visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

Si no desea que ocurra esto, puede crear un público nuevo que esté definido de forma explícita como público contrario al destinatario, como se muestra en el siguiente ejemplo:

![Prioridad de EE. UU. > No EE. UU.](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

### Actividad de una sola experiencia

Con una actividad de **[!UICONTROL Segmentación de experiencias]** de una sola experiencia, los visitantes permanecerán en una experiencia aunque dejen de cumplir los requisitos para la audiencia que les asigne dicha experiencia. Si no desea que ocurra esto, puede crear otra experiencia dirigida a la audiencia contraria (por ejemplo, &quot;No Estados Unidos&quot; en oposición a &quot;Estados Unidos&quot;). Como otra opción, puede crear una actividad **[!UICONTROL Prueba A/B]** dirigida a la audiencia deseada con una asignación del tráfico del 100 %, como se muestra en el siguiente ejemplo:

![Experiencia de prioridad 1](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)

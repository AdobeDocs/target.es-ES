---
keywords: Target Standard;Recommendations;Target Premium;Automated Personalization;auto-target;auto target;permissions;what is adobe target;
description: Adobe Target es la solución de Adobe Experience Cloud que le proporciona todo lo necesario para adaptar y personalizar la experiencia de sus clientes a fin de maximizar los ingresos de sus sitios web y móviles, aplicaciones, medios sociales y otros canales digitales.
landing-page-description: Personalize your customers' experience to maximize revenue on your web and mobile sites, apps, social media, and other digital channels.
title: Introducción a Adobe Target
feature: intro
translation-type: tm+mt
source-git-commit: 90cc6d010988984c8f05e04ed3610b573829b6b6
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 85%

---


# Introducción a Target{#introduction-to-target}

[!DNL Adobe Target] es la solución de que le proporciona todo lo necesario para adaptar y personalizar la experiencia de sus clientes a fin de maximizar los ingresos de sus sitios web y móviles, aplicaciones, medios sociales y otros canales digitales.[!DNL Adobe Experience Cloud]

La solución [!DNL Adobe Target] tiene varios componentes:

## Target Standard   {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard] es un front-end para [!DNL Adobe Target] que sirve para crear y administrar de forma visual pruebas A/B y actividades de segmentación basada en reglas, además de permitir conectarse a Adobe Experience Cloud. [!DNL Target Standard] también admite la inserción de código personalizado tanto dentro como fuera del flujo de trabajo del [!UICONTROL Compositor de experiencias visuales]. [!DNL Target Standard] ofrece una estrategia de implementación simplificada con sus propiedades digitales: una sola línea de código en cada página gestiona toda la comunicación necesaria entre su sitio y [!DNL Adobe Target].

[!DNL Target Standard] tiene incorporadas las prácticas recomendadas del sector y está diseñado para que puedan usarlo tanto usuarios nuevos como experimentados. Puede compartir datos y resultados y colaborar fácilmente con otros integrantes del equipo que utilicen [!DNL Adobe Experience Cloud].

## Target Premium {#premium}

[!DNL Target Premium] es una licencia avanzada de [!DNL Target] que añade funciones superiores a [!DNL Target Standard].

[!DNL Target Premium] los temas de esta ayuda incluyen la insignia Premium en la parte superior de la página:

![Distintivo Premium](/help/assets/premium.png)

Target Premium incluye las siguientes características avanzadas:

### Personalización automatizada

La [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) proporciona algoritmos de aprendizaje del equipo para obtener experiencias personalizadas y tasas de conversión mejoradas para experiencias digitales.

Personalización automatizada (anteriormente denominada Test&amp;Target 1:1) registra la actividad de los visitantes al sitio web y crea un perfil de los visitantes, para poder segmentar el contenido a visitantes con un perfil similar. Realiza el seguimiento de las respuestas al contenido, tanto de visitantes individuales como de la población en su conjunto, para después utilizar sofisticados métodos de modelado que permiten segmentar el contenido para cada visitante, teniendo en cuenta todos los datos conocidos sobre dicho visitante.

Personalización automatizada aprende por sí misma y requiere el mínimo análisis humano. Es una solución 100 % automatizada que aprende continuamente. El sistema crea modelos y obtiene de forma automática información sobre los productos que probablemente interesen más a un visitante en particular. Cada vez que el visitante interactúa con el sitio, se recopila información y se almacena en el perfil del visitante. Hay disponibles varios algoritmos para proporcionar el mejor modelo para su sistema.

### Segmentación automática

[La segmentación automática utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función de su perfil de cliente y del comportamiento de visitantes anteriores con perfiles similares, todo ello con el fin de personalizar el contenido y dirigir las conversiones.](/help/c-activities/auto-target/auto-target-to-optimize.md)

### Las actividades de

[Las actividades de Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) muestran automáticamente productos o contenido que podría interesar a sus clientes, en función de la actividad previa del usuario. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.

Una recomendación determina cómo se sugiere un producto a un cliente, según las actividades de dicho cliente en el sitio. Por ejemplo:

* Anime a las personas que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo.

   Cree una recomendación que muestre artículos que a menudo se compran juntos, empleando el criterio “Otras personas que compraron esto también compraron aquello”.

* Incremente el tiempo que pasan los visitantes en su sitio de contenido multimedia recomendando contenido de vídeo parecido al que están viendo.

   Cree una recomendación que sugiera otros vídeos, empleando el criterio “Otras personas que vieron esto también vieron aquello”.

* Sugiera que los clientes que vieron información sobre planes de ahorro en su banco también lean información sobre cuentas de planes de pensiones.

   Muestre otros productos que compraron otras personas después de ver un determinado producto, sin mostrar el primer producto en las recomendaciones, empleando el criterio “Otras personas que vieron esto también compraron”.

### Recommendations como oferta

[Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md) permite incluir recomendaciones dentro de la [!UICONTROL Prueba A/B] (incluidas [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) y las actividades de [!UICONTROL Segmentación de experiencias] (XT).

Esta funcionalidad revela capacidades completamente nuevas, como:

* Recomendaciones de prueba y segmentación y contenido que no sea de recomendación dentro de la misma actividad.
* Experimentar fácilmente con la colocación de recomendaciones en la página, incluido el orden de varias recomendaciones.
* Insertar automáticamente tráfico a la experiencia de recomendaciones de mejor rendimiento mediante [!UICONTROL Asignación automática].
* Asignar de forma dinámica a los visitantes a experiencias de recomendaciones adaptadas según su perfil mediante el uso de [!UICONTROL Segmentación automática].

### Permisos de usuario de Enterprise

[La funcionalidad ](/help/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) Permisos de usuario de Enterprise le permite crear diferentes proyectos (llamados &quot;Perfiles de producto&quot; en la  [!DNL Adobe Admin Console for Enterprise]) para permitirle asignar diferentes permisos a un único usuario que dicte los derechos de acceso de ese usuario para cada proyecto. Estos proyectos independientes pueden compararse con el modo en el que funcionan los grupos de informes en [!DNL Adobe Analytics]. Cada proyecto tiene usuarios específicos con funciones específicas que se aplican a un conjunto de propiedades. El resultado es que los clientes podrán restringir el acceso de vista, edición, aprobación y publicación a sus usuarios en función de la región, el entorno (dev/stage/prod), el canal u otros criterios personalizados.

## Recommendations Classic {#section_9554068100054D2DBDB298CBE5A0E413}

>[!IMPORTANT]
>
>[!DNL Recommendations Classic] es un producto heredado. Para obtener la mejor experiencia [!DNL Recommendations], actualice a [!DNL Recommendations] actividades disponibles en [!DNL Adobe Target Premium], que se describe más arriba.

[!DNL Recommendations Classic] muestra automáticamente productos o contenido que podrían interesar a sus clientes en función de la actividad previa del usuario en el sitio web. Las recomendaciones sirven para dirigir a los clientes hacia artículos que de otra manera no conocerían, algo que mejora las ventas generadas en el sitio web.

Para obtener más información, consulte la [documentación de Recommendations Classic](/help/assets/adobe-recommendations-classic.pdf).

## Experience League: Kit de bienvenida de Adobe Target {#kit}

Cree su programa de optimización y personalización en Adobe Target con este kit de bienvenida. Incluye información, herramientas y recursos clave que le ayudarán a prepararse para su primera [!DNL Adobe Target] actividad y a iniciarla, con beneficios rápidos a corto plazo y estrategias de optimización a largo plazo.

[El kit de bienvenida de Adobe Target](https://expleague.azureedge.net/pdf/Adobe-Target-Welcome-Kit.pdf)

## Vídeo de capacitación: Tipos de actividades (9:03) ![Distintivo de información general](/help/assets/overview.png)

En el siguiente vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium] y el modo en que el flujo de trabajo guiado de tres pasos de Target puede ayudarle a lograr sus objetivos.

* Describir los tipos de actividades incluidas en Adobe Target
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

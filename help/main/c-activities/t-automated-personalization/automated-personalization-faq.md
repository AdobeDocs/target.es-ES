---
keywords: resolución de problemas;preguntas más frecuentes;FAQ;personalización automatizada;control;experiencia predeterminada;prácticas recomendadas
description: Explore una lista de preguntas frecuentes (FAQ) y respuestas acerca de las actividades de [!UICONTROL Automated Personalization] (AP) en [!UICONTROL Adobe Target].
title: ¿Cómo puedo encontrar preguntas frecuentes sobre las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 6%
---
# Preguntas frecuentes sobre Automated Personalization {#ap-faq}

>[!BEGINSHADEBOX]

**En esta página:** Encuentre respuestas a las preguntas más frecuentes acerca de las actividades de **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Las siguientes preguntas y respuestas tratan sobre cómo configurar las actividades de **[!UICONTROL Automated Personalization]** en [!DNL Adobe Target], cómo se crean los modelos de personalización, cómo se asigna el tráfico y cómo leer los resultados.

## Configuración de una actividad {#set-up-an-activity}

+++ ¿Cuáles son las prácticas recomendadas para configurar una actividad [!UICONTROL Automated Personalization]?

* Preste mucha atención a la *forma de actividad* (número de ubicaciones × número de ofertas), no solo al recuento total de experiencias. Las combinaciones cartesianas de ubicaciones y ofertas afectan el rendimiento en tiempo de creación más que el número sin procesar de experiencias. Para obtener un rendimiento y una capacidad de administración óptimos, limite las actividades de **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** a 4-6 ubicaciones con 4-6 ofertas por ubicación, tal como se describe en la pregunta &quot;¿Cuáles son algunos límites en Automated Personalization?&quot; en esta sección. No se recomiendan configuraciones más grandes que pueden llevar a una carga o edición lentas en **[!UICONTROL Compositor de experiencias visuales]**.
* Para personalizar una página con poco tráfico o realizar cambios estructurales en la experiencia que está personalizando, considere la posibilidad de usar una [**[!UICONTROL actividad de segmentación automática &#x200B;]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) en lugar de&#x200B;**[!UICONTROL &#x200B; Automated Personalization &#x200B;]**.
* Considere la posibilidad de ejecutar una actividad **[!UICONTROL Prueba A/B]** entre las ofertas y las ubicaciones que planea usar en su actividad **[!UICONTROL Automated Personalization]** para confirmar que las ubicaciones y las ofertas tengan un impacto en el objetivo de optimización. Si la actividad **[!UICONTROL Prueba A/B]** no muestra una diferencia significativa, es probable que **[!UICONTROL Automated Personalization]** tampoco genere un alza.

  Si una prueba A/B...N no muestra diferencias estadísticamente significativas entre experiencias, es probable que una o más de las siguientes situaciones sean responsables:

  * Es probable que las ofertas no sean lo suficientemente diferentes entre sí.
  * Las ubicaciones que ha seleccionado no afectan a la métrica de éxito.
  * El objetivo de optimización está demasiado lejos en la funnel de conversión como para verse afectado por las ofertas seleccionadas.

* Use el [Estimador de tráfico](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) para tener una idea de cuánto tiempo tardan los modelos de personalización en desarrollar su actividad de **[!UICONTROL Automated Personalization]**.
* Decida la asignación entre el control y el tráfico objetivo antes de comenzar la actividad, según sus objetivos. En la tabla siguiente se enumeran los tres escenarios que se deben tener en cuenta en función del objetivo de la actividad y el tipo de control seleccionado.

  | Objetivo de control y actividad | Asignación recomendada al control | Detalles |
  | --- | --- | --- |
  | **[!UICONTROL Experiencias aleatorias]** como control y el objetivo es probar la eficacia del algoritmo de personalización | 50% | Este objetivo requiere una imagen más precisa del alza. Es muy probable que también quiera comparar la tasa de conversión de sus experiencias u ofertas con la tasa que daría una simple **[!UICONTROL prueba A/B]** (un control servido de forma aleatoria). |
  | **[!UICONTROL Experiencias aleatorias]** como control y el objetivo es maximizar el tráfico personalizado | 10% a 30% | Utilice esta opción si se siente cómodo con el algoritmo y desea personalizar la máxima cantidad de tráfico. La compensación es la precisión de la información de crecimiento: los intervalos de confianza del tráfico de control son más grandes, a medida que menos tráfico fluye hacia ellos. |
  | **[!UICONTROL Experiencia específica]** como control, con cualquiera de los dos objetivos | 10% a 30% | Utilice esta opción para comparar una experiencia específica basada en especialistas en marketing con los modelos de personalización. Cuando se selecciona una sola experiencia como control, ese tráfico no se propaga en todas las ofertas o experiencias de la actividad. |

* Utilice reglas de segmentación con la mayor moderación posible, ya que pueden interferir con la capacidad del modelo para optimizar. Para obtener más información, consulte [ofertas de Automated Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).
* Los grupos de informes pueden limitar el éxito de su actividad **[!UICONTROL Automated Personalization]**, así que utilícelos únicamente bajo condiciones específicas. Para obtener más información, consulte [Grupos de informes de ofertas en Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

  * Use grupos de informes solo si se cumplen todas las condiciones siguientes:

    * Planea reemplazar o agregar ofertas mientras la actividad se está ejecutando.
    * Las ofertas del grupo de informes atraen a los mismos visitantes.
    * Las ofertas del grupo de informes tienen aproximadamente la misma tasa de respuesta general.

  * No hay personalización entre ofertas en un grupo de informes. El modelo de personalización trata todas las ofertas como lo mismo.
  * No coloque todas las ofertas en una actividad en un solo grupo de informes. De este modo, todas las ofertas se atenderán de forma aleatoria y uniforme a todos los visitantes de la actividad.

+++

+++ ¿Cuáles son los límites de [!UICONTROL Automated Personalization]?

[!DNL Target] tiene un límite estricto de 30 000 experiencias, pero funciona mejor cuando se crean menos de 10 000 experiencias. El mismo límite se aplica cuando la actividad tiene habilitada la opción **[!UICONTROL No permitir duplicados]**.

Aunque las actividades de **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** admiten un gran número de experiencias, el rendimiento de la creación depende en gran medida de la *forma de la actividad* (número de ubicaciones × número de ofertas). Ciertas configuraciones crean grandes combinaciones cartesianas que pueden afectar significativamente al rendimiento de carga y edición, incluso por debajo de los límites de experiencia documentados.

Para obtener un rendimiento y una capacidad de administración óptimos, limite las actividades de **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** a entre 4 y 6 ubicaciones con entre 4 y 6 ofertas por ubicación. No se recomiendan configuraciones más grandes que podrían restringirse en la interfaz de usuario de [!DNL Target].

En la IU actual de [!DNL Target], las actividades **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** están configuradas directamente en el paso **[!UICONTROL Experiencias]**. [!DNL Target] puede mostrar advertencias dentro de la línea o evitar que guarde una actividad cuando la configuración supere los umbrales admitidos, y vuelve a validar la forma de la actividad en **[!UICONTROL Siguiente]**, **[!UICONTROL Guardar]** y **[!UICONTROL Publicar]**.

Para obtener más información sobre los límites de caracteres y de otro tipo (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de [!DNL Target], vea [Límites](/help/main/r-troubleshooting-target/target-limits.md).

+++

+++ ¿Puedo especificar una experiencia específica para usarla como control en una actividad [!UICONTROL Automated Personalization]?

Puede seleccionar una experiencia específica para utilizarla como control mientras crea una actividad de [**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP) o [**[!UICONTROL Segmentación automática]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a esa experiencia, según el porcentaje de asignación de tráfico configurado en la actividad. A continuación, puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Seleccionar la experiencia de control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

+++ ¿Cómo se implementa la segmentación a nivel de oferta?

Cuando llega cada visitante, las reglas de segmentación a nivel de oferta determinan el conjunto de ofertas que el visitante puede ver. A continuación, el algoritmo elige, entre esas ofertas, la oferta que el modelo predice que tiene los mejores ingresos esperados o posibilidades de conversión. La segmentación de ofertas afecta a la eficacia de los algoritmos de aprendizaje automático de [!DNL Target], por lo que debe utilizarse con la mayor moderación posible. Para obtener más información, consulte [ofertas de Automated Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

+++

## Creación de modelos y asignación de tráfico {#models-and-traffic}

+++ ¿Cómo está [!UICONTROL Automated Personalization] asignando el tráfico de mi actividad?

**[!UICONTROL Automated Personalization]** dirige a los visitantes a la experiencia que tiene la mayor métrica de éxito prevista, según los modelos de [bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) más recientes. Esta previsión se basa en la información específica y el contexto de visita del visitante.

Por ejemplo, supongamos que una actividad **[!UICONTROL Automated Personalization]** tiene dos ubicaciones con dos ofertas cada una. En la primera ubicación, la Oferta A tiene una tasa de conversión pronosticada del 3 % para un visitante específico y la Oferta B tiene una tasa de conversión pronosticada del 1 %. En la segunda ubicación, la Oferta C tiene una tasa de conversión pronosticada del 2 % para el mismo visitante y la Oferta D tiene una tasa de conversión pronosticada del 5 %. Por lo tanto, **[!UICONTROL Automated Personalization]** le sirve a este visitante una experiencia con la Oferta A y la Oferta D.

+++

+++ ¿Cómo crea [!UICONTROL Automated Personalization] modelos con respecto a los entornos?

Un modelo se crea para identificar el rendimiento de la estrategia personalizada en comparación con el tráfico servido aleatoriamente en lugar de enviar todo el tráfico a la experiencia ganadora general. Este modelo considera las visitas y conversiones solo en el entorno predeterminado.

Se ha creado un segundo conjunto de modelos para cada grupo de informes (**[!UICONTROL Automated Personalization]**) o experiencia (**[!UICONTROL Segmentación automática]**). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

Por lo tanto, las solicitudes se proporcionan con el mismo modelo, independientemente del entorno. Sin embargo, la pluralidad del tráfico debería proceder del entorno predeterminado para garantizar que la experiencia ganadora general identificada sea coherente con el comportamiento en el mundo real.

+++

+++ ¿Cuánto tiempo debo esperar para que los modelos se creen?

El tiempo que tardan los modelos en desarrollar su actividad depende típicamente del tráfico a las ubicaciones de la actividad seleccionada y de la métrica de éxito de la actividad. Use [Estimador de tráfico](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) para determinar la cantidad de tiempo esperada que los modelos tardan en desarrollar su actividad.

+++

+++ ¿Cómo puedo reducir el tiempo necesario para que los modelos se creen en mi actividad [!UICONTROL Automated Personalization]?

Revise la configuración de la actividad para ver si hay cambios que mejoren la velocidad con la que se crean los modelos. Por ejemplo, cambie una métrica de éxito de RPV a conversión, elija una métrica de éxito que esté más cerca de sus experiencias de actividad en el funnel de ventas, suelte algunas experiencias de la actividad o utilice una página de tráfico más alto. Para obtener más información, consulte [Solucionar problemas de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ Se ha creado un modelo en mi actividad [!UICONTROL Automated Personalization]. ¿Las visitas a esa experiencia están personalizadas?

No. Deben crearse al menos dos modelos dentro de la actividad para que comience la personalización.

+++

## Resultados y alza {#results-and-lift}

+++ ¿Cuándo puedo ver los resultados de mi actividad [!UICONTROL Automated Personalization]?

Puede comenzar a observar los resultados de su actividad **[!UICONTROL Automated Personalization]** después de que al menos dos experiencias tengan modelos creados (indicados por una marca de verificación verde).

+++

+++ ¿Por qué no se muestra el alza en mi actividad [!UICONTROL Automated Personalization]?

Se requieren cuatro factores para que una actividad **[!UICONTROL Automated Personalization]** genere un alza:

* Las ofertas de cada ubicación deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ubicaciones deben estar en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y poder estadístico en la actividad para detectar el aumento.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarnos primero de que, mediante una actividad **[!UICONTROL Prueba A/B]** simple y no personalizada, el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales. Para ver el procedimiento completo, consulte [Solucionar problemas de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ ¿Cómo puedo comparar [!UICONTROL Automated Personalization] con una experiencia predeterminada?

No hay ninguna opción llave en mano para comparar **[!UICONTROL Automated Personalization]** con una experiencia predeterminada. Como solución alternativa, si existe una oferta o experiencia predeterminada como parte de la actividad, haga clic en el segmento **[!UICONTROL Control]** de los informes y busque esa oferta en el informe a nivel de oferta resultante. La tasa de conversión registrada para esta oferta se puede comparar con la tasa de conversión de todo el segmento &quot;Bosque aleatorio&quot;. Esta comparación muestra el rendimiento del modelo en comparación con la oferta predeterminada.

+++

## Administración de una actividad activa {#manage-live-activity}

+++ ¿Cuándo debería detener mi actividad [!UICONTROL Automated Personalization]?

**[!UICONTROL Automated Personalization]** se puede usar como una personalización &quot;siempre activada&quot; que se optimiza constantemente. Especialmente para contenido permanente, no es necesario detener tu actividad de **[!UICONTROL Automated Personalization]**. Si desea realizar cambios sustanciales en el contenido que no sean similares a las ofertas que hay actualmente en su actividad, la práctica recomendada es comenzar una nueva actividad. El inicio de una nueva actividad ayuda a otros usuarios que revisan los informes a evitar confundir o relacionar resultados pasados con contenido diferente.

+++

+++ ¿Puedo cambiar la métrica de objetivos a mitad de camino a través de una actividad [!UICONTROL Automated Personalization]?

[!DNL Adobe] no recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la interfaz de usuario de [!DNL Target], inicie siempre una nueva actividad en su lugar. [!DNL Adobe] no garantiza lo que sucederá si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de **[!UICONTROL Asignación automática]**, **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]** que usan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

+++

+++ ¿Puedo usar la opción [!UICONTROL Restablecer los datos del informe] al ejecutar una actividad de [!UICONTROL Automated Personalization]?

[!DNL Adobe] no recomienda usar la opción **[!UICONTROL Restablecer datos del informe]** para las actividades **[!UICONTROL Automated Personalization]**. Aunque quita los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo **[!UICONTROL Automated Personalization]**. En lugar de usar la opción **[!UICONTROL Restablecer los datos del informe]**, cree una nueva actividad y desactive la actividad original. Esta guía también se aplica a las actividades **[!UICONTROL Asignación automática]** y **[!UICONTROL Segmentación automática]**.

+++

+++ ¿Por qué los visitantes ven experiencias para una actividad de [!UICONTROL Automated Personalization] que no deberían ver?

Las actividades de **[!UICONTROL Automated Personalization]** se evalúan una vez por sesión. Si hay sesiones activas que se han clasificado para una experiencia en particular y desde entonces se han añadido nuevas ofertas, los visitantes ven el nuevo contenido junto con las ofertas mostradas anteriormente. Anteriormente, estos visitantes cumplían los requisitos para recibir esas experiencias, por lo que siguen viéndolas durante la sesión. Para evaluar la actividad en cada visita a la página, cambie al tipo de actividad **[!UICONTROL Segmentación de experiencias]** (XT).

+++

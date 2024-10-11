---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas
description: Descubra cómo una actividad de [!UICONTROL Auto-Target] proporciona a cada visitante la experiencia más adaptada en función de los perfiles de los clientes y del comportamiento de visitantes similares.
title: ¿Qué es una actividad de [!UICONTROL Auto-Target]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
hide: true
hidefromtoc: true
source-git-commit: 5fc18c6d3b493ea0a58048cc20ce3a6c2ffb7d14
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 18%

---

# Resumen de [!UICONTROL Auto-Target]

[!UICONTROL Auto-Target] actividades en [!DNL Adobe Target] utilizan aprendizaje automático avanzado para seleccionar entre varias experiencias de alto rendimiento definidas por expertos en marketing para personalizar el contenido y dirigir las conversiones. [!UICONTROL Auto-Target] ofrece a cada visitante la experiencia más adaptada en función del perfil de cada cliente y del comportamiento de los visitantes anteriores con perfiles similares.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) admite actividades [!UICONTROL Auto-Target]. Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## Caso de éxito real con segmentación automática {#success}

Un importante minorista de ropa recientemente utilizó una actividad [!UICONTROL Auto-Target] con diez experiencias basadas en categorías de productos (además de un control aleatorio) para ofrecer el contenido adecuado a cada visitante. Se eligió &quot;[!UICONTROL Add to Cart]&quot; como métrica de optimización principal. Las experiencias segmentadas tuvieron un alza media del 29,09 %. Después de crear los modelos [!UICONTROL Auto-Target], la actividad se estableció en experiencias personalizadas al 90 %.

En solo diez días, se lograron más de 1.700.000 dólares en alza.

Siga leyendo para aprender a usar [!UICONTROL Auto-Target] a fin de aumentar el alza y los ingresos de su organización.

## Información general {#section_972257739A2648AFA7E7556B693079C9}

Mientras [crea una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) mediante el flujo de trabajo guiado de tres pasos, elija la opción **[!UICONTROL Auto-Target for personalized experiences]** en la página **[!UICONTROL Targeting]** (paso 2).

![Configuración del método de asignación de tráfico](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

La opción [!UICONTROL Auto-Target] dentro del flujo de actividad A/B le permite aprovechar el aprendizaje automático para personalizar en un solo clic basándose en un conjunto de experiencias definidas por el especialista en marketing. [!UICONTROL Auto-Target] está diseñado para ofrecer una optimización máxima, en comparación con las pruebas A/B tradicionales o [!UICONTROL Auto Allocate], determinando qué experiencia mostrar para cada visitante. A diferencia de una actividad A/B en la que el objetivo es encontrar un único ganador, [!UICONTROL Auto-Target] determina automáticamente la mejor experiencia para un visitante determinado. La mejor experiencia se basa en el perfil del visitante y otra información contextual para ofrecer una experiencia altamente personalizada.

De manera similar a [!UICONTROL Automated Personalization], [!UICONTROL Auto-Target] usa un [algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), un método puntero de ensamblado de la ciencia de datos, para determinar la mejor experiencia para mostrar a un visitante. Dado que [!UICONTROL Auto-Target] puede adaptarse a los cambios en el comportamiento de los visitantes, puede ejecutarse de forma perpetua para proporcionar un aumento. Este método a veces se denomina modo &quot;siempre-activo&quot;.

A diferencia de una actividad A/B en la que la asignación de experiencias para un visitante dado es fija, [!UICONTROL Auto-Target] optimiza el objetivo comercial especificado en cada visita. Al igual que en [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], de manera predeterminada, reserva parte del tráfico de la actividad como grupo de control para medir el alza. A los visitantes del grupo de control se les sirve una experiencia aleatoria en la actividad.

## Consideraciones

Hay algunas consideraciones importantes que se deben tener en cuenta al usar [!UICONTROL Auto-Target]:

* No puede cambiar una actividad específica de [!UICONTROL Auto-Target] a [!UICONTROL Automated Personalization], y viceversa.
* No puede cambiar de la asignación de tráfico [!UICONTROL Manual] (tradicional [!UICONTROL A/B Test]) a [!UICONTROL Auto-Target], y viceversa después de guardar una actividad como borrador.
* Un modelo se crea para identificar el rendimiento de la estrategia personalizada en comparación con el tráfico servido aleatoriamente en lugar de enviar todo el tráfico a la experiencia ganadora general. Este modelo considera las visitas y conversiones solo en el entorno predeterminado.

  El tráfico de un segundo conjunto de modelos se crea para cada grupo de modelado (AP) o experiencia (AT). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

  Las solicitudes se proporcionan con el mismo modelo, independientemente del entorno. Sin embargo, la pluralidad del tráfico debería proceder del entorno predeterminado para garantizar que la experiencia ganadora general identificada sea coherente con el comportamiento en el mundo real.

* Utilice un mínimo de dos experiencias.

## Terminología   {#section_A309B7E0B258467789A5CACDC1D923F3}

Los siguientes términos pueden resultar útiles al tratar el tema de [!UICONTROL Auto-Target]:

| Término | Definición |
|---|---|
| [Bandido multibrazo](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| [Bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El bosque aleatorio es una solución pionera de aprendizaje automático. En términos de ciencia de datos, se trata de una clasificación de conjunto, o método de regresión, que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. En [!DNL Target], el bosque aleatorio se usa para determinar qué experiencia se espera que tenga la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. |
| [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el &quot;coste&quot; de encontrar esa experiencia. El muestreo Thompson siempre elige un ganador, incluso si no hay diferencia estadística entre dos experiencias. |

## Cómo funciona [!UICONTROL Auto-Target] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Obtenga más información acerca de los datos y algoritmos subyacentes de [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] en los siguientes vínculos:

| Término | Detalles |
|--- |--- |
| [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El algoritmo de personalización principal de [!DNL Target] que se usa en [!UICONTROL Auto-Target] y en [!UICONTROL Automated Personalization] es el de bosque aleatorio. Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un mejor rendimiento predictivo que el que se podría obtener de cualquiera de los algoritmos de aprendizaje constituyentes. El algoritmo de bosque aleatorio en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target] es una clasificación, o método de regresión, que funciona mediante la construcción de una multitud de árboles de decisión en el momento de la formación. |
| [Cargando datos para los algoritmos Personalization de [!DNL Target]](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Hay varias formas de introducir datos para los modelos [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization]. |
| [Recopilación de datos para los algoritmos Personalization de [!DNL Target]](/help/main/c-activities/t-automated-personalization/ap-data.md) | Los algoritmos de personalización de [!DNL Target] recopilan automáticamente varios datos. |

## Determinación de la asignación de tráfico.  {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependiendo del objetivo de su actividad, puede elegir una asignación de tráfico diferente entre control y experiencias personalizadas. Lo mejor es determinar este objetivo antes de realizar su actividad en vivo.

La lista desplegable [!UICONTROL Custom Allocation] le permite elegir entre las siguientes opciones:

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![Lista desplegable Objetivo de asignación](/help/main/c-activities/assets/split-new-ui.png)

En la tabla siguiente se explican las tres opciones:

| Objetivo de la actividad | Asignación de tráfico sugerida | Compensaciones |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**: si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo de destino. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control. | 50 % de control/50 % de experiencia personalizada dividida | <ul><li>Maximiza la precisión del aumento entre el control y el personalizado</li><li>Relativamente menos visitantes tienen una experiencia personalizada</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**: si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10 % de los visitantes en el control a fin de asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. La compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control. | Lo mejor es usar una división de Experiencia personalizada del 10 % - 30 %/70 % - 90 % | <ul><li>Maximiza el número de visitantes que tienen una experiencia personalizada</li><li>Maximiza el alza</li><li>Menos precisión en cuanto a lo que significa el aumento para la actividad</li></ul> |
| **Asignación personalizada** | Divida manualmente el porcentaje según lo desee. | <ul><li>Puede que no consiga los resultados deseados. Si no está seguro, siga las sugerencias de cualquiera de las opciones anteriores</li></ul> |

Para ajustar el porcentaje [!UICONTROL Control], haga clic en [!UICONTROL Experiences] en el panel [!UICONTROL Traffic Allocation] y, a continuación, ajuste los porcentajes como desee. No se puede reducir el grupo de control por debajo del 10 %.

Puede [seleccionar una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o utilizar la opción de experiencia aleatoria.

## ¿Cuándo se debe elegir [!UICONTROL Auto-Target] sobre [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

Hay varios escenarios en los que puede preferir usar [!UICONTROL Auto-Target] sobre [!UICONTROL Automated Personalization]:

* Si desea definir la experiencia completa y no ofertas individuales que se combinan automáticamente para formar una experiencia.
* Si desea usar el conjunto completo de características de [!UICONTROL Visual Experience Composer] (VEC) que no admite [!UICONTROL Auto Personalization]: el editor de código personalizado, las audiencias de experiencia múltiple y más.
* Si desea realizar cambios estructurales en su página en diferentes experiencias. Por ejemplo, si desea reorganizar los elementos de la página principal, [!UICONTROL Auto-Target] es más apropiado para usar que [!UICONTROL Automated Personalization].

## ¿Qué tiene [!UICONTROL Auto-Target] en común con [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### El algoritmo se optimiza para obtener un resultado favorable para cada visita.

* El algoritmo predice la tendencia de un visitante a la conversión (o los ingresos estimados procedentes de la conversión) para ofrecer la mejor experiencia.
* Un visitante es elegible para una nueva experiencia al final de una sesión existente (a menos que el visitante esté en el grupo de control, en cuyo caso la experiencia que se asigna al visitante en la primera visita permanece igual para las visitas posteriores).
* En una sesión, la predicción no cambia para mantener la coherencia visual.

### El algoritmo se adapta a los cambios en el comportamiento de los visitantes.

* El método multi-armed bandit garantiza que el modelo siempre &quot;gasta&quot; una pequeña fracción del tráfico para seguir aprendiendo a lo largo de la vida de la actividad y para evitar la sobreexplotación de las tendencias aprendidas anteriormente.
* Los modelos subyacentes se reconstruyen cada 24 horas utilizando los datos de comportamiento del visitante más recientes para garantizar que [!DNL Target] siempre aproveche los cambios en las preferencias de visitante.
* Si el algoritmo no es capaz de determinar experiencias ganadoras para usuarios individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, sin dejar por ello de buscar ganadores personalizados. La experiencia con mejor rendimiento se determina empleando [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

### El algoritmo se optimiza continuamente para una métrica de objetivo único.

* Esta métrica puede estar basada en conversiones o en ingresos (más específicamente [!UICONTROL Revenue per Visit]).

### [!DNL Target] recopila automáticamente información sobre los visitantes para crear los modelos de personalización.

* Para obtener más información acerca de los parámetros utilizados en [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization], vea [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] utiliza automáticamente todas las [!DNL Adobe Experience Cloud] audiencias compartidas para crear los modelos de personalización.

* No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de [!DNL Experience Cloud Audiences] con [!DNL Target], consulte [Audiencias de Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

### Los especialistas en marketing pueden cargar datos sin conexión, puntuaciones de tendencia u otros datos personalizados para crear modelos de personalización.

* Más información sobre [cargar datos de [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## ¿En qué se diferencian [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target] requiere frecuentemente menos tráfico que [!UICONTROL Automated Personalization] para generar un modelo personalizado.

Aunque la cantidad de tráfico *por experiencia* necesario para que los modelos [!UICONTROL Auto-Target] o [!UICONTROL Auto Personalization] se creen es la misma, normalmente hay más experiencias en una actividad [!UICONTROL Automated Personalization] que en una actividad [!UICONTROL Auto-Target].

Por ejemplo, si tuvo una actividad [!UICONTROL Auto Personalization] en la que creó dos ofertas por ubicación con dos ubicaciones, habría cuatro (2 = 4) experiencias totales incluidas en la actividad (sin exclusiones). Con [!UICONTROL Auto-Target], podría configurar la experiencia 1 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2, y la experiencia 2 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2. Dado que [!UICONTROL Auto-Target] le permite elegir tener múltiples cambios dentro de una experiencia, puede reducir la cantidad total de experiencias en su actividad.

Para [!UICONTROL Auto-Target], se pueden usar reglas simples para comprender los requisitos de tráfico:

* **Cuando [!UICONTROL Conversion] es su métrica de éxito:** 1.000 visitas y al menos 50 conversiones por día y experiencia, además la actividad debe tener al menos 7.000 visitas y 350 conversiones.
* **Cuando [!UICONTROL Revenue per Visit] es su métrica de éxito:** 1.000 visitas y al menos 50 conversiones por día y experiencia, además la actividad debe tener al menos 1.000 conversiones por experiencia. Por lo general, el RPV requiere más datos para construir modelos debido a la mayor varianza de datos que normalmente existe en los ingresos de visita en comparación con la tasa de conversión.

### [!UICONTROL Auto-Target] tiene una funcionalidad de configuración completa.

* Dado que [!UICONTROL Auto-Target] está incrustado en el flujo de trabajo de la actividad A/B, [!UICONTROL Auto-Target] se beneficia del [!UICONTROL Visual Experience Composer] (VEC), que es más maduro y completo. También puede usar [vínculos de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) con [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] proporciona un amplio marco de pruebas en línea.

* El método multi-armed bandit forma parte de un marco de pruebas en línea más amplio que permite a [!DNL Adobe] científicos de datos e investigadores comprender los beneficios de sus continuas mejoras en condiciones reales.
* En el futuro, este banco de pruebas nos permitirá abrir la plataforma de aprendizaje automático de [!DNL Adobe] a clientes expertos en datos para que puedan incorporar sus propios modelos y aumentar los modelos de [!DNL Target].

## Informes y [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obtener más información, consulte [Informes y segmentación automática](/help/main/c-activities/auto-target/reporting-and-auto-target.md).
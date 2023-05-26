---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas
description: Descubra cómo puede hacer una [!UICONTROL Segmentación automática] actividad en [!DNL Target] ofrece a cada visitante la experiencia más adaptada en función de sus perfiles y del comportamiento de visitantes similares.
title: Qué es un [!UICONTROL Segmentación automática] ¿Actividad?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '1965'
ht-degree: 51%

---

# [!UICONTROL Información general sobre la segmentación automática]

[!UICONTROL Segmentación automática] actividades en [!DNL Adobe Target] utilice aprendizaje automático avanzado para seleccionar entre varias experiencias de alto nivel de rendimiento definidas por expertos en marketing para personalizar el contenido y dirigir las conversiones. [!UICONTROL Segmentación automática] ofrece a cada visitante la experiencia más adaptada en función del perfil de cada cliente y del comportamiento de los visitantes anteriores con perfiles similares.

>[!NOTE]
>
>* La [!UICONTROL segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) admite [!UICONTROL Segmentación automática] actividades. Para obtener más información, consulte [Compatibilidad con A4T para actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).


## Caso de éxito real con segmentación automática {#success}

Un importante minorista de ropa recientemente utilizó un [!UICONTROL Segmentación automática] actividad con diez experiencias basadas en categorías de productos (además de control aleatorio) para ofrecer el contenido adecuado a cada visitante. &quot;[!UICONTROL Añadir al carro]&quot; se eligió como métrica de optimización principal. Las experiencias segmentadas tuvieron un alza media del 29,09 %. Después de crear la variable [!UICONTROL Segmentación automática] modelos, la actividad se estableció en experiencias personalizadas al 90 %.

En solo diez días, se lograron más de 1.700.000 dólares en alza.

Siga leyendo para aprender a utilizar [!UICONTROL Segmentación automática] para aumentar el alza y los ingresos de su organización.

## Información general {#section_972257739A2648AFA7E7556B693079C9}

Al [crear una actividad A/B mediante el flujo de trabajo guiado de tres pasos](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), tiene la opción de asignar el tráfico con la opción [!UICONTROL Segmentación automática para experiencias personalizadas]:

![Opción de segmentación automática para experiencias personalizadas](/help/main/c-activities/assets/auto-target-ui-new.png)

La opción de [!UICONTROL segmentación automática] dentro del flujo de actividad A/B le permite aprovechar el aprendizaje automático para personalizar en un solo clic basándose en un conjunto de experiencias definidas por el especialista en marketing. [!UICONTROL Segmentación automática] está diseñado para ofrecer la máxima optimización, en comparación con las pruebas A/B tradicionales o [!UICONTROL Asignación automática], determinando qué experiencia mostrar para cada visitante. Al contrario que en una actividad A/B, cuyo objetivo es encontrar un único ganador, la [!UICONTROL segmentación automática] determina la mejor experiencia para un visitante específico (según su perfil e información adicional) y así ofrecerle una experiencia con un alto nivel de personalización.

De forma similar a [!UICONTROL Automated Personalization], [!UICONTROL Segmentación automática] utiliza un [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), un método puntero de ensamblado de la ciencia de datos, para determinar la mejor experiencia para mostrar a un visitante. Debido a que la [!UICONTROL segmentación automática] se puede adaptar a los cambios en el comportamiento de los visitantes, se puede ejecutar de forma perpetua para proporcionar un aumento. A veces, este modo se denomina “siempre-activo”.

Al contrario que en una actividad A/B, en la que la asignación de experiencias para un visitante dado es fija, la [!UICONTROL segmentación automática] optimiza el objetivo comercial especificado en cada visita. Al igual que en la [!UICONTROL Personalización automática], la [!UICONTROL segmentación automática], de forma predeterminada, reserva parte del tráfico de la actividad como grupo de control para medir el aumento. A los visitantes del grupo de control se les sirve una experiencia aleatoria en la actividad.

## Consideraciones

Hay algunas consideraciones importantes que se deben tener en cuenta al utilizar [!UICONTROL Segmentación automática]:

* No puede cambiar una actividad específica de [!UICONTROL Segmentación automática] hasta [!UICONTROL Automated Personalization]y viceversa.
* No puede cambiar de [!UICONTROL Manual] asignación de tráfico (tradicional) [!UICONTROL Prueba A/B]) a [!UICONTROL Segmentación automática]y viceversa después de que una actividad se guarde como borrador.
* Se crea un modelo para identificar el rendimiento de la estrategia personalizada frente al tráfico servido aleatoriamente, en lugar de enviar todo el tráfico a la experiencia ganadora general. Este modelo considera las visitas y conversiones solo en el entorno predeterminado.

   El tráfico de un segundo conjunto de modelos se crea para cada grupo de modelado (AP) o experiencia (AT). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

   Las solicitudes se atienden con el mismo modelo, independientemente del entorno, pero la pluralidad del tráfico debe provenir del entorno predeterminado para garantizar que la experiencia ganadora general identificada sea coherente con el comportamiento en el mundo real.

* Utilice un mínimo de dos experiencias.

## Terminología   {#section_A309B7E0B258467789A5CACDC1D923F3}

Los siguientes términos pueden resultar útiles al tratar el tema de la [!UICONTROL segmentación automática]:

| Término | Definición |
|---|---|
| [Multi-armed bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| [Bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El bosque aleatorio es una solución pionera de aprendizaje automático. En términos de ciencia de datos, se trata de una clasificación de conjunto, o método de regresión, que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. En [!DNL Target], el bosque aleatorio se utiliza para determinar qué experiencia se espera que tenga la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. |
| [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el &quot;coste&quot; de encontrar esa experiencia. El muestreo Thompson siempre selecciona un ganador, aunque no haya diferencias estadísticas entre las dos experiencias. |

## Cómo funciona la [!UICONTROL segmentación automática] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Obtenga más información acerca de los datos y algoritmos detrás de la [!UICONTROL segmentación automática] y la Personalización automatizada en los siguientes vínculos:

| Término | Detalles |
|--- |--- |
| [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El algoritmo de personalización principal de Target que se utiliza en la [!UICONTROL Segmentación automática] y en la Personalización automatizada es el de bosque aleatorio.  Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un rendimiento más predictivo que el que podría obtenerse de cualquier algoritmo de aprendizaje constituyente. Algoritmo de bosque aleatorio en [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] actividades es un método de clasificación, o regresión, que opera mediante la construcción de una multitud de árboles de decisión en el momento del entrenamiento. |
| [Carga de datos para los algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Hay varias formas de introducir datos para los modelos de [!UICONTROL Segmentación automática] y Personalización automatizada. |
| [Recopilación de datos para los algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md) | Los algoritmos de personalización de Target recopilan automáticamente varios datos. |

## Determinación de la asignación de tráfico.  {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependiendo del objetivo de su actividad, puede elegir una asignación de tráfico diferente entre control y experiencias personalizadas. Lo mejor es determinar este objetivo antes de realizar su actividad en vivo.

La lista desplegable [!UICONTROL Asignación personalizada] le permite elegir entre las siguientes opciones:

* Evaluar el Algoritmo de personalización
* Maximice el tráfico de personalización
* Asignación personalizada

![Lista desplegable Objetivo de asignación](/help/main/c-activities/assets/split-new.png)

| Objetivo de la actividad | Asignación de tráfico sugerida | Compensaciones |
|--- |--- |--- |
| **Evaluar el algoritmo de personalización (50/50)**: Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control. | 50 % de control/50 % de experiencia personalizada dividida | <ul><li>Maximiza la precisión del aumento entre el control y el personalizado</li><li>Relativamente menos visitantes tienen una experiencia personalizada</li></ul> |
| **Maximización del tráfico de personalización (90/10)**: Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10 % de los visitantes en el control para asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. Tenga en cuenta que la compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control. | Lo mejor es usar una división de Experiencia personalizada del 10 % - 30 %/70 % - 90 % | <ul><li>Maximiza el número de visitantes que tienen una experiencia personalizada</li><li>Maximiza el alza</li><li>Menos precisión en cuanto a lo que significa el aumento para la actividad</li></ul> |
| **Asignación personalizada** | Divida manualmente el porcentaje según lo desee. | <ul><li>Puede que no consiga los resultados deseados. Si no está seguro, siga las sugerencias de cualquiera de las opciones anteriores</li></ul> |

Para ajustar el [!UICONTROL Control] porcentaje, haga clic en los iconos de la [!UICONTROL Asignación] columna. No se puede reducir el grupo de control por debajo del 10 %.

![Cambiar la asignación del tráfico de segmentación automática](/help/main/c-activities/assets/auto-target-control.png)

Puede [seleccionar una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o utilizar la opción de experiencia aleatoria.

## ¿Cuándo debe elegir [!UICONTROL Segmentación automática] sobre [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

Hay varios escenarios en los que puede preferir utilizar [!UICONTROL Segmentación automática] sobre [!UICONTROL Automated Personalization]:

* Si quiere definir la experiencia completa y no ofertas individuales que se combinarán automáticamente para formar una experiencia.
* Si desea utilizar el conjunto completo de [!UICONTROL Compositor de experiencias visuales] Funciones de (VEC) no compatibles con [!UICONTROL Personalización automática]: el editor de código personalizado, las audiencias de experiencia múltiple y más.
* Si desea realizar cambios estructurales en su página en diferentes experiencias. Por ejemplo, si desea reorganizar los elementos de la página principal, [!UICONTROL Segmentación automática] es más apropiado utilizar que [!UICONTROL Automated Personalization].

## ¿Qué hace [!UICONTROL Segmentación automática] tienen en común con [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### El algoritmo se optimiza para lograr un resultado positivo en cada visita.

* El algoritmo predice la tendencia de un visitante a la conversión (o los ingresos estimados procedentes de la conversión) para ofrecer la mejor experiencia.
* Un visitante es elegible para una nueva experiencia al final de una sesión existente (a menos que el visitante esté en el grupo de control, en cuyo caso la experiencia que se asigna a ese visitante en la primera visita permanece igual para las visitas posteriores).
* En una sesión, la predicción no cambia para mantener la coherencia visual.

### El algoritmo se adapta a los cambios de comportamiento de los visitantes.

* El método multi-armed bandit garantiza que el modelo siempre &quot;gasta&quot; una pequeña fracción del tráfico para seguir aprendiendo a lo largo de la vida de la actividad y para evitar la sobreexplotación de las tendencias aprendidas anteriormente.
* Los modelos subyacentes se reconstruyen cada 24 horas utilizando los datos de comportamiento del visitante más recientes para garantizar que [!DNL Target] siempre aprovecha los cambios en las preferencias de los visitantes.
* Si el algoritmo no es capaz de determinar experiencias ganadoras para usuarios individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, sin dejar por ello de buscar ganadores personalizados. La experiencia con mejor rendimiento se determina empleando [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

### El algoritmo se optimiza continuamente para lograr una única métrica de objetivos.

* Esta métrica puede estar basada en conversiones o en ingresos (o, mejor dicho, en [!UICONTROL Ingresos por visita]).

### [!DNL Target] recopila automáticamente información sobre los visitantes para crear los modelos de personalización.

* Para obtener más información sobre los parámetros utilizados en la [!UICONTROL segmentación automática] y la personalización automatizada, consulte [Recopilación de datos de personalización automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] utiliza automáticamente todas[!DNL Adobe Experience Cloud] las audiencias compartidas por para crear los modelos de personalización.

* No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de [!DNL Experience Cloud Audiences] con [!DNL Target], consulte [Audiencias de Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md)

### Los expertos en marketing pueden cargar datos sin conexión, puntuaciones de inclinación u otros datos personalizados para crear modelos de personalización.

* Obtenga más información sobre [cargar datos para la segmentación automática y la personalización automatizada[!UICONTROL .]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)

## ¿Cómo [!UICONTROL Segmentación automática] diferir de [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL La segmentación automática] requiere frecuentemente menos tráfico que la personalización automatizada para crear un modelo personalizado.

Aunque la cantidad de tráfico *por experiencia* requerida para los modelos de [!UICONTROL segmentación automática] o [!UICONTROL personalización automática] para compilar es la misma, usualmente hay más experiencias en una actividad de personalización automatizada que una actividad de [!UICONTROL segmentación automática.]

Por ejemplo, si tuviera un [!UICONTROL Personalización automática] actividad en la que ha creado dos ofertas por ubicación con dos ubicaciones, habría cuatro (2 = 4) experiencias totales incluidas en la actividad (sin exclusiones). Utilizando la [!UICONTROL segmentación automática], puede configurar la experiencia 1 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2, y la experiencia 2 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2. Debido a que la [!UICONTROL segmentación automática] le permite elegir tener múltiples cambios dentro de una experiencia, puede reducir la cantidad total de experiencias en su actividad.

Para la [!UICONTROL segmentación automática], se pueden usar reglas simples para comprender los requisitos de tráfico:

* **Cuando la conversión es su métrica de éxito:** 1000 visitas y al menos 50 conversiones por día por experiencia; además, la actividad debe tener al menos 7000 visitas y 350 conversiones.
* **Cuando los ingresos por visita son su métrica de éxito:** 1000 visitas y al menos 50 conversiones por día por experiencia, y además la actividad debe tener al menos 1000 conversiones por experiencia. Por lo general, el RPV requiere más datos para construir modelos debido a la mayor varianza de datos que normalmente existe en los ingresos de visita en comparación con la tasa de conversión.

### [!UICONTROL La segmentación automática] cuenta con una funcionalidad de configuración completa.

* Porque [!UICONTROL Segmentación automática] está incrustado en el flujo de trabajo de la actividad A/B, [!UICONTROL Segmentación automática] se beneficia de los más maduros y completos [!UICONTROL Compositor de experiencias visuales] (VEC). También puede utilizar [Vínculos de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) con [!UICONTROL Segmentación automática].

### [!UICONTROL La segmentación automática] proporciona un amplio marco de pruebas en línea.

* El método multi-armed bandit forma parte de un marco de pruebas en línea más amplio que permite [!DNL Adobe] científicos de datos e investigadores para comprender los beneficios de sus continuas mejoras en condiciones reales.
* En el futuro, este banco de pruebas nos permitirá abrir [!DNL Adobe] plataforma de aprendizaje automático para clientes expertos en datos, de modo que puedan incorporar sus propios modelos para aumentar el [!DNL Target] modelos.

## Informes y [!UICONTROL segmentación automática] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obtener más información, consulte [Informes y segmentación automática](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

## Vídeo de formación: Explicación de las actividades de Segmentación automática ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo explica cómo configurar una actividad A/B de [!UICONTROL Segmentación automática].

Tras completar esta formación, debe ser capaz de:

* Definición de las pruebas de [!UICONTROL Segmentación automática]
* Comparación y contraste entre la [!UICONTROL Segmentación automática][!UICONTROL  y la Personalización automatizada.]
* Creación de actividades de [!UICONTROL Segmentación automática]

>[!VIDEO](https://video.tv.adobe.com/v/18558)

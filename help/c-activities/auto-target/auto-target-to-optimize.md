---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: El Destinatario automático en Adobe Target utiliza aprendizaje automático avanzado para seleccionar entre varias experiencias de alto rendimiento definidas por expertos en marketing para personalizar el contenido y dirigir las conversiones. La segmentación automática proporciona la experiencia más adaptada a cada visitante según su perfil de cliente individual y el comportamiento de visitantes anteriores con perfiles similares.
title: Descripción general del Destinatario automático
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 777b5a84fed7455274183d2b9fe7f20096087064
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 87%

---


# ![Descripción general del Destinatario automático PREMIUM](/help/assets/premium.png)

[!UICONTROL La segmentación automática] utiliza aprendizaje automático avanzado para seleccionar entre varias experiencias de alto rendimiento definidas por expertos en marketing para personalizar el contenido y dirigir las conversiones. La segmentación automática proporciona la experiencia más adaptada a cada visitante según su perfil de cliente individual y el comportamiento de visitantes anteriores con perfiles similares.

>[!NOTE]
>
>La [!UICONTROL segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/c-intro/intro.md).

## Historia de éxito real con Destinatario automático {#success}

Un importante minorista de ropa ha utilizado recientemente una actividad de Destinatario  automático con diez experiencias basadas en la categoría de productos (además de un control aleatorio) para ofrecer el contenido adecuado a cada visitante. Se eligió &quot;[!UICONTROL Añadir al carro]&quot; como métrica de optimización principal. Las experiencias objetivo tuvieron un alza promedio del 29,09%. Después de crear los modelos de Destinatario  automático, la actividad se estableció en un 90 % de experiencias personalizadas.

En sólo diez días, se lograron más de 1.700.000 dólares de alza.

Siga leyendo para aprender a utilizar el Destinatario  automático para aumentar el alza y los ingresos de su organización.

## Información general {#section_972257739A2648AFA7E7556B693079C9}

Al [crear una actividad A/B mediante el flujo de trabajo guiado de tres pasos](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), tiene la opción de asignar el tráfico con la opción [!UICONTROL Segmentación automática para experiencias personalizadas]:

![Opción de segmentación automática para experiencias personalizadas](/help/c-activities/assets/auto-target-ui-new.png)

La opción de [!UICONTROL segmentación automática] dentro del flujo de actividad A/B le permite aprovechar el aprendizaje automático para personalizar en un solo clic basándose en un conjunto de experiencias definidas por el especialista en marketing. [!UICONTROL La segmentación automática] está diseñada para ofrecer una optimización máxima, en comparación con las pruebas A/B tradicionales o la asignación automática, determinando qué experiencia mostrar para cada visitante. Al contrario que en una actividad A/B, cuyo objetivo es encontrar un único ganador, la [!UICONTROL segmentación automática] determina la mejor experiencia para un visitante específico (según su perfil e información adicional) y así ofrecerle una experiencia con un alto nivel de personalización.

De forma parecida a la Personalización automatizada, la [!UICONTROL segmentación automática] utiliza un algoritmo de bosque aleatorio (un método puntero de ensamblado de la ciencia de datos) para determinar la mejor experiencia para mostrar a un visitante. Debido a que la [!UICONTROL segmentación automática] se puede adaptar a los cambios en el comportamiento de los visitantes, se puede ejecutar de forma perpetua para proporcionar un aumento. A veces, este modo se denomina “siempre-activo”.

Al contrario que en una actividad A/B, en la que la asignación de experiencias para un visitante dado es fija, la [!UICONTROL segmentación automática] optimiza el objetivo comercial especificado en cada visita. Al igual que en la [!UICONTROL Personalización automática], la [!UICONTROL segmentación automática], de forma predeterminada, reserva parte del tráfico de la actividad como grupo de control para medir el aumento. A los visitantes del grupo de control se les sirve una experiencia aleatoria en la actividad.

## Consideraciones

There are a few important considerations to keep in mind when using [!UICONTROL Auto-Target]:

* No puede cambiar una actividad específica de segmentación automática a [!UICONTROL Personalización automatizada] y viceversa.
* No puede pasar de la asignación de tráfico manual (prueba tradicional A/B) a la [!UICONTROL orientación automática] y viceversa después de que una actividad esté activa.
* Se ha creado un modelo para identificar el rendimiento de la estrategia personalizada frente al tráfico servido al azar frente al envío de todo el tráfico a la experiencia ganadora general. Este modelo solo tiene en cuenta las visitas y las conversiones en el entorno predeterminado.

   El tráfico de un segundo conjunto de modelos se genera para cada grupo de modelos (AP) o experiencia (AT). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

   Por lo tanto, las solicitudes se presentarán con el mismo modelo, independientemente del entorno, pero la pluralidad de tráfico debe provenir del entorno predeterminado para garantizar que la experiencia ganadora global identificada sea coherente con el comportamiento real.

* Hay que usar un mínimo de dos experiencias.

## Terminología {#section_A309B7E0B258467789A5CACDC1D923F3}

Los siguientes términos pueden resultar útiles al tratar el tema de la [!UICONTROL segmentación automática]:

| Término | Definición |
|---|---|
| Multi-armed bandit | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| Bosque aleatorio | El bosque aleatorio es una solución pionera de aprendizaje automático. En el ámbito de la ciencia de datos, es un método de clasificación o regresión del ensamblado que funciona construyendo un gran número de árboles de decisión basados en los atributos del visitante y de la visita. En Target, el bosque aleatorio se utiliza para determinar qué experiencia se prevé que tendrá la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. Para obtener más información sobre el bosque aleatorio, consulte  [Algoritmo de bosque aleatorio](/help/c-activities/t-automated-personalization/algo-random-forest.md). |
| Muestreo Thompson | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el “coste” de encontrar dicha experiencia. El muestreo Thompson siempre selecciona un ganador, aunque no haya diferencias estadísticas entre las dos experiencias. Para obtener más información, consulte [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Cómo funciona la [!UICONTROL segmentación automática] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Obtenga más información acerca de los datos y algoritmos detrás de la [!UICONTROL segmentación automática] y la Personalización automatizada en los siguientes vínculos:

| Término | Detalles |
|--- |--- |
| [Algoritmo de bosque aleatorio](/help/c-activities/t-automated-personalization/algo-random-forest.md) | El algoritmo de personalización principal de Target que se utiliza en la [!UICONTROL Segmentación automática] y en la Personalización automatizada es el de bosque aleatorio. Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un rendimiento más predictivo que el que podría obtenerse de cualquier algoritmo de aprendizaje constituyente. El algoritmo de bosque aleatorio del sistema de personalización automatizada es un método de clasificación o regresión que funciona creando una multitud de árboles de decisión en tiempo de aprendizaje. |
| [Carga de datos para los algoritmos de personalización de Target](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Hay varias formas de introducir datos para los modelos de [!UICONTROL Segmentación automática] y Personalización automatizada. |
| [Recopilación de datos para los algoritmos de personalización de Target](/help/c-activities/t-automated-personalization/ap-data.md) | Los algoritmos de personalización de Target recopilan automáticamente una variedad de datos. |

## Determinación de la asignación de tráfico.  {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependiendo del objetivo de su actividad, puede elegir una asignación de tráfico diferente entre control y experiencias personalizadas. Lo mejor es determinar este objetivo antes de realizar su actividad en vivo.

La lista desplegable [!UICONTROL Asignación personalizada] le permite elegir entre las siguientes opciones:

* Evaluar el Algoritmo de personalización
* Maximice el tráfico de personalización
* Asignación personalizada

![Lista desplegable Objetivo de asignación](/help/c-activities/assets/split-new.png)

| Objetivo de la actividad | Asignación de tráfico sugerida | Compensaciones |
|--- |--- |--- |
| **Evaluar el algoritmo de personalización (50/50)**: Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza. Se sugiere utilizar con “experiencias aleatorias” como control. | 50 % de control/50 % de experiencia personalizada dividida | <ul><li>Maximiza la precisión del aumento entre el control y el personalizado</li><li>Relativamente, tendrá menos visitantes una experiencia personalizada</li></ul> |
| **Maximización del tráfico de personalización (90/10)**: Si su objetivo es crear una actividad “siempre activada”, ponga el 10% de los visitantes en el control a fin de asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. Tenga en cuenta que la compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tendrá menos precisión en la estimación del alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control. | Lo mejor es usar una división de Experiencia personalizada del 10 % - 30 %/70 % - 90 % | <ul><li>Maximiza el número de visitantes que tienen una experiencia personalizada</li><li>Maximiza el alza</li><li>Menos precisión en cuanto a lo que significa el aumento para la actividad</li></ul> |
| **Asignación personalizada** | Divida manualmente el porcentaje según lo desee. | <ul><li>Puede que no consiga los resultados deseados. Si no está seguro, siga las sugerencias de cualquiera de las opciones anteriores</li></ul> |

Para ajustar el porcentaje de Control, haga clic en los iconos de la columna Asignación. No se puede reducir el grupo de control por debajo del 10 %.

![Cambiar la asignación del tráfico de segmentación automática](/help/c-activities/assets/auto-target-control.png)

Puede [seleccionar una experiencia específica para utilizarla como control](/help/c-activities/t-automated-personalization/experience-as-control.md) o utilizar la opción de experiencia aleatoria.

## ¿Cuándo se debe elegir la [!UICONTROL Segmentación automática] en lugar de la Personalización automatizada? {#section_BBC4871C87944DD7A8B925811A30C633}

Hay varios escenarios en los que puede preferir usar la [!UICONTROL Segmentación automática] sobre la Personalización Automatizada:

* Si quiere definir la experiencia completa y no ofertas individuales que se combinarán automáticamente para formar una experiencia.
* Si desea aprovechar el conjunto completo de funciones del Compositor de experiencias visuales (VEC) que no admite [!UICONTROL Personalización automática]: el editor de código personalizado, las audiencias de experiencia múltiple y más.
* Si desea realizar cambios estructurales en su página en diferentes experiencias. Por ejemplo, si desea reorganizar el orden de los elementos en su página de inicio, sería más apropiado utilizar la [!UICONTROL Segmentación automática] que la Personalización automatizada.

## ¿Qué tienen en común la [!UICONTROL Segmentación automática] y la Personalización automatizada?{#section_2A601F482F9A44E38D4B694668711319}

**El algoritmo se optimiza para lograr un resultado positivo en cada visita.**

* El algoritmo predice la tendencia de un visitante a la conversión (o el resultado estimado de la conversión) para poder ofrecer la mejor experiencia.
* Un visitante es apto para una nueva experiencia al finalizar una sesión existente (a menos que el visitante esté en el grupo de control, en cuyo caso la experiencia que se le asigna al visitante en su primera visita sigue siendo la misma para visitas posteriores).
* En una sesión, la predicción no cambia para mantener la coherencia visual.

**El algoritmo se adapta a los cambios de comportamiento de los visitantes.**

* El método multi-armed bandit garantiza que el modelo siempre destine una pequeña fracción de tráfico a seguir con el aprendizaje mientras dure el aprendizaje de la actividad y a evitar la sobreexplotación de las tendencias aprendidas anteriormente.
* Los modelos subyacentes se regeneran cada 24 horas a partir de los últimos datos de comportamiento de los visitantes para garantizar que Target siempre explotando los cambios de preferencias de los visitantes.
* Si el algoritmo no es capaz de determinar experiencias ganadoras para usuarios individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, sin dejar por ello de buscar ganadores personalizados. La experiencia con mejor rendimiento se determina empleando [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**El algoritmo se optimiza continuamente para lograr una única métrica de objetivos.**

* Esta métrica puede estar basada en la conversión o en los ingresos (más concretamente, Ingresos por visita).

**Target recopila automáticamente información sobre los visitantes para crear los modelos de personalización.**

* Para obtener más información sobre los parámetros utilizados en la [!UICONTROL segmentación automática] y la personalización automatizada, consulte [Recopilación de datos de personalización automatizada](/help/c-activities/t-automated-personalization/ap-data.md).

**Target utiliza automáticamente todas las audiencias compartidas por Experience Cloud para crear los modelos de personalización.**

* No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de Audiencias de Experience Cloud con Target, consulte  [Audiencias de Experience Cloud](/help/c-integrating-target-with-mac/mmp.md)

**Los expertos en marketing pueden cargar datos sin conexión, puntuaciones de inclinación u otros datos personalizados para crear modelos de personalización.**

* Obtenga más información sobre [cargar datos para la segmentación automática y la personalización automatizada](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## ¿En qué se diferencian la [!UICONTROL segmentación automática] y la personalización automatizada?{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL La segmentación automática] requiere frecuentemente menos tráfico que la personalización automatizada para crear un modelo personalizado.**

Aunque la cantidad de tráfico *por experiencia* requerida para los modelos de [!UICONTROL segmentación automática] o [!UICONTROL personalización automática] para compilar es la misma, usualmente hay más experiencias en una actividad de personalización automatizada que una actividad de [!UICONTROL segmentación automática]. Por ejemplo, si tuvo una actividad de [!UICONTROL personalización automática] en la que creó dos ofertas por ubicación con dos ubicaciones, habría cuatro (2 = 4) experiencias totales incluidas en la actividad (sin exclusiones). Utilizando la [!UICONTROL segmentación automática], puede configurar la experiencia 1 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2, y la experiencia 2 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2. Debido a que la [!UICONTROL segmentación automática] le permite elegir tener múltiples cambios dentro de una experiencia, puede reducir la cantidad total de experiencias en su actividad.

Para la [!UICONTROL segmentación automática], se pueden usar reglas simples para comprender los requisitos de tráfico:

* **Cuando la conversión es su métrica de éxito:** 1000 visitas y al menos 50 conversiones por día por experiencia; además, la actividad debe tener al menos 7000 visitas y 350 conversiones.
* **Cuando los ingresos por visita son su métrica de éxito:** 1000 visitas y al menos 50 conversiones por día por experiencia, y además la actividad debe tener al menos 1000 conversiones por experiencia. Por lo general, el RPV requiere más datos para construir modelos debido a la mayor varianza de datos que normalmente existe en los ingresos de visita en comparación con la tasa de conversión.

**[!UICONTROL La segmentación automática] cuenta con una funcionalidad de configuración completa.**

* Al estar integrado en el flujo de trabajo de la actividad A/B, la [!UICONTROL segmentación automática] utiliza el compositor de experiencias visuales (VEC), una herramienta más antigua y completa. También puede aprovechar los [vínculos de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md) con la [!UICONTROL segmentación automática].

**[!UICONTROL La segmentación automática] proporciona un amplio marco de pruebas en línea.**

* El método multi-armed bandit forma parte de un marco de pruebas en línea más amplio que permite a nuestros científicos de datos e investigadores comprender los beneficios de sus continuas mejoras en condiciones reales.
* En el futuro, este banco de pruebas nos permitirá abrir nuestra plataforma de aprendizaje automático a nuestros clientes expertos en datos para que puedan traer sus propios modelos para aumentar los modelos de Target.

## Informes y [!UICONTROL segmentación automática] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obtener más información, consulte [Informe Resumen de la segmentación automática](/help/c-reports/auto-target-summary-report.md) en la sección [Informes](/help/c-reports/reports.md).

## Vídeo de capacitación: Distintivo de ![información general de Actividades de Destinatario automático](/help/assets/overview.png)

Este vídeo explica cómo configurar una actividad A/B de [!UICONTROL Segmentación automática].

Tras completar esta formación, debe ser capaz de:

* Definición de las pruebas de [!UICONTROL Segmentación automática]
* Comparación y contraste entre la [!UICONTROL Segmentación automática] y la Personalización automatizada.
* Creación de actividades de [!UICONTROL Segmentación automática]

>[!VIDEO](https://video.tv.adobe.com/v/18558)
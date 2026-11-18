---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas
description: Descubra cómo una actividad de [!UICONTROL Segmentación automática] proporciona la experiencia más adaptada a cada visitante según los perfiles de los clientes y el comportamiento de visitantes similares.
title: ¿Qué es una actividad de [!UICONTROL Segmentación automática]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: 'https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 12%
---
# Introducción a [!UICONTROL Segmentación automática] {#auto-target-overview}

>[!BEGINSHADEBOX]

**En esta página:** Descubre cómo una actividad de **[!UICONTROL Segmentación automática]** ofrece a cada visitante la experiencia más adaptada, cómo funciona, cómo elegir la asignación de tráfico y cómo se compara con **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Las actividades de **[!UICONTROL Segmentación automática]** en [!DNL Adobe Target] utilizan aprendizaje automático avanzado para seleccionar entre varias experiencias de alto rendimiento definidas por expertos en marketing para personalizar el contenido y dirigir las conversiones. **[!UICONTROL Segmentación automática]** ofrece a cada visitante la experiencia más adaptada en función del perfil del cliente y del comportamiento de visitantes anteriores con perfiles similares.

>[!NOTE]
>
>* **[!UICONTROL Segmentación automática]** está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>* **[!UICONTROL Analytics for Target]** (A4T) admite actividades de **[!UICONTROL Segmentación automática]**. Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

Cuando [cree una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) con el flujo de trabajo guiado de tres pasos, elija la opción **[!UICONTROL Segmentación automática para experiencias personalizadas]** en la página **[!UICONTROL Segmentación]** (paso 2). Para ver los pasos, consulte [Crear una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md).

![Configuración del método de asignación de tráfico](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

Esta opción, dentro del flujo de actividad A/B, permite utilizar el aprendizaje automático para personalizar el contenido con un solo clic, basándose en un conjunto de experiencias definidas por el especialista en marketing. **[!UICONTROL Segmentación automática]** está diseñada para ofrecer la máxima optimización, en comparación con las pruebas A/B tradicionales o **[!UICONTROL Asignación automática]**, al determinar qué experiencia mostrar para cada visitante. A diferencia de una actividad A/B, cuyo objetivo es encontrar un solo ganador, **[!UICONTROL Segmentación automática]** determina automáticamente la mejor experiencia para un visitante determinado. La mejor experiencia se basa en el perfil del visitante y otra información contextual.

De manera similar a **[!UICONTROL Automated Personalization]**, **[!UICONTROL Segmentación automática]** usa un [algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), un método puntero de ensamblado de la ciencia de datos, para determinar la mejor experiencia para mostrar a un visitante. **[!UICONTROL La segmentación automática]** se puede adaptar a los cambios en el comportamiento de los visitantes, de modo que se pueda ejecutar de manera perpetua para proporcionar un aumento. Este método a veces se denomina modo &quot;siempre-activo&quot;.

A diferencia de una actividad A/B, en la que la asignación de experiencias para un visitante dado es fija, **[!UICONTROL la segmentación automática]** optimiza el objetivo comercial especificado en cada visita. Al igual que en **[!UICONTROL Automated Personalization]**, **[!UICONTROL la segmentación automática]** reserva parte del tráfico de la actividad como grupo de control de forma predeterminada para medir el alza. A los visitantes del grupo de control se les sirve una experiencia aleatoria en la actividad.

## Consideraciones {#considerations}

Tenga en cuenta los siguientes puntos cuando use **[!UICONTROL Segmentación automática]**:

* Preste atención a la forma de la actividad. El rendimiento depende más del número de ubicaciones × ofertas que del recuento de experiencias sin procesar. Las combinaciones cartesianas grandes pueden ralentizar la carga y la edición en el **[!UICONTROL Compositor de experiencias visuales]**, incluso por debajo de los límites de experiencia documentados.

  Como práctica recomendada, mantenga las actividades de **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]** en 4-6 ubicaciones con 4-6 ofertas por ubicación. No se recomiendan configuraciones más grandes. Estas actividades se crean directamente en el paso **[!UICONTROL Experiencias]**, por lo que la interfaz de usuario de [!DNL Target] puede mostrar advertencias en línea o bloquear el guardado cuando la configuración supera los umbrales admitidos.

* No puede cambiar una actividad específica de **[!UICONTROL Segmentación automática]** a **[!UICONTROL Automated Personalization]**, o al contrario.
* No puede cambiar de la asignación de tráfico **[!UICONTROL Manual]** (tradicional **[!UICONTROL prueba A/B]**) a la **[!UICONTROL Segmentación automática]**, o viceversa, después de guardar una actividad como borrador.
* Un modelo se crea para identificar el rendimiento de la estrategia personalizada en comparación con el tráfico servido aleatoriamente en lugar de enviar todo el tráfico a la experiencia ganadora general. Este modelo considera las visitas y conversiones solo en el entorno predeterminado.

  Se crea un segundo conjunto de modelos para cada grupo de modelado (AP) o experiencia (AT). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

  Las solicitudes se proporcionan con el mismo modelo, independientemente del entorno. Sin embargo, la pluralidad del tráfico debería proceder del entorno predeterminado para garantizar que la experiencia ganadora general identificada sea coherente con el comportamiento en el mundo real.

* Utilice un mínimo de dos experiencias.

## Terminología {#section_A309B7E0B258467789A5CACDC1D923F3}

Los siguientes términos pueden resultar útiles al tratar el tema de la **[!UICONTROL segmentación automática]**:

| Término | Definición |
|---|---|
| [Bandido multibrazo](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| [Bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El bosque aleatorio es una solución pionera de aprendizaje automático. En términos de ciencia de datos, es una clasificación de conjunto, o método de regresión, que funciona construyendo muchos árboles de decisión basados en los atributos del visitante y la visita. En [!DNL Target], el bosque aleatorio se usa para determinar qué experiencia se espera que tenga la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. |
| [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el &quot;coste&quot; de encontrar esa experiencia. El muestreo Thompson siempre elige un ganador, incluso si no hay diferencia estadística entre dos experiencias. |

## Cómo funciona [!UICONTROL Segmentación automática] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Las siguientes páginas describen los datos y algoritmos subyacentes a **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**:

| Tema | Detalles |
|--- |--- |
| [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | El algoritmo de personalización principal de [!DNL Target], usado en **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**, es el de bosque aleatorio. Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un mejor rendimiento predictivo que el que se podría obtener de cualquiera de los algoritmos de aprendizaje constituyentes. El algoritmo de bosque aleatorio en las actividades **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** es un método de clasificación o regresión que funciona mediante la construcción de una multitud de árboles de decisión en el momento de entrenar. |
| [Cargando Datos Para [!DNL Target] Algoritmos De Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) | Hay varias formas de introducir datos para los modelos **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**. |
| [Recopilación de datos para [!DNL Target] algoritmos de Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md) | Los algoritmos de personalización de [!DNL Target] recopilan automáticamente varios datos. |

## Determinar la asignación del tráfico {#section_AB3656F71D2D4C67A55A24B38092958F}

Según el objetivo de la actividad, puede elegir una asignación de tráfico diferente entre el control y las experiencias personalizadas. Lo mejor es determinar este objetivo antes de realizar su actividad en vivo.

La lista desplegable **[!UICONTROL Asignación personalizada]** le permite elegir entre las siguientes opciones:

* **[!UICONTROL Evaluar el algoritmo de Personalization (50/50)]**
* **[!UICONTROL Maximizar el tráfico de Personalization (90/10)]**
* **[!UICONTROL Asignación personalizada]**

![Lista desplegable Objetivo de asignación](/help/main/c-activities/assets/split-new-ui.png)

En la tabla siguiente se explican las tres opciones:

| Objetivo de la actividad | Asignación de tráfico sugerida | Compensaciones |
|--- |--- |--- |
| **[!UICONTROL Evaluar el algoritmo de personalización (50/50)]**: Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control. | 50 % de control/50 % de experiencia personalizada dividida | <ul><li>Maximiza la precisión del aumento entre el control y el personalizado</li><li>Relativamente menos visitantes tienen una experiencia personalizada</li></ul> |
| **[!UICONTROL Maximizar el tráfico de Personalization (90/10)]**: Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10% de los visitantes en el control a fin de asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. La compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control. | Lo mejor es usar una división de Experiencia personalizada del 10 % - 30 %/70 % - 90 % | <ul><li>Maximiza el número de visitantes que tienen una experiencia personalizada</li><li>Maximiza el alza</li><li>Menos precisión en cuanto a lo que significa el aumento para la actividad</li></ul> |
| **[!UICONTROL Asignación personalizada]** | Divida manualmente el porcentaje según lo desee. | <ul><li>Puede que no consiga los resultados deseados. Si no está seguro, siga las sugerencias de cualquiera de las opciones anteriores</li></ul> |

Para ajustar el porcentaje de **[!UICONTROL Control]**, haga clic en **[!UICONTROL Experiencias]** en el panel **[!UICONTROL Asignación del tráfico]** y, a continuación, ajuste los porcentajes como desee. No se puede reducir el grupo de control por debajo del 10 %.

Puede [seleccionar una experiencia específica para usarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o puede usar la opción **[!UICONTROL experiencia aleatoria]**.

## Comparar [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] {#compare-at-ap}

**[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]** comparten el mismo algoritmo y los mismos datos, pero difieren en la forma en que se crean las experiencias y en la cantidad de tráfico que necesitan los modelos.

### Qué tienen en común los dos tipos de actividades {#section_2A601F482F9A44E38D4B694668711319}

* **Optimización para cada visita.** El algoritmo predice la tendencia de un visitante a convertir (o los ingresos estimados de la conversión) para ofrecer la mejor experiencia. Un visitante puede disfrutar de una nueva experiencia al final de una sesión existente. La excepción es un visitante del grupo de control que mantiene la experiencia asignada en la primera visita. Dentro de una sesión, la predicción no cambia para mantener la coherencia visual.
* **Adaptación a los cambios en el comportamiento de los visitantes.** El bandido multiarmado siempre &quot;gasta&quot; una pequeña fracción del tráfico para seguir aprendiendo a lo largo de la vida de la actividad y para evitar la sobreexplotación de las tendencias previamente aprendidas. Los modelos subyacentes se reconstruyen cada 24 horas utilizando los datos de comportamiento del visitante más recientes. Si el algoritmo no puede determinar experiencias ganadoras para usuarios individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, que se encuentra usando [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling), mientras sigue buscando ganadores personalizados.
* **Una métrica de un solo objetivo.** El algoritmo se optimiza continuamente para una métrica, que puede estar basada en conversiones o en ingresos (más específicamente, **[!UICONTROL Ingresos por visita]**).
* **Recopilación automática de datos.** [!DNL Target] recopila automáticamente información sobre los visitantes para crear los modelos de personalización. Para obtener más información sobre los parámetros utilizados, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).
* **Audiencias compartidas.** [!DNL Target] utiliza automáticamente todas las [!DNL Adobe Experience Cloud] audiencias compartidas para crear los modelos de personalización. No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de [!DNL Experience Cloud Audiences] con [!DNL Target], consulte [Audiencias de Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).
* **Datos personalizados.** Los especialistas en marketing pueden cargar datos sin conexión, puntuaciones de tendencia u otros datos personalizados para crear modelos de personalización. Más información sobre [cargar datos para la segmentación automática y Automated Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

### Diferencias entre los dos tipos de actividad {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

Considere la opción de **[!UICONTROL segmentación automática]** en lugar de **[!UICONTROL Automated Personalization]** cuando quiera definir toda la experiencia, usar el conjunto completo de características de **[!UICONTROL Compositor de experiencias visuales]** (VEC) o hacer cambios estructurales en su página.

| | [!UICONTROL Segmentación automática] | [!UICONTROL Personalización automatizada] |
|---|---|---|
| **Definición de experiencia** | Puede definir toda la experiencia, que puede contener varios cambios. | Las ofertas individuales se combinan automáticamente para formar una experiencia. |
| **[!UICONTROL Características del Compositor de experiencias visuales]** | **[!UICONTROL Segmentación automática]** está integrada en el flujo de trabajo de la actividad A/B, por lo que se beneficia del VEC más maduro y completo. También puede usar [vínculos de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md). | No se admiten el editor de código personalizado, las audiencias de experiencias múltiples y otras funciones. |
| **Cambios estructurales en la página** | Más apropiado. Por ejemplo, puede reorganizar los elementos de la página principal. | Menos apropiado. |
| **Número de experiencias** | Normalmente son menos, ya que una experiencia puede contener varios cambios. | Normalmente son más, ya que las experiencias son todas las combinaciones de ofertas y ubicaciones. |
| **Tráfico necesario para crear los modelos** | Con frecuencia, menos en total. | Frecuentemente más en total. |

La cantidad de tráfico *por experiencia* necesaria para crear los modelos es la misma para ambos tipos de actividad. **[!UICONTROL La segmentación automática]** requiere con frecuencia menos tráfico total porque suele tener menos experiencias.

Por ejemplo, en una actividad **[!UICONTROL Automated Personalization]** con dos ofertas por ubicación y dos ubicaciones, hay cuatro (2 × 2 = 4) experiencias totales en la actividad (sin exclusiones). En **[!UICONTROL Segmentación automática]**, puede configurar la experiencia 1 para incluir la oferta 1 en la ubicación 1 y la oferta 2 en la ubicación 2, y la experiencia 2 para incluir la oferta 2 en la ubicación 1 y la oferta 1 en la ubicación 2. **[!UICONTROL La segmentación automática]** permite múltiples cambios dentro de una experiencia, por lo que puede reducir la cantidad total de experiencias en su actividad.

### Requisitos de tráfico para [!UICONTROL segmentación automática] {#traffic-requirements}

Las siguientes reglas generales ayudan a comprender los requisitos de tráfico:

* **Cuando [!UICONTROL Conversión] es tu métrica de éxito:** 1000 visitas y al menos 50 conversiones por día por experiencia. Además, la actividad debe tener al menos 7000 visitas y 350 conversiones.
* **Cuando [!UICONTROL Ingresos por visita] es su métrica de éxito:** 1,000 visitas y al menos 50 conversiones por día por experiencia. Además, la actividad debe tener al menos 1000 conversiones por experiencia. **[!UICONTROL Ingresos por visita]** generalmente requieren más datos para crear modelos, debido a que la variación en los ingresos por visita suele ser mayor que en la tasa de conversión.

**[!UICONTROL Segmentación automática]** también proporciona un amplio marco de pruebas en línea. El método multi-armed bandit forma parte de un marco de pruebas en línea más amplio que permite a [!DNL Adobe] científicos e investigadores de datos comprender los beneficios de sus continuas mejoras en condiciones reales. En el futuro, este banco de pruebas permitirá que [!DNL Adobe] abra su plataforma de aprendizaje automático a clientes expertos en datos para que puedan incorporar sus propios modelos y aumentar los modelos de [!DNL Target].

Para obtener más información sobre los informes, consulte [Informes y segmentación automática](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

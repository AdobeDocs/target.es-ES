---
keywords: personalización automatizada;ap;audiencias;ensamblado;bosque aleatorio;multi-armed bandit;muestreo thompson;ml;aprendizaje automático
description: Aprenda a utilizar las actividades de [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target] que usan aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante.
title: ¿Qué es una actividad de [!UICONTROL Automated Personalization] (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: 'https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 15%
---
# Introducción a [!UICONTROL Automated Personalization] {#automated-personalization-overview}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo una actividad de **[!UICONTROL Automated Personalization]** coincide con las variaciones de ofertas para cada visitante, y qué considerar al usarla.

>[!ENDSHADEBOX]

>[!NOTE]
>
>**[!UICONTROL Automated Personalization]** está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md#premium).

Las actividades de **[!UICONTROL Automated Personalization]** (AP) en [!DNL Adobe Target] combinan ofertas o mensajes, y utilizan aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante en función de su perfil de cliente, para personalizar el contenido y dirigir las conversiones.

Los especialistas en marketing implementan un archivo en su sitio, que les permite apuntar y hacer clic en cualquier contenido y, a continuación, crear opciones de contenido adicionales para esa área utilizando el **[!UICONTROL Compositor de experiencias visuales]** (VEC). A continuación, el algoritmo determina automáticamente qué parte del contenido se ofrece a cada visitante en función de todos los datos de comportamiento que tiene el sistema del visitante.

**[!UICONTROL Automated Personalization]** se adapta a los cambios en el comportamiento de los visitantes, por lo que puede ejecutarse sin una fecha de fin establecida para proporcionar un alza y una personalización continuas. Este modo a veces se denomina &quot;siempre-activo&quot;. El experto en marketing no necesita ejecutar una prueba, analizar los resultados y proporcionar un ganador antes de conocer el alza. **[!UICONTROL Automated Personalization]** también es útil en la fase de detección de las pruebas y cuando se dirigen a visitantes diversos. Para obtener más información sobre las diferencias con la segmentación automática **1, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).**

Los siguientes términos pueden resultar útiles al tratar el tema de **[!UICONTROL Automated Personalization]**:

| Término | Definición |
|---|---|
| Multi-armed bandit | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| Bosque aleatorio | Un enfoque líder de aprendizaje automático. En términos de ciencia de datos, se trata de un método de clasificación o regresión por conjuntos que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. |
| Muestreo Thompson | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el &quot;coste&quot; de encontrar esa experiencia. El muestreo Thompson siempre elige un ganador, incluso si no hay diferencia estadística entre dos experiencias. Para obtener más información, consulte [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Funcionamiento del modelo de personalización {#how-ap-works}

**[!UICONTROL Automated Personalization]** usa un algoritmo de bosque aleatorio para personalizar. El bosque aleatorio es un enfoque de aprendizaje automático líder. En términos de ciencia de datos, se trata de un método de clasificación o regresión por conjuntos que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. En [!DNL Target], el bosque aleatorio se usa para determinar qué experiencia se espera que tenga la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico.

Por ejemplo, es probable que los visitantes que utilizan Chrome, son miembros de fidelidad de oro y acceden a su sitio los martes conviertan con la Experiencia A. Es más probable que los visitantes de Nueva York conviertan con la Experiencia B.

Para obtener más información acerca del bosque aleatorio en [!DNL Target], vea [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

| Aspecto | Cómo funciona |
|---|---|
| **Optimización para cada visita** | El algoritmo predice la probabilidad de que un visitante realice una conversión (o los ingresos estimados procedentes de la conversión) para ofrecer la mejor experiencia. Un visitante puede disfrutar de una nueva experiencia al final de una sesión existente, a menos que esté en el grupo de control. Un visitante del grupo de control ve la misma experiencia que en la primera visita. La experiencia no cambia dentro de una sesión para mantener la coherencia visual. |
| **Adaptación a cambios en el comportamiento de visitantes** | El bandido multi-armado siempre gasta una pequeña fracción de tráfico para continuar aprendiendo durante toda la vida de la actividad y para evitar la sobreexplotación de las tendencias previamente aprendidas. Los modelos subyacentes se reconstruyen cada 24 horas utilizando los datos de comportamiento del visitante más recientes. Si el algoritmo no puede determinar experiencias ganadoras para visitantes individuales, mostrará la experiencia con mejor rendimiento general, que se encuentra usando [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling), mientras que seguirá buscando ganadores personalizados. |
| **Métrica de objetivo** | El modelo se optimiza continuamente para lograr una única métrica de objetivos, que puede basarse en conversiones o en ingresos (o, mejor dicho, en **[!UICONTROL ingresos por visita]**). |
| **Datos y audiencias** | [!DNL Target] recopila automáticamente información sobre los visitantes para crear los modelos de personalización. Para obtener más información sobre los atributos utilizados en **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md). [!DNL Target] también usa automáticamente todas las audiencias compartidas de [!DNL Adobe Experience Cloud], por lo que no es necesario que haga nada para agregar audiencias al modelo. Para obtener más información, consulte [Audiencias de Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md). |
| **Datos personalizados** | Los especialistas en marketing pueden cargar datos sin conexión, como información de CRM, puntuaciones de tendencia de cancelación por parte del cliente u otros datos personalizados para crear modelos de personalización. Los datos se pueden introducir con [parámetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}, [parámetros de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank} o [API del lado del servidor para actualizar perfiles](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}. |

## Vídeo de formación: Tipos de actividades {#training-video}

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target]. **[!UICONTROL Automated Personalization]** se discute a partir de las 5:55.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

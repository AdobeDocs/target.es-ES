---
keywords: personalización automatizada;ap;audiencias;ensamblado;bosque aleatorio;multi-armed bandit;muestreo thompson;ml;aprendizaje automático
description: Aprenda a usar actividades de [!UICONTROL Automated Personalization] (AP) en  [!DNL Adobe Target] que usan aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante.
title: ¿Qué es una actividad de [!UICONTROL Automated Personalization] (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 29%

---

# [!UICONTROL Automated Personalization] (AP)

Las actividades de [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target] combinan ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante en función de su perfil de cliente para personalizar el contenido y dirigir las conversiones.

>[!NOTE]
>
>[!UICONTROL Automated Personalization] está disponible como parte de la solución [!DNL Target Premium]. Esta característica no está disponible en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información sobre las funciones avanzadas que proporciona esta licencia, consulte [Target Premium](/help/main/c-intro/intro.md#premium).

De manera similar a [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] usa un [algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), un método puntero de ensamblado de la ciencia de datos, como su principal algoritmo de personalización para determinar la mejor experiencia para mostrar a un visitante. [!UICONTROL Automated Personalization] puede ser útil en la fase de detección de la prueba. También es útil para permitir que el aprendizaje de la máquina pueda determinar el contenido más eficaz al segmentar varios visitantes. Con el tiempo, el algoritmo aprende a predecir el contenido más eficaz y muestra el que más probabilidades tiene de ayudarle a lograr sus objetivos.

Para obtener más información sobre las diferencias entre [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target], consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Los especialistas en marketing implementan un archivo en su sitio, que les permite apuntar y hacer clic en cualquier contenido y, a continuación, crear y seleccionar opciones de contenido adicionales para esa área utilizando el [!UICONTROL Visual Experience Composer] (VEC). A continuación, el algoritmo determina automáticamente qué parte del contenido se ofrece a cada visitante en función de todos los datos de comportamiento que tiene el sistema del visitante, proporcionando una experiencia personalizada. Dado que [!UICONTROL Automated Personalization] se puede adaptar a los cambios en el comportamiento del visitante, se puede ejecutar sin una fecha de finalización establecida para proporcionar un alza y una personalización continuas. Este modo a veces se denomina &quot;siempre-activo&quot;. El experto en marketing no necesita ejecutar una prueba, analizar los resultados y proporcionar un ganador antes de conocer el alza encontrada en la optimización, es decir, un pedido estándar de operaciones para implementar el resultado de una actividad A/B estándar.

Los siguientes términos pueden resultar útiles al tratar el tema de [!UICONTROL Automated Personalization]:

| Término | Definición |
|---|---|
| Multi-armed bandit | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| Bosque aleatorio | Un enfoque líder de aprendizaje automático. En términos de ciencia de datos, se trata de un método de clasificación o regresión por conjuntos que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. |
| Muestreo Thompson | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el &quot;coste&quot; de encontrar esa experiencia. El muestreo Thompson siempre selecciona un ganador, aunque no haya diferencias estadísticas entre las dos experiencias. Para obtener más información, consulte [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tenga en cuenta los siguientes detalles al usar [!UICONTROL Automated Personalization]:

## [!UICONTROL Automated Personalization] utiliza un algoritmo de bosque aleatorio para personalizar

El bosque aleatorio es un enfoque de aprendizaje automático líder. En términos de ciencia de datos, se trata de un método de clasificación o regresión por conjuntos que funciona mediante la construcción de muchos árboles de decisión basados en los atributos del visitante y la visita. En [!DNL Target], el bosque aleatorio se usa para determinar qué experiencia se espera que tenga la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. Por ejemplo, es probable que los visitantes que utilizan Chrome, son miembros de fidelidad de oro y acceden a su sitio los martes conviertan con la Experiencia A. Es más probable que los visitantes de Nueva York conviertan con la Experiencia B. Para obtener más información acerca del bosque aleatorio en [!DNL Target], vea [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## El modelo de personalización se optimiza para cada visita

* El algoritmo predice la probabilidad de conversión de un visitante (o los ingresos estimados por conversión) para ofrecer la mejor experiencia.
* Un visitante es elegible para una nueva experiencia al final de una sesión existente, a menos que ese visitante esté en el grupo de control. Si el visitante está en el grupo de control, la experiencia que ve en la primera visita es la misma que en las visitas posteriores.
* La experiencia presentada no cambia dentro de una sesión para mantener la coherencia visual.

## El modelo de personalización se adapta a los cambios en el comportamiento del visitante

* El método multi-armed bandit garantiza que el modelo siempre &quot;gasta&quot; una pequeña fracción del tráfico para continuar aprendiendo a lo largo de la vida de la actividad y evitar la sobreexplotación de las tendencias aprendidas anteriormente.
* Los modelos subyacentes se reconstruyen cada 24 horas utilizando los datos de comportamiento del visitante más recientes para garantizar que [!DNL Target] siempre esté usando preferencias de visitante cambiantes.
* Si el algoritmo no es capaz de determinar experiencias ganadoras para visitantes individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, sin dejar por ello de buscar ganadores personalizados. La experiencia con mejor rendimiento se determina empleando el [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

## El modelo se optimiza continuamente para lograr una única métrica de objetivos

* Esta métrica puede estar basada en conversiones o en ingresos (o, mejor dicho, [!UICONTROL Revenue per Visitor]).

## [!DNL Target] recopila automáticamente información sobre los visitantes para crear los modelos de personalización

* Para obtener más información acerca de los atributos utilizados en [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization], vea [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## [!DNL Target] utiliza automáticamente todas las [!DNL Adobe Experience Cloud] audiencias compartidas para crear los modelos de personalización

* No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de [!DNL Experience Cloud Audiences] con [!DNL Target], consulte [Audiencias de Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

## Los especialistas en marketing pueden cargar datos sin conexión, puntuaciones de tendencia u otros datos personalizados para crear modelos de personalización

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización. Hay varias formas de introducir datos en los algoritmos de personalización [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target].

* [Parámetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}
* [Parámetros de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}
* [API del lado del servidor para actualizar perfiles](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}

Para obtener información acerca de los datos que los algoritmos de personalización [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target] recopilan y usan automáticamente, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Vídeo de formación: Tipos de actividades

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target]. [!UICONTROL Automated Personalization] se discute a partir del 5:55.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

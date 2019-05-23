---
description: Personalización automatizada (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante en función de su perfil de cliente, con el fin de personalizar el contenido y dirigir las conversiones.
keywords: personalización automatizada;Audiencias;ensamblado;bosque aleatorio
seo-description: Personalización automatizada (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante en función de su perfil de cliente, con el fin de personalizar el contenido y dirigir las conversiones.
seo-title: Personalización automatizada
solution: Target
title: Personalización automatizada
title-outputclass: premium
topic: Advanced
uuid: cf9489f2-45b2-4028-8956-36d0afe0ee0a
badge: premium
translation-type: tm+mt
source-git-commit: 5405e95cf516f973b69834ac114a1e351cd3040a

---


# ![PREMIUM](/help/assets/premium.png) Personalización automatizada{#automated-personalization}

[!UICONTROL Personalización automatizada] (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante en función de su perfil de cliente, con el fin de personalizar el contenido y dirigir las conversiones.

>[!NOTE]
>
>[!UICONTROL La personalización automatizada] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una [!DNL Target Premium]licencia. Si dispone de una [!DNL Target Premium]licencia, la tarjeta [!DNL Target Premium] sustituye la [!DNL Target Standard]tarjeta en [!DNL Adobe Experience Cloud].

Al igual que la [!UICONTROL segmentación automática], la [!UICONTROL Personalización automatizada] utiliza un algoritmo de bosque aleatorio, un método puntero de ensamblado de la ciencia de datos, como su principal algoritmo de personalización a fin de determinar la mejor experiencia para mostrar a un visitante. [!UICONTROL La Personalización automatizada resulta útil en la fase de detección de las pruebas. ] También es útil para permitir que el aprendizaje de la máquina pueda determinar el contenido más eficaz al segmentar varios visitantes. Con el tiempo, el algoritmo aprende a predecir el contenido más eficaz y muestra el que más probabilidades tiene de ayudarle a lograr sus objetivos.

Para obtener más información sobre las diferencias entre la [!UICONTROL Personalización automatizada] y la [!UICONTROL Segmentación automática], consulte [Segmentación automática para experiencias personalizadas](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

Los especialistas en marketing implementan un archivo en su sitio, que les permite apuntar y hacer clic en cualquier contenido y, a continuación, crear y seleccionar opciones de contenido adicionales para dicha área utilizando el VEC ([!UICONTROL Compositor de experiencias visuales]). A continuación, el algoritmo determina automáticamente qué parte del contenido se ofrece a cada visitante en función de todos los datos de comportamiento que tiene el sistema del visitante, proporcionando una experiencia personalizada. Como la [!UICONTROL Personalización automatizada] puede adaptarse a los cambios en el comportamiento del visitante, se puede ejecutar sin una fecha de fin determinada para proporcionar un alta y una personalización continuas. A veces, este modo se denomina “siempre-activo”. El experto en marketing no necesita ejecutar una prueba, analizar los resultados y proporcionar un ganador antes de conocer el alza encontrada en la optimización, es decir, un pedido estándar de operaciones para implementar el resultado de una actividad A/B estándar.

Los términos siguientes le resultarán útiles cuando hable sobre la [!UICONTROL Personalización automatizada]:

| Término | Definición |
|---|---|
| Multi-armed bandit | Un método multi-armed bandit en la optimización equilibra el aprendizaje de exploración y la explotación de dicho aprendizaje. |
| Bosque aleatorio | El bosque aleatorio es una solución pionera de aprendizaje automático. En el ámbito de la ciencia de datos, es un método de clasificación o regresión del ensamblado que funciona construyendo un gran número de árboles de decisión basados en los atributos del visitante y de la visita. En Target, el bosque aleatorio se utiliza para determinar qué experiencia se prevé que tendrá la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. Para obtener más información sobre el bosque aleatorio, consulte   [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Muestreo Thompson | El objetivo del muestreo Thompson es determinar qué experiencia es la mejor globalmente (sin personalizar), al mismo tiempo que se minimiza el “coste” de encontrar dicha experiencia. El muestreo Thompson siempre selecciona un ganador, aunque no haya diferencias estadísticas entre las dos experiencias. Para obtener más información, consulte [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Al utilizar la [!UICONTROL Personalización automatizada], plantéese lo siguiente:

**[!UICONTROL La Personalización automatizada]utiliza un algoritmo de bosque aleatorio para la personalización.**

El bosque aleatorio es una solución pionera de aprendizaje automático. En el ámbito de la ciencia de datos, es un método de clasificación o regresión del ensamblado que funciona construyendo un gran número de árboles de decisión basados en los atributos del visitante y de la visita. En Target, el bosque aleatorio se utiliza para determinar qué experiencia se prevé que tendrá la mayor probabilidad de conversión (o los mayores ingresos por visita) para cada visitante específico. Por ejemplo, es probable que los visitantes que utilizan Chrome, son miembros de fidelidad de oro y acceden a su sitio los martes conviertan con la Experiencia A, mientras que es más probable que los visitantes de Nueva York conviertan con la Experiencia B. Para obtener más información sobre el bosque aleatorio en Target, consulte   [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

**El modelo de personalización se optimiza en cada visita.**

* El algoritmo predice la probabilidad de un visitante a la conversión (o el resultado estimado de la conversión) para poder ofrecer la mejor experiencia.
* Un visitante es apto para una nueva experiencia al finalizar una sesión existente (a menos que esté en el grupo de control, en cuyo caso las experiencia que el visitante ve en la primera visita es la misma que verá en las visitas siguientes).
* Dentro de una sesión, la experiencia presentada no cambia para mantener la coherencia visual.

**El modelo de personalización se adapta a los cambios de comportamiento de los visitantes.**

* El método multi-armed bandit garantiza que el modelo siempre destine una pequeña fracción de tráfico a seguir aprendiendo mientras dure la actividad y a evitar la sobreexplotación de las tendencias aprendidas anteriormente.
* Los modelos subyacentes se regeneran cada 24 horas a partir de los últimos datos de comportamiento de los visitantes para garantizar que Target siempre pueda utilizar los cambios de preferencias de los visitantes.
* Si el algoritmo no es capaz de determinar experiencias ganadoras para visitantes individuales, pasa automáticamente a mostrar la experiencia con mejor rendimiento general, sin dejar por ello de buscar ganadores personalizados. La experiencia con mejor rendimiento se determina empleando el [Muestreo Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**El modelo se optimiza continuamente para lograr una única métrica de objetivos.**

* Esta métrica puede estar basada en conversiones o en resultados (o, mejor dicho, en los [!UICONTROL Resultados por visitante]).

**Target recopila automáticamente información sobre los visitantes para crear los modelos de personalización.**

* Para obtener más información sobre los atributos utilizados en la [!UICONTROL segmentación automática] y la [!UICONTROL personalización automatizada], consulte [Recopilación de datos de personalización automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target utiliza automáticamente todas[!DNL Adobe Experience Cloud]las audiencias compartidas por para crear los modelos de personalización.**

* No es necesario que haga nada para agregar audiencias al modelo. Para obtener información sobre el uso de [!DNL Experience Cloud Audiences] con [!DNL Target], consulte [Audiencias de Experience Cloud](../../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969).

**Los expertos en marketing pueden cargar datos sin conexión, puntuaciones de inclinación u otros datos personalizados para crear modelos de personalización.**

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización. Hay muchas maneras de introducir datos en los algoritmos de personalización de [!UICONTROL Personalización automatizada] (AP) y de [!UICONTROL Segmentación automática].

* [Parámetros de mbox](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [Parámetros de perfil](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [API del lado del servidor para actualizar perfiles](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)

Para obtener información sobre los datos que los algoritmos de [!UICONTROL Personalización automatizada] y de [!UICONTROL Segmentación automática] recopilan y utilizan automáticamente, consulte [Recopilación de datos de personalización automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Vídeo de formación: Tipos de actividades

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium]. [!UICONTROL La personalización automatizada se describe a partir del minuto 5:55.]

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
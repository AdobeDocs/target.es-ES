---
keywords: resolución de problemas;preguntas más frecuentes;FAQ;personalización automatizada;control;experiencia predeterminada;prácticas recomendadas
description: Explore una lista de preguntas más frecuentes (FAQ) y respuestas acerca de actividades de [!UICONTROL Automated Personalization] (AP) en [!UICONTROL Adobe Target].
title: ¿Cómo puedo encontrar preguntas frecuentes acerca de [!UICONTROL Automated Personalization] actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 20%

---

# Preguntas frecuentes sobre Automated Personalization

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con [!UICONTROL Automated Personalization] actividades en [!DNL Adobe Target].

## ¿Puedo especificar una experiencia específica para usarla como control en una actividad [!UICONTROL Automated Personalization]?

+++Ver detalles

Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## ¿Cómo puedo comparar [!UICONTROL Automated Personalization] con una experiencia predeterminada? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Ver detalles

No existe la opción llave en mano de comparar [!UICONTROL Automated Personalization] con una experiencia predeterminada. Sin embargo, como solución alternativa, si existe una oferta o experiencia predeterminada como parte de la actividad general, para comprender su rendimiento inicial, haga clic en el segmento &quot;[!UICONTROL Control]&quot; de los informes y busque esa oferta concreta en el informe a nivel de oferta resultante. La tasa de conversión registrada para esta oferta se puede utilizar para compararla con la tasa de conversión del segmento completo &quot;Bosque aleatorio&quot;. Esto ayuda a comparar cómo funciona la máquina en comparación la oferta predeterminada.

+++

## ¿Cuáles son las prácticas recomendadas para configurar una actividad [!UICONTROL Automated Personalization]? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Ver detalles

* Si desea personalizar una página con poco tráfico o realizar cambios estructurales en la experiencia que está personalizando, considere la posibilidad de utilizar una actividad [!UICONTROL Auto-Target] en lugar de [!UICONTROL Automated Personalization]. Consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Considere completar una actividad [!UICONTROL A/B Test] entre las ofertas y las ubicaciones que planea usar en su actividad [!UICONTROL Automated Personalization] para asegurarse de que la ubicación y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad [!UICONTROL A/B Test] no muestra una diferencia significativa, [!UICONTROL Automated Personalization] probablemente tampoco genere un alza.

   * Si una prueba A/B...N no muestra diferencias estadísticamente significativas entre experiencias, es probable que una o más de las siguientes situaciones sean responsables:

      * Es probable que las ofertas no sean lo suficientemente diferentes entre sí.
      * Las ubicaciones que ha seleccionado no afectan a la métrica de éxito.
      * El objetivo de optimización está demasiado lejos en el canal de conversión como para verse afectado por las ofertas seleccionadas.

* Asegúrese de usar el [Estimador de tráfico](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para que pueda tener una idea de cuánto tiempo tardan los modelos de personalización en desarrollar su actividad [!UICONTROL Automated Personalization].
* Decida la asignación entre el control y el objetivo antes de comenzar la actividad en función de sus objetivos.

  Hay tres situaciones que se deben tener en cuenta en función del objetivo de la actividad y el tipo de control seleccionado:

   * **Experiencias aleatorias como control y el objetivo de la actividad es probar la eficacia del algoritmo de personalización**: Si su objetivo es evaluar el algoritmo de personalización, desea tener una imagen más precisa del alza. Es probable que también quiera comparar la tasa de conversión de sus experiencias u ofertas si simplemente creó un [!UICONTROL A/B Test] (un control servido de forma aleatoria). En ese caso, se recomienda utilizar una asignación del 50% a un control de experiencias servidas aleatoriamente.
   * **&quot;Experiencias aleatorias&quot; como control y el objetivo de la actividad es maximizar el tráfico personalizado**: Si se siente cómodo con el algoritmo y desea tener la máxima cantidad de tráfico personalizado, se recomienda una asignación de 10% a 30% para el control. La compensación aquí es la precisión que ve en la información de crecimiento. Los intervalos de confianza del tráfico de control son más grandes porque hay menos tráfico fluido hacia ellos.
   * **Experiencia específica como control, con cualquier tipo de objetivo**: Si desea comparar una experiencia específica basada en especialistas en marketing en los modelos de personalización, se recomienda una asignación de 10% a 30% para el control. Al seleccionar solo una experiencia como control, ese tráfico no se propaga en todas las ofertas o experiencias de la actividad.

* Las reglas de orientación deben usarse con la menor cantidad posible porque pueden interferir con la capacidad del modelo para optimizar.
* Los grupos de informes pueden limitar el éxito de su actividad [!UICONTROL Automated Personalization]. Utilice los grupos de informes solo bajo condiciones específicas:

   * Use grupos de informes solo si se cumplen las siguientes condiciones:

      * Planea reemplazar o agregar nuevas ofertas mientras se ejecuta la actividad.
      * Las ofertas del grupo de informes atraen a los mismos visitantes.
      * Las ofertas de ese grupo de informes tienen aproximadamente la misma tasa de respuesta general.

   * No hay personalización entre ofertas en un grupo de informes. El modelo de personalización trata todas las ofertas como lo mismo.
   * No coloque todas las ofertas en una actividad en un solo grupo de informes. De este modo, todas las ofertas se atenderán de forma aleatoria y uniforme a todos los visitantes de la actividad.

+++

## ¿Cuáles son los límites de [!UICONTROL Automated Personalization]? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Ver detalles

[!DNL Target] tiene un límite estricto de 30 000 experiencias, pero funciona mejor cuando se crean menos de 10 000 experiencias.

Este mismo límite se aplica incluso cuando la actividad tiene habilitada la opción [!UICONTROL Disalow Duplicates].

Para obtener más información sobre los límites de caracteres y de otro tipo (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de [!DNL Target], vea [Límites](/help/main/r-troubleshooting-target/target-limits.md).

+++

## ¿Cómo se implementa la orientación a nivel de oferta?  {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Ver detalles

Cuando llega cada visitante, el conjunto de posibles ofertas que el visitante puede ver que está determinado por las reglas de orientación de nivel de oferta. A continuación, el algoritmo elige la oferta que el modelo predice que tiene los mejores ingresos esperados o posibilidades de conversión entre esas ofertas. La segmentación de ofertas afecta a la eficacia de [!DNL Target] algoritmos de aprendizaje automático y, como resultado, debe utilizarse con la mayor moderación posible.

+++

## ¿Por qué no se muestra el alza en mi actividad [!UICONTROL Automated Personalization]? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Ver detalles

Hay cuatro factores necesarios para que una actividad [!UICONTROL Automated Personalization] genere un alza:

* Las ofertas de cada ubicación deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ubicaciones deben estar en algún lugar que marque la diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y poder estadístico en la actividad para detectar el aumento.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una actividad [!UICONTROL A/B Test] simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de las pruebas A/B muestran un alza estadísticamente significativa en una o más experiencias, es probable que una actividad personalizada tenga éxito. Personalization puede funcionar incluso si no hay diferencias en las tasas de respuesta generales de las experiencias. Normalmente, el problema se debe a que las ofertas o ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

Para obtener más información, [Solucionar problemas de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## ¿Cómo está [!UICONTROL Automated Personalization] asignando el tráfico de mi actividad? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Ver detalles

[!UICONTROL Automated Personalization] dirige a los visitantes a la experiencia que tiene la mayor métrica de éxito prevista en función de los [modelos de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) creados más recientemente para cada modelo. Este pronóstico se basa en la información específica del visitante y el contexto de la visita.

Por ejemplo, supongamos que una actividad [!UICONTROL Automated Personalization] tiene dos ubicaciones con dos ofertas cada una. En la primera ubicación, la Oferta A tiene una tasa de conversión pronosticada del 3 % para un visitante específico y la Oferta B tiene una tasa de conversión pronosticada del 1 %. En la segunda ubicación, la Oferta C tiene una tasa de conversión pronosticada del 2 % para el mismo visitante y la Oferta D tiene una tasa de conversión pronosticada del 5 %. Por lo tanto, [!UICONTROL Automated Personalization] proporciona a este visitante una experiencia con la oferta A y la oferta D.

+++

## ¿Cuándo debería detener mi actividad [!UICONTROL Automated Personalization]? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Ver detalles

[!UICONTROL Automated Personalization] se puede usar como una personalización &quot;siempre activada&quot; que se optimiza constantemente. Especialmente para contenido permanente, no es necesario detener su actividad [!UICONTROL Automated Personalization]. Si desea realizar cambios sustanciales en el contenido que no sean similares a las ofertas que se encuentran actualmente en su actividad [!UICONTROL Automated Personalization], se recomienda iniciar una nueva actividad. El inicio de una nueva actividad ayuda a otros usuarios a revisar los informes a no confundir ni relacionar resultados pasados con contenido diferente.

+++

## ¿Cuánto tiempo debo esperar para que los modelos se creen? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Ver detalles

El tiempo que tardan los modelos en desarrollar su actividad depende típicamente del tráfico a las ubicaciones de la actividad seleccionada y la métrica de éxito de la actividad. Use [Estimador de tráfico](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para determinar la cantidad de tiempo esperada que los modelos tardan en desarrollar su actividad.

+++

## Se ha creado un modelo en mi actividad [!UICONTROL Automated Personalization]. ¿Las visitas a esa experiencia están personalizadas? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Ver detalles

No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

+++

## ¿Cuándo puedo ver los resultados de mi actividad [!UICONTROL Automated Personalization]? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Ver detalles

Puede comenzar a observar los resultados de su actividad [!UICONTROL Automated Personalization] después de que tenga al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tiene los modelos generados.

+++

## ¿Cómo puedo reducir el tiempo necesario para que los modelos se creen en mi actividad [!UICONTROL Automated Personalization]? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Ver detalles

Revise la configuración de la actividad y compruebe si hay algún cambio que esté dispuesto a realizar para mejorar la velocidad a la que se crean los modelos.

* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos.
* ¿Hay algunas experiencias que puede retirar de su actividad? Reducir el número de experiencias en una actividad acelera el tiempo para crear modelos.
* ¿Hay una página de mayor tráfico en la que esta actividad tendría más éxito? Cuantos más tráfico y conversiones haya en las ubicaciones de las actividades, más rápidos se crearán los modelos.

+++

## ¿Por qué los visitantes ven experiencias para una actividad de [!UICONTROL Automated Personalization] que no deberían ver? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Ver detalles

[!UICONTROL Automated Personalization] actividades se evalúan una vez por sesión. Si hay sesiones activas que se han clasificado para una experiencia en particular y ahora se le han agregado nuevas ofertas, los visitantes verán el nuevo contenido junto con las ofertas mostradas anteriormente. Debido a que estos visitantes se clasificaban anteriormente para esas experiencias, siguen viendo esas experiencias durante la sesión. Para evaluar esto en cada visita a la página, debe cambiar al tipo de actividad [!UICONTROL Experience Targeting] (XT).

+++

## ¿Puedo cambiar la métrica de objetivo a mitad de camino a través de una actividad [!UICONTROL Automated Personalization]? {#change-metric}

+++Ver detalles

[!DNL Adobe] no recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. [!DNL Adobe] no garantiza lo que suceda si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] que usan [!DNL Target] o [!DNL Analytics] (A4T) como origen de informes.

+++

## ¿Puedo usar la opción [!UICONTROL Reset Report Data] mientras ejecuto una actividad [!UICONTROL Automated Personalization]?

+++Ver detalles

[!DNL Adobe] no recomienda usar la opción [!UICONTROL Reset Report Data] para las actividades [!UICONTROL Automated Personalization]. Aunque quita los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo [!UICONTROL Automated Personalization]. En lugar de usar la opción [!UICONTROL Reset Report Data] para [!UICONTROL Automated Personalization] actividades, cree una nueva actividad y desactive la actividad original. Esta guía también se aplica a las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].

+++

## ¿Cómo genera modelos [!UICONTROL Automated Personalization] con respecto a los entornos?

+++Ver detalles

Un modelo se crea para identificar el rendimiento de la estrategia personalizada en comparación con el tráfico servido aleatoriamente en lugar de enviar todo el tráfico a la experiencia ganadora general. Este modelo considera las visitas y conversiones solo en el entorno predeterminado.

El tráfico de un segundo conjunto de modelos se genera para cada grupo de modelado ([!UICONTROL Automated Personalization]) o experiencia ([!UICONTROL Auto-Target]). Para cada uno de estos modelos, se tienen en cuenta las visitas y conversiones en todos los entornos.

Por lo tanto, las solicitudes se proporcionan con el mismo modelo, independientemente del entorno. Sin embargo, la pluralidad del tráfico debería proceder del entorno predeterminado para garantizar que la experiencia ganadora general identificada sea coherente con el comportamiento en el mundo real.

+++

---
description: Lista de preguntas más frecuentes sobre la Personalización automatizada (AP).
keywords: resolución de problemas;preguntas más frecuentes;FAQ;personalización automatizada
seo-description: Lista de preguntas más frecuentes sobre la Personalización automatizada (AP).
seo-title: Preguntas más frecuentes sobre Personalización automatizada
solution: Target
title: Preguntas más frecuentes sobre Personalización automatizada
title-outputclass: premium
topic: Premium
uuid: 4c8aadd3-75c3-4388-b838-e62576dfb955
badge: premium
translation-type: tm+mt
source-git-commit: 761771a48c0ae957d455974b1f04fa3a8350a8a0

---


# ![PREMIUM](/help/assets/premium.png) Preguntas más frecuentes sobre la Personalización automatizada{#automated-personalization-faq}

Lista de preguntas más frecuentes sobre la Personalización automatizada (AP).

## ¿Cómo puedo comparar la Personalización automatizada con una experiencia predeterminada?{#section_46C1A620A2384C2C8392D6716DD18495}

No existe una opción para comparar la AP con una experiencia predeterminada. Sin embargo, como alternativa, si existe una oferta o experiencia predeterminada como parte de la actividad general, para comprender su rendimiento inicial puede hacer clic en el segmento “Control” de los informes y colocar la oferta concreta en el informe a nivel de oferta resultante. Las tasas de conversión registradas para esta oferta pueden usarse para compararlas con las tasas de conversión del segmento “Bosque aleatorio” al completo. Esto ayuda a comparar cómo funciona la máquina en comparación la oferta predeterminada.

## ¿Qué es lo mejor para configurar una actividad de Personalización automatizada?   {#section_E155B26282BE49B58EA2683413D11DE6}

* Si está buscando personalizar una página de menor tráfico o si desea realizar cambios estructurales en la experiencia que está personalizando, considere usar la segmentación automática en lugar de la Personalización automatizada. Consulte [Segmentación automática para experiencias personalizadas](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).
* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su actividad de Personalización automatizada para garantizar que la ubicación y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no puede demostrar una diferencia significativa, la Personalización automatizada probablemente tampoco generará elevación.

   * Si una prueba A/B...N no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Asegúrate de usar el   [Estimador de tráfico](../../c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para que pueda tener una idea de cuánto tiempo tardará la creación de modelos de personalización en su actividad de Personalización automatizada.
* Decida la asignación entre el control y el objetivo antes de comenzar la actividad en función de sus objetivos.

   * ¿El objetivo de su actividad de personalización automatizada es determinar cómo funciona el algoritmo de personalización en general o ejecutar una optimización de personalización “siempre activada” en su página? Dependiendo de su respuesta a esta pregunta, querrá usar una asignación de tráfico diferente entre el control y el objetivo.
   * si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza.
   * Si su objetivo es crear una actividad “siempre activada”, ponga el del 10 % al 30 % de los visitantes en el control para asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. Tenga en cuenta que la compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tendrá menos precisión en la estimación del alza.

* Las reglas de orientación deben usarse con la menor cantidad posible porque pueden interferir con la capacidad del modelo para optimizar.
* Los grupos de informes pueden limitar el éxito de su actividad de personalización automatizada. Solo deben usarse bajo condiciones específicas.

   * Utilice grupos de informes solo si se cumplen las siguientes condiciones: (1) planea reemplazar/agregar nuevas ofertas mientras la actividad se está ejecutando, (2) las ofertas en el grupo de informes atraen a los mismos visitantes y (3) las ofertas en ese grupo de informes tienen aproximadamente la misma tasa de respuesta global.
   * No hay personalización entre ofertas en un grupo de informes: todas las ofertas son tratadas como iguales por el modelo de personalización.
   * No coloque todas las ofertas en una actividad en un solo grupo de informes. Esta decisión hará que todas las ofertas sean servidas al azar uniformemente a todos los visitantes de la actividad.

## ¿Cuáles son los límites de la Personalización automatizada?   {#section_08BA09ED51B547299963C94FE6417CFA}

Target tiene un límite estricto de 30 000 experiencias, pero funciona mejor cuando se crean menos de 10 000 experiencias.

## ¿Cómo se implementa la orientación a nivel de oferta?   {#section_9D7A86EA93D74E9B8C81072A681263A4}

Cuando llega cada visitante, el conjunto de posibles ofertas que el visitante puede ver que está determinado por las reglas de orientación de nivel de oferta. Luego, el algoritmo elige la oferta que el modelo predice que tendrá los mejores ingresos o posibilidades de conversión entre esas ofertas. Tenga en cuenta que la orientación de ofertas afecta a la eficacia de los algoritmos de aprendizaje automático de Target y, como resultado, debe utilizarse de la forma más moderada posible.

## Mi actividad no muestra ningún alza. {#section_BFA07C8C258F45318F73A461B8F32737}¿A qué se debe?

Hay varios factores necesarios para que una actividad de AP genere un alza:

* Las ofertas en cada ubicación deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ubicaciones deben estar en algún lugar que marque la diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y poder estadístico en la actividad para detectar el aumento.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema radica en que las ofertas/ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización para que se detecten con relevancia estadística.

Para obtener más información, [Resolución de problemas de personalización automatizada](../../c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

## ¿Cómo está la personalización automatizada asignando el tráfico de mi actividad?{#section_4369364F77804E0D9B78BEE551DA5659}

La personalización automatizada dirige a los visitantes a la experiencia que tiene la mayor métrica de éxito prevista en función de los modelos de [bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA) más recientes creados para cada modelo. Este pronóstico se basa en la información específica del visitante y el contexto de la visita.

Por ejemplo, supongamos que una actividad AP tiene dos ubicaciones con dos ofertas cada una. En la primera ubicación, la Oferta A tiene una tasa de conversión pronosticada del 3 % para un visitante específico y la Oferta B tiene una tasa de conversión pronosticada del 1 %. En la segunda ubicación, la Oferta C tiene una tasa de conversión pronosticada del 2 % para el mismo visitante y la Oferta D tiene una tasa de conversión pronosticada del 5 %. Por lo tanto, la Personalización Automatizada le brindaría a este visitante una experiencia con la Oferta A y la Oferta D.

## ¿Cuándo debería detener mi actividad de personalización automatizada?   {#section_C51F3DAB8887463BB147373F6FE06B93}

La personalización automatizada se puede utilizar como una personalización “siempre activada” que se optimizará constantemente. Especialmente para contenido permanente, no es necesario detener su actividad de personalización automatizada. Si desea realizar cambios sustanciales en el contenido que no son similares a las ofertas actuales en su actividad de Personalización automatizada, la mejor práctica es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

## ¿Cuánto tiempo debo esperar para que los modelos se creen?   {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

La cantidad de tiempo que tardan los modelos en desarrollar su actividad depende típicamente del tráfico a la/s ubicación/es de la actividad seleccionada y la métrica de éxito de la actividad. Use la [Estimador de tráfico](../../c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para determinar la duración esperada que los modelos necesitarán para desarrollar su actividad.

## Se ha creado un modelo dentro de mi actividad. {#section_51EA953C6D1D4A3185FC9DD290D66621}¿Las visitas a esa experiencia están personalizadas?

No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

## ¿Cuándo puedo ver los resultados de mi actividad de personalización automatizada?   {#section_05DB5ACAE6AD429C9510766A7268EE2C}

Puede comenzar a observar los resultados de su actividad de personalización automatizada una vez que tenga al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tienen los modelos generados.

## ¿Cómo puedo disminuir la cantidad de tiempo necesario para que los modelos se desarrollen en mi actividad?   {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

Revise la configuración de su actividad y vea si hay algún cambio que esté dispuesto a hacer para mejorar la velocidad a la que se construirán los modelos.

* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumentará los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos.
* ¿Hay algunas experiencias que puede retirar de su actividad? Disminuir el número de experiencias en una actividad acelerará la cantidad de tiempo para construir modelos.
* ¿Hay una página con mayor tráfico donde esta actividad sería más exitosa? Cuanto más tráfico y conversiones haya en sus ubicaciones de actividad, más rápido se crearán los modelos.

## ¿Por qué los visitantes ven experiencias para una actividad AP que no deberían ver?{#section_41CECEAE0881446A8D9F3B016857914B}

Las actividades de personalización automatizada se evalúan una vez por sesión. Si hubo sesiones activas que se han calificado para una experiencia en particular y ahora se han agregado nuevas ofertas, los usuarios verán el nuevo contenido junto con las ofertas que se mostraron anteriormente. Debido a que anteriormente se han calificado para esas experiencias, todavía las verían durante la sesión. Si desea evaluar esto en cada visita a una página, debe cambiar al tipo de actividad de segmentación de experiencias (XT).

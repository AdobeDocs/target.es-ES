---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas;tráfico
description: Explore los temas de solución de problemas y las preguntas más frecuentes sobre [!UICONTROL Segmentación automática] actividades.
title: ¿Cómo puedo solucionar problemas? [!UICONTROL Segmentación automática] ¿Actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1925'
ht-degree: 40%

---

# [!UICONTROL Segmentación automática] Preguntas frecuentes y solución de problemas

Resolución de problemas y preguntas más frecuentes (FAQ) acerca de [!UICONTROL Segmentación automática] actividades en [!DNL Adobe Target].

## [!UICONTROL Preguntas más frecuentes sobre la segmentación automática] {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con actividades de [!UICONTROL Segmentación automática]:

### ¿Cuáles son las prácticas recomendadas para configurar una actividad de [!UICONTROL segmentación automática]?

+++Respuesta
* Decida si el valor comercial de una actividad [!UICONTROL Ingresos por visita] (RPV) La métrica de éxito vale la pena por los requisitos de tráfico adicionales. Por lo general, RPV necesita al menos 1000 conversiones por experiencia para que una actividad funcione frente a la conversión.
* Decida la asignación entre el control y las experiencias personalizadas antes de comenzar la actividad en función de sus objetivos.
* Determine si tiene tráfico suficiente en la página donde su [!UICONTROL Segmentación automática] la actividad se ejecuta para que los modelos de personalización se creen en un período de tiempo razonable.
* Si está probando el algoritmo de personalización, no debe cambiar experiencias ni agregar ni eliminar atributos de perfil mientras la actividad está activa.
* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su [!UICONTROL Segmentación automática] actividad para garantizar que las ubicaciones y ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no demuestra una diferencia significativa, [!UICONTROL Segmentación automática] es probable que tampoco genere un alza.

  Si una prueba A/B no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Intente no realizar cambios sustanciales en las experiencias durante la actividad.

+++

### Does [!UICONTROL Adobe] que recomienda utilizar [!UICONTROL Segmentación automática] con una división 90 (Control)/10 (Segmentación) hasta que se crean los modelos?

+++Respuesta La división óptima de la asignación del tráfico depende de lo que desee lograr.

Si su objetivo es personalizar el mayor tráfico posible, puede mantener una asignación objetivo del 90 % y un control del 10 % durante toda la actividad. Si su objetivo es ejecutar un experimento comparando el rendimiento de los algoritmos personalizados con el control, entonces es mejor una división al 50/50 durante toda la actividad.

Una práctica recomendada es mantener la división de asignación de tráfico durante la duración de la actividad para que los visitantes no cambien entre las experiencias de segmentación y de control.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Si un visitante lo hace **no** consulte la [!UICONTROL Segmentación automática] actividad y convierte, ¿la conversión cuenta en mi actividad?

+++Responda No, solo los visitantes que cumplen los requisitos y ven el [!UICONTROL Segmentación automática] Las actividades de se cuentan en los informes.

+++

### ¿Por qué no mi [!UICONTROL Segmentación automática] la actividad de parece estar generando cualquier alza.

+++Respuesta Hay cuatro factores necesarios para una [!UICONTROL Segmentación automática] actividad para generar el alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio.

Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema se debe a que las ofertas y ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

### ¿Cuándo debería detener mi actividad de [!UICONTROL segmentación automática]?

+++Respuesta
[!UICONTROL Segmentación automática] se puede utilizar como una personalización &quot;siempre activada&quot; que se optimiza constantemente. Especialmente para contenido permanente, no es necesario detener su [!UICONTROL actividad de segmentación] automática.

Si desea realizar cambios sustanciales en el contenido de su [!UICONTROL Segmentación automática] Una actividad, la práctica recomendada es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

+++

### ¿Cuánto tiempo debo esperar para que los modelos se creen? {#how-long}

+++Respuesta El tiempo que tardan los modelos en desarrollar su [!UICONTROL Segmentación automática] la actividad suele depender del tráfico a las ubicaciones de la actividad seleccionada y las tasas de conversión asociadas con la métrica de éxito de la actividad.

[!UICONTROL Segmentación automática] no intenta crear un modelo personalizado para una experiencia determinada hasta que hay al menos 50 conversiones para esa experiencia. Además, si el modelo creado no es de calidad suficiente (tal y como determina la evaluación sin conexión de los datos de &quot;prueba&quot; de retención, utilizando [una métrica conocida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), el modelo no se utiliza para servir tráfico de forma personalizada.

Otros puntos que hay que tener en cuenta acerca de la creación de modelos de [!UICONTROL Segmentación automática]:

* Una vez publicada una actividad, [!UICONTROL Segmentación automática] considera hasta los últimos 45 días de datos servidos aleatoriamente al intentar crear modelos. Por ejemplo, el tráfico de control, además de algunos datos servidos aleatoriamente extra que mantiene el algoritmo.
* Cuando su métrica de éxito es [!UICONTROL Ingresos por visita], estas actividades generalmente requieren más datos para crear modelos debido a la mayor variación de datos que suele existir en los ingresos por visita en comparación con la tasa de conversión.
* Dado que los modelos se crean según la experiencia, sustituir una experiencia por otra significa que se debe recopilar tráfico suficiente (al menos 50 conversiones) para la nueva antes de poder reconstruir los modelos personalizados.

+++

### Se ha creado un modelo en mi actividad. ¿Las visitas a esa experiencia están personalizadas?

+++Respuesta No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

+++

### ¿Cuándo puedo empezar a ver los resultados de mi [!UICONTROL Segmentación automática] actividad?

+++Respuesta Puede empezar a ver los resultados de su [!UICONTROL Segmentación automática] pruebe después de tener al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tiene los modelos generados.

+++

### ¿Puedo especificar una experiencia específica para utilizarla como control?

+++Respuesta Puede seleccionar una experiencia para utilizarla como control mientras crea una [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) Actividad de (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### ¿Puedo cambiar la métrica de objetivo a mitad de camino a través de una [!UICONTROL Segmentación automática] actividad? {#change-metric}

+++El Adobe de respuestas no recomienda cambiar la métrica de objetivos a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. El Adobe no garantiza lo que sucede si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] que utilizan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

+++

### ¿Puedo usar el [!UICONTROL Restablecer datos del informe] al ejecutar una [!UICONTROL Segmentación automática] actividad?

+++Responder usando el [!UICONTROL Restablecer datos del informe] opción para [!UICONTROL Segmentación automática] no se sugiere ninguna actividad de. Aunque elimina los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo de [!UICONTROL Segmentación automática]. En lugar de utilizar la opción [!UICONTROL Restablecer los datos del informe] para las actividades de [!UICONTROL Segmentación automática], cree una nueva actividad y desactive la actividad original.

Esta guía también se aplica a [!UICONTROL Asignación automática] y [!UICONTROL Automated Personalization] actividades.

+++

### ¿Qué sucede si elimino una sola experiencia de una [!UICONTROL Segmentación automática] actividad?

+++Respuesta
[!DNL Target] crea un modelo por experiencia, por lo que eliminar una experiencia significa [!DNL Target] crea un modelo menos y no afecta a los modelos del resto de experiencias.

Por ejemplo, suponga que tiene una actividad de [!UICONTROL Segmentación automática] con ocho experiencias y que no le gusta el rendimiento de una experiencia. Puede eliminar esa experiencia y no afectará a los modelos de las siete experiencias restantes.

+++

## Solución de problemas de la [!UICONTROL segmentación automática] {#section_23995AB813F24525AF294D20A20875C8}

A veces, las actividades no salen como se esperaba. A continuación se indican algunos de los posibles desafíos a los que podría enfrentarse al utilizar [!UICONTROL Segmentación automática] y algunas soluciones sugeridas.

### Mi [!UICONTROL actividad de segmentación automática] está tardando demasiado en crear modelos.

+++Sugerencias para la resolución de problemas Existen varios cambios en la configuración de la actividad que pueden reducir el tiempo esperado para crear modelos, incluida la cantidad de experiencias en el [!UICONTROL Segmentación automática] actividad, el tráfico hacia el sitio y la métrica de éxito seleccionada.

**Solución:** Revise la configuración de la actividad y compruebe si hay algún cambio que esté dispuesto a realizar para mejorar la velocidad a la que se crean los modelos.

* Si la métrica de éxito se establece en [!UICONTROL RPV], ¿puede cambiar a la conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. No perderá datos de actividad si cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad menor aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas experiencias que puede retirar de su actividad? Reducir el número de experiencias en una actividad reduce el tiempo para crear modelos.
* ¿Hay una página con mayor tráfico en la que esta actividad sería más exitosa? Cuantos más tráfico y conversiones haya en las ubicaciones de las actividades, más rápidos se crearán los modelos.

+++

### Mi actividad de [!UICONTROL segmentación automática] no está generando ningún alza.

+++Sugerencias para la resolución de problemas Existen cuatro factores necesarios para una [!UICONTROL Segmentación automática] actividad para generar el alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** primero, asegúrese de que su actividad personalice el tráfico. Si los modelos no están diseñados para todas las experiencias, su actividad de [!UICONTROL segmentación automática] todavía estará sirviendo aleatoriamente una porción significativa de visitas para intentar construir todos los modelos lo más rápido posible. Si los modelos no están construidos, la [!UICONTROL segmentación automática] no está personalizando el tráfico.

A continuación, asegúrese de que las ofertas y las ubicaciones de la actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un alza estadísticamente significativa en una o más experiencias, es probable que funcione una actividad personalizada. La personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta generales de las experiencias. Normalmente, el problema se debe a que las ofertas y ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

### Las métricas que dependen de una métrica de conversión nunca se convierten.

+++Sugerencias para solucionar problemas: esto es lo que se espera.

En un [!UICONTROL Segmentación automática] actividad, una vez que se convierte la métrica de conversión (ya sea objetivo de optimización u objetivo de anuncio), el usuario se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 sigue sin convertirse porque cuando se convierte C1, el visitante se libera.

+++

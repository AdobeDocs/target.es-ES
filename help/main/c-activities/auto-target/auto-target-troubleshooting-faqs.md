---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas;tráfico
description: Explore los temas de solución de problemas y las preguntas más frecuentes acerca de [!UICONTROL Auto-Target] actividades.
title: ¿Cómo puedo solucionar problemas de [!UICONTROL Auto-Target] actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1850'
ht-degree: 32%

---

# Preguntas frecuentes y solución de problemas de [!UICONTROL Auto-Target]

Resolución de problemas y preguntas más frecuentes (FAQ) acerca de [!UICONTROL Auto-Target] actividades en [!DNL Adobe Target].

## [!UICONTROL Auto-Target] preguntas más frecuentes {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con [!UICONTROL Auto-Target] actividades:

### ¿Cuáles son las prácticas recomendadas para configurar una actividad [!UICONTROL Auto-Target]?

+++Respuesta
* Decida si el valor comercial de una métrica de éxito [!UICONTROL Revenue per Visit] (RPV) vale la pena por los requisitos de tráfico adicionales. Por lo general, RPV necesita al menos 1000 conversiones por experiencia para que una actividad funcione frente a la conversión.
* Decida la asignación entre el control y las experiencias personalizadas antes de comenzar la actividad en función de sus objetivos.
* Determine si tiene tráfico suficiente en la página donde se ejecuta la actividad [!UICONTROL Auto-Target] para que los modelos de personalización se creen en un período de tiempo razonable.
* Si está probando el algoritmo de personalización, no debe cambiar experiencias ni agregar ni eliminar atributos de perfil mientras la actividad está activa.
* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su actividad [!UICONTROL Auto-Target] para asegurarse de que las ubicaciones y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no demuestra una diferencia significativa, [!UICONTROL Auto-Target] probablemente tampoco genere un alza.

  Si una prueba A/B no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Intente no realizar cambios sustanciales en las experiencias durante la actividad.

+++

### ¿Se recomienda [!UICONTROL Adobe] usar [!UICONTROL Auto Target] con una división 90 (Control)/10 (Segmentación) hasta que se creen los modelos?

+++Respuesta 
La división óptima de la asignación del tráfico depende de lo que desee lograr.

Si su objetivo es personalizar el mayor tráfico posible, puede mantener una asignación objetivo del 90 % y un control del 10 % durante toda la actividad. Si su objetivo es ejecutar un experimento comparando el rendimiento de los algoritmos personalizados con el control, entonces es mejor una división al 50/50 durante toda la actividad.

Una práctica recomendada es mantener la división de asignación de tráfico durante la duración de la actividad para que los visitantes no cambien entre las experiencias de segmentación y de control.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Si un visitante **no** ve la actividad [!UICONTROL Auto-Target] y se convierte, ¿la conversión cuenta en mi actividad?

+++Respuesta
No, solo los visitantes que califiquen y vean la actividad [!UICONTROL Auto-Target] se contarán en los informes.

+++

### ¿Por qué mi actividad [!UICONTROL Auto-Target] no parece estar generando ningún alza?

+++Respuesta
Hay cuatro factores necesarios para que una actividad [!UICONTROL Auto-Target] genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio.

Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema se debe a que las ofertas y ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

### ¿Cuándo debería detener mi actividad [!UICONTROL Auto-Target]?

+++Respuesta
[!UICONTROL Auto-Target] se puede usar como una personalización &quot;siempre activada&quot; que se optimiza constantemente. Especialmente para contenido permanente, no es necesario detener su actividad [!UICONTROL Auto-Target].

Si desea realizar cambios sustanciales en el contenido en su actividad [!UICONTROL Auto-Target], la práctica recomendada es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

+++

### ¿Cuánto tiempo debo esperar para que los modelos se creen? {#how-long}

+++Respuesta
El tiempo que tardan los modelos en desarrollar su actividad [!UICONTROL Auto-Target] depende típicamente del tráfico a las ubicaciones de la actividad seleccionada y las tasas de conversión asociadas con la métrica de éxito de la actividad.

[!UICONTROL Auto-Target] no intenta crear un modelo personalizado para una experiencia determinada hasta que existen al menos 50 conversiones para esa experiencia. Además, si el modelo creado no es de calidad suficiente (tal y como determina la evaluación sin conexión de los datos de &quot;prueba&quot; de retención, con [una métrica conocida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), no se utilizará para servir tráfico de forma personalizada.

Otros puntos que se deben tener en cuenta acerca de la creación de modelos de [!UICONTROL Auto-Target]:

* Después de que una actividad esté activa, [!UICONTROL Auto-Target] considera hasta los últimos 45 días de datos servidos aleatoriamente al intentar crear modelos. Por ejemplo, el tráfico de control, además de algunos datos servidos aleatoriamente extra que mantiene el algoritmo.
* Si [!UICONTROL Revenue per Visit] es su métrica de éxito, estas actividades generalmente requieren más datos para crear modelos debido a la mayor variación de datos que suele existir en los ingresos por visita en comparación con la tasa de conversión.
* Dado que los modelos se crean según la experiencia, sustituir una experiencia por otra significa que se debe recopilar tráfico suficiente (al menos 50 conversiones) para la nueva antes de poder reconstruir los modelos personalizados.

+++

### Se ha creado un modelo en mi actividad. ¿Las visitas a esa experiencia están personalizadas?

+++Respuesta
No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

+++

### ¿Cuándo puedo empezar a ver los resultados de mi actividad [!UICONTROL Auto-Target]?

+++Respuesta
Puede comenzar a observar los resultados de su prueba [!UICONTROL Auto-Target] después de que tenga al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tiene los modelos generados.

+++

### ¿Puedo especificar una experiencia específica para utilizarla como control?

+++Respuesta
Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### ¿Puedo cambiar la métrica de objetivo a mitad de camino a través de una actividad [!UICONTROL Auto-Target]? {#change-metric}

+++Respuesta
Adobe no recomienda cambiar la métrica de objetivos a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. Adobe no garantiza lo que sucede si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] que usan [!DNL Target] o [!DNL Analytics] (A4T) como origen de informes.

+++

### ¿Puedo usar la opción [!UICONTROL Reset Report Data] mientras ejecuto una actividad [!UICONTROL Auto-Target]?

+++Respuesta
No se recomienda usar la opción [!UICONTROL Reset Report Data] para las actividades [!UICONTROL Auto-Target]. Aunque quita los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo [!UICONTROL Auto-Target]. En lugar de usar la opción [!UICONTROL Reset Report Data] para [!UICONTROL Auto-Target] actividades, cree una nueva actividad y desactive la actividad original.

Esta guía también se aplica a las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Automated Personalization].

+++

### ¿Qué sucede si elimino una sola experiencia de una actividad [!UICONTROL Auto-Target]?

+++Respuesta
[!DNL Target] crea un modelo por experiencia, por lo que al eliminar una experiencia, [!DNL Target] crea un modelo menos y no afecta a los modelos del resto de experiencias.

Por ejemplo, suponga que tiene una actividad [!UICONTROL Auto-Target] con ocho experiencias y que no le gusta el rendimiento de una experiencia. Puede eliminar esa experiencia y no afectará a los modelos de las siete experiencias restantes.

+++

## Resolución de problemas [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

A veces, las actividades no salen como se esperaba. Estos son algunos de los desafíos potenciales que podría enfrentar al usar [!UICONTROL Auto-Target] y algunas soluciones sugeridas.

### Mi actividad [!UICONTROL Auto-Target] está tardando demasiado en crear modelos.

+++Sugerencias de resolución de problemas
Hay varios cambios en la configuración de la actividad que pueden disminuir el tiempo esperado para crear modelos, incluida la cantidad de experiencias en su actividad [!UICONTROL Auto-Target], el tráfico hacia su sitio y la métrica de éxito seleccionada.

**Solución:** revise la configuración de la actividad y vea si hay algún cambio que desee realizar para mejorar la velocidad a la que se crean los modelos.

* Si la métrica de éxito está establecida en [!UICONTROL RPV], ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. No perderá datos de actividad si cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad menor aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas experiencias que puede retirar de su actividad? Reducir el número de experiencias en una actividad reduce el tiempo para crear modelos.
* ¿Hay una página con mayor tráfico en la que esta actividad sería más exitosa? Cuantos más tráfico y conversiones haya en las ubicaciones de las actividades, más rápidos se crearán los modelos.

+++

### Mi actividad [!UICONTROL Auto-Target] no está generando ningún alza.

+++Sugerencias de resolución de problemas
Hay cuatro factores necesarios para que una actividad [!UICONTROL Auto-Target] genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** primero, asegúrese de que su actividad personalice el tráfico. Si los modelos no están diseñados para todas las experiencias, su actividad [!UICONTROL Auto-Target] todavía estará sirviendo aleatoriamente una porción significativa de visitas para intentar construir todos los modelos lo más rápido posible. Si los modelos no están generados, [!UICONTROL Auto-Target] no está personalizando el tráfico.

A continuación, asegúrese de que las ofertas y las ubicaciones de la actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un alza estadísticamente significativa en una o más experiencias, es probable que funcione una actividad personalizada. Personalization puede funcionar incluso si no hay diferencias en las tasas de respuesta generales de las experiencias. Normalmente, el problema se debe a que las ofertas y ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

### Las métricas que dependen de una métrica de conversión nunca se convierten.

+++Sugerencias de resolución de problemas
Esto es esperable.

En una actividad de [!UICONTROL Auto-Target], una vez convertida la métrica de conversión (ya sea por objetivos de optimización o de anuncio), el usuario se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 sigue sin convertirse porque cuando se convierte C1, el visitante se libera.

+++

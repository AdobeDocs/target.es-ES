---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas;tráfico
description: Explore los temas de solución de problemas y las preguntas más frecuentes acerca de las actividades de segmentación automática en Adobe Target.
title: ¿Cómo puedo solucionar problemas de las actividades de segmentación automática?
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1919'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Resolución de problemas de segmentación automática y preguntas frecuentes

Resolución de problemas y preguntas más frecuentes (FAQ) acerca de la [!UICONTROL Segmentación automática] en [!DNL Adobe Target].

## Preguntas más frecuentes sobre la segmentación automática {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con actividades de [!UICONTROL Segmentación automática]:

### ¿Cuáles son las prácticas recomendadas para configurar una actividad de [!UICONTROL segmentación automática]?

* Decida si el valor comercial de una métrica de éxito de Ingresos por visita (RPV) merece los requisitos de tráfico adicionales. Por lo general, RPV necesita al menos 1000 conversiones por experiencia para que una actividad funcione frente a la conversión.
* Decida la asignación entre el control y las experiencias personalizadas antes de comenzar la actividad en función de sus objetivos.
* Determine si tiene tráfico suficiente en la página donde se ejecutará su actividad de [!UICONTROL segmentación automática] para que los modelos de personalización se creen en un periodo de tiempo razonable.
   * Si está probando el algoritmo de personalización, no debe cambiar experiencias o agregar/eliminar atributos de perfil mientras la actividad está activa.

* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su actividad de [!UICONTROL segmentación automática] para garantizar que la ubicación y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no demuestra una diferencia significativa, la [!UICONTROL segmentación automática] tampoco generará un alza.

   * Si una prueba A/B no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Trate de no hacer cambios sustanciales en las experiencias durante el curso de la actividad.

### ¿Se recomienda utilizar la [!UICONTROL segmentación automática] con una división 90 (Control)/10 (Segmentación) hasta que se creen los modelos?

La división óptima de la asignación del tráfico depende de lo que desee lograr.

Si su objetivo es personalizar el mayor tráfico posible, puede mantener un control del 90 % y del 10 % durante toda la actividad. Si su objetivo es ejecutar un experimento comparando el rendimiento de los algoritmos personalizados con el control, entonces es mejor una división al 50/50 durante toda la actividad.

Una práctica recomendada es mantener la división de asignación de tráfico durante la duración de la actividad para que los visitantes no cambien entre las experiencias de segmentación y de control.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

### Si un visitante NO ve la actividad de la [!UICONTROL segmentación automática] y cambia, ¿la conversión cuenta en mi actividad?

No, solo los visitantes que califiquen y vean la actividad de [!UICONTROL segmentación automática] se cuentan en los informes.

### Mi actividad de [!UICONTROL segmentación automática] parece que no está generando ningún alza. ¿A qué se debe?

Hay varios factores necesarios para que una actividad de [!UICONTROL segmentación automática] genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben ubicarse en algún lugar que marque una diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio.

Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema radica en que las ofertas/ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización para que se detecten con relevancia estadística.

### ¿Cuándo debería detener mi actividad de [!UICONTROL segmentación automática]?

[!UICONTROL La segmentación automática] se puede utilizar como una personalización “siempre activada” que se optimizará constantemente. Especialmente para contenido permanente, no es necesario detener su [!UICONTROL actividad de segmentación] automática.

Si desea realizar cambios sustanciales en el contenido en su actividad de [!UICONTROL segmentación automática], la práctica recomendada es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

### ¿Cuánto tiempo debo esperar para que los modelos se creen? {#how-long}

La cantidad de tiempo que tardan los modelos en desarrollar su actividad de [!UICONTROL segmentación automática] depende típicamente del tráfico a las ubicaciones de la actividad seleccionada y la métrica de éxito de la actividad.

[!UICONTROL La segmentación automática] no intentará crear un modelo personalizado para una experiencia determinada hasta que haya al menos 50 conversiones para esa experiencia. Además, si el modelo creado no es de calidad suficiente (tal y como determina la evaluación sin conexión de los datos de “prueba” de retención, con [una métrica conocida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), no se utilizará para servir tráfico de forma personalizada.

Otros puntos que hay que tener en cuenta acerca de la creación de modelos de [!UICONTROL Segmentación automática]:

* Una vez que una actividad está activa, la [!UICONTROL Segmentación automática] considera hasta los últimos 45 días de datos suministrados aleatoriamente al intentar crear modelos (es decir, tráfico de control, además de algunos datos servidos aleatoriamente extra que nuestro algoritmo mantiene).
* Cuando su métrica de éxito es [!UICONTROL Ingresos por visita], estas actividades generalmente requieren más datos para crear modelos debido a la mayor variación de datos que suele existir en los ingresos por visita en comparación con la tasa de conversión.
* Dado que los modelos se crean según la experiencia, sustituir una experiencia por otra significa que se debe recopilar tráfico suficiente (es decir, al menos 50 conversiones) para la nueva antes de poder volver a crear los modelos personalizados.

### Se ha creado un modelo en mi actividad. ¿Las visitas a esa experiencia están personalizadas?

No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

### ¿Cuándo puedo empezar a ver los resultados de mi actividad de la [!UICONTROL segmentación automática]?

Puede comenzar a observar los resultados de su actividad de [!UICONTROL segmentación automática] después de que tenga al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tienen los modelos generados.

### ¿Puedo especificar una experiencia específica para utilizarla como control?

Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

### ¿Puedo cambiar la métrica de objetivo a mitad de camino a través de una actividad de segmentación automática?  {#change-metric}

No se recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. No garantizamos lo que pueda suceder si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] que utilizan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

### ¿Puedo usar la opción Restablecer los datos del informe al ejecutar una actividad de segmentación automática?

No se recomienda utilizar la opción [!UICONTROL Restablecer los datos del informe] para las actividades de [!UICONTROL Segmentación automática]. Aunque elimina los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo de [!UICONTROL Segmentación automática]. En lugar de utilizar la opción [!UICONTROL Restablecer los datos del informe] para las actividades de [!UICONTROL Segmentación automática], cree una nueva actividad y desactive la actividad original. (Nota: Esta guía también se aplica a las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Automated Personalization]).

### ¿Qué sucede si elimino una sola experiencia de una actividad de segmentación automática?

[!DNL Target] crea un modelo por experiencia, por lo que al eliminar una experiencia [!DNL Target] generará un modelo menos y no afectará a los modelos del resto de experiencias.

Por ejemplo, suponga que tiene una actividad de [!UICONTROL Segmentación automática] con ocho experiencias y que no le gusta el rendimiento de una experiencia. Puede eliminar esa experiencia y no afectará a los modelos de las siete experiencias restantes.

## Solución de problemas de la [!UICONTROL segmentación automática] {#section_23995AB813F24525AF294D20A20875C8}

A veces, las actividades no salen como se esperaba. A continuación, le presentamos algunos de los posibles desafíos a los que se puede enfrentar al usar la [!UICONTROL segmentación automática] y algunas soluciones sugeridas.

### Mi [!UICONTROL actividad de segmentación automática] está tardando demasiado en crear modelos.

Hay varios cambios en la configuración de la actividad que pueden disminuir el tiempo esperado para crear modelos, incluida la cantidad de experiencias en su actividad de [!UICONTROL segmentación automática], el tráfico hacia su sitio y la métrica de éxito seleccionada.

**Solución:** revise la configuración de su actividad y vea si hay algún cambio que esté dispuesto a hacer para mejorar la velocidad a la que se crean los modelos.

* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. No perderá datos de actividad si cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumentará los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas experiencias que puede retirar de su actividad? Disminuir el número de experiencias en una actividad reducirá la cantidad de tiempo para construir modelos.
* ¿Hay una página con mayor tráfico en la que esta actividad sería más exitosa? Cuanto más tráfico y conversiones haya en sus ubicaciones de actividad, más rápido se crearán los modelos.

### Mi actividad de [!UICONTROL segmentación automática] no está generando ningún alza.

Hay varios factores necesarios para que una actividad de AP genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben ubicarse en algún lugar que marque una diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** primero, asegúrese de que su actividad personalice el tráfico. Si los modelos no están diseñados para todas las experiencias, su actividad de [!UICONTROL segmentación automática] todavía estará sirviendo aleatoriamente una porción significativa de visitas para intentar construir todos los modelos lo más rápido posible. Si los modelos no están construidos, la [!UICONTROL segmentación automática] no está personalizando el tráfico.

A continuación, asegúrese de que las ofertas y los lugares de actividad marquen realmente la diferencia en las tasas de respuesta generales mediante una prueba A/B simple, no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema radica en que las ofertas/ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización para que se detecten con relevancia estadística.

### Las métricas que dependen de la métrica de conversión nunca se convierten.

Esto es esperable.

En una actividad de [!UICONTROL Segmentación automática], una vez convertida la métrica de conversión (ya sea por objetivos de optimización o de anuncio), el usuario se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 aún no se convierte porque en cuanto se convierte C1, se libera el visitante.

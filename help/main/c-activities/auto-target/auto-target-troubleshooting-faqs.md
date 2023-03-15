---
keywords: segmentación automática;segmentación;asignación de tráfico;preguntas más frecuentes;faq;solución de problemas;solucionar problemas;tráfico
description: Explore los temas de solución de problemas y las preguntas más frecuentes acerca de las actividades de segmentación automática en Adobe Target.
title: ¿Cómo puedo solucionar problemas de las actividades de segmentación automática?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1920'
ht-degree: 58%

---

# Segmentación automática Preguntas frecuentes y solución de problemas

Resolución de problemas y preguntas más frecuentes (FAQ) sobre [!UICONTROL Segmentación automática] actividades en [!DNL Adobe Target].

## [!UICONTROL Preguntas más frecuentes sobre la segmentación automática] {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con actividades de [!UICONTROL Segmentación automática]:

### ¿Cuáles son las prácticas recomendadas para configurar una actividad de [!UICONTROL segmentación automática]?

+++Respuesta
* Decida si el valor comercial de un [!UICONTROL Ingresos por visita] La métrica de éxito (RPV) vale los requisitos de tráfico adicionales. Por lo general, RPV necesita al menos 1000 conversiones por experiencia para que una actividad funcione frente a la conversión.
* Decida la asignación entre el control y las experiencias personalizadas antes de comenzar la actividad en función de sus objetivos.
* Determine si tiene tráfico suficiente en la página donde se ejecutará su actividad de [!UICONTROL segmentación automática] para que los modelos de personalización se creen en un periodo de tiempo razonable.
   * Si está probando el algoritmo de personalización, no debe cambiar experiencias o agregar o eliminar atributos de perfil mientras la actividad está activa.

* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su [!UICONTROL Segmentación automática] para garantizar que las ubicaciones y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no demuestra una diferencia significativa, la [!UICONTROL segmentación automática] tampoco generará un alza.

   * Si una prueba A/B no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Trate de no hacer cambios sustanciales en las experiencias durante el curso de la actividad.

+++

### ¿Recomienda el Adobe utilizar [!UICONTROL Segmentación automática] con una división 90(Control)/10 (Segmentado) hasta que se construyan los modelos?

+++Respuesta La división óptima de la asignación del tráfico depende de lo que desee lograr.

Si su objetivo es personalizar el mayor tráfico posible, puede mantener una asignación objetivo del 90 % y un 10 % de control durante toda la actividad. Si su objetivo es ejecutar un experimento comparando el rendimiento de los algoritmos personalizados con el control, entonces es mejor una división al 50/50 durante toda la actividad.

Una práctica recomendada es mantener la división de asignación de tráfico durante la duración de la actividad para que los visitantes no cambien entre las experiencias de segmentación y de control.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Si un visitante lo hace **not** consulte la [!UICONTROL Segmentación automática] actividad y se convierte, ¿la conversión cuenta en mi actividad?

+++Respuesta No, solo los visitantes que califican para y ven la variable [!UICONTROL Segmentación automática] la actividad se cuenta en los informes.

+++

### ¿Por qué no es mi [!UICONTROL Segmentación automática] parece que está generando cualquier alza.

+++Respuesta Hay cuatro factores necesarios para una [!UICONTROL Segmentación automática] actividad para generar alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben ubicarse en algún lugar que marque una diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio.

Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema radica en que las ofertas/ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización para que se detecten con relevancia estadística.

+++

### ¿Cuándo debería detener mi actividad de [!UICONTROL segmentación automática]?

+++Respuesta
[!UICONTROL Segmentación automática] se puede utilizar como una personalización &quot;siempre activada&quot; que se optimizará constantemente. Especialmente para contenido permanente, no es necesario detener su [!UICONTROL actividad de segmentación] automática.

Si desea realizar cambios sustanciales en el contenido de su [!UICONTROL Segmentación automática] , la práctica recomendada es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

+++

### ¿Cuánto tiempo debo esperar para que los modelos se creen? {#how-long}

+++Respuesta El tiempo que tardan los modelos en crear en su [!UICONTROL Segmentación automática] la actividad suele depender del tráfico a las ubicaciones de la actividad seleccionada y las tasas de conversión asociadas con la métrica de éxito de la actividad.

[!UICONTROL Segmentación automática] no intenta crear un modelo personalizado para una experiencia determinada hasta que haya al menos 50 conversiones para esa experiencia. Además, si el modelo creado no es de calidad suficiente (tal como se determina mediante la evaluación sin conexión de los datos de &quot;prueba&quot; de retención, utilizando [una métrica conocida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), el modelo no se utiliza para servir tráfico de forma personalizada.

Otros puntos que hay que tener en cuenta acerca de la creación de modelos de [!UICONTROL Segmentación automática]:

* Después de que una actividad esté activa, [!UICONTROL Segmentación automática] considera hasta los últimos 45 días de datos suministrados aleatoriamente al intentar crear modelos (por ejemplo, tráfico de control, además de algunos datos suministrados aleatoriamente adicionales mantenidos por el algoritmo).
* Cuando su métrica de éxito es [!UICONTROL Ingresos por visita], estas actividades generalmente requieren más datos para crear modelos debido a la mayor variación de datos que suele existir en los ingresos por visita en comparación con la tasa de conversión.
* Como los modelos se crean según la experiencia, reemplazar una experiencia por otra significa que se debe recopilar tráfico suficiente (al menos 50 conversiones) para la nueva experiencia antes de poder volver a crear los modelos personalizados.

+++

### Se ha creado un modelo en mi actividad. ¿Las visitas a esa experiencia están personalizadas?

+++Respuesta No, debe haber al menos dos modelos integrados en la actividad para que comience la personalización.

+++

### ¿Cuándo puedo empezar a ver los resultados de mi [!UICONTROL Segmentación automática] actividad?

+++Respuesta Puede empezar a ver los resultados de su [!UICONTROL Segmentación automática] realice una prueba después de tener al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tienen los modelos creados.

+++

### ¿Puedo especificar una experiencia específica para utilizarla como control?

+++Respuesta Puede seleccionar una experiencia para utilizarla como control mientras crea una [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### ¿Puedo cambiar la métrica de objetivos a mitad de camino a través de un [!UICONTROL Segmentación automática] actividad? {#change-metric}

El Adobe +++Respuesta no recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. No garantizamos lo que pueda suceder si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] que utilizan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

+++

### ¿Puedo usar la variable [!UICONTROL Restablecer los datos del informe] mientras se ejecuta una [!UICONTROL Segmentación automática] actividad?

+++Respuesta Usando la variable [!UICONTROL Restablecer los datos del informe] para [!UICONTROL Segmentación automática] actividades no sugeridas. Aunque elimina los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo de [!UICONTROL Segmentación automática]. En lugar de utilizar la opción [!UICONTROL Restablecer los datos del informe] para las actividades de [!UICONTROL Segmentación automática], cree una nueva actividad y desactive la actividad original.

Esta guía también se aplica a: [!UICONTROL Asignación automática] y [!UICONTROL Automated Personalization] actividades.

+++

### Qué sucede si elimino una sola experiencia de una [!UICONTROL Segmentación automática] actividad?

+++Respuesta
[!DNL Target] crea un modelo por experiencia, por lo que eliminar una experiencia significa [!DNL Target] crea un modelo menos y no afecta a los modelos para las demás experiencias.

Por ejemplo, suponga que tiene una actividad de [!UICONTROL Segmentación automática] con ocho experiencias y que no le gusta el rendimiento de una experiencia. Puede eliminar esa experiencia y no afecta a los modelos de las siete experiencias restantes.

+++

## Solución de problemas de la [!UICONTROL segmentación automática] {#section_23995AB813F24525AF294D20A20875C8}

A veces, las actividades no salen como se esperaba. Estos son algunos de los posibles desafíos que podría enfrentar al usar [!UICONTROL Segmentación automática] y algunas soluciones sugeridas.

### Mi [!UICONTROL actividad de segmentación automática] está tardando demasiado en crear modelos.

+++Sugerencias de solución de problemas Existen varios cambios en la configuración de la actividad que pueden disminuir el tiempo esperado para crear modelos, incluido el número de experiencias en la [!UICONTROL Segmentación automática] actividad, el tráfico al sitio y la métrica de éxito seleccionada.

**Solución:** revise la configuración de su actividad y vea si hay algún cambio que esté dispuesto a hacer para mejorar la velocidad a la que se crean los modelos.

* Si la métrica de éxito está configurada en [!UICONTROL RPV], ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. No perderá datos de actividad si cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas experiencias que puede retirar de su actividad? Reducir el número de experiencias en una actividad reduce el tiempo para crear modelos.
* ¿Hay una página con mayor tráfico en la que esta actividad sería más exitosa? Cuanto más tráfico y conversiones haya en sus ubicaciones de actividad, más rápido se crearán los modelos.

+++

### Mi actividad de [!UICONTROL segmentación automática] no está generando ningún alza.

+++Sugerencias de solución de problemas Existen cuatro factores necesarios para que una actividad AT genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben estar ubicadas en algún lugar que marque una diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** primero, asegúrese de que su actividad personalice el tráfico. Si los modelos no están diseñados para todas las experiencias, su actividad de [!UICONTROL segmentación automática] todavía estará sirviendo aleatoriamente una porción significativa de visitas para intentar construir todos los modelos lo más rápido posible. Si los modelos no están construidos, la [!UICONTROL segmentación automática] no está personalizando el tráfico.

A continuación, asegúrese de que las ofertas y los lugares de actividad marquen realmente la diferencia en las tasas de respuesta generales mediante una prueba A/B simple, no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema se debe a que las ofertas y las ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para que se detecten con relevancia estadística.

+++

### Las métricas que dependen de una métrica de conversión nunca se convierten.

+++Sugerencias de solución de problemas Esto es esperado.

En una actividad de [!UICONTROL Segmentación automática], una vez convertida la métrica de conversión (ya sea por objetivos de optimización o de anuncio), el usuario se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 aún no se convierte porque en cuanto se convierte C1, se libera el visitante.

+++

---
keywords: destinatario automático;segmentación;asignación de tráfico;preguntas más frecuentes;preguntas más frecuentes;preguntas más frecuentes;solución de problemas;resolución de problemas;tráfico
description: Resolución de problemas y preguntas más frecuentes sobre el Destinatario automático en Adobe Target.
title: Solución de problemas de Destinatario automático y preguntas más frecuentes
feature: Auto-Target
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 68%

---


# ![](/help/assets/premium.png) PREMIUMAuto-Destinatario solución de problemas y preguntas más frecuentes

Resolución de problemas y preguntas más frecuentes (FAQ) sobre [!UICONTROL Destinatario automático] en [!DNL Adobe Target].

## Preguntas más frecuentes sobre la segmentación automática {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte las siguientes preguntas más frecuentes y respuestas mientras trabaja con actividades [!UICONTROL Destinatario automático]:

### ¿Cuáles son las prácticas recomendadas para configurar una actividad de [!UICONTROL segmentación automática]?

* Decida si el valor comercial de una métrica de éxito de Ingresos por visita (RPV) merece los requisitos de tráfico adicionales. Por lo general, RPV necesita al menos 1000 conversiones por experiencia para que una actividad funcione frente a la conversión.
* Decida la asignación entre el control y las experiencias personalizadas antes de comenzar la actividad en función de sus objetivos.
* Determine si tiene tráfico suficiente en la página donde se ejecutará su actividad de [!UICONTROL segmentación automática] para que los modelos de personalización se creen en un periodo de tiempo razonable.
   * Si está probando el algoritmo de personalización, no debe cambiar experiencias o agregar/eliminar atributos de perfil mientras la actividad está activa.

* Considere completar una actividad A/B entre las ofertas y las ubicaciones que planea utilizar en su actividad de [!UICONTROL segmentación automática] para garantizar que la ubicación y las ofertas tengan un impacto en el objetivo de optimización. Si una actividad A/B no demuestra una diferencia significativa, la [!UICONTROL segmentación automática] tampoco generará un alza.

   * Si una prueba A/B no muestra diferencias estadísticamente significativas entre las experiencias, es probable que las ofertas que está considerando no sean suficientemente diferentes entre sí, las ubicaciones que seleccionó no influyen en la métrica de éxito o el objetivo de optimización está demasiado lejos en el embudo de conversión como para verse afectado por las ofertas elegidas.

* Trate de no hacer cambios sustanciales en las experiencias durante el curso de la actividad.

### ¿Recomendamos que usemos el Destinatario automático con una división 90 (Control)/10 (Segmentación) hasta que se creen los modelos?

La división óptima de la asignación de tráfico depende de lo que desee lograr.

Si su objetivo es personalizar el mayor tráfico posible, puede mantener un control del 90 % y del 10 % durante la duración de la actividad. Si su objetivo es ejecutar un experimento comparando el rendimiento de los algoritmos personalizados con el control, entonces una división 50/50 es mejor para la duración de la actividad.

Lo mejor es mantener la división de asignación de tráfico durante la duración de la actividad para que los visitantes no cambien entre las experiencias de destino y de control.

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

Si desea realizar cambios sustanciales en el contenido en su actividad de [!UICONTROL segmentación automática], la mejor práctica es comenzar una nueva actividad para que otros usuarios que revisen los informes no confundan ni relacionen resultados pasados con contenido diferente.

### ¿Cuánto tiempo debo esperar para que los modelos se creen?   {#how-long}

El tiempo que tardan los modelos en generar su actividad [!UICONTROL Destinatario automático] generalmente depende del tráfico de las ubicaciones de actividad seleccionadas y de las tasas de conversión asociadas con la métrica de éxito de actividad.

[!UICONTROL La segmentación automática no ] intentará crear un modelo personalizado para una experiencia determinada hasta que haya al menos 50 conversiones para esa experiencia. Además, si el modelo creado tiene una calidad insuficiente (como lo determina la evaluación sin conexión de los datos de &quot;prueba&quot; de retención, utilizando [una métrica conocida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), el modelo no se utilizará para servir el tráfico de manera personalizada.

Otros puntos que hay que tener en cuenta sobre la creación de modelos de [!UICONTROL Destinatario automático]:

* Una vez que una actividad está activa, [!UICONTROL Destinatario automático] considera hasta los últimos 45 días de datos suministrados al azar al intentar crear modelos (es decir, controlar el tráfico, además de algunos datos suministrados al azar por nuestro algoritmo).
* Cuando [!UICONTROL Ingresos por visita] es la métrica de éxito, estas actividades generalmente requieren más datos para generar modelos debido a la mayor varianza de datos que generalmente existe en los ingresos por visita en comparación con la tasa de conversión.
* Dado que los modelos se crean por experiencia, reemplazar una experiencia por otra significa que se debe recopilar suficiente tráfico (es decir, al menos 50 conversiones) para la nueva experiencia antes de que se puedan volver a crear los modelos personalizados.

### Se ha creado un modelo en mi actividad. ¿Las visitas a esa experiencia están personalizadas?  

No, debe haber al menos dos modelos integrados dentro de su actividad para que comience la personalización.

### ¿Cuándo puedo empezar a ver los resultados de mi actividad de la [!UICONTROL segmentación automática]?

Puede comenzar a observar los resultados de su actividad de [!UICONTROL segmentación automática] después de que tenga al menos dos experiencias con los modelos creados (marca de verificación verde) para la experiencia que tienen los modelos generados.

### ¿Puedo especificar una experiencia específica para utilizarla como control?

Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) o de [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta función le permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a esa experiencia.

Para obtener más información, consulte [Uso de una experiencia específica como control](/help/c-activities/t-automated-personalization/experience-as-control.md).

### ¿Puedo cambiar la métrica de objetivos a medio camino a través de una actividad de Destinatario automático? {#change-metric}

No se recomienda cambiar la métrica de objetivos a mitad de camino a través de una actividad. Aunque es posible cambiar la métrica de objetivos durante una actividad mediante la [!DNL Target] interfaz de usuario, siempre debe realizar el inicio de una nueva actividad. No garantizamos lo que sucede si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a [!UICONTROL actividades de asignación automática], [!UICONTROL Destinatario automático] y [!UICONTROL Automated Personalization] que utilizan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de sistema de informes.

### ¿Puedo utilizar la opción Restablecer datos del informe al ejecutar una actividad de Destinatario automático?

No se sugiere utilizar la opción [!UICONTROL Restablecer datos del informe] para actividades [!UICONTROL Destinatario automático]. Aunque elimina los datos de sistema de informes visibles, esta opción no elimina todos los registros de capacitación del modelo [!UICONTROL Destinatario automático]. En lugar de utilizar la opción [!UICONTROL Restablecer datos del informe] para actividades [!UICONTROL Destinatario automático], cree una nueva actividad y desactive la actividad original. (Nota: Esta guía también se aplica a las actividades [!UICONTROL de asignación automática] y [!UICONTROL Automated Personalization]).

### ¿Qué sucede si elimino una sola experiencia de una actividad de Destinatario automático?

[!DNL Target] crea un modelo por experiencia, por lo que eliminar una experiencia significa que solo  [!DNL Target] generará un modelo menos y no afectará a los modelos de las otras experiencias.

Por ejemplo, supongamos que tiene una actividad [!UICONTROL Destinatario automático] con ocho experiencias y no le gusta el rendimiento de una experiencia. Puede eliminar esa experiencia y no afectará a los modelos de las siete experiencias restantes.

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


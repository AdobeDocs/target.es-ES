---
description: A veces, las actividades no salen como se esperaba. A continuación, le presentamos algunos de los posibles desafíos a los que se puede enfrentar al usar la personalización automatizada y algunas soluciones sugeridas.
title: Resolución de problemas de la personalización automatizada
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 94%

---


# ![PREMIUM](/help/assets/premium.png) Resolución de problemas de la personalización automatizada{#troubleshoot-automated-personalization}

A veces, las actividades no salen como se esperaba. A continuación, le presentamos algunos de los posibles desafíos a los que se puede enfrentar al usar la personalización automatizada y algunas soluciones sugeridas.

## Mi actividad AP está tardando demasiado en crear modelos. {#section_20028B204DBB4D77A324BA193434AEE2}

Hay varios cambios en la configuración de la actividad que pueden disminuir el tiempo esperado para crear modelos, incluida la cantidad de experiencias que hay en la prueba de personalización automatizada, el tráfico hacia su sitio y la métrica de éxito seleccionada.

**Solución:** revise la configuración de su actividad y vea si hay algún cambio que esté dispuesto a hacer para mejorar la velocidad a la que se crean los modelos.

* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. No perderá datos de actividad si cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas ofertas o experiencias que puede excluir de su actividad? Disminuir el número de experiencias en una actividad acelera la cantidad de tiempo para crear modelos.
* ¿Hay una página con mayor tráfico donde esta actividad sería más exitosa? Cuanto más tráfico y conversiones haya en sus ubicaciones de actividad, más rápido se crearán los modelos.

## Mi actividad AP no generó ningún alza.    {#section_8900BC8968474438B8092F7A94C0C6CF}

Hay varios factores necesarios para que una actividad AP genere alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben ubicarse en algún lugar que marque una diferencia en el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** el mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de muestra antes de tiempo para asegurarse de que haya suficiente energía para ver un levantamiento razonable y ejecutar la prueba A/B durante un tiempo determinado sin detenerlo ni realizar ningún cambio. Si los resultados de una prueba A/B muestran un aumento estadísticamente significativo en una o más de las experiencias, entonces es probable que una actividad personalizada funcione. Por supuesto, la personalización puede funcionar incluso si no hay diferencias en las tasas de respuesta general de las experiencias. Normalmente, el problema radica en que las ofertas/ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización para que se detecten con relevancia estadística.

## Mi dirección URL de actividad AP muestra contenido de ofertas en páginas incorrectas.    {#section_82A224406DBF4107B05204BEFBBE458C}

En AP, las reglas de prueba de plantilla y URL se agregan a la restricción de entrada de solicitud [!DNL Target] (por ejemplo, destinatario-global-mbox), donde se evalúan una sola vez. Una vez que un usuario cumple los requisitos para una actividad, las reglas de objetivo de nivel de solicitud de Destinatario no se vuelven a evaluar. Sin embargo, se agrega la audiencia de segmentación a las reglas de segmentación de ubicación.

**Solución:** agregue las reglas de plantillas necesarias como audiencia de entrada de la campaña. La evaluación de audiencia sucede con cada solicitud/llamada.

Este problema se corregirá en una versión próxima.

## Las métricas que dependen de la métrica de conversión nunca se convierten.    {#section_076D1F44298C4E4A849AC52F5A33214D}

Esto es esperable.

En una actividad AP, una vez que se convierte la métrica de conversión (ya sea objetivo de optimización u objetivo de anuncio), el usuario se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 aún no se convierte porque en cuanto se convierte C1, se libera el visitante.

## Mis URL de experiencia no funcionan como deberían.    {#section_7B08DA1F30AA483E9406336DAF361BA4}

* Si no ve la vista previa en la ficha nueva (debido a la memoria caché del navegador), intente actualizar la ficha dos o tres veces o copie el vínculo y ábralo en un navegador nuevo o en una sesión nueva.
* Vuelva a generar los vínculos URL de experiencia si cambió algún contenido y comparta los nuevos vínculos con sus compañeros de equipo.


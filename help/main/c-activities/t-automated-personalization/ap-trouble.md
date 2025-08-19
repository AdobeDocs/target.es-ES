---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explore los desafíos potenciales que podría enfrentar al usar actividades de [!UICONTROL Automated Personalization] (AP) en Adobe Target, junto con las soluciones sugeridas.
title: ¿Cómo puedo solucionar problemas de [!UICONTROL Automated Personalization] actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 31%

---

# Solucionar problemas de [!UICONTROL Automated Personalization]

A veces, las actividades no salen como se esperaba. Estos son algunos de los desafíos potenciales que podría enfrentar al usar [!UICONTROL Automated Personalization] (AP), y algunas soluciones sugeridas.

## Mi actividad [!UICONTROL Automated Personalization] está tardando demasiado en crear modelos. {#section_20028B204DBB4D77A324BA193434AEE2}

+++Ver detalles

Hay varios cambios en la configuración de la actividad que pueden disminuir el tiempo esperado para crear modelos, incluida la cantidad de experiencias en su actividad [!UICONTROL Automated Personalization], el tráfico hacia su sitio y la métrica de éxito seleccionada.

**Solución:** revise la configuración de la actividad y vea si hay algún cambio que desee realizar para mejorar la velocidad a la que se crean los modelos.

* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. Los datos de actividad no se pierden si se cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad más baja aumenta los requisitos de tráfico necesarios para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas ofertas o experiencias que puede excluir de su actividad? Reducir el número de experiencias en una actividad acelera el tiempo para crear modelos.
* ¿Hay una página de mayor tráfico en la que esta actividad tendría más éxito? Cuantos más tráfico y conversiones haya en las ubicaciones de las actividades, más rápidos se crearán los modelos.

+++

## Mi actividad [!UICONTROL Automated Personalization] no generó alza. {#section_8900BC8968474438B8092F7A94C0C6CF}

+++Ver detalles

Hay varios factores necesarios para que una actividad [!UICONTROL Automated Personalization] genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** el mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Asegúrese de calcular los tamaños de las muestras con antelación. El cálculo de los tamaños de muestra con antelación ayuda a garantizar que haya suficiente potencia para ver un alza razonable. A continuación, puede ejecutar la prueba A/B durante un tiempo fijo sin detenerla ni realizar ningún cambio. Si el resultado de una prueba A/B muestra un alza estadísticamente significativa en una o más experiencias, es probable que una actividad personalizada tenga éxito. Personalization puede funcionar incluso si no hay diferencias en las tasas de respuesta generales de las experiencias. Normalmente, el problema se debe a que las ofertas o ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

## Mi dirección URL de actividad [!UICONTROL Automated Personalization] muestra contenido de ofertas en páginas incorrectas. {#section_82A224406DBF4107B05204BEFBBE458C}

+++Ver detalles

En [!UICONTROL Automated Personalization], las reglas de prueba de plantilla y dirección URL se agregan a la restricción de entrada de solicitud [!DNL Target] (por ejemplo, target-global-mbox), donde se evalúan una sola vez. Una vez que un usuario cumple los requisitos para una actividad, las reglas de segmentación de nivel de solicitud de Target no se vuelven a evaluar. Sin embargo, se agrega la audiencia de segmentación a las reglas de segmentación de ubicación.

**Solución:** Agregue las reglas de plantilla necesarias como audiencia de entrada de la actividad. La evaluación de audiencia sucede con cada solicitud/llamada.

+++

## Las métricas que dependen de una métrica de conversión nunca se convierten. {#section_076D1F44298C4E4A849AC52F5A33214D}

+++Ver detalles

Esto es esperable.

En una actividad de [!UICONTROL Automated Personalization], una vez convertida la métrica de conversión (ya sea por objetivos de optimización o de anuncio), el visitante se libera de la experiencia y se reinicia la actividad.

Por ejemplo, existe una actividad con una métrica de conversión (C1) y una métrica adicional (A1). A1 depende de C1. Cuando un visitante entra a la actividad por primera vez y no se convierten los criterios de conversión de A1 y C1, la métrica A1 no se convierte debido a la dependencia de métrica de éxito. Si el visitante convierte C1 y luego convierte A1, A1 sigue sin convertirse porque cuando se convierte C1, el visitante se libera.

+++

## Mis URL de experiencia no funcionan como deberían.   {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++Ver detalles

* Si no puede ver la vista previa en la nueva pestaña (debido a la caché del explorador), intente actualizarla dos o tres veces. También puede copiar el vínculo y abrirlo en un explorador nuevo o en una sesión nueva.
* Vuelva a generar los vínculos URL de experiencia si cambió algún contenido y comparta los nuevos vínculos con sus compañeros de equipo.

+++

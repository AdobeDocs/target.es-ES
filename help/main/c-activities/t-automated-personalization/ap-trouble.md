---
keywords: Automated Personalization;ap;solucionar problemas;resolución de problemas;modelo;alza
description: Explore los desafíos potenciales que podría enfrentar al usar las actividades de [!UICONTROL Automated Personalization] (AP) en Adobe Target, junto con las soluciones sugeridas.
title: ¿Cómo puedo solucionar problemas de actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: 'https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 7%
---
# Solucionar problemas de [!UICONTROL Automated Personalization] {#ap-troubleshooting}

>[!BEGINSHADEBOX]

**En esta página:** Encuentre soluciones a problemas comunes con las actividades de **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Las actividades no siempre salen como se esperaba. Utilice la siguiente lista para identificar la causa de los problemas más comunes en las actividades de [!UICONTROL Automated Personalization] (AP) y para aplicar la solución sugerida.

## Modelos y alza {#models-and-lift}

+++ Mi actividad [!UICONTROL Automated Personalization] está tardando demasiado en crear modelos

Hay varias opciones de configuración de actividad que afectan el tiempo que los modelos necesitan para generar, incluida la cantidad de experiencias en su actividad de **[!UICONTROL Automated Personalization]**, el tráfico hacia su sitio y la métrica de éxito seleccionada.

**Solución:** Revise la configuración de su actividad y compruebe si puede realizar cambios que mejoren la velocidad a la que se crean los modelos.

* Si su métrica de éxito está configurada en RPV, ¿puede cambiar a conversión? Las actividades de conversión tienden a requerir menos tráfico para construir modelos. Los datos de actividad no se pierden si se cambia la métrica de éxito de RPV a conversión.
* ¿Su métrica de éxito está muy por debajo del embudo de ventas de sus experiencias de actividad? Una tasa de conversión de actividad menor aumenta los requisitos de tráfico para que los modelos se creen, ya que se requiere un número mínimo de conversiones.
* ¿Hay algunas ofertas o experiencias que puede excluir de su actividad? Reducir el número de experiencias en una actividad acelera el tiempo para crear modelos.
* ¿Hay una página de mayor tráfico en la que esta actividad tendría más éxito? Cuantos más tráfico y conversiones haya en las ubicaciones de las actividades, más rápidos se crearán los modelos.

+++

+++ Mi actividad [!UICONTROL Automated Personalization] no generó alza

Se requieren varios factores para que una actividad **[!UICONTROL Automated Personalization]** genere un alza:

* Las ofertas deben ser lo suficientemente diferentes como para influir en los visitantes.
* Las ofertas deben encontrarse en algún lugar que marque la diferencia con el objetivo de optimización.
* Debe haber suficiente tráfico y “poder” estadístico en la prueba para detectar el alza.
* El algoritmo de personalización debe funcionar bien.

**Solución:** El mejor curso de acción es asegurarse primero de que el contenido y las ubicaciones que componen las experiencias de actividad marquen realmente una diferencia en las tasas de respuesta generales mediante una prueba A/B simple no personalizada. Calcule los tamaños de la muestra con antelación para asegurarse de que haya suficiente potencia para ver un alza razonable y, a continuación, ejecute la prueba A/B durante un tiempo fijo sin detenerla ni realizar ningún cambio. Si los resultados de las pruebas A/B muestran un alza estadísticamente significativa en una o más experiencias, es probable que una actividad personalizada tenga éxito. Personalization puede funcionar incluso si no hay diferencias en las tasas de respuesta generales de las experiencias. Normalmente, el problema se debe a que las ofertas o ubicaciones no tienen un impacto lo suficientemente grande en el objetivo de optimización como para ser detectadas con relevancia estadística.

+++

## Configuración de actividades e informes {#setup-and-reporting}

+++ Mi URL de actividad [!UICONTROL Automated Personalization] muestra contenido de ofertas en páginas incorrectas

**Causa:** En **[!UICONTROL Automated Personalization]**, las reglas de prueba de plantillas y URL se agregan a la restricción de entrada de solicitud [!DNL Target] (por ejemplo, target-global-mbox), donde se evalúan solo una vez. Una vez que un visitante se califica para una actividad, las reglas de segmentación de nivel de solicitud [!DNL Target] no se vuelven a evaluar, mientras que la audiencia de segmentación se agrega a las reglas de segmentación de ubicación.

**Solución:** Agregue las reglas de plantilla necesarias como audiencia de entrada de la actividad. La evaluación de audiencias se produce con cada solicitud (llamada a ).

+++

+++ Las métricas que dependen de una métrica de conversión nunca se convierten

Este comportamiento es predecible.

En una actividad de **[!UICONTROL Automated Personalization]**, una vez que se convierte la métrica de conversión (ya sea un objetivo de optimización o de anuncio), el visitante se libera de la experiencia y se reinicia la actividad.

Por ejemplo, una actividad tiene una métrica de conversión (C1) y una métrica adicional (A1) que depende de C1. Cuando un visitante entra en la actividad por primera vez y no ha convertido C1 ni A1, A1 no se convierte debido a la dependencia de la métrica de éxito. Si el visitante convierte C1 y luego A1, A1 sigue sin convertirse, ya que el visitante se libera cuando se convierte C1.

+++

+++ Mis URL de experiencia no funcionan como deberían

**Solución:** Utilice las siguientes acciones:

* Si no puede ver la vista previa en la nueva pestaña (debido a la caché del explorador), intente actualizarla dos o tres veces. También puede copiar el vínculo y abrirlo en un explorador nuevo o en una sesión nueva.
* Si ha cambiado algún contenido, vuelva a generar los vínculos de la URL de la experiencia y comparta los nuevos vínculos con sus compañeros.

+++

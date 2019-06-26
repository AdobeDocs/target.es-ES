---
description: Seleccione una experiencia para utilizarla como control al crear una actividad de Personalización automatizada (AP) o de Segmentación automática.
keywords: experiencia; control; personalización automatizada; segmentación automática
seo-description: Seleccione una experiencia para utilizarla como control al crear una actividad de Personalización automatizada (AP) o de Segmentación automática en Adobe Target.
seo-title: Uso de una experiencia específica como control en Adobe Target
solution: Target,Analytics
title: Usar una experiencia específica como control
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![PREMIUM](/help/assets/premium.png) Seleccione el control para la actividad de Personalización automatizada o de Segmentación automática

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

Esta función permite enrutar el tráfico de control a las experiencias relevantes, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado contra el tráfico de control hacia ese control.

Las opciones para configurar un control en actividades AP y AT son un poco diferentes que otros tipos de actividades. En una prueba A/B manual, puede cambiar los informes que se muestran mientras el control y el alza se calcula en función de la tasa de conversión de dicha experiencia de control. Esto puede hacer que esto cambie fácilmente, ya que el tráfico se sirve aleatoriamente a cada una de las experiencias incluidas en la actividad, independientemente de la configuración que se establezca inicialmente en el control. En otras palabras, si se selecciona el control no influye en la forma en que se sirve el tráfico. En las actividades AP y AT, su decisión sobre lo que se debe elegir, ya que el control influye en el modo en que se sirve el tráfico de visitantes. Como resultado, debe pensar más detenidamente sobre su decisión.

Hay dos opciones disponibles para el control en las actividades AP y AT: experiencias servidas aleatoriamente o una experiencia específica.

* **Servido de forma aleatoria**: Para un control aleatorio, el porcentaje de control de tráfico proporciona todas las experiencias de la actividad sin tener en cuenta el perfil del visitante. Puede considerar el control como ayuda para responder a la pregunta: «Si solo ofrezco aleatoriamente una experiencia (u oferta) a los visitantes y no considere sus perfiles,¿cuál es la tasa de conversión de dicha experiencia (u oferta)? »» El control es como una prueba A/B dentro de la actividad AI. Tener esta información de la tasa de conversión no personalizada para cada experiencia u oferta puede resultar útil para saber cuándo analizar los resultados de la actividad.

* **Experiencia específica**: Un control de experiencia específico permite comparar el tráfico proporcionado por los modelos de personalización de Target con una experiencia específica definida por el especialista en mercadotecnia (por ejemplo, su página principal predeterminada). Con esta opción, el porcentaje de control de tráfico proporciona tráfico de forma aleatoria solo para esa experiencia.

## Especificar una experiencia específica como control

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. Especifique la asignación de tráfico que desee para la experiencia de control y las demás experiencias.

   Para un control de experiencia específico, se recomienda el 10% y el 30%.

1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## Limitaciones y consideraciones conocidas

Tenga en cuenta los siguientes puntos al utilizar una experiencia específica como control:

* No se recomienda cambiar la experiencia de control en una actividad ya activa. La última experiencia de control seleccionada se nombra en los informes (incluso si los informes anteriores se basan en otra experiencia).
* No se recomienda eliminar la experiencia de control.
* Agregar un gran número de nuevas ofertas y experiencias a una actividad en directo con una experiencia específica, ya que no se recomienda controlar.
* En actividades AP, incluido el establecimiento de objetivos en la experiencia de control que podría restringir aún más a los usuarios que ven esa experiencia.
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. La información de alza y confianza está disponible en el nivel de tráfico &quot;segmentado&quot; y &quot;de control&quot; para la actividad AP. La información de alza y confianza está disponible si se selecciona &quot;aleatorio&quot; como control. Esto se debe a que la comparación de una tasa de conversión de una experiencia específica con la tasa de conversión de una oferta no es lógica debido a la diferencia en las unidades. La información disponible en una actividad AT es la misma, independientemente del tipo de control seleccionado.
* Debido a que todo el tráfico de control va a una única experiencia o grupo de ofertas cuando se selecciona la experiencia como control (en comparación con aleatorio, donde la cantidad de tráfico de control se divide sobre el número de experiencias o ofertas de la actividad), generalmente no necesita tanta cantidad de tráfico para fluir al control. 10% es un buen lugar para empezar.
* Si realiza una de las siguientes acciones en una actividad en directo con una experiencia específica como control, el control se restablece automáticamente a experiencias servidas aleatoriamente (en lugar de a la experiencia específica seleccionada anteriormente):

   * Eliminar una experiencia
   * Eliminar una ubicación u oferta (solo AP)
   * Excluir una experiencia, manualmente, eliminando ofertas duplicadas o mediante un grupo de exclusión (solo AP)


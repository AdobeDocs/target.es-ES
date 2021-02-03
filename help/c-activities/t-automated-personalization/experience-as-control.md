---
keywords: experiencia;control;Automated Personalization;segmentación automática
description: Seleccione una experiencia para utilizarla como control mientras crea una actividad de Automated Personalization (AP) o de Segmentación automática (AT) en Adobe Target.
title: Usar una experiencia específica como control
feature: Automated Personalization
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 99%

---


# ![PREMIUM](/help/assets/premium.png) Seleccione el control de la actividad de Automated Personalization o de Segmentación automática

Puede seleccionar una experiencia servida aleatoriamente o una experiencia específica para utilizarla como control al crear una actividad de [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP) o de [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta funcionalidad le permite dirigir el tráfico de control a una experiencia relevante, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a ese control.

Las opciones para configurar un control en actividades AP y AT son un diferentes a tipos de actividades. En una prueba A/B manual, puede cambiar qué controles se muestran en los informes. El crecimiento se calcula según la tasa de conversión de esa experiencia de control. Puede cambiarlo fácilmente ya que el tráfico se sirve aleatoriamente a cada una de las experiencias incluidas en la actividad, independientemente de la configuración que se establezca en el control. En otras palabras, seleccionar el control no influye en la forma en que se sirve el tráfico. En las actividades AP y AT, su decisión sobre qué elegir como control influye en el modo en que se sirve el tráfico de visitantes. Por tanto, es importante que piense bien su decisión.

Hay dos opciones disponibles para el control en las actividades AP y AT: experiencias servidas aleatoriamente o una experiencia específica.

* **Servido de forma aleatoria**: Para un control aleatorio, el porcentaje de control de tráfico proporciona todas las experiencias de la actividad sin tener en cuenta el perfil del visitante. Puede considerar el control como ayuda para responder a la pregunta: “Si solo ofrezco aleatoriamente una experiencia (u oferta) a los visitantes y no considero sus perfiles,¿cuál es la tasa de conversión de dicha experiencia (u oferta)?” El control es como una prueba A/B dentro de la actividad AI. Tener esta información de la tasa de conversión no personalizada para cada experiencia u oferta puede resultar útil para saber cuándo analizar los resultados de la actividad.

* **Experiencia específica**: Un control de experiencia específico permite comparar el tráfico proporcionado por los modelos de personalización de Target con una experiencia específica definida por el especialista en marketing (por ejemplo, su página principal predeterminada). Con esta opción, el porcentaje de control de tráfico proporciona tráfico de forma aleatoria solo para esa experiencia.

## Especificar una experiencia determinada como control

1. Cuando se crea una [actividad AP](/help/c-activities/t-automated-personalization/create-ap-activity.md) o una [actividad AT](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), se pueden configurar las experiencias como se desee.
1. En la página [!UICONTROL Segmentación] (paso 2 del flujo de trabajo guiado de tres partes), seleccione la experiencia que desee como control.
1. Especifique la asignación de tráfico que desee para la experiencia de control y las demás experiencias.

   Para un control de experiencia específico, se recomienda el 10% y el 30%.

1. Continúe con la página [!UICONTROL Objetivos y configuración].

## Limitaciones y consideraciones conocidas

Tenga en cuenta los siguientes puntos al utilizar una experiencia específica como control:

* No se recomienda cambiar la experiencia de control en una actividad ya activa. La última experiencia de control seleccionada se nombra en los informes (incluso si los informes anteriores se basan en otra experiencia).
* No se recomienda eliminar la experiencia de control.
* No se recomienda añadir un gran número de nuevas ofertas y experiencias a una actividad en directo con una experiencia específica como control.
* En actividades AP, no se recomienda incluir la segmentación en la experiencia de control que podría restringir aún más a los usuarios que ven esa experiencia.
* En las actividades AP, la información de crecimiento y de confianza *NO* está disponible en el informe de nivel de oferta si se selecciona una experiencia específica. La información de crecimiento y de confianza está disponible en el nivel de tráfico &quot;segmentado&quot; y &quot;de control&quot; para la actividad AP. La información de crecimiento y de confianza está disponible si se selecciona &quot;aleatorio&quot; como control. Esto se debe a que la comparación de una tasa de conversión de una experiencia específica con la tasa de conversión de una oferta no es lógica debido a la diferencia en las unidades. La información disponible en una actividad AT es la misma, independientemente del tipo de control seleccionado.
* Debido a que todo el tráfico de control va a una única experiencia o grupo de ofertas cuando se selecciona la experiencia como control (en comparación con aleatorio, donde la cantidad de tráfico de control se divide sobre el número de experiencias u ofertas de la actividad), generalmente no necesita tanta cantidad de tráfico para fluir al control. 10% es una buena cifra para empezar.
* Si realiza una de las siguientes acciones en una actividad en directo con una experiencia específica como control, el control se restablece automáticamente a experiencias servidas aleatoriamente (en lugar de a la experiencia específica seleccionada anteriormente):

   * Eliminar una experiencia
   * Eliminar una ubicación u oferta (solo AP)
   * Excluir una experiencia, manualmente, eliminando ofertas duplicadas o mediante un grupo de exclusión (solo AP)


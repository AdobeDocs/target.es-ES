---
keywords: experiencia;control;Automated Personalization;segmentación automática
description: Obtenga información sobre cómo seleccionar una experiencia para utilizarla como control al crear una actividad [!UICONTROL Automated Personalization] (AP) o [!UICONTROL Auto-Target] en  [!DNL Adobe Target].
title: ¿Cómo puedo usar una experiencia específica como control en una actividad de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
hide: true
hidefromtoc: true
source-git-commit: 19f70ce944e4db4aa0774da034a0d16be34a4ec8
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 42%

---

# Seleccione el control de la actividad [!UICONTROL Automated Personalization] o [!UICONTROL Auto-Target]

Puede seleccionar una experiencia servida aleatoriamente o una experiencia específica para utilizarla como control al crear una actividad [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) o [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esta funcionalidad le permite dirigir el tráfico de control a una experiencia relevante, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado respecto al tráfico de control a ese control.

Las opciones para establecer un control en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target] son un poco diferentes de otros tipos de actividades. En un(a) manual [!UICONTROL A/B Test], puede cambiar qué controles se muestran en los informes. El alza se calcula según la tasa de conversión de esa experiencia de control. Puede cambiarlo fácilmente ya que el tráfico se sirve aleatoriamente a cada una de las experiencias incluidas en la actividad, independientemente de la configuración que se establezca en el control. En otras palabras, seleccionar el control no afecta al modo en que se sirve el tráfico. En las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target], su decisión sobre qué elegir como control influye en el modo en que se sirve el tráfico de visitantes. Como resultado, debe pensar más cuidadosamente acerca de su decisión.

Hay dos opciones disponibles para el control en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target]:

* **Servido de forma aleatoria**: Para un control aleatorio, el porcentaje de control de tráfico proporciona todas las experiencias de la actividad sin tener en cuenta el perfil del visitante. Puede considerar el control como ayuda para responder a la pregunta: &quot;Si solo ofrezco aleatoriamente una experiencia (u oferta) a los visitantes y no considero sus perfiles, ¿cuál es la tasa de conversión de dicha experiencia (u oferta)?&quot; El control es como un [!UICONTROL A/B Test] dentro de su actividad de IA. Tener esta información de la tasa de conversión no personalizada para cada experiencia u oferta puede resultar útil para saber cuándo analizar los resultados de la actividad.

* **Experiencia específica**: Un control de experiencia específico permite comparar el tráfico proporcionado por [!DNL Target] modelos de personalización con una experiencia específica definida por el especialista en marketing (por ejemplo, su página principal predeterminada). Con esta opción, el porcentaje de control de tráfico proporciona tráfico de forma aleatoria solo para esa experiencia.

## Especificar una experiencia determinada como control

1. Al crear o editar una actividad [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) o [[!UICONTROL Auto-Target] actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure las experiencias como desee.
1. En la página [!UICONTROL Targeting] (paso 2 del flujo de trabajo guiado de tres partes), seleccione la experiencia que desee como control.
1. Especifique la asignación de tráfico que desee para la experiencia de control y las demás experiencias.

   Para un control de experiencia específico, se recomienda el 10% y el 30%.

1. Continuar con la página [!UICONTROL Goals & Settings].

## Limitaciones y consideraciones conocidas

Tenga en cuenta los siguientes puntos al utilizar una experiencia específica como control:

* No se recomienda cambiar la experiencia de control en una actividad ya activa. La última experiencia de control seleccionada se nombra en los informes (incluso si los informes anteriores se basan en otra experiencia).
* No se recomienda eliminar la experiencia de control.
* No se recomienda añadir muchas ofertas o experiencias nuevas a una actividad en directo con una experiencia específica como control.
* En [!UICONTROL Automated Personalization] actividades, no se recomienda incluir la segmentación en la experiencia de control que podría restringir aún más a los usuarios que ven esa experiencia.
* En [!UICONTROL Automated Personalization] actividades, la información de alza y confianza está *NO* disponible en el informe de nivel de oferta si se selecciona una experiencia específica. La información de alza y confianza está disponible en el nivel de tráfico &quot;segmentado&quot; y &quot;de control&quot; para la actividad [!UICONTROL Automated Personalization]. La información de crecimiento y de confianza está disponible si se selecciona &quot;aleatorio&quot; como control. Esto se debe a que la comparación de una tasa de conversión de una experiencia específica con la tasa de conversión de una oferta no es lógica debido a la diferencia en las unidades. La información disponible en una actividad [!UICONTROL Auto-Target] es la misma, independientemente del tipo de control seleccionado.
* Debido a que todo el tráfico de control va a una única experiencia o grupo de ofertas cuando se selecciona la experiencia como control (en comparación con aleatorio, donde la cantidad de tráfico de control se divide sobre el número de experiencias u ofertas de la actividad), generalmente no necesita tanta cantidad de tráfico para fluir al control. 10% es una buena cifra para empezar.
* Si realiza una de las siguientes acciones en una actividad en directo con una experiencia específica como control, el control se restablece automáticamente a experiencias servidas aleatoriamente (en lugar de a la experiencia específica seleccionada anteriormente):

   * Eliminar una experiencia
   * Quitar una ubicación u oferta ([!UICONTROL Automated Personalization] solamente)
   * Excluir una experiencia manualmente, eliminando ofertas duplicadas o mediante un grupo de exclusión ([!UICONTROL Automated Personalization] solamente)

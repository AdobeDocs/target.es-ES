---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;solo actividad;específica
description: Aprenda a crear audiencias solo de actividad en Adobe [!DNL Target] que son para un solo uso.
title: ¿Puedo crear una audiencia para usarla una sola vez?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 55%

---

# Crear una audiencia solo de actividad

Cree audiencias solo de actividad desde el [!DNL Adobe Target] flujo de trabajo guiado de tres pasos al crear una actividad. Estas audiencias ad-hoc pueden usarse en otros lugares dentro de la misma actividad, pero no se almacenan en la [!UICONTROL Biblioteca de audiencias] para su uso en otras actividades.

Las audiencias solo de actividad proporcionan las siguientes ventajas:

* Puede utilizar audiencias solo de actividad para crear una audiencia que quiera usar una única vez y que no desee almacenar en la [!UICONTROL Biblioteca de audiencias]. Las audiencias solo de actividad ayudan a evitar que [!UICONTROL Biblioteca de audiencias] de estar saturado de audiencias que no quiere volver a usar.
* Las audiencias solo de actividad no pueden verse en la [!UICONTROL Biblioteca de audiencias]. Como estas audiencias no están visibles en la biblioteca, están protegidas de cambios no deseados por parte de otros usuarios de su organización.

1. Al crear un [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en el **[!UICONTROL Segmentación]** , haga clic en las tres elipses verticales y, a continuación, haga clic en **[!UICONTROL Reemplazar audiencia]**.

   ![Resultado del paso](assets/edit_audience.png)

1. Haga clic en **[!UICONTROL Crear audiencia]**.

1. Haga clic en **[!UICONTROL Solo esta actividad]**.

   ![imagen de solo austeridad de actividad](assets/activity-only-aud.png)

1. Escriba un nombre descriptivo para la audiencia.
1. Arrastre y suelte los atributos deseados en el generador de audiencias.

   Las reglas permiten limitar la audiencia a un subconjunto de los visitantes del sitio. Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para audiencias](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de audiencia.

1. Haga clic en **[!UICONTROL Finalizado]**.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con audiencias solo de actividad:

* Puede crear audiencias solo de actividad en la [!UICONTROL Compositor de experiencias visuales] (VEC) o en el [!UICONTROL Compositor de experiencias basadas en formularios]. Esta funcionalidad reemplaza las reglas de refinamiento de versiones anteriores de [!DNL Target].
* Puede crear una actividad para almacenarla en la [!UICONTROL Biblioteca de audiencias] y reutilizarla en otras actividades, o crear una audiencia solo de actividad. Después de guardar la audiencia, no puede cambiar su tipo.
* Los refinamientos de actividades existentes se migran a audiencias solo de actividad.
* Las audiencias solo de actividad tienen un estado de [!UICONTROL Utilizada] o [!UICONTROL No utilizada]. Las audiencias solo de actividad no utilizadas se muestran hasta que la actividad se guarda. Si se dejan sin utilizar e intenta guardarlas, se muestra un mensaje de advertencia que indica que las audiencias solo de actividad no utilizadas se eliminarán.
* Puede ver los detalles de definición de una audiencia en forma de tarjeta emergente a la que se accede desde el selector de audiencias, sin necesidad de abrir la audiencia.
* Puede [combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias solo de actividad.
* Las audiencias solo de actividad no admiten reglas de exclusión.

   Puede utilizar las siguientes alternativas para utilizar reglas de exclusión:

   * [Crear y usar una audiencia de biblioteca](/help/main/c-target/c-audiences/create-audience.md) en lugar de una audiencia solo de actividad.
   * [Combinación de varias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) (hasta 20) biblioteca audiencias en una audiencia solo de actividad. Al combinar audiencias, las reglas de inclusión y exclusión en audiencias de biblioteca individuales se pueden usar incluso cuando la audiencia combinada se guarda como una audiencia solo de actividad.

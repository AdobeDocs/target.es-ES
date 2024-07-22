---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;solo actividad;específica
description: Aprenda a crear audiencias solo de actividad en el Adobe  [!DNL Target]  que se utilicen una sola vez.
title: ¿Puedo crear una audiencia para usarla una sola vez?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 31%

---

# Crear una audiencia solo de actividad

Cree audiencias solo de actividad dentro del flujo de trabajo guiado de tres pasos de [!DNL Adobe Target] al crear una actividad. Estas audiencias ad-hoc pueden usarse en otros lugares dentro de la misma actividad, pero no se almacenan en [!UICONTROL Audiences Library] para su uso en otras actividades.

Las audiencias solo de actividad proporcionan las siguientes ventajas:

* Puede usar audiencias solo de actividad para crear una audiencia que quiera usar una sola vez y que no desee almacenar en el [!UICONTROL Audiences Library]. Las audiencias solo de actividad ayudan a evitar que [!UICONTROL Audiences Library] se llene de elementos que no desea volver a usar.
* Las audiencias solo de actividad no son visibles en [!UICONTROL Audiences Library]. Como estas audiencias no son visibles en la biblioteca, están protegidas contra cambios no deseados por parte de otros miembros de la organización.

1. Al crear una [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Targeting]**, haga clic en los tres puntos verticales y luego haga clic en **[!UICONTROL Replace Audience]**.

   ![Resultado del paso](assets/edit_audience.png)

1. Haga clic en **[!UICONTROL Create Audience]**.

1. Haga clic en **[!UICONTROL This activity only]**.

   ![imagen de solo actividad](assets/activity-only-aud.png)

1. Escriba un nombre descriptivo para la audiencia.
1. Arrastre y suelte los atributos deseados en el generador de audiencias.

   Las reglas permiten limitar la audiencia a un subconjunto de los visitantes del sitio. Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para audiencias](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de audiencia.

1. Haga clic en **[!UICONTROL Done]**.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con audiencias solo de actividad:

* Puede crear audiencias solo de actividad en [!UICONTROL Visual Experience Composer] (VEC) o en [!UICONTROL Form-Based Experience Composer]. Esta funcionalidad reemplaza las reglas de refinamiento de versiones anteriores de [!DNL Target].
* Puede crear una actividad para almacenarla en [!UICONTROL Audience Library] y reutilizarla en otras actividades, o bien crear una audiencia solo de actividad. Después de guardar la audiencia, no puede cambiar su tipo.
* Los refinamientos de actividades existentes se migran a audiencias solo de actividad.
* Las audiencias solo de actividad tienen un estado de [!UICONTROL Used] o [!UICONTROL Unused]. Las audiencias solo de actividad no utilizadas se muestran hasta que la actividad se guarda. Si se dejan sin utilizar e intenta guardarlas, se muestra un mensaje de advertencia que indica que las audiencias solo de actividad no utilizadas se eliminarán.
* Puede ver los detalles de definición de una audiencia en forma de tarjeta emergente a la que se accede desde el selector de audiencias, sin necesidad de abrir la audiencia.
* Puede [combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias solo de actividad.
* Las audiencias solo de actividad no admiten reglas de exclusión.

  Puede utilizar las siguientes alternativas para utilizar reglas de exclusión:

   * [Cree y use una audiencia de biblioteca](/help/main/c-target/c-audiences/create-audience.md) en lugar de una audiencia solo de actividad.
   * [Combine varias ](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) audiencias de biblioteca (hasta 20) en una audiencia solo de actividad. Al combinar audiencias, se pueden utilizar reglas de inclusión y exclusión en audiencias de biblioteca individuales incluso cuando la audiencia combinada se guarda como una audiencia solo de actividad.

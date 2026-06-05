---
keywords: público;reglas de público;crear público;creación de público;solo actividad;específica
description: Aprenda a crear audiencias solo de actividad en Adobe [!DNL Target] que se puedan usar una sola vez.
title: ¿Puedo crear una audiencia para usarla una sola vez?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
TQID: https://experienceleague.adobe.com/IWQT8Lw7uXxY8znUlzOIB-92M2sdjvMj91Ut-gAvZVU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 477
ht-degree: 30%

---

# Crear un público solo de actividad

Cree audiencias solo de actividad dentro del flujo de trabajo guiado de tres pasos de [!DNL Adobe Target] al crear una actividad. Estas audiencias ad-hoc pueden usarse en otros lugares dentro de la misma actividad, pero no se almacenan en la [!UICONTROL Biblioteca de audiencias] para su uso en otras actividades.

Los públicos solo de actividad proporcionan las siguientes ventajas:

* Puede usar audiencias solo de actividad para crear una audiencia que quiera usar una sola vez y que no quiera almacenar en la [!UICONTROL Biblioteca de audiencias]. Las audiencias solo de actividad ayudan a evitar que [!UICONTROL Biblioteca de audiencias] se llene de elementos que no desea volver a usar.
* Las audiencias solo de actividad no son visibles en la [!UICONTROL Biblioteca de audiencias]. Como estas audiencias no son visibles en la biblioteca, están protegidas contra cambios no deseados por parte de otros miembros de la organización.

1. Al crear una [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Segmentación]**, haga clic en los tres puntos verticales y luego haga clic en **[!UICONTROL Reemplazar audiencia]**.

   ![Resultado del paso](assets/edit_audience.png)

1. Haga clic en **[!UICONTROL Crear audiencia]**.

1. Haga clic en **[!UICONTROL Esta actividad solamente]**.

   ![imagen de solo actividad](assets/activity-only-aud.png)

1. Escriba un nombre descriptivo para el público.
1. Arrastre y suelte los atributos deseados en el generador de audiencias.

   Las reglas permiten limitar la audiencia a un subconjunto de los visitantes del sitio. Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para públicos](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de público.

1. Haga clic en **[!UICONTROL Finalizado]**.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con audiencias solo de actividad:

* Puede crear audiencias solo de actividad en [!UICONTROL Compositor de experiencias visuales] (VEC) o en [!UICONTROL Compositor de experiencias basadas en formularios]. Esta funcionalidad reemplaza las reglas de refinamiento de versiones anteriores de [!DNL Target].
* Puede crear una actividad para almacenarla en la [!UICONTROL biblioteca de audiencias] y reutilizarla en otras actividades, o bien crear una audiencia solo de actividad. Después de guardar la audiencia, no puede cambiar su tipo.
* Los refinamientos de actividades existentes se migran a audiencias solo de actividad.
* Las audiencias solo de actividad tienen un estado de [!UICONTROL Usado] o [!UICONTROL No usado]. Las audiencias solo de actividad no utilizadas se muestran hasta que la actividad se guarda. Si se dejan sin utilizar e intenta guardarlas, se muestra un mensaje de advertencia que indica que las audiencias solo de actividad no utilizadas se eliminarán.
* Puede ver los detalles de definición de una audiencia en forma de tarjeta emergente a la que se accede desde el selector de audiencias, sin necesidad de abrir la audiencia.
* Puede [combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias solo de actividad.
* Las audiencias solo de actividad no admiten reglas de exclusión.

  Puede utilizar las siguientes alternativas para utilizar reglas de exclusión:

   * [Cree y use una audiencia de biblioteca](/help/main/c-target/c-audiences/create-audience.md) en lugar de una audiencia solo de actividad.
   * [Combine varias ](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) audiencias de biblioteca (hasta 20) en una audiencia solo de actividad. Al combinar audiencias, se pueden utilizar reglas de inclusión y exclusión en audiencias de biblioteca individuales incluso cuando la audiencia combinada se guarda como una audiencia solo de actividad.

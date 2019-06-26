---
description: Cree audiencias solo de actividad dentro del flujo de trabajo guiado de tres pasos para la creación de una actividad. Estas audiencias ad-hoc pueden usarse en otros lugares dentro de la misma actividad, pero no se almacenan en la biblioteca de audiencias para su uso en otras actividades.
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;solo actividad;específica
seo-description: Cree audiencias solo de actividad desde el flujo de trabajo guiado de tres pasos de Adobe Target al crear una actividad. Estas audiencias ad-hoc pueden usarse en otros lugares dentro de la misma actividad, pero no se almacenan en la biblioteca de audiencias para su uso en otras actividades.
seo-title: Crear una audiencia solo de actividad en Adobe Target
solution: Target
title: Crear una audiencia solo de actividad
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Crear una audiencia solo de actividad{#create-an-activity-only-audience}

Cree audiencias solo de actividad dentro del flujo de trabajo guiado de tres pasos para la creación de una actividad. These ad hoc audiences can be used in other places within the same activity, but are not stored in the [!UICONTROL Audiences Library] for use in other activities.

Las audiencias solo de actividad proporcionan las siguientes ventajas:

* You can use activity-only audiences to create an audience that you want to use only once and you do not want to store it in the [!UICONTROL Audiences Library]. This prevents the [!UICONTROL Audiences Library] from being cluttered with audiences that you never want to use again.
* Activity-only audiences are not visible in the [!UICONTROL Audiences Library]. Por ello quedan resguardadas de cualquier cambio no deseado por parte de otros usuarios de la organización.

1. While creating an [activity](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Target]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![Resultado del paso](assets/edit_audience.png)

1. On the [!UICONTROL Choose Audience] page, click **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. Haga clic en **[!UICONTROL Crear audiencia]**.
1. Escriba un nombre descriptivo para la audiencia.
1. Haga clic en **[!UICONTROL + Agregar regla]**.

   Las reglas permiten limitar la audiencia a un subconjunto de los visitantes del sitio.

1. Seleccione un tipo de regla.

   Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para audiencias](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de audiencia.

1. Defina los parámetros de la regla.
1. Haga clic en **[!UICONTROL Guardar]**.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con audiencias solo de actividad:

* Puede crear audiencias solo de actividad en el Compositor de experiencias visuales (VEC) o en el Compositor de experiencias basadas en formularios. Esta funcionalidad reemplaza las reglas de refinamiento de versiones anteriores de Target.
* You can create an activity to store in the [!UICONTROL Audience Library] for reuse in other activities or you create an activity-only audience. Después de guardar la audiencia, no puede cambiar su tipo.
* Los refinamientos de actividades existentes se migran a audiencias solo de actividad.
* Activity-only audiences have a status of [!UICONTROL Used] or [!UICONTROL Unused]. Las audiencias solo de actividad no utilizadas se muestran hasta que la actividad se guarda. Si se dejan sin utilizar e intenta guardarlas, se muestra un mensaje de advertencia que indica que las audiencias solo de actividad no utilizadas se eliminarán.
* Puede ver los detalles de definición de una audiencia en forma de tarjeta emergente a la que se accede desde el selector de audiencias, sin necesidad de abrir la audiencia.
* Puede [combinar varias audiencias](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias solo de actividad.


---
keywords: Pruebas multivariable;URL de actividad
description: Aprenda a especificar la dirección URL de la actividad que determina la página que se usa en la prueba y que se abre cuando se diseña la actividad [!UICONTROL Multivariate Test] mediante  [!DNL Adobe Target].
title: ¿Qué es la URL de actividad en una actividad [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
hide: true
hidefromtoc: true
source-git-commit: 4805da617962e29794bd3af16138f3887ad250d0
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 31%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en [!UICONTROL Multivariate Test] (MVT) y que se abre cuando se diseña la prueba en [!DNL Adobe Target].

1. Cuando se le pida durante la [creación de la actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] y [!DNL `http://www.adobe.com`] coinciden.

   De manera predeterminada, [!UICONTROL Visual Experience Composer] (VEC) abre la página que se ha especificado en [Configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. (Condicional) Para mostrar una página diferente después de que se abra el VEC, haga clic en el icono **[!UICONTROL Configure]**, luego seleccione **[!UICONTROL Page Delivery]** y especifique la dirección URL.

1. (Condicional) Haga clic en **[!UICONTROL Add Rule]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * [!UICONTROL  URL]
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment]
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

   Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con AND.

   Haga clic en **[!UICONTROL Save]** cuando haya finalizado.

>[!NOTE]
>
>Si escribe una dirección URL de un sitio que no incluye el código JavaScript [!DNL Target], no podrá seleccionar elementos de página.
>
>De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Render using JavaScript]** si desea poder modificar esos elementos usando [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

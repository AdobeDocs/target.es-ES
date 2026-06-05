---
keywords: Segmentación de experiencias;XT;URL de actividad;URL
description: Aprenda a especificar la [!UICONTROL URL de actividad] que determina la página que se usa en la prueba y que se abre cuando la actividad de [!UICONTROL Segmentación de experiencias] está diseñada con [!DNL Adobe Target].
title: ¿Cuál es la [!UICONTROL URL de actividad] en una actividad de [!UICONTROL segmentación de experiencias] (XT)?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---

# URL de actividad en [!UICONTROL actividades de segmentación de experiencias] (XT)

La [!UICONTROL URL de actividad] determina la página que se usa en una actividad de [!DNL Adobe Target] [!UICONTROL segmentación de experiencias] (XT). Esta es la página que se abre en [!UICONTROL Compositor de experiencias visuales] (VEC) o [!UICONTROL Compositor de experiencias basadas en formularios] cuando se diseña la actividad.

1. Cuando se le pida, al [crear una actividad XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique la URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] y [!DNL `http://www.adobe.com`] coinciden.
   >
   >De manera predeterminada, el VEC o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) abre la página que se ha especificado en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.
   >
   >Si especifica una dirección URL para un sitio que no incluye una biblioteca JavaScript [[!DNL Target] at.js o  [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=es){target=_blank}, no podrá seleccionar elementos de página.

1. (Condicional) Para mostrar una página diferente después de que se abra el VEC, haga clic en **[!UICONTROL Configurar]**, seleccione **[!UICONTROL Entrega de páginas]** y, a continuación, especifique la dirección URL en el campo [!UICONTROL URL].

   ![Cuadro de diálogo Entrega de páginas](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

1. (Condicional) Haga clic en **[!UICONTROL Agregar regla de plantilla]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox

   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

---
keywords: Segmentación de experiencias;XT;URL de actividad;URL
description: Obtenga información sobre cómo especificar la URL de actividad que determina la página que se usa en la prueba y que se abre cuando la actividad de segmentación de experiencias se diseña con Adobe Target.
title: ¿Qué es la URL de actividad en una actividad de segmentación de experiencias (XT)?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# URL de actividad en actividades de segmentación de experiencias (XT)

El [!UICONTROL URL de actividad] determina la página que se usa en [!DNL Adobe Target] [!UICONTROL Segmentación de experiencias] (XT) y que se abre en la [!UICONTROL Compositor de experiencias visuales] (VEC) o [!UICONTROL Compositor de experiencias basadas en formularios] cuando se diseña la actividad.

1. Cuando se le pida, al [crear una actividad XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique la URL de la actividad. Escriba la URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.
   >
   >De forma predeterminada, el VEC o el Compositor de experiencias basadas en formularios abre la página que se ha especificado en su [Configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.
   >
   >Si indica una dirección URL de un sitio que no incluye el código de JavaScript de Target Standard, no podrá seleccionar elementos de página.

1. (Condicional) Para mostrar una página diferente después de que se abra el VEC, haga clic en **[!UICONTROL Configurar]**, seleccione **[!UICONTROL Entrega de páginas]** y especifique la URL en el campo [!UICONTROL URL].

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

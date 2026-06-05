---
keywords: url de actividad;url;url diferente
description: Descubra cómo establecer la [!UICONTROL URL de actividad] para definir páginas de prueba y garantizar un diseño de prueba preciso.
title: ¿Qué es la URL de actividad en una actividad A/B?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 305
ht-degree: 38%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña con [!DNL Adobe Target].

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] coinciden.

## Especifique una dirección URL diferente

De manera predeterminada, [!UICONTROL Compositor de experiencias visuales] abre la página especificada en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. (Condicional) Para mostrar una página diferente después de que se abra [!UICONTROL Compositor de experiencias visuales], en la página **[!UICONTROL Experiencias]**, haga clic en **[!UICONTROL Configurar]** en la parte superior de la página y, a continuación, seleccione **[!UICONTROL Entrega de páginas]**.

1. Especifique la dirección URL en el campo **[!UICONTROL URL]**.

1. (Condicional) Haga clic en **[!UICONTROL Agregar regla]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox
   * Personalizado

   Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

   Si escribe una dirección URL de un sitio que no incluye el código JavaScript de [!DNL Target], no podrá seleccionar elementos de página.

   De manera predeterminada, el [!UICONTROL compositor de experiencias visuales] no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Render usando JavaScript]** si quiere modificar esos elementos usando [!UICONTROL Compositor de experiencias visuales].—>

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

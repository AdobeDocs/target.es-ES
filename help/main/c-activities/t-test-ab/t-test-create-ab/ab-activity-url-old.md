---
keywords: url de actividad;url;url diferente
description: Aprenda a especificar la dirección URL de actividad que determina la página que se usa en la prueba y que se abre cuando esta se diseña con [!DNL Adobe Target].
title: ¿Qué es la URL de actividad en una actividad A/B?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 55%
---
# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña con Adobe Target.

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] coinciden.

## Especifique una dirección URL diferente

De manera predeterminada, [!UICONTROL Compositor de experiencias visuales] abre la página especificada en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. Para mostrar una página diferente después de que se abra [!UICONTROL Compositor de experiencias visuales], en la página **[!UICONTROL Experiencias]**, haga clic en el icono de engranaje **[!UICONTROL Configurar]** y, a continuación, seleccione **[!UICONTROL Entrega de páginas]**.

1. Especifique la dirección URL en el campo **[!UICONTROL URL]**.

   ![Cuadro de diálogo Entrega de páginas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Si introduce una dirección URL de un sitio que no incluye el código estándar [!DNL Target] de JavaScript, no podrá seleccionar elementos de la página.

De manera predeterminada, el [!UICONTROL compositor de experiencias visuales] no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

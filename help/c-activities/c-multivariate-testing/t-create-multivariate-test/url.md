---
description: La URL de actividad determina la página que se utiliza en la prueba multivariable (MVT) y que se abre cuando la prueba está diseñada en Target.
keywords: Segmentación
seo-description: La URL de actividad determina la página que se utiliza en la prueba multivariable (MVT) y que se abre cuando la prueba está diseñada en Adobe Target.
seo-title: Dirección URL de actividad
solution: Target
title: Dirección URL de actividad
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL de actividad{#activity-url}

The activity URL determines the page that is used in the [!UICONTROL Multivariate Test] (MVT), and that opens when the test is designed in [!DNL Adobe Target].

When prompted during [activity creation](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Puede especificar una página diferente durante la creación de la actividad.

To display a different page after the VEC opens, click the **[!UICONTROL Configure]** icon, then select **[!UICONTROL Page Delivery]**, then specify the URL.

![Cuadro de diálogo Entrega de página](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Haga clic en **[!UICONTROL Agregar regla de plantilla]para agregar más páginas o secciones a la actividad.**

Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

* Dirección URL
* Dominio
* Ruta
* Fragmento hash (#)
* Consulta
* Parámetro

Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

Haga clic en **[!UICONTROL Guardar]cuando haya finalizado.**

>[!NOTE]
>
>Si escribe una dirección URL de un sitio que no incluye el código de JavaScript de Target Standard, no podrá seleccionar elementos de página.

De forma predeterminada, el VEC no permite cambios en elementos que contengan JavaScript, como banners rotativos. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.
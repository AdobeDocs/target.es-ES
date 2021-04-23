---
keywords: Pruebas multivariable;dirección url de la actividad
description: Aprenda a especificar la dirección URL de actividad que determina la página que se usa en la prueba y que se abre cuando la actividad de prueba multivariable se diseña con Adobe Target.
title: ¿Qué es la URL de actividad en una actividad multivariada (MVT)?
feature: Pruebas multivariable
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 79%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la [!UICONTROL Prueba multivariada] (MVT) y que se abre cuando se diseña la prueba en [!DNL Adobe Target].

Cuando se le pida durante la [creación de la actividad](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Siguiente]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.

De forma predeterminada, el [!UICONTROL Compositor de experiencias visuales] (VEC) abre la página que se especifica en la configuración del [Compositor de experiencias visuales](/help/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

Para mostrar una página diferente después de que se abra el VEC, haga clic en el icono **[!UICONTROL Configurar]**, luego seleccione **[!UICONTROL Entrega de página]** y, a continuación, especifique la dirección URL.

![Cuadro de diálogo Entrega de páginas](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Haga clic en **[!UICONTROL Agregar regla de plantilla]** para agregar más páginas o secciones a la actividad.

Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

* Dirección URL
* Dominio
* Ruta
* Fragmento hash (#)
* Consulta
* Parámetro

Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

>[!NOTE]
>
>Si escribe una dirección URL de un sitio que no incluye el código de JavaScript de Target Standard, no podrá seleccionar elementos de página.

De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

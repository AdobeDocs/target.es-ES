---
keywords: Pruebas multivariable;URL de actividad
description: Obtenga información sobre cómo especificar la dirección URL de la actividad que determina la página que se usa en la prueba y que se abre cuando la variable [!UICONTROL Prueba multivariable] la actividad está diseñada con [!DNL Adobe Target].
title: ¿Qué es la URL de actividad en un? [!UICONTROL Prueba multivariable] ¿Actividad de (MVT)?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 70%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la [!UICONTROL Prueba multivariada] (MVT) y que se abre cuando se diseña la prueba en [!DNL Adobe Target].

Cuando se le pida durante la [creación de la actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Siguiente]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.

De manera predeterminada, el [!UICONTROL Compositor de experiencias visuales] (VEC) abre la página que se ha especificado en [Configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

Para mostrar una página diferente después de que se abra el VEC, haga clic en el icono **[!UICONTROL Configurar]**, luego seleccione **[!UICONTROL Entrega de página]** y, a continuación, especifique la dirección URL.

![Cuadro de diálogo Entrega de páginas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Haga clic en **[!UICONTROL Agregar regla de plantilla]** para agregar más páginas o secciones a la actividad.

Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

* Dirección URL
* Dominio
* Ruta
* Fragmento hash (#)
* Consulta
* Parámetro

Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con AND.

Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

>[!NOTE]
>
>Si escribe una dirección URL de un sitio que no incluye el [!DNL Target] Código JavaScript, no se pueden seleccionar elementos de página.

De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

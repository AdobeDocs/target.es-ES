---
keywords: activity url;url;different url
description: La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña.
title: Dirección URL de actividad
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 93%

---


# URL de actividad{#activity-url}

La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña.

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://www.adobe.com`] coinciden.

## Especifique una dirección URL diferente

By default, the [!UICONTROL Visual Experience Composer] opens the page that is specified in your [Visual Experience Composer settings](/help/administrating-target/visual-experience-composer-set-up.md)
. Puede especificar una página diferente durante la creación de la actividad.

Para visualizar una página diferente tras abrir el [!UICONTROL Compositor de experiencias visuales], haga clic en el icono de engranaje **[!UICONTROL Configurar]** y, a continuación, seleccione **[!UICONTROL Publicación de página]**. Introduzca la URL en el campo URL de actividad.

![Cuadro de diálogo Entrega de páginas](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Haga clic en **[!UICONTROL Agregar regla de plantilla]** para agregar más páginas o secciones a la actividad.

Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

* Dirección URL
* Dominio
* Ruta
* Fragmento hash (#)
* Consulta
* Parámetro de mbox

Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

>[!NOTE]
>
>Si introduce una dirección URL de un sitio que no incluye el código estándar [!DNL Target] de JavaScript, no podrá seleccionar elementos de la página.

De manera predeterminada, el [!UICONTROL compositor de experiencias visuales] no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

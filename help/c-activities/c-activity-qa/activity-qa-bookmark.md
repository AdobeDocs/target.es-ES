---
keywords: qa;preview;bookmarklet;preview links
description: Información para ayudarle a utilizar el bookmarklet de control de calidad de Adobe Target para forzar el Destinatario a que lo libere del modo de control de calidad.
title: bookmarklet de control de calidad de actividad para Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 43%

---


# Bookmarklet de control de calidad de la actividad{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

Como el modo de [control de calidad](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) es persistente, después de examinar un sitio web en modo de control de calidad, la sesión de debe caducar o tiene que indicar a que lo libere del modo de control de calidad antes de poder ver su sitio como lo vería un visitante. [!DNL Target][!DNL Target] Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

A continuación, el bookmarklet debe aparecer en la barra de herramientas para su reutilización.

>[!NOTE]
>
>El proceso para crear un bookmarklet varía según el tipo y la versión del explorador. Consulte la ayuda del explorador o busque en Internet para obtener instrucciones específicas.

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

Por ejemplo:

`https://www.mysite.com/?at_preview_token=`

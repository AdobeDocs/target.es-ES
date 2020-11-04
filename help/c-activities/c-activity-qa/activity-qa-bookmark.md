---
keywords: qa;preview;bookmarklet;preview links
description: Información para ayudarle a utilizar el bookmarklet de control de calidad de Adobe Target para obligar al Destinatario a liberarlo del modo de control de calidad.
title: bookmarklet de control de calidad de actividad para Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 6278a01928fcb9dd0b34d7a8b5313f09f1e8da0f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# Bookmarklet de control de calidad de la actividad{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>El proceso para crear un bookmarklet varía según el tipo y la versión del explorador. Consulte la ayuda del explorador o busque en Internet para obtener instrucciones específicas.

## bookmarklet de control de calidad de actividad para at.js 1.*x* 

Como el modo de [control de calidad](/help/c-activities/c-activity-qa/activity-qa.md) es persistente, después de examinar un sitio web en modo de control de calidad, la sesión de debe caducar o tiene que indicar a que lo libere del modo de control de calidad antes de poder ver su sitio como lo vería un visitante. [!DNL Target][!DNL Target] Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

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

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

Por ejemplo:

`https://www.mysite.com/?at_preview_token=`

## bookmarklet de control de calidad de actividad para at.js 2.*x* 

A diferencia de at.js 1.*x*, at.js 2.*x* no admite cookies de terceros y el modo de control de calidad solo es fijo para el dominio de origen (mediante una cookie de origen configurada por at.js). Por lo tanto, en at.js 2.*x*, la sesión del modo de control de calidad se administra solamente en el lado del cliente y no se envían cookies del modo de control de calidad a Destinatario.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## Uso del bookmarklet de control de calidad de la Actividad

Haga clic en el bookmarklet en la barra de herramientas del explorador.


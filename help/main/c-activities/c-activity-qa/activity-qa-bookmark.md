---
keywords: control de calidad;vista previa;bookmarklet;vínculos de vista previa
description: Aprenda a usar el bookmarklet Adobe [!DNL Target] QA para forzar [!DNL Target] a liberarlo del modo de control de calidad.
title: ¿Cómo utilizo el bookmarklet de control de calidad de la actividad?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 13%

---

# Bookmarklet de control de calidad de la actividad

Información para ayudarlo a usar el bookmarklet de control de calidad [!DNL Target] a fin de obligar a [!DNL Target] a liberarlo del modo de control de calidad.

>[!NOTE]
>
>El proceso para crear un bookmarklet varía según el tipo y la versión del explorador. Consulte la ayuda del explorador o busque en Internet para obtener instrucciones específicas.

## bookmarklet de control de calidad de la actividad para at.js 1.*x*  

Como el [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) es persistente, después de examinar un sitio web en modo de control de calidad, la sesión [!DNL Target] debe caducar o tiene que indicar a [!DNL Target] que lo libere del modo de control de calidad antes de poder ver el sitio como lo vería un visitante. Use el bookmarklet QA [!DNL Target] para sacarse del modo de control de calidad.

Para usar el bookmarklet QA [!DNL Target], cree un bookmarklet que contenga el siguiente código JavaScript y agréguelo a la barra de herramientas de Marcadores del explorador:

```javascript
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

También puede forzar la salida manual del modo de control de calidad cargando una página en su sitio con el parámetro `at_preview_token` con un valor vacío.

Por ejemplo:

`https://www.mysite.com/?at_preview_token=`

## bookmarklet de control de calidad de la actividad para at.js 2.*x*  

A diferencia de at.js 1.*x*, at.js 2.*x* no admite cookies de terceros y el modo de control de calidad solo es adhesivo para el dominio de origen (mediante una cookie de origen establecida por at.js). Por lo tanto, en at.js 2.*x*, la sesión en modo de control de calidad solo se administra en el lado del cliente y no se envían cookies en modo de control de calidad a Target.

Para usar el bookmarklet QA [!DNL Target], cree un bookmarklet que contenga el siguiente código JavaScript y agréguelo a la barra de herramientas de Marcadores del explorador:

```javascript
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

## Usar el bookmarklet de control de calidad de actividad

Haga clic en el bookmarklet de la barra de herramientas del explorador.

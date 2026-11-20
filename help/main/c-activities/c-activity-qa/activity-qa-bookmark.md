---
keywords: control de calidad;vista previa;bookmarklet;vínculos de vista previa
description: Aprenda a utilizar el bookmarklet QA [!DNL Target] de Adobe para forzar a [!DNL Target] a liberarlo del modo de control de calidad.
title: ¿Cómo utilizo el bookmarklet de control de calidad de la actividad?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%
---
# Bookmarklet de control de calidad de la actividad {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a usar el bookmarklet de control de calidad [!DNL Target] para salir del modo **[!UICONTROL control de calidad de la actividad]** y ver su sitio como si fuera un visitante habitual.

>[!ENDSHADEBOX]

Después de examinar un sitio web en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), el modo de control de calidad persiste en todas las páginas hasta que caduque la sesión de [!DNL Target]. Un bookmarklet es un marcador del explorador que ejecuta JavaScript. El bookmarklet de control de calidad [!DNL Target] obliga a [!DNL Target] a liberarlo del modo de control de calidad, para que no tenga que esperar a que la sesión caduque. Utilice la versión que coincida con la versión de at.js implementada en el sitio.

>[!NOTE]
>
>El proceso para crear un bookmarklet varía según el tipo y la versión del explorador. Consulte la ayuda de su navegador o busque en Internet para obtener instrucciones específicas.

## bookmarklet de control de calidad de la actividad para at.js 1.*x*

Para usar el bookmarklet QA [!DNL Target], cree un bookmarklet que contenga el siguiente código JavaScript y agréguelo a la barra de herramientas Marcadores del explorador:

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

También puede forzar la salida manual del modo de control de calidad cargando una página en su sitio con el parámetro `at_preview_token` establecido en un valor vacío. Por ejemplo:

`https://www.mysite.com/?at_preview_token=`

## bookmarklet de control de calidad de la actividad para at.js 2.*x*

A diferencia de at.js 1.*x*, at.js 2.*x* no admite cookies de terceros. El modo de control de calidad solo persiste para el dominio de origen, mediante una cookie de origen configurada por at.js. Como resultado, la sesión en modo de control de calidad se administra solamente en el lado del cliente y no se envían cookies en modo de control de calidad a [!DNL Target].

Para usar el bookmarklet QA [!DNL Target], cree un bookmarklet que contenga el siguiente código JavaScript y agréguelo a la barra de herramientas Marcadores del explorador:

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## Usar el bookmarklet de control de calidad de actividad

Después de añadir el bookmarklet que coincide con su versión de at.js a su explorador, utilícelo siempre que desee dejar el modo de control de calidad:

1. Abra cualquier página del sitio mientras esté en modo de control de calidad.
1. Haga clic en el bookmarklet de la barra de herramientas marcadores del explorador.
1. Cargue una página del sitio. [!DNL Target] libera la sesión del modo de control de calidad y el sitio se muestra tal como lo hace para un visitante normal.

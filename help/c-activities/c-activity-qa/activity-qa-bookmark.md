---
description: Información para ayudarlo a usar el bookmarklet de control de calidad de Target para obligar a Target a liberarlo del modo de control de calidad.
keywords: control de calidad;vista previa;bookmarklet;vínculos de vista previa
seo-description: Información para ayudarlo a usar el bookmarklet de control de calidad de Target para obligar a Target a liberarlo del modo de control de calidad.
seo-title: Bookmarklet de control de calidad de la actividad
solution: Target
title: Bookmarklet de control de calidad de la actividad
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Bookmarklet de control de calidad de la actividad{#activity-qa-bookmarklet}

Información para ayudarlo a usar el bookmarklet de control de calidad de Target para obligar a Target a liberarlo del modo de control de calidad.

Como el modo de [control de calidad](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) es persistente, después de examinar un sitio web en modo de control de calidad, la sesión de Target debe caducar o tiene que indicar a Target que lo libere del modo de control de calidad antes de poder ver su sitio como lo vería un visitante. Use el bookmarklet QA Target para sacarse del modo de control de caliad.

Para utilizar el bookmarklet QA de Target, cree un bookmarklet que contenga el siguiente código JavaScript y agréguelo a la barra de herramientas de Marcadores del explorador:

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

También puede forzar la salida manual del modo de control de calidad cargando una página en su sitio con un parámetro `at_preview_token` con valor en blanco (por ejemplo, `https://www.mysite.com/?at_preview_token=`).

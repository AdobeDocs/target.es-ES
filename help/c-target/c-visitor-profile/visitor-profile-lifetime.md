---
keywords: Información general y referencia
description: De forma predeterminada, los perfiles de los visitantes se almacenan durante 14 días. Esta duración del perfil puede ampliarse.
title: Duración del perfil del visitante
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 83%

---


# Duración del perfil del visitante{#visitor-profile-lifetime}

De forma predeterminada, un perfil de visitante caduca después de 14 días de inactividad para ese visitante. Esta duración del perfil puede ampliarse.

[Póngase en contacto con ClientCare o con su consultor de Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para extender la duración del perfil sin coste adicional. La duración puede llegar a establecerse en 90 días.

La biblioteca JavaScript de [!DNL Target] que utiliza ([!DNL at.js] o [!DNL mbox.js]) determina si necesita o no descargar un nuevo archivo:

| Biblioteca de segmentos | Detalles |
|--- |--- |
| at.js | No es necesario que descargue un nuevo archivo at.js si su perfil se extiende más allá del valor predeterminado. |
| mbox.js | Si se amplía la duración del perfil más allá de los 14 días predeterminados, debe descargar un nuevo archivo mbox.js después de que su asesor o ClientCare hayan cambiado su configuración. La extensión de la cookie para admitir la duración del perfil modificada se incluye en el archivo mbox.js actualizado. Cuando empiece a usar la biblioteca nueva, las duraciones del perfil de los visitantes se actualizarán. |

La fecha de caducidad no se restablece para los perfiles existentes. Si un visitante previo no regresa durante 15 días, ese perfil caduca. Si un visitante previo regresa antes de que el perfil de dos semanas original caduque, el perfil se restablece con la duración extendida. Todos los perfiles del visitante nuevos se establecen con el perfil de duración extendida.

En el siguiente escenario, suponga que uno o ambos sitios están implementados con mbox.js, lo que requiere una actualización de código después de actualizar el perfil. Si ambos sitios están bajo un único código de cliente y un visitante visita ambos sitios, el perfil se establece en la duración de los perfiles en el sitio que se visitó por última vez. Por ejemplo, si el Sitio 1 cuenta con una duración de perfil de 84 días y el Sitio 2 tiene una duración de 14 días; y el visitante visita el Sitio 1 y a continuación visita el Sitio 2, el perfil de este visitante caducará tras 14 días de inactividad. Si el visitante visita el Sitio 1 después de visitar el Sitio 2, el perfil caducará tras 84 días de inactividad.

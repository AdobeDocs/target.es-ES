---
keywords: Overview and Reference
description: De forma predeterminada, los perfiles de los visitantes se almacenan durante 14 días. Esta duración del perfil puede ampliarse.
title: Duración del perfil del visitante
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---


# Duración del perfil del visitante{#visitor-profile-lifetime}

De forma predeterminada, un perfil de visitante caduca después de 14 días de inactividad para ese visitante. Esta duración del perfil puede ampliarse.

[Póngase en contacto con ClientCare o con su consultor de Adobe](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para extender la duración del perfil sin coste adicional. La duración puede llegar a establecerse en 90 días.

La biblioteca JavaScript de [!DNL Target] que utiliza ([!DNL at.js] o [!DNL mbox.js]) determina si necesita o no descargar un nuevo archivo:

| Biblioteca de segmentos | Detalles |
|--- |--- |
| at.js | No es necesario que descargue un nuevo archivo at.js si su perfil se extiende más allá del valor predeterminado. |
| mbox.js | Si se amplía la duración del perfil más allá de los 14 días predeterminados, debe descargar un nuevo archivo mbox.js después de que su asesor o ClientCare hayan cambiado su configuración. La extensión de la cookie para admitir la duración del perfil modificada se incluye en el archivo mbox.js actualizado. Cuando empiece a usar la biblioteca nueva, las duraciones del perfil de los visitantes se actualizarán. |

La fecha de caducidad no se restablece para los perfiles existentes. Si un visitante previo no regresa durante 15 días, ese perfil caduca. Si un visitante previo regresa antes de que el perfil de dos semanas original caduque, el perfil se restablece con la duración extendida. Todos los perfiles del visitante nuevos se establecen con el perfil de duración extendida.

Si dispone de dos sitios bajo un único código de cliente y un visitante visita ambos sitios, el perfil se establece a la duración de perfil del sitio que visitó en último lugar. Por ejemplo, si el Sitio 1 cuenta con una duración de perfil de 84 días y el Sitio 2 tiene una duración de 14 días; y el visitante visita el Sitio 1 y a continuación visita el Sitio 2, el perfil de este visitante caducará tras 14 días de inactividad. Si el visitante visita el Sitio 1 después de visitar el Sitio 2, el perfil caducará tras 84 días de inactividad.

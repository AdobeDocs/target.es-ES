---
keywords: Información general y referencia
description: Obtenga más información sobre cuándo caduca un perfil del visitante (de forma predeterminada, 14 días) en Adobe Target. La duración del perfil se puede ampliar poniéndose en contacto con Adobe Client Care.
title: ¿Qué es la duración del perfil del visitante y puedo ampliarlo?
feature: Audiencias
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 73%

---

# Duración del perfil del visitante

De forma predeterminada, un perfil de visitante caduca después de 14 días de inactividad para ese visitante. Esta duración del perfil puede ampliarse.

[Póngase en contacto con ClientCare o con su consultor de Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para extender la duración del perfil sin coste adicional. La duración puede llegar a establecerse en 90 días.

La biblioteca JavaScript de [!DNL Target] que utiliza ([!DNL at.js] o [!DNL mbox.js]) determina si necesita o no descargar un nuevo archivo:

| Biblioteca de segmentos | Detalles |
|--- |--- |
| at.js | No es necesario que descargue un nuevo archivo at.js si su perfil se extiende más allá del valor predeterminado. |
| mbox.js | Si se amplía la duración del perfil más allá de los 14 días predeterminados, debe descargar un nuevo archivo mbox.js después de que su asesor o ClientCare hayan cambiado su configuración. La extensión de la cookie para admitir la duración del perfil modificada se incluye en el archivo mbox.js actualizado. Cuando empiece a usar la biblioteca nueva, las duraciones del perfil de los visitantes se actualizarán. |

La fecha de caducidad no se restablece para los perfiles existentes. Si un visitante previo no regresa durante 15 días, ese perfil caduca. Si un visitante previo regresa antes de que el perfil de dos semanas original caduque, el perfil se restablece con la duración extendida. Todos los perfiles del visitante nuevos se establecen con el perfil de duración extendida.

En el siguiente escenario, supongamos que uno o ambos sitios se implementan con mbox.js, lo que requiere una actualización de código después de actualizar el perfil. Si ambos sitios están bajo un único código de cliente y un visitante visita ambos, el perfil se establece en la duración de los perfiles del sitio que visitó en último lugar. Por ejemplo, si el Sitio 1 cuenta con una duración de perfil de 84 días y el Sitio 2 tiene una duración de 14 días; y el visitante visita el Sitio 1 y a continuación visita el Sitio 2, el perfil de este visitante caducará tras 14 días de inactividad. Si el visitante visita el Sitio 1 después de visitar el Sitio 2, el perfil caducará tras 84 días de inactividad.

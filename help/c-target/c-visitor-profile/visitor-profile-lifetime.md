---
keywords: Información general y referencia
description: Obtenga más información sobre cuándo caduca un perfil del visitante en [!DNL Adobe Target].
title: ¿Qué es la duración del perfil del visitante y puedo ampliarlo?
feature: Audiencias
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 45%

---

# Duración del perfil del visitante

De forma predeterminada, un perfil de visitante en [!DNL Adobe Target] caduca tras 14 días de inactividad para ese visitante. Esta duración del perfil puede ampliarse.

[Póngase en contacto con ClientCare o con su consultor de Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para extender la duración del perfil sin coste adicional. La duración puede llegar a establecerse en 90 días.

No es necesario descargar un nuevo archivo [!DNL Platform Web SDK] o un archivo at.js si el perfil se amplía más allá del valor predeterminado.

La fecha de caducidad no se restablece para los perfiles existentes. Si un visitante previo no regresa durante 15 días, ese perfil caduca. Si un visitante previo regresa antes de que el perfil de dos semanas original caduque, el perfil se restablece con la duración extendida. Todos los perfiles del visitante nuevos se establecen con el perfil de duración extendida.

En el siguiente escenario, suponga que uno o ambos sitios están implementados con [!DNL Platform Web SDK]. Si ambos sitios están bajo un único código de cliente y un visitante visita ambos, el perfil se establece en la duración de los perfiles del sitio que visitó en último lugar. Por ejemplo, supongamos que el Sitio 1 tiene una duración de perfil de 84 días. El sitio 2 tiene una duración de 14 días. Si el visitante visita el Sitio 1 y luego el Sitio 2, el perfil de ese visitante caduca tras 14 días de inactividad. Si el visitante visita el Sitio 1 después de visitar el Sitio 2, el perfil caducará tras 84 días de inactividad.

---
keywords: Información general y referencia
description: Obtenga más información acerca de cuándo caduca un perfil de visitante en  [!DNL Adobe Target].
title: ¿Cuál es la duración del perfil del visitante y puedo ampliarlo?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
TQID: https://experienceleague.adobe.com/yMfacKgQthOmpfhFiuO-jGGPWZh5VrliOSi0TQ-uis0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 62%

---

# Duración del perfil del visitante

De manera predeterminada, un perfil de visitante en [!DNL Adobe Target] caduca después de 14 días de inactividad para ese visitante. Esta duración del perfil puede ampliarse.

[Póngase en contacto con ClientCare o con su consultor de Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para extender la duración del perfil sin coste adicional. La duración puede llegar a establecerse en 90 días.

No es necesario que descargue un nuevo archivo [!DNL Platform Web SDK] o at.js si su perfil se extiende más allá del valor predeterminado.

La fecha de caducidad no se restablece para los perfiles existentes. Si un visitante previo no regresa durante 15 días, ese perfil caduca. Si un visitante previo regresa antes de que el perfil de dos semanas original caduque, el perfil se restablece con la duración extendida. Todos los perfiles del visitante nuevos se establecen con el perfil de duración extendida.

---
description: Información sobre los complementos at.js admitidos y no admitidos en Target.
keywords: complementos de at.js;complementos admitidos;complementos no admitidos;ttMeta;ttmeta;mboxTrack
seo-description: Información sobre los complementos at.js admitidos y no admitidos para Adobe Target.
seo-title: Complementos de at.js para Adobe Target
solution: Target
title: Complementos de at.js
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: c3afa420f33f98d7c4bb332acdef7a248fe4670a

---


# at.js plug-ins{#at-js-plug-ins}

Información sobre los complementos at.js admitidos y no admitidos en Adobe Target.

Muchas personas han compilado complementos personalizados y complementos de respuesta para [!DNL mbox.js]. Puede que [!DNL at.js] no admita estos complementos personalizados sin que se actualicen.

Si está usando un complemento que no aparece en la lista aquí y le gustaría conocer el estado, póngase en contacto con el representante de la cuenta.

Este es el estado actual de algunos de los complementos que muchos clientes usan cuando trabajan con [!DNL at.js]:

| Complemento | Detalles |
|--- |--- |
| mboxTrack | No compatible.<br>Esto se sustituye por la función [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Actualice los complementos para aplicar la nueva función.<br>Consulte la página de [integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Plugin de copia de seguridad de perfil persistente | No compatible.<br>Este complemento se consideró obsoleto cuando la duración del perfil de Target se amplió de dos semanas a 90 días. Consulte la fecha de caducidad de su cookie de mbox para ver la configuración de duración del perfil definida en su cuenta.<br>Póngase en contacto con ClientCare si le gustaría extender la duración del perfil a 90 días. |
| ttMeta | Old SiteCatalyst plugins should be disabled and replaced with [Adobe Analytics as the reporting source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). El complemento ttMeta debería deshabilitarse y reemplazarse con [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |
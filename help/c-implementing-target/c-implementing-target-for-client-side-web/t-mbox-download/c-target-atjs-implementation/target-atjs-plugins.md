---
description: Información sobre los complementos compatibles e incompatibles de at.js.
keywords: complementos de at.js;complementos compatibles;complementos incompatibles; Ttmeta; ttmeta; Mboxtrack
seo-description: Información sobre los complementos compatibles y no compatibles de at. js para Adobe Target.
seo-title: Complementos de at. js para Adobe Target
solution: Target
title: Complementos de at.js
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: 6908038449c9f172fcd509ca9c0616bee5a7674f

---


# at.js plug-ins{#at-js-plug-ins}

Información sobre los complementos compatibles e incompatibles de at.js.

Muchas personas han compilado complementos personalizados y complementos de respuesta para [!DNL mbox.js]. Puede que [!DNL at.js] no admita estos complementos personalizados sin que se actualicen.

Si está usando un complemento que no aparece en la lista aquí y le gustaría conocer el estado, póngase en contacto con el representante de la cuenta.

Este es el estado actual de algunos de los complementos que muchos clientes usan cuando trabajan con [!DNL at.js]:

| Complemento | Detalles |
|--- |--- |
| mboxTrack | No compatible.<br>Esto se sustituye por la función [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Actualice los complementos para aplicar la nueva función.<br>Consulte la página de [integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Plugin de copia de seguridad de perfil persistente | No compatible.<br>Este complemento se consideró obsoleto cuando la duración del perfil de Target se amplió de dos semanas a 90 días. Consulte la fecha de caducidad de su cookie de mbox para ver la configuración de duración del perfil definida en su cuenta.<br>Póngase en contacto con ClientCare si le gustaría extender la duración del perfil a 90 días. |
| ttMeta | No compatible.<br>En lugar de este complemento, use [tokens de respuesta](/help/administrating-target/response-tokens.md). |
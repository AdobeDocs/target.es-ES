---
keywords: at.js plugins;supported plugins;unsupported plugins;ttMeta;ttmeta;mboxTrack
description: Información sobre los complementos compatibles y no compatibles de at.js para Adobe Target.
title: Complementos de at.js para Adobe Target
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Complementos de at.js

Información sobre los complementos compatibles y no compatibles de at.js en Adobe Target.

Muchas personas han compilado complementos personalizados y complementos de respuesta para [!DNL mbox.js]. Puede que [!DNL at.js] no admita estos complementos personalizados sin que se actualicen.

Si está usando un complemento que no aparece en la lista aquí y le gustaría conocer el estado, póngase en contacto con el representante de la cuenta.

Este es el estado actual de algunos de los complementos que muchos clientes usan cuando trabajan con [!DNL at.js]:

| Complemento | Detalles |
|--- |--- |
| mboxTrack | No compatible.<br>Esto se sustituye por la función [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Actualice los complementos para aplicar la nueva función.<br>Consulte la página de [integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Plugin de copia de seguridad de perfil persistente | No compatible.<br>Este complemento se consideró obsoleto cuando la duración del perfil de Target se amplió de dos semanas a 90 días. Consulte la fecha de caducidad de su cookie de mbox para ver la configuración de duración del perfil definida en su cuenta.<br>Póngase en contacto con ClientCare si le gustaría extender la duración del perfil a 90 días. |
| ttMeta | Los antiguos complementos de SiteCatalyst deben deshabilitarse y reemplazarse con [Adobe Analytics como Fuente de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). El complemento ttMeta debería deshabilitarse y reemplazarse con [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |
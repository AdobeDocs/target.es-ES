---
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
keywords: client care;cname;programa certificado;nombre canónico;cookies;certificado
seo-description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
seo-title: CNAME y Adobe Target
solution: Target
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 72260f1bf82dfeab2582add69111439498ad5eb8

---


# CNAME y Adobe Target{#cname-and-adobe-target}

Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target. Para gestionar mejor los problemas de bloqueo de publicidad, se utiliza un CNAME para que se realicen llamadas a un dominio propiedad del cliente en lugar de un dominio propiedad de Adobe.

Realice los pasos siguientes para solicitar asistencia de CNAME en Target:

1. Abra un  [ticket de atención al cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) solicitando asistencia de CNAME para sus llamadas de Adobe Target.
1. Inscríbase en el [programa Adobe Managed Certificate (AMC)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) y siga los pasos de implementación que se proporcionan en la guía [!DNL Adobe Analytics]*Cookies de origen*.

   El programa AMC ayuda a eliminar el esfuerzo y la confusión que experimentan los clientes al implementar cookies de origen. Después de inscribirse en este programa, Adobe comprará y emitirá el certificado para instalarlo en servidores seguros.

   >[!NOTE]
   >
   >Es necesario configurar CNAME antes de inscribirse en el programa AMC.

1. Tras completar las tareas anteriores, debe actualizar `serverDomain` el nuevo CNAME en at. js.

## Vídeo de capacitación: Cookies individuales y uso de certificados administrados de Adobe

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. La conversación del programa Certificado gestionado de Adobe comienza a las 10:21.

[Adobe Analytics: Cookies personales y uso de certificados administrados de Adobe](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)

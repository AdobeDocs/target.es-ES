---
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
keywords: client care;cname;programa certificado;nombre canónico;cookies;certificado; amc; certificado administrado de Adobe
seo-description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
seo-title: CNAME y Adobe Target
solution: Target
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME y Adobe Target {#cname-and-adobe-target}

Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en [!DNL Target]. Para gestionar mejor los problemas de bloqueo de publicidad o las políticas de cookies relacionadas con ITP, se utiliza un CNAME para que se realicen llamadas a un dominio propiedad del cliente en lugar de un dominio propiedad de Adobe.

Realice los pasos siguientes para solicitar asistencia de CNAME en [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Cree registros CNAME (consulte las instrucciones más abajo).

   Una vez recibidos el ticket, un especialista de FPSSL deberá proporcionarle un par de registros CNAME. Estos registros deben configurarse en el servidor DNS de su empresa antes de que Adobe pueda adquirir el certificado en su nombre.

   CNAMES será similar al siguiente ejemplo:

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. Cuando estos CNAMES estén en su sitio, Adobe trabajará con digicert para adquirir e instalar un certificado en los servidores de producción de Adobe.

1. Tras completar las tareas anteriores, debe actualizar `serverDomain` el nuevo CNAME en at. js.

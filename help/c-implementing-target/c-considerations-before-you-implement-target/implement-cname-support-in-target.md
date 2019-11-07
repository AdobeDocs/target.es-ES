---
keywords: client care;cname;programa de certificado;nombre canónico;cookies;certificado;amc;certificado administrado por adobe
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CNAME y Adobe Target {#cname-and-adobe-target}

Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en [!DNL Target]. Para gestionar mejor los problemas de bloqueo de anuncios o las directivas de cookies relacionadas con ITP, se utiliza un CNAME de modo que las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de Adobe.

Realice los pasos siguientes para solicitar asistencia de CNAME en [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Cree registros CNAME (consulte las instrucciones a continuación).

   Al recibir la entrada, un especialista en FPSSL le proporcionará un par de registros CNAME. Estos registros deben configurarse en el servidor DNS de su empresa para que Adobe pueda comprar el certificado en su nombre.

   CNAMES será similar al siguiente ejemplo:

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. Cuando estos CNAMES estén establecidos, Adobe trabajará con DigiCert para adquirir e instalar un certificado en los servidores de producción de Adobe.

1. Cuando haya completado las tareas anteriores, debe actualizar `serverDomain` al nuevo CNAME en at.js.

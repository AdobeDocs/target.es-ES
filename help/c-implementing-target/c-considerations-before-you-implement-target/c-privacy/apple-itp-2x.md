---
keywords: apple;ITP;intelligent tracking prevention
description: Información sobre la compatibilidad de Adobe Target con ITP 2.x de Apple mediante la biblioteca 4.3 de ID de Experience Cloud (ECID).
title: Compatibilidad con Adobe Target y Apple ITP
feature: privacy and security
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 52%

---


# Prevención inteligente del seguimiento de Apple (ITP) 2.x

Prevención inteligente del seguimiento (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que fue en 2017, iba orientada al uso de cookies por terceros. De hecho, Apple bloqueó toda la información sobre cookies de terceros, lo cual a su vez causó problemas graves para las empresas de tecnología de anuncios y de marketing, ya que las cookies de terceros se utilizan generalmente para rastrear visitantes y recopilar sus datos. Ahora Apple busca imponer limitaciones y restricciones sobre cómo se utilizan las cookies de origen en Safari.

Estas versiones de ITP incluyen las restricciones siguientes:

| Versión | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Las cookies del lado del cliente restringidas que se colocan en el explorador mediante la API `document.cookie` con una caducidad de siete días.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Se ha reducido drásticamente la caducidad de siete días a un día.<br>Publicado el miércoles, 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Se han eliminado varias soluciones alternativas, como el uso de localStorage o el uso de JavaScript `Document.referrer property`.<br>Publicado el 23 de septiembre de 2019. |

## What is the impact to me as an Adobe Target customer? {#impact}

[!DNL Target] le proporciona bibliotecas JavaScript para que las implemente en sus páginas, de modo que [!DNL Target] pueda facilitar una personalización en tiempo real para sus visitantes. Existen tres bibliotecas de Target JavaScript ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

Apple ITP 2.x tiene un impacto [!DNL Target] en las siguientes áreas:

| Impacto | Detalles |
| --- | --- |
| Aumento potencial del número de visitantes únicos | Debido a que la ventana de caducidad está configurada en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), es posible que vea un aumento de visitantes exclusivos procedentes de los exploradores Safari. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. La nueva cookie [!DNL Target] supone un nuevo visitante único aunque el usuario sea el mismo. |
| Reducción de los periodos retroactivos de las actividades [!DNL Target] | Los perfiles de visitante para las actividades [!DNL Target] pueden tener un período retroactivo reducido para la toma de decisiones. Las cookies [!DNL Target] se aprovechan para identificar a un visitante y almacenar atributos de perfil de usuario para la personalización. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |
| Secuencias de comandos de perfil basadas en 3rdPartyID | Debido a que la ventana de caducidad está configurada en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), los scripts [de](/help/c-target/c-visitor-profile/profile-parameters.md) perfil basados en la cookie 3rdPartyID dejarán de funcionar al caducar. |
| Direcciones URL de control de calidad/Previsualización en dispositivos iOS | Debido a que la ventana de caducidad está configurada en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), las direcciones URL [de](/help/c-activities/c-activity-qa/activity-qa.md) control de calidad/Previsualización dejarán de funcionar al caducar porque las direcciones URL están basadas en la cookie 3rdPartyID. |

## ¿Esto afectará a mi implementación actual de [!DNL Target]?

En un navegador Safari, vaya hasta el sitio web en el que tenga una biblioteca JavaScript de [!DNL Target]. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Si utiliza la biblioteca Experience Cloud ID (ECID) además de la biblioteca JavaScript de Target, su implementación se verá afectada de las formas enumeradas en este artículo: [Impacto de Safari ITP 2.1 para clientes de Adobe Experience Cloud y Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## ¿Cómo puedo mitigar el impacto de futuras versiones de ITP 2.x en el Destinatario?

Para mitigar el impacto de las futuras versiones de ITP 2.x en el Destinatario, complete las siguientes tareas:

1. Implemente la biblioteca Experience Cloud ID (ECID) en sus páginas.

   La biblioteca ECID activa el sistema de identificación de personas para las soluciones principales de Experience Cloud. La biblioteca ECID permite identificar a los visitantes del mismo sitio y sus datos en diferentes soluciones de Experience Cloud al asignar identificadores únicos y persistentes. La biblioteca ECID se actualizará frecuentemente para ayudarle a mitigar cualquier cambio relacionado con ITP que afecte a su implementación.

   Para ITP 2.x, la biblioteca [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) debe utilizarse para la mitigación.

1. Use el CNAME e inscríbase en el programa de Adobe Analytics&#39; Managed Certificate.

   Después de instalar la biblioteca ECID 4.3.0+, puede aprovechar el CNAME y el programa de Managed Certificate de Adobe Analytics. Este programa permite implementar de forma gratuita un certificado de origen para cookies de origen sin coste. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Después de implementar una biblioteca de Target JavaScript junto con la biblioteca ECID versión 4.3.0+ e inscribirse en el programa de Adobe Managed Certificate para aprovechar CNAME, tendrá un plan de mitigación sólido y a largo plazo para los cambios relacionados con ITP.

Mientras el sector realiza avances para crear una web más segura para los consumidores, [!DNL Adobe Target] está absolutamente comprometido a ofrecer experiencias personalizadas sin dejar de cumplir y superar las expectativas de privacidad de los visitantes. [!DNL Adobe Target] ya ha anunciado la compatibilidad con las políticas [de Chrome del mismo sitio de](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, además de la compatibilidad con ITP 2.x de Apple.

A medida que las políticas sigan evolucionando para proteger a nuestros consumidores, [!DNL Adobe] también seguirá siendo compatible con estas iniciativas en [!DNL Target], sin dejar de ayudar a nuestros clientes a proporcionar las mejores experiencias personalizadas de vanguardia.

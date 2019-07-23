---
description: Información sobre la compatibilidad de Target con ITP 2.1 y ITP 2.2 de Apple a través de la biblioteca Experience Cloud ID (ECID) 4.3.
keywords: apple; ITP; prevención inteligente del seguimiento
seo-description: Información sobre la compatibilidad de Adobe Target con ITP 2.1 y ITP 2.2 de Apple a través de la biblioteca Experience Cloud ID (ECID) 4.3.
seo-title: Compatibilidad con Adobe Target y Apple ITP
solution: Target
subtopic: Primeros pasos
title: Apple ITP 2. x
topic: Standard
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple Intelligent Tracking Prevention (ITP) 2. x

Intelligent Tracking Prevention (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que fue en 2017, segmentó el uso de cookies de terceros. De hecho, Apple bloqueó toda la información sobre cookies de terceros, lo cual a su vez causaba un quebrado grave de las empresas tecnológicas de publicidad y técnicas de publicidad porque las cookies de terceros se utilizan generalmente para rastrear visitantes y recopilar datos de visitantes. Ahora Apple está avanzando para imponer limitaciones y restricciones sobre cómo se utilizan las cookies de origen en Safari.

Estas versiones de ITP incluyen las restricciones siguientes:

| Versión  | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Se redujo drásticamente la caducidad de siete días a un día.<br>Publicado el 24 de abril de 2019. |

## ¿Cuál es el impacto para mí como cliente de Adobe Target?

[!DNL Target] proporciona bibliotecas JavaScript para que se implemente en sus páginas, de modo que [!DNL Target] pueda proporcionar personalización en tiempo real a los visitantes. There are three Target JavaScript libraries ([at.js 1.*x* y at. js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)y [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que ubican las cookies del lado del cliente [!DNL Target] en los navegadores de los visitantes a través `document.cookie` de la API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.1 and 2.2 and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2).

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| Impacto | Detalles |
| --- | --- |
| Aumento potencial de contadores de visitantes únicos | Debido a que la ventana de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2), es posible que vea un aumento de visitantes únicos provenientes de navegadores Safari. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | Visitor profiles for [!DNL Target] activities might have a decreased lookback period for decisioning. [!DNL Target] las cookies se aprovechan para identificar a un visitante y almacenar atributos de perfil de usuario para personalización. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. Implemente la biblioteca Experience Cloud ID (ECID) en sus páginas.

   La biblioteca ECID activa el marco de identificación de las personas para las soluciones principales de Experience Cloud. La biblioteca ECID permite identificar los mismos visitantes del sitio y sus datos en diferentes soluciones de Experience Cloud asignando identificadores únicos y persistentes. La biblioteca ECID se actualizará frecuentemente para ayudarle a mitigar cualquier cambio relacionado con ITP que afecte a su implementación.

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. Use el CNAME y la matriculación de Adobe en el programa de certificados administrados de Adobe Analytics.

   Después de instalar la biblioteca ECID 4.3.0 +, puede aprovechar el CNAME de Adobe Analytics y el programa de certificados administrados. Este programa permite implementar de forma gratuita un certificado de origen para cookies de origen. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

Después de implementar una biblioteca de Target JavaScript junto con la biblioteca ECID v 4.3.0 + y registrarse en el programa de certificados administrados de Adobe para aprovechar CNAME, tendrá un plan de mitigación robusto y a largo plazo para los cambios relacionados con ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] ya ha anunciado la compatibilidad con [samesite Chrome de](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, además de la compatibilidad con ITP 2.1 y ITP 2.2 de Apple.

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.

---
description: Información sobre la compatibilidad de Target con ITP 2.1 e ITP 2.2 de Apple mediante la biblioteca 4.3 de Experience Cloud ID (ECID).
keywords: apple;ITP;prevención inteligente del seguimiento
seo-description: Información sobre la compatibilidad de Adobe Target con ITP 2.1 e ITP 2.2 de Apple a través de la biblioteca 4.3 de Experience Cloud ID (ECID).
seo-title: Adobe Target and Apple ITP support
solution: Target
subtopic: Primeros pasos
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que se publicó en 2017, se centró en el uso de cookies de terceros. De hecho, Apple bloqueó todas las cookies de terceros, lo que a su vez causó un gran dolor de cabeza para las empresas de tecnología de publicidad y de tecnología de publicidad, ya que las cookies de terceros generalmente se utilizan para rastrear a los visitantes y recopilar datos de los visitantes. Ahora, Apple va a colocar limitaciones y restricciones en el uso de cookies de origen dentro de Safari.

Estas versiones de ITP incluyen las siguientes restricciones:

| Versión | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Se han reducido las cookies del lado del cliente que se colocan en el navegador mediante la `document.cookie` API a una caducidad de siete días.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Redujo drásticamente la tapa de 7 días a un día.<br>Publicado el 24 de abril de 2019. |

## ¿Cuál es el impacto para mí como cliente de Adobe Target?

[!DNL Target] proporciona bibliotecas de JavaScript para que las implemente en las páginas y así [!DNL Target] pueda ofrecer personalización en tiempo real a los visitantes. Existen tres bibliotecas de Target JavaScript ([at.js 1).*x* y at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)y [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que colocan [!DNL Target] cookies de cliente en los exploradores de los visitantes a través de la `document.cookie` API. Como resultado, [!DNL Target] las cookies se ven afectadas por el ITP 2.1 y 2.2 de Apple y caducan al cabo de siete días (con ITP 2.1) y al cabo de un día (con ITP 2.2).

Apple ITP 2.1 and 2.1 impact  in the following areas:[!DNL Target]

| Impacto | Detalles |
| --- | --- |
| Posible aumento de los recuentos de visitantes únicos | Debido a que la ventana de caducidad está configurada en siete días (con ITP 2.1) y un día (con ITP 2.2), es posible que vea un aumento de visitantes únicos procedentes de los exploradores Safari. Si los visitantes vuelven a visitar su dominio después de siete días (ITP 2.1) o un día (ITP 2.2), [!DNL Target] se ve obligado a colocar una nueva [!DNL Target] cookie en su dominio en lugar de la cookie caducada. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Menores períodos de búsqueda de [!DNL Target] actividades | Visitor profiles for  activities might have a decreased lookback period for decisioning. [!DNL Target] [!DNL Target] cookies are leveraged to identity a visitor and store user profile attributes for personalization. Given that  cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged  cookie cannot be used for decisioning.[!DNL Target][!DNL Target] |

## Is my current implementation of  impacted?[!DNL Target]

In a Safari browser, navigate to your website on which you have a  JavaScript library. [!DNL Target] If you see a  cookie set in the context of a CNAME, such as , then you are not impacted by ITP 2.1 or 2.2.[!DNL Target]`analytics.company.com`

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers.[](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to ?[!DNL Target]

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to , complete the following tasks:[!DNL Target]

1. Deploy the Experience Cloud ID (ECID) library to your pages.

   The ECID library enables the people identification framework for Experience Cloud Core solutions. La biblioteca ECID le permite identificar a los mismos visitantes del sitio y sus datos en diferentes soluciones de Experience Cloud mediante la asignación de identificadores únicos y persistentes. La biblioteca ECID se actualizará con frecuencia para ayudarle a mitigar los cambios relacionados con ITP que afecten a su implementación.

   Para ITP 2.1 e ITP 2.2, la biblioteca [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) debe utilizarse para la mitigación.

1. Utilice el CNAME de Adobe e inscríbase en el programa de certificados administrados de Adobe Analytics.

   Después de instalar la biblioteca ECID 4.3.0 o posterior, puede aprovechar el CNAME y el programa de certificados administrados de Adobe Analytics. This program lets you implement a first-party certificate for first-party cookies at no charge. El aprovechamiento de CNAME ayudará a [!DNL Target] los clientes a mitigar el impacto de ITP 2.1 e ITP 2.2.

   Si no aprovecha CNAME, puede iniciar el proceso hablando con el representante de su cuenta e inscribiéndose en el programa [de certificados administrados de](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)Adobe.

Después de implementar una biblioteca JavaScript de Target junto con la biblioteca ECID v4.3.0 o posterior y de inscribirse en el programa de certificados administrados de Adobe para aprovechar CNAME, tendrá un plan de mitigación sólido y a largo plazo para los cambios relacionados con ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] ya ha anunciado la compatibilidad con las políticas [de Chrome del mismo sitio de](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, además de la compatibilidad con ITP 2.1 y ITP 2.2 de Apple.

As policies continue to evolve to protect our consumers,  will also continue to support these initiatives in , while helping our customers provide the best-in-class personalized experiences.[!DNL Adobe][!DNL Target]

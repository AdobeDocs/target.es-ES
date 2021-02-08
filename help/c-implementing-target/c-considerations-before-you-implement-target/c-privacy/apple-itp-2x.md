---
keywords: apple;ITP;prevención inteligente del seguimiento;id de la nube de experiencias;ecid
description: Conozca Adobe Target y el impacto de la iniciativa de prevención inteligente del seguimiento (ITP) de Apple que busca proteger la privacidad de los usuarios de Safari.
title: ¿Cómo gestiona Destinatario la compatibilidad con Apple ITP?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 50%

---


# Prevención inteligente del seguimiento de Apple (ITP) 2.x

Información sobre la compatibilidad de [!DNL Adobe Target] con ITP 2.x de Apple a través de la biblioteca 4.3 de ID de Experience Cloud (ECID).

Prevención inteligente del seguimiento (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que fue en 2017, iba orientada al uso de cookies por terceros. De hecho, Apple bloqueó toda la información sobre cookies de terceros, lo cual a su vez causó problemas graves para las empresas de tecnología de anuncios y de marketing, ya que las cookies de terceros se utilizan generalmente para rastrear visitantes y recopilar sus datos. Ahora Apple busca imponer limitaciones y restricciones sobre cómo se utilizan las cookies de origen en Safari.

Estas versiones de ITP incluyen las restricciones siguientes:

| Versión | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Las cookies del lado del cliente restringidas que se colocan en el explorador mediante la API `document.cookie` con una caducidad de siete días.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Se ha reducido drásticamente la caducidad de siete días a un día.<br>Publicado el miércoles, 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Se han eliminado varias soluciones alternativas, como el uso de localStorage o el uso de JavaScript `Document.referrer property`.<br>Publicado el 23 de septiembre de 2019. |

## ¿Cuál es el impacto para mí como cliente de Adobe Target? {#impact}

[!DNL Target] le proporciona bibliotecas JavaScript para que las implemente en sus páginas, de modo que [!DNL Target] pueda facilitar una personalización en tiempo real para sus visitantes. Existen tres bibliotecas de Target JavaScript ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que colocan las cookies del cliente [!DNL Target] en los exploradores de sus visitantes mediante la API `document.cookie`. Como resultado, las cookies [!DNL Target] se ven afectadas por el ITP 2.x de Apple y caducan al cabo de siete días (con ITP 2.1) y al cabo de un día (con ITP 2.2 e ITP 2.3).

Apple ITP 2.x afecta a [!DNL Target] en las siguientes áreas:

| Impacto | Detalles |
| --- | --- |
| Aumento potencial del número de visitantes únicos | Debido a que la ventana de caducidad está configurada en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), es posible que vea un aumento de visitantes exclusivos procedentes de los exploradores Safari. Si sus visitantes vuelven a visitar su dominio después de siete días (ITP 2.1) o un día (ITP 2.2 e ITP 2.3), [!DNL Target] se ve obligado a colocar una nueva [!DNL Target] cookie en su dominio en lugar de la cookie caducada. La nueva cookie [!DNL Target] supone un nuevo visitante único aunque el usuario sea el mismo. |
| Reducción de los periodos retroactivos de las actividades [!DNL Target] | Los perfiles de visitante para las actividades [!DNL Target] pueden tener un período retroactivo reducido para la toma de decisiones. Las cookies [!DNL Target] se aprovechan para identificar a un visitante y almacenar atributos de perfil de usuario para la personalización. Dado que las cookies [!DNL Target] pueden caducar en Safari después de siete días (ITP 2.1) o de un día (ITP 2.2 y 2.3), los datos de perfil del usuario que se vincularon a la cookie [!DNL Target] purgada no pueden utilizarse para la toma de decisiones. |
| Secuencias de comandos de perfil basadas en 3rdPartyID | Debido a que la ventana de caducidad se ha establecido en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [las secuencias de comandos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) basadas en la cookie 3rdPartyID dejarán de funcionar al caducar. |
| Direcciones URL de control de calidad/Previsualización en dispositivos iOS | Debido a que la ventana de caducidad se ha establecido en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [las direcciones URL de control de calidad/Previsualización](/help/c-activities/c-activity-qa/activity-qa.md) dejarán de funcionar al caducar porque las direcciones URL se basan en la cookie 3rdPartyID. |

## ¿Esto afectará a mi implementación actual de [!DNL Target]?

En un navegador Safari, vaya hasta el sitio web en el que tenga una biblioteca JavaScript de [!DNL Target]. Si ve una cookie [!DNL Target] configurada en el contexto de un CNAME, como `analytics.company.com`, ITP 2.x no le afecta.

Si utiliza la biblioteca Experience Cloud ID (ECID) además de la biblioteca JavaScript de Target, su implementación se verá afectada de las formas enumeradas en este artículo: [Impacto de Safari ITP 2.1 para clientes de Adobe Experience Cloud y Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## ¿Cómo puedo mitigar el impacto de futuras versiones de ITP 2.x en el Destinatario?

Para mitigar el impacto de las futuras versiones de ITP 2.x en el Destinatario, complete las siguientes tareas:

1. Implemente la biblioteca Experience Cloud ID (ECID) en sus páginas.

   La biblioteca ECID activa el sistema de identificación de personas para las soluciones principales de Experience Cloud. La biblioteca ECID permite identificar a los visitantes del mismo sitio y sus datos en diferentes soluciones de Experience Cloud al asignar identificadores únicos y persistentes. La biblioteca ECID se actualizará frecuentemente para ayudarle a mitigar cualquier cambio relacionado con ITP que afecte a su implementación.

   Para ITP 2.x, [ECID library 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) debe utilizarse para la mitigación.

1. Use el CNAME e inscríbase en el programa de Adobe Analytics&#39; Managed Certificate.

   Después de instalar la biblioteca ECID 4.3.0+, puede aprovechar el CNAME y el programa de Managed Certificate de Adobe Analytics. Este programa permite implementar de forma gratuita un certificado de origen para cookies de origen sin coste. El aprovechamiento de CNAME ayudará a [!DNL Target] clientes a mitigar el impacto de ITP 2.x.

   Si no aprovecha CNAME, puede realizar el inicio del proceso hablando con su representante de cuentas e inscribiéndose en el [Programa de certificados administrados por Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Después de implementar una biblioteca de Target JavaScript junto con la biblioteca ECID versión 4.3.0+ e inscribirse en el programa de Adobe Managed Certificate para aprovechar CNAME, tendrá un plan de mitigación sólido y a largo plazo para los cambios relacionados con ITP.

Mientras el sector realiza avances para crear una web más segura para los consumidores, [!DNL Adobe Target] está absolutamente comprometido a ofrecer experiencias personalizadas sin dejar de cumplir y superar las expectativas de privacidad de los visitantes. [!DNL Adobe Target] ya ha anunciado compatibilidad con las  [políticas de Chrome SameSite de ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, además de la compatibilidad con ITP 2.x de Apple.

A medida que las políticas sigan evolucionando para proteger a nuestros consumidores, [!DNL Adobe] también seguirá siendo compatible con estas iniciativas en [!DNL Target], sin dejar de ayudar a nuestros clientes a proporcionar las mejores experiencias personalizadas de vanguardia.

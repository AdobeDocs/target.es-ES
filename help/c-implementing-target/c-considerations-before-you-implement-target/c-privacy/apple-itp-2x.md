---
keywords: apple;ITP;prevención inteligente del seguimiento;experience cloud id;ecid
description: Obtenga información sobre el Adobe [!DNL Target] y el impacto de la iniciativa Prevención inteligente del seguimiento de Apple (ITP) que busca proteger la privacidad de los usuarios de Safari.
title: ¿Cómo gestiona [!DNL Target] la compatibilidad con Apple ITP?
feature: Privacidad y seguridad
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 52%

---

# Prevención inteligente del seguimiento de Apple (ITP) 2.x

Información sobre la compatibilidad de [!DNL Adobe Target] con ITP 2.x de Apple a través de la biblioteca 4.3 del ID de Experience Cloud (ECID).

Prevención inteligente del seguimiento (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que fue en 2017, iba orientada al uso de cookies por terceros. De hecho, Apple bloqueó toda la información sobre cookies de terceros, lo cual a su vez causó problemas graves para las empresas de tecnología de anuncios y de marketing, ya que las cookies de terceros se utilizan generalmente para rastrear visitantes y recopilar sus datos. Ahora Apple busca imponer limitaciones y restricciones sobre cómo se utilizan las cookies de origen en Safari.

Estas versiones de ITP incluyen las restricciones siguientes:

| Versión | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Las cookies del lado del cliente restringidas que se colocan en el explorador mediante la API `document.cookie` con una caducidad de siete días.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Se ha reducido drásticamente la caducidad de siete días a un día.<br>Publicado el miércoles, 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Se han eliminado varias soluciones, como usar localStorage o JavaScript `Document.referrer property`.<br>Publicado el 23 de septiembre de 2019. |

## ¿Cuál es el impacto para mí como cliente [!DNL Target] de Adobe? {#impact}

[!DNL Target] le proporciona bibliotecas JavaScript para que las implemente en sus páginas, de modo que [!DNL Target] pueda facilitar una personalización en tiempo real para sus visitantes. Existen tres bibliotecas de Target JavaScript at.js 1.x, at.js 2.x, que colocan las cookies del lado del cliente [!DNL Target] en los navegadores de los visitantes a través de la API `document.cookie` . Como resultado, las cookies [!DNL Target] se ven afectadas por ITP 2.x de Apple y caducarán pasados siete días (con ITP 2.1) y después de un día (con ITP 2.2 e ITP 2.3).

Apple ITP 2.x afecta a [!DNL Target] en las siguientes áreas:

| Impacto | Detalles |
| --- | --- |
| Aumento potencial del número de visitantes únicos | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), es posible que vea un aumento de visitantes únicos procedentes de navegadores Safari. Si los visitantes vuelven a su dominio después de siete días (ITP 2.1) o un día (ITP 2.2 e ITP 2.3), [!DNL Target] se ve obligado a colocar una nueva cookie [!DNL Target] en su dominio en lugar de la cookie caducada. La nueva cookie [!DNL Target] supone un nuevo visitante único aunque el usuario sea el mismo. |
| Reducción de los periodos retroactivos de las actividades [!DNL Target] | Los perfiles de visitante para las actividades [!DNL Target] pueden tener un período retroactivo reducido para la toma de decisiones. Las cookies [!DNL Target] se aprovechan para identificar a un visitante y almacenar atributos de perfil de usuario para la personalización. Dado que las cookies [!DNL Target] pueden caducar en Safari después de siete días (ITP 2.1) o un día (ITP 2.2 y 2.3), los datos de perfil de usuario asociados a la cookie [!DNL Target] depurada no se pueden usar para la toma de decisiones. |
| Scripts de perfil basados en 3rdPartyID | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [scripts de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) basados en la cookie 3rdPartyID dejarán de funcionar al expirar. |
| URL de control de calidad/vista previa en dispositivos iOS | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [QA/Preview URLs](/help/c-activities/c-activity-qa/activity-qa.md) dejará de funcionar al expirar, ya que las direcciones URL se basan en la cookie 3rdPartyID. |

## ¿Esto afectará a mi implementación actual de [!DNL Target]?

En un navegador Safari, vaya hasta el sitio web en el que tenga una biblioteca JavaScript de [!DNL Target]. Si ve una cookie [!DNL Target] configurada en el contexto de un CNAME como `analytics.company.com`, ITP 2.x no le afectará.

Si utiliza la biblioteca Experience Cloud ID (ECID) además de la biblioteca JavaScript de Target, su implementación se verá afectada de las formas enumeradas en este artículo: [Impacto de Safari ITP 2.1 para clientes de Adobe Experience Cloud y Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## ¿Cómo puedo mitigar el impacto de las futuras versiones de ITP 2.x en Target?

Para mitigar el impacto de las futuras versiones de ITP 2.x en Target, complete las siguientes tareas:

1. Implemente la biblioteca Experience Cloud ID (ECID) en sus páginas.

   La biblioteca ECID activa el sistema de identificación de personas para las soluciones principales de Experience Cloud. La biblioteca ECID permite identificar a los visitantes del mismo sitio y sus datos en diferentes soluciones de Experience Cloud al asignar identificadores únicos y persistentes. La biblioteca ECID se actualizará frecuentemente para ayudarle a mitigar cualquier cambio relacionado con ITP que afecte a su implementación.

   Para ITP 2.x, [ECID library 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html?lang=es) debe utilizarse para la mitigación.

1. Use el CNAME e inscríbase en el programa de Adobe Analytics&#39; Managed Certificate.

   Después de instalar la biblioteca ECID 4.3.0+, puede aprovechar el CNAME y el programa de Managed Certificate de Adobe Analytics. Este programa permite implementar de forma gratuita un certificado de origen para cookies de origen sin coste. El uso de CNAME ayudará a los clientes [!DNL Target] a mitigar el impacto de ITP 2.x.

   Si no está aprovechando el CNAME, puede iniciar el proceso hablando con su representante de cuentas e inscribiéndose en el [Programa de certificados administrados de Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Después de implementar una biblioteca de Target JavaScript junto con la biblioteca ECID versión 4.3.0+ e inscribirse en el programa de Adobe Managed Certificate para aprovechar CNAME, tendrá un plan de mitigación sólido y a largo plazo para los cambios relacionados con ITP.

Mientras el sector realiza avances para crear una web más segura para los consumidores, [!DNL Adobe Target] está absolutamente comprometido a ofrecer experiencias personalizadas sin dejar de cumplir y superar las expectativas de privacidad de los visitantes. [!DNL Adobe Target] ya ha anunciado la compatibilidad con las directivas de SameSite Chrome de  [ ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, además de la compatibilidad con ITP 2.x de Apple.

A medida que las políticas sigan evolucionando para proteger a nuestros consumidores, [!DNL Adobe] también seguirá siendo compatible con estas iniciativas en [!DNL Target], sin dejar de ayudar a nuestros clientes a proporcionar las mejores experiencias personalizadas de vanguardia.

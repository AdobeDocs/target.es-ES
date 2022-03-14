---
keywords: apple;ITP;prevención inteligente del seguimiento;experience cloud id;ecid;itp
description: Más información sobre Adobe [!DNL Target] y el impacto de la iniciativa Prevención inteligente del seguimiento de Apple (ITP) que busca proteger la privacidad de los usuarios de Safari.
title: How [!DNL Target] ¿Gestionar la compatibilidad con ITP de Apple?
feature: Privacy & Security
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 38%

---

# Prevención inteligente del seguimiento de Apple (ITP) 2.x

Prevención inteligente del seguimiento (ITP) es la iniciativa de Apple para proteger la privacidad de los usuarios de Safari. La primera versión de ITP, que fue en 2017, iba orientada al uso de cookies por terceros. De hecho, Apple bloqueó toda la información sobre cookies de terceros, lo cual a su vez causó problemas graves para las empresas de tecnología de anuncios y de marketing, ya que las cookies de terceros se utilizan generalmente para rastrear visitantes y recopilar sus datos. Ahora Apple busca imponer limitaciones y restricciones sobre cómo se utilizan las cookies de origen en Safari.

Estas versiones de ITP incluyen las restricciones siguientes:

| Versión | Detalles |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Las cookies del lado del cliente restringidas que se colocan en el explorador mediante la API `document.cookie` con una caducidad de siete días.<br>Publicado el 21 de febrero de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Se ha reducido drásticamente la caducidad de siete días a un día.<br>Publicado el miércoles, 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-3-2/) | Se han eliminado varias soluciones, como usar localStorage o JavaScript `Document.referrer property`.<br>Publicado el 23 de septiembre de 2019.<br>Función de defensa de encubrimiento CNAME para ITP lanzada en Safari 14, macOS Big Sur, Catalina, Mojave, iOS 14 y iPadOS 14. Todas las cookies creadas por una respuesta HTTP oculta por CNAME de terceros se configurarán para que caduquen en siete días.<br>Anunciado el 12 de noviembre de 2020. |

## ¿Cuál es el impacto para mí como Adobe? [!DNL Target] cliente? {#impact}

[!DNL Target] le proporciona bibliotecas JavaScript para que las implemente en sus páginas, de modo que [!DNL Target] pueda facilitar una personalización en tiempo real para sus visitantes. Existen tres bibliotecas de Target JavaScript at.js 1.x, at.js 2.x, que ubican al lado del cliente [!DNL Target] en los navegadores de los visitantes a través de la variable `document.cookie` API. Como resultado, [!DNL Target] las cookies se ven afectadas por ITP 2.1, 2.2 y 2.3 de Apple y caducarán pasados siete días (con ITP 2.1) y después de un día (con ITP 2.2 e ITP 2.3).

Impacto de Apple ITP 2.x [!DNL Target] en las siguientes áreas:

| Impacto | Detalles |
| --- | --- |
| Aumento potencial del número de visitantes únicos | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), es posible que vea un aumento de visitantes únicos procedentes de navegadores Safari. Si los visitantes vuelven al dominio después de siete días (ITP 2.1) o un día (ITP 2.2 e ITP 2.3), [!DNL Target] se ve obligado a colocar un [!DNL Target] en su dominio en lugar de la cookie caducada. La nueva cookie [!DNL Target] supone un nuevo visitante único aunque el usuario sea el mismo. |
| Reducción de los periodos retroactivos de las actividades [!DNL Target] | Los perfiles de visitante para las actividades [!DNL Target] pueden tener un período retroactivo reducido para la toma de decisiones. Las cookies [!DNL Target] se aprovechan para identificar a un visitante y almacenar atributos de perfil de usuario para la personalización. Dado que [!DNL Target] las cookies pueden caducar en Safari después de siete días (ITP 2.1) o un día (ITP 2.2 y 2.3), los datos de perfil de usuario asociados a la depuración [!DNL Target] no se puede usar para la toma de decisiones. |
| Scripts de perfil basados en 3rdPartyID | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [scripts de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md) basado en la cookie 3rdPartyID dejará de funcionar cuando caduque. |
| URL de control de calidad/vista previa en dispositivos iOS | Debido a que el periodo de caducidad se establece en siete días (con ITP 2.1) y un día (con ITP 2.2 e ITP 2.3), [Direcciones URL de control de calidad/vista previa](/help/main/c-activities/c-activity-qa/activity-qa.md) dejará de funcionar cuando caduque porque las direcciones URL se basan en la cookie 3rdPartyID . |

## ¿Esto afectará a mi implementación actual de [!DNL Target]?

Si utiliza la biblioteca de ID de Experience Cloud (ECID) además de la variable [!DNL Target] biblioteca JavaScript, su implementación se verá afectada de las formas enumeradas en este artículo: [Impacto de Safari ITP 2.1 en clientes de Adobe Experience Cloud y Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

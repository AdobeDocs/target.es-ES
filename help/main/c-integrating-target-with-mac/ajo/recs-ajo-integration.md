---
keywords: ajo;adobe recorrido optimizer;integración de target de adobe recorrido optimizer;recommendations;recomendaciones de target;integración
description: Integrar [!DNL Adobe Target Recommendations] con [!DNL Adobe Journey Optimizer].
title: ¿Cómo se usa [!DNL Target Recommendations] en recorridos de clientes que utilizan [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
source-git-commit: 1faedc44c4f8f95000b666af8eecaf1eca5bf48d
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# Integrar [!DNL Adobe Target Recommendations] y [!DNL Adobe Journey Optimizer]

Este artículo explica casos de uso e información para ayudarle a configurar la integración entre [!DNL Adobe Target Recommendation] y [!DNL Adobe Journey Optimizer] para ofrecer a sus clientes experiencias conectadas, contextuales y personalizadas.

## Requisitos previos  

Para usar la variable [!DNL Target Recommendations] y [!DNL Adobe Journey Optimizer] integración, necesita lo siguiente:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementado con la variable [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}.

  La función no está disponible con un [!DNL Target Standard] licencia o al implementar [!DNL Target] con at.js u otro [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Ejemplos de uso

Los siguientes son solo dos casos de uso posibles para la integración de [!DNL Target Recommendations] con [!DNL Adobe Journey Optimizer]:

* **[!DNL Customer Journey Optimizer]envía un correo electrónico personalizado después del abandono del carro de compras**: este caso de uso se basa en un cliente que visita un sitio web, coloca artículos en el carro de compras y luego abandona el sitio sin completar el proceso de compra.

  Supongamos, por ejemplo, que un visitante visita el sitio web de una empresa de ropa y coloca dos abrigos de invierno y una sudadera en el carro de compras. A continuación, el visitante se distrae y abandona el sitio web o no está seguro de las compras y cierra el explorador o la aplicación.

  Después de un período de tiempo especificado, quizá unas pocas horas o un día, una acción personalizada en [!DNL Adobe Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar el contenido del carro de compras abandonado. [!DNL Adobe Journey Optimizer] a continuación, envía a este visitante un correo electrónico personalizado como recordatorio de que el proceso de compra no se ha completado, junto con imágenes y vínculos a los artículos abandonados.

* **[!DNL Customer Journey Optimizer]envía un correo electrónico después de la visita al sitio mediante el perfil de usuario**: este caso de uso se basa en un cliente que visita un sitio web, ve varios artículos y luego abandona el sitio sin colocar artículos en el carro de compras.

  Después de un período de tiempo especificado, una acción personalizada en [!DNL Adobe Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar qué artículos vio este visitante con el [!DNL Adobe Experience Cloud Identifier] (EDID). [!DNL Adobe Journey Optimizer] a continuación, envía a este visitante un correo electrónico personalizado como recordatorio de que el proceso de compra no se ha completado, junto con imágenes y vínculos a los artículos abandonados.


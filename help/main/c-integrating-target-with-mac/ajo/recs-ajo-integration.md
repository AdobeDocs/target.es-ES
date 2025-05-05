---
keywords: ajo;adobe recorrido optimizer;integración de target de adobe recorrido optimizer;recommendations;recomendaciones de target;integración
description: Integrar [!DNL Adobe Target Recommendations] con [!DNL Adobe Journey Optimizer].
title: ¿Cómo uso  [!DNL Target Recommendations] en recorridos de clientes que usan [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# Integrar [!DNL Adobe Target Recommendations] y [!DNL Adobe Journey Optimizer]

Este artículo proporciona casos de uso e instrucciones para integrar [!DNL Adobe Target Recommendations] con [!DNL Adobe Journey Optimizer], lo que le permite ofrecer experiencias del cliente conectadas, contextuales y personalizadas.

Esta integración le ayuda a lograr más conversiones y a ver el impacto de los mensajes de correo electrónico que contienen recomendaciones personalizadas.

## Requisitos previos  

Para usar la integración de [!DNL Target Recommendations] y [!DNL Adobe Journey Optimizer], necesita lo siguiente:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementó mediante el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Esta característica no está disponible con una licencia de [!DNL Target Standard] o al implementar [!DNL Target] con at.js u otros SDK de [!DNL Target].

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target=_blank}.

## Ejemplos de uso

Estos casos de uso son solo algunos casos de uso posibles para integrar [!DNL Target Recommendations] con [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico personalizado después del abandono del carro de compras**: este caso de uso se basa en un cliente que visita un sitio web, coloca artículos en el carro de compras y luego abandona el sitio sin completar el proceso de compra.

  Supongamos, por ejemplo, que un visitante visita el sitio web de una empresa de ropa y coloca dos abrigos de invierno y una sudadera en el carro de compras. A continuación, el visitante se distrae y abandona el sitio web o no está seguro de las compras y cierra el explorador o la aplicación.

  Después de un período especificado, quizás unas pocas horas o un día, una acción personalizada en [!DNL Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar el contenido del carro de compras abandonado mediante un algoritmo de [recomendaciones basadas en el carro de compras](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Journey Optimizer] envía a este visitante un correo electrónico personalizado como recordatorio de que el proceso de compra no se ha completado, junto con imágenes y vínculos a los elementos abandonados.

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico masivo después de las visitas al sitio para recordar a los visitantes qué artículos se vieron**: Este caso de uso se basa en los visitantes que visitan un sitio web, ven varios artículos y luego abandonan el sitio o la aplicación sin colocar artículos en el carro de compras.

  Después de un período especificado, una acción personalizada en [!DNL Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar qué elementos vio cada visitante, usando el [!DNL Adobe Experience Cloud Identifier] (EDID) de cada visitante, el perfil [!DNL Target] del visitante y un algoritmo [basado en el usuario](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). A continuación, [!DNL Adobe Journey Optimizer] envía a cada miembro de la audiencia cualificada un correo electrónico personalizado con imágenes y vínculos a los artículos vistos de cada visitante para que el visitante regrese y realice una compra.

  En este escenario, se usa el [!UICONTROL Experience Cloud Visitor ID] (ECID) y el contenido del perfil [!DNL Target] de cada visitante para generar la recomendación basada en el algoritmo visualizado recientemente.

  Supongamos, por ejemplo, que un visitante visita un sitio web de venta minorista y visualiza varios relojes. El perfil [!DNL Target] de este visitante se ha actualizado con una lista de los relojes visualizados. Usando el ECID y el perfil [!DNL Target] del visitante, [!DNL Target] envía la recomendación a [!DNL Journey Optimizer]. [!DNL Journey Optimizer] envía un correo electrónico con imágenes y vínculos a los relojes que vio el visitante mediante el algoritmo de visualizaciones recientes. Otro visitante recibe un correo electrónico personalizado con imágenes y vínculos a los artículos que vio el visitante. Cada mensaje de correo electrónico está personalizado para cada visitante.

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico masivo a los visitantes calificados después de la visita al sitio para sugerir artículos populares**: Este caso de uso se basa en un visitante que visita un sitio web, pero no ve ningún artículo en particular. El correo electrónico se envía por lotes a todos los visitantes que cumplen los requisitos para una audiencia concreta, por ejemplo:

  Supongamos que el visitante no ve ningún reloj en particular. Tal vez el visitante simplemente hizo clic en el sitio y vio páginas de categorías o entradas de blog. Como resultado, el perfil [!DNL Target] no tiene información específica sobre los artículos vistos recientemente. En este caso, [!DNL Target Recommendations] usa una [recomendación de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md) para que [!DNL Journey Optimizer] pueda enviar un mensaje de correo electrónico con imágenes y vínculos a artículos populares del sitio web para que el visitante regrese y posiblemente realice una compra.

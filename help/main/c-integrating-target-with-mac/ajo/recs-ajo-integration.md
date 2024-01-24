---
keywords: ajo;adobe recorrido optimizer;integración de target de adobe recorrido optimizer;recommendations;recomendaciones de target;integración
description: Integrar [!DNL Adobe Target Recommendations] con [!DNL Adobe Journey Optimizer].
title: ¿Cómo se usa [!DNL Target Recommendations] en recorridos de clientes que utilizan [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
source-git-commit: f0e8ec873b2cc7bb6bb03aa99d5e5e96beac3b56
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 2%

---

# Integrar [!DNL Adobe Target Recommendations] y [!DNL Adobe Journey Optimizer]

Este artículo explica casos de uso e información para ayudarle a configurar la integración entre [!DNL Adobe Target Recommendations] y [!DNL Adobe Journey Optimizer] para ofrecer a sus clientes experiencias conectadas, contextuales y personalizadas.

Esta integración puede ayudarle a lograr más conversiones y a ver el impacto de los mensajes de correo electrónico que contienen recomendaciones personalizadas.

## Requisitos previos  

Para usar la variable [!DNL Target Recommendations] y [!DNL Adobe Journey Optimizer] integración, necesita lo siguiente:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementado con la variable [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}.

  La función no está disponible con un [!DNL Target Standard] licencia o al implementar [!DNL Target] con at.js u otro [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Ejemplos de uso

Los siguientes son solo algunos casos de uso posibles para la integración de [!DNL Target Recommendations] con [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico personalizado después del abandono del carro de compras**: este caso de uso se basa en un cliente que visita un sitio web, coloca artículos en el carro de compras y luego abandona el sitio sin completar el proceso de compra.

  Supongamos, por ejemplo, que un visitante visita el sitio web de una empresa de ropa y coloca dos abrigos de invierno y una sudadera en el carro de compras. A continuación, el visitante se distrae y abandona el sitio web o no está seguro de las compras y cierra el explorador o la aplicación.

  Después de un período especificado, quizá unas pocas horas o un día, una acción personalizada en [!DNL Adobe Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar el contenido del carro de compras abandonado mediante una [recomendaciones basadas en el carro de compras](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritmo. [!DNL Adobe Journey Optimizer] a continuación, envía a este visitante un correo electrónico personalizado como recordatorio de que el proceso de compra no se ha completado, junto con imágenes y vínculos a los artículos abandonados.

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico tras la visita al sitio para recordar al visitante qué artículos se han visto**: este caso de uso se basa en un visitante que visita un sitio web, ve varios artículos y luego abandona el sitio sin colocar artículos en el carro de compras.

  Después de un período especificado, una acción personalizada en [!DNL Adobe Journey Optimizer] realiza una llamada a [!DNL Target Recommendations] para determinar qué artículos vio este visitante, utilizando el [!DNL Adobe Experience Cloud Identifier] (EDID), el del visitante [!DNL Target] perfil y una [basado en el usuario](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritmo. [!DNL Adobe Journey Optimizer] a continuación, envía a este visitante un correo electrónico personalizado con imágenes y vínculos a los artículos vistos para que el visitante vuelva al sitio web y realice una compra.

  En este escenario, la variable [!UICONTROL ID de visitante de Experience Cloud] (ECID) y el contenido de la [!DNL Target] Este perfil es el que se utiliza para generar la recomendación en función del algoritmo visualizado recientemente.

  Supongamos, por ejemplo, que un visitante visita un sitio web de venta minorista y visualiza varios relojes. El de este visitante [!DNL Target] el perfil se actualiza con una lista de los relojes visualizados. Uso del ECID y del del visitante [!DNL Target] perfil, [!DNL Target] envía la recomendación a [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] a continuación, envía un correo electrónico que contiene imágenes y vínculos a los relojes que este visitante vio mediante el algoritmo vistos recientemente.

* **[!DNL Adobe Journey Optimizer]envía un correo electrónico después de la visita al sitio para sugerir artículos populares**: este caso de uso se basa en un visitante que visita un sitio web, pero no visualiza ningún elemento en particular. A diferencia de los casos de uso anteriores, el correo electrónico se envía por lotes a todas las personas aptas para una audiencia determinada, por ejemplo.

  Supongamos que el visitante no ve ningún reloj en particular. Tal vez el visitante simplemente hizo clic en el sitio y vio páginas de categorías o entradas de blog. Como resultado, la variable [!DNL Target] el perfil no tiene información específica sobre artículos vistos recientemente. En esta situación, [!DNL Target Recommendations] puede usar un [recomendación de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md) para que [!DNL Adobe Journey Optimizer] Puede enviar un correo electrónico con imágenes y vínculos a artículos populares del sitio web para que el visitante vuelva al sitio web y posiblemente realice una compra.



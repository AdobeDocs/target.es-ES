---
keywords: SDK web de Adobe Experience Platform;sdk web de aep;sdk web;sdk;adobe experience cloud;red perimetral de platform;red perimetral de adobe experience platform;red perimetral de aep
description: Aprenda a utilizar el SDK web de Adobe Experience Platform para interactuar con los distintos servicios de Adobe Experience Cloud a través de la red perimetral de AEP.
title: ¿Cómo se implementa con el SDK web de Experience Platform?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 8%

---

# SDK web de Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (SDK web de AEP) es una biblioteca JavaScript del lado del cliente que permite a los clientes de [!DNL Adobe Experience Cloud] para interactuar con los distintos servicios del Experience Cloud (incluido [!DNL Target]) a través de la función [!UICONTROL Adobe Experience Platform Edge Network]. Además de la biblioteca JavaScript, hay un [!DNL Adobe Experience Platform] para ayudarle con las configuraciones del SDK web.

Para obtener más información, consulte los siguientes vínculos en la sección *SDK web de Adobe Experience Platform* ayuda:

* Para obtener información completa: [¿Qué es el SDK web de Adobe Experience Platform?](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* Para información específica de [!DNL Target]: [Información general de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Tutorial: Implementar Adobe Experience Cloud con el SDK web de Platform

Obtenga información sobre cómo [implementar aplicaciones Experience Cloud mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}. Para obtener información específica sobre Target, consulte [Configuración de Target con el SDK web de Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank} dentro del tutorial.

## Documentación recomendada

Además del [!DNL Platform Web SDK] documentación mencionada anteriormente, los temas de esta guía también tienen información específica para [!DNL Platform Web SDK] en lo que se refiere a [!DNL Target] funciones y funcionalidades.

| Función | Descripción/Vínculo |
| --- | --- |
| [Control de calidad de la actividad](/help/main/c-activities/c-activity-qa/activity-qa.md) | Use direcciones URL de control de calidad en [!DNL Adobe Target] para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias e informes de control de calidad que permanecen segmentados a partir de datos de actividades activas. [!UICONTROL Control de calidad de la actividad] permite probar completamente el [!DNL Target] antes de lanzarlas en directo.<br>Consulte [Compatibilidad con el modo de control de calidad de la biblioteca JavaScript de Target](/help/main/c-activities/c-activity-qa/activity-qa.md#compatibility) y [Vista previa de direcciones URL](/help/main/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que le permite crear actividades basadas en [!DNL Analytics] métricas de conversión y segmentos de audiencia. La integración de A4T le permite utilizar [!DNL Analytics] para examinar los resultados.<br>Consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) y [Pasos de implementación para una implementación del SDK web de Adobe Experience Platform](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Audiencias](/help/main/c-target/target.md) | Audiencias en [!DNL Adobe Target] determine quién ve el contenido y las experiencias en una actividad segmentada.<br>Consulte [Usar la lista Audiencias](/help/main/c-target/c-audiences/audiences.md#use-list) y [Combinación de varias audiencias](/help/main/c-target/combining-multiple-audiences.md). |
| [Creación de audiencias](/help/main/c-target/c-audiences/audiences.md) | Usar audiencias creadas en [!DNL Adobe Experience Platform] proporciona datos de clientes más completos que conducen a una personalización más impactante.<ul>Consulte [Usar audiencias de [!DNL Adobe Experience Platform]](/help/main/c-target/c-audiences/audiences.md#aep). |
| [Decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Agregue las decisiones de oferta creadas en Adobe Journey Optimizer a las actividades de Target (prueba A/B manual o segmentación de experiencias) para determinar y ofrecer la siguiente mejor oferta para sus visitantes en la web y dispositivos móviles. |
| [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Las ofertas de redireccionamiento hacen que los navegadores de los visitantes redirijan a una página nueva.<br>Consulte [¿El [!DNL Adobe Experience Platform Web SDK] ¿admite ofertas de redireccionamiento para A4T?](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Tokens de respuesta](/help/main/administrating-target/response-tokens.md) | Los tokens de respuesta le permiten enviar datos de Target a Google Analytics y otras integraciones de terceros.<br>Consulte [Envío de datos a los Google Analytics mediante el SDK web de Platform](/help/main/administrating-target/response-tokens.md#platform-web-sdk) para ver una muestra de código de cómo realizar esta tarea. |
| [Implementación de aplicación de una sola página](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) en el *Información general del SDK web de plataforma* guía. | [!UICONTROL SDK web de Adobe Experience Platform] proporciona funciones enriquecidas que equipan su negocio para ejecutar personalizaciones en tecnologías de próxima generación del lado del cliente, como aplicaciones de una sola página (SPA). |
| [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/main/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS (Seguridad de capa de transporte) le ayuda a mantener los estándares de seguridad más altos y a promover la seguridad de los datos de los clientes. |

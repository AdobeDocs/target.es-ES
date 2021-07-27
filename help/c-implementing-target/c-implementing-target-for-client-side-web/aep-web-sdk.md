---
keywords: SDK web de Adobe Experience Platform;sdk web de aep;sdk web;sdk;adobe experience cloud;red perimetral de platform;red perimetral de adobe experience platform;red perimetral de aep
description: Aprenda a utilizar el SDK web de Adobe Experience Platform para interactuar con los distintos servicios de Adobe Experience Cloud a través de la red perimetral de AEP.
title: ¿Cómo se implementa con el SDK web de Experience Platform?
feature: SDK web de AEP
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 0cfab8d09b74b3eb0ead33a0c37f9dab68a88305
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 7%

---

# SDK web de Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (SDK web de AEP) es una biblioteca JavaScript del lado del cliente que permite  [!DNL Adobe Experience Cloud] a los clientes de interactuar con los distintos servicios del Experience Cloud (incluido  [!DNL Target]) a través de la red perimetral de  [!UICONTROL Adobe Experience Platform]. Además de la biblioteca JavaScript, existe una extensión [!DNL Experience Platform Launch] que le ayudará con las configuraciones del SDK web.

Para obtener más información, consulte los siguientes vínculos en la ayuda de *Adobe Experience Platform Web SDK*:

* Para obtener información completa: [Qué es el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* Para información específica de [!DNL Target]: [Información general de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Documentación recomendada en esta guía

Además de la documentación [!DNL Platform Web SKD] mencionada anteriormente, los temas de esta guía también tienen información específica del [!DNL Platform Web SDK] en lo que se refiere a las [!DNL Target] características y funcionalidades.

| Función | Descripción/Vínculo |
| --- | --- |
| [Control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md) | Use direcciones URL de control de calidad en [!DNL Adobe Target] para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias y realización de informes de control de calidad que permanecen segmentados a partir de datos de actividades activas. [!UICONTROL El ] control de calidad de la actividad le permite probar completamente sus  [!DNL Target] actividades antes de iniciarlas en directo.<br>Consulte  [Compatibilidad con el modo de control de calidad de la biblioteca JavaScript de Target y ](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) URL de  [vista previa](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que le permite crear actividades basadas en métricas de  [!DNL Analytics] conversión y segmentos de audiencia. La integración de A4T permite utilizar informes [!DNL Analytics] para examinar los resultados.<br>Consulte  [Tipos de actividades ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) compatibles y pasos de  [implementación para una implementación](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) del SDK web de Adobe Experience Platform. |
| [Audiencias](/help/c-target/target.md) | Las audiencias en [!DNL Adobe Target] determinan quién ve el contenido y las experiencias en una actividad segmentada.<br>Consulte  [Usar la ](/help/c-target/c-audiences/audiences.md#use-list) lista Audiencias  [Combinar varias audiencias](/help/c-target/combining-multiple-audiences.md). |
| [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Las ofertas de redireccionamiento hacen que los navegadores de los visitantes redirijan a una página nueva.<br>Consulte  [¿ [!DNL Adobe Experience Platform Web SDK] Compatibilidad con ofertas de redireccionamiento para A4T?](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Tokens de respuesta](/help/administrating-target/response-tokens.md) | Los tokens de respuesta le permiten enviar datos de Target a Google Analytics y otras integraciones de terceros.<br>Consulte  [Envío de datos a los Google Analytics mediante el ](/help/administrating-target/response-tokens.md#platform-web-sdk) SDK web de Platform para ver una muestra de código de cómo realizar esta tarea. |
| [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS (Seguridad de capa de transporte) le ayuda a mantener los estándares de seguridad más altos y a promover la seguridad de los datos de los clientes. |

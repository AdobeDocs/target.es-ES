---
keywords: integración de at.js;integraciones compatibles;integraciones incompatibles;integraciones de terceros
description: Consulte las integraciones admitidas (y no admitidas) por Adobe [!DNL Target] at.js, incluido Analytics para [!DNL Target] (A4T), el servicio de ID de Experience Cloud y más.
title: ¿Qué integraciones admite at.js?
feature: at.js
role: Developer
exl-id: 148c744d-2a2b-40f8-964b-c51283ae7d1c
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 81%

---

# Integraciones de at.js

Información sobre integraciones comunes con [!DNL Target] y su estado de compatibilidad con at.js.

Si tiene una necesidad imperiosa de una integración que no se admite ni se menciona aquí, póngase en contacto con su representante de cuentas o asesor.

## Integraciones compatibles {#section_3B44A970D3FB42D1973701452C868B55}

| Integración | Detalles |
|--- |--- |
| Analytics for Target (A4T) | Consulte [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE). |
| Perfiles y audiencias (P&amp;A) | Consulte [Audiencias](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en el *Guía del usuario de los servicios principales*. |
| Servicio Experience Cloud ID | Consulte la [documentación del servicio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| Etiquetas en [!DNL Adobe Experience Platform] | Las etiquetas de [!DNL Adobe Experience Platform] son la siguiente generación de funcionalidades de administración de etiquetas de [!DNL Adobe]. Las etiquetas ofrecen a los clientes una forma sencilla de implementar y administrar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente. Consulte [Implementación [!DNL Target] using [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}. |
| Servicio en la nube Adobe Experience Manager (AEM) | El servicio en la nube AEM permite la creación de pruebas A/B y actividades de segmentación de experiencias en el flujo de trabajo de AEM. Admite at.js con Adobe Experience Manager 6.2 con FP-11577 (o posterior). Para obtener más información, consulte [Integración con Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) y seleccione su versión de AEM. |
| Fragmentos de experiencia de AEM | Los fragmentos de experiencia creados en AEM en Target le permiten combinar la facilidad de uso y la potencia de AEM con potentes capacidades de Inteligencia automatizada (AI) y Aprendizaje automático (ML) en Target para probar y personalizar experiencias a escala. AEM aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. AEM le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo: AEM ajusta automáticamente la experiencia empleando su contenido.  Consulte [fragmentos de experiencia de AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Integraciones incompatibles {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integración | Detalles |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Esta era la integración que enviaba identificadores de campaña y fórmula a [!DNL SiteCatalyst] mediante la llamada a página para que usted pudiera generar informes en la interfaz del usuario de [!DNL SiteCatalyst]. Esta funcionalidad se ha reemplazado por A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Esta era la integración que generó las llamadas de mbox denominadas `"SiteCatalyst: Event"` y `"SiteCatalyst: Purchase"` para que usted pudiera generar métricas de éxito y perfiles de usuarios basados en evars y props. Esta funcionalidad se ha reemplazado por A4T y P&amp;A. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Esta era la integración que hacía una llamada a la API del front-end para recuperar segmentos AAM y luego enviarlos como parámetros de mbox en cada llamada de mbox en la página. |

## Integraciones de terceros {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integración | Detalles |
|--- |--- |
| Otros administradores de etiquetas | at.js debería funcionar con plataformas de administración de etiquetas que no son de Adobe, pero tenga cuidado de usar características de integración personalizada que otros proveedores han desarrollado. Dichas integraciones podrían depender de funciones mbox.js internas que ya no existen en at.js. |
| Proveedores de datos externos (por ejemplo, las API de clima, Demandbase y BlueKai) | Muchos proveedores de datos de terceros utilizados para complementar el perfil de usuario de Target se pueden integrar utilizando at.js [Proveedores de datos](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)función {target=_blank} . |

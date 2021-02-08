---
keywords: aplicación móvil;preguntas más frecuentes;faq;aplicación móvil de destinatario
description: Vista las preguntas más frecuentes y sus respuestas sobre Adobe Target para aplicaciones móviles.
title: ¿Cuáles son las preguntas más frecuentes sobre Destinatario para aplicaciones móviles?
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# Preguntas más frecuentes sobre destinatario para aplicaciones móviles

Lista de las preguntas más frecuentes sobre [!DNL Target] aplicaciones móviles.

## ¿Debo utilizar [!DNL Adobe Experience Platform Launch] para implementar el SDK o puedo implementar el SDK sin utilizar [!DNL Launch]?

El SDK está disponible en la [git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/) de Adobe Marketing Cloud. Si no utiliza [Iniciar](https://experienceleague.adobe.com/docs/launch/using/overview.html), debe administrar su propio archivo de configuración y administrarlo en la aplicación.

## ¿Qué SDK están disponibles actualmente?

Los SDK de Adobe Experience Platform Mobile admiten actualmente iOS, Android y React. Para obtener más información, consulte la [guía de SDK móviles de la plataforma de Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## ¿Cuál es la frecuencia de la característica basada en la ubicación, en términos de verificación de la latitud y la longitud?

Consulte la [documentación de Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) para obtener más información.

## ¿Necesito at.js para que funcionen los SDK de Adobe Experience Platform Mobile?

No, no necesita at.js para utilizar los SDK móviles. at.js es la [!DNL Target] biblioteca JavaScript para sitios Web. Los SDK de Adobe Experience Platform Mobile son para aplicaciones móviles.

## ¿Es Destinatario Mobile una funcionalidad de SKU de producto de Adobe Target Premium?

No. Para los clientes [!DNL Adobe Target Standard], puede utilizar nuestros SDK móviles para las actividades A/B Test and Experience Targeting (XT) solo con el complemento de la aplicación móvil [!DNL Target Standard]. Si desea utilizar funciones de Recommendations o de AI en la aplicación móvil, necesita una licencia [Adobe Target Premium](/help/c-intro/intro.md#premium).

## ¿Existe una integración de aplicaciones móviles entre Adobe Experience Manager (AEM) y actividades móviles de Destinatario?

Está en nuestra hoja de ruta, pero todavía no hay cronología. Actualmente, puede compartir fragmentos de experiencia [JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM a Destinatario y podría haber posibilidades de usarlos en una actividad de aplicación móvil.

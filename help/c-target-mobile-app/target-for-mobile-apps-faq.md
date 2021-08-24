---
keywords: aplicación móvil;preguntas más frecuentes;faq;aplicación móvil de target
description: Vea las preguntas más frecuentes y sus respuestas sobre Adobe [!DNL Target] para aplicaciones móviles.
title: ¿Qué son las preguntas más frecuentes sobre [!DNL Target] para aplicaciones móviles?
feature: Implementar Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Preguntas frecuentes sobre Target para aplicaciones móviles

Lista de las preguntas más frecuentes sobre [!DNL Target] para aplicaciones móviles.

## ¿Debería utilizar etiquetas en [!DNL Adobe Experience Platform] para implementar el SDK o puedo implementar el SDK sin utilizar [!DNL Launch]?

El SDK está disponible en el [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si no utiliza etiquetas [en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html), debe administrar su propio archivo de configuración y administrarlo en la aplicación.

## ¿Qué SDK están disponibles hoy en día?

Los SDK de Adobe Experience Platform Mobile son compatibles actualmente con iOS, Android y React. Para obtener más información, consulte la [Guía de SDK para móviles de la plataforma Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## ¿Cuál es la frecuencia de la función basada en la ubicación, en términos de verificación de la latitud y longitud?

Consulte la [documentación de Adobes Places](https://placesdocs.com/places-services-by-adobe-documentation/) para obtener más información.

## ¿Necesito at.js para que funcionen los SDK de Adobe Experience Platform Mobile?

No, no es necesario que at.js utilice los SDK para móviles. at.js es la [!DNL Target] biblioteca JavaScript para sitios web. Los SDK de Adobe Experience Platform Mobile son para aplicaciones móviles.

## ¿Es [!DNL Target] Mobile una funcionalidad de Adobe [!DNL Target] Premium Product SKU únicamente?

No. Para los clientes [!DNL Adobe Target Standard], puede utilizar nuestros SDK móviles para pruebas A/B y actividades de segmentación de experiencias (XT) solo con el complemento [!DNL Target Standard] Aplicación móvil. Si desea utilizar Recommendations o funciones con tecnología de IA en la aplicación móvil, necesita una licencia [Adobe Target Premium](/help/c-intro/intro.md#premium).

## ¿Existe una integración de aplicación móvil entre las actividades móviles de Adobe Experience Manager (AEM) y [!DNL Target]?

Está en nuestra hoja de ruta, pero todavía no hay cronología. Actualmente, puede compartir JSON [Fragmentos de experiencia](/help/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM a Target y es posible que los utilice en una actividad de aplicación móvil.

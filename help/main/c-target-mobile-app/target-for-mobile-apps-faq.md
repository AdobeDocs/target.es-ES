---
keywords: aplicación móvil;preguntas más frecuentes;faq;aplicación móvil de target
description: Ver las preguntas más frecuentes y sus respuestas sobre el Adobe [!DNL Target] para aplicaciones móviles.
title: Preguntas frecuentes sobre [!DNL Target] para aplicaciones móviles?
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 3%

---

# Preguntas frecuentes sobre Target para aplicaciones móviles

Lista de las preguntas más frecuentes sobre [!DNL Target] para aplicaciones móviles.

## ¿Debería usar etiquetas en [!DNL Adobe Experience Platform] para implementar el SDK o puedo implementar el SDK sin utilizar [!DNL Launch]?

El SDK está disponible en el [Git de Adobe Marketing Cloud](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si no utiliza [etiquetas en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es), debe administrar su propio archivo de configuración y administrarlo en la aplicación.

## ¿Qué SDK están disponibles hoy en día?

Actualmente, los SDK de Adobe Experience Platform Mobile son compatibles con iOS, Android y React. Para obtener más información, consulte la [Guía de SDK para móviles de la plataforma Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## ¿Cuál es la frecuencia de la función basada en la ubicación, en términos de verificación de la latitud y longitud?

Consulte la [Documentación del servicio Adobe Places](https://experienceleague.adobe.com/docs/places/using/home.html) para obtener más información.

## ¿Necesito at.js para que funcionen los SDK de Adobe Experience Platform Mobile?

No, no es necesario que at.js utilice los SDK para móviles. at.js es la variable [!DNL Target] Biblioteca JavaScript para sitios web. Los SDK de Adobe Experience Platform Mobile son para aplicaciones móviles.

## Is [!DNL Target] Móvil de una funcionalidad de Adobe [!DNL Target] ¿Solo SKU de producto Premium?

No. Para [!DNL Adobe Target Standard] Los clientes de pueden usar nuestros SDK móviles para pruebas A/B y actividades de segmentación de experiencias (XT) solo con la variable [!DNL Target Standard] Complemento de aplicación móvil. Si desea utilizar Recommendations o funciones con tecnología de IA en la aplicación móvil, necesita un [Adobe Target Premium](/help/main/c-intro/intro.md#premium) licencia.

## ¿Existe una integración de aplicación móvil entre Adobe Experience Manager (AEM) y [!DNL Target] actividades móviles?

Está en nuestra hoja de ruta, pero todavía no hay cronología. Actualmente, puede compartir JSON [Fragmentos de experiencias](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM a Target y podría utilizarse en una actividad de aplicación móvil.

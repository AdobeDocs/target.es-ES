---
description: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles.
keywords: aplicación móvil;preguntas más frecuentes;faq;aplicación móvil de destino
seo-description: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles.
seo-title: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles
title: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# Preguntas más frecuentes sobre Target para aplicaciones móviles

Lista de preguntas más frecuentes sobre [!DNL Target] las aplicaciones móviles.

## ¿Debo usar [!DNL Adobe Experience Platform Launch] para implementar el SDK o puedo implementar el SDK sin usar [!DNL Launch]?

El SDK está disponible en el git [de](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)Adobe Marketing Cloud. Si no utiliza [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), debe administrar su propio archivo de configuración y administrarlo en la aplicación.

## ¿Puede utilizarse el Compositor de experiencias visuales (VEC) para aplicaciones móviles con la compatibilidad React-Native con el SDK v5 de la plataforma Adobe Experience?

El [VEC para aplicaciones](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) móviles nativas no admite actualmente la aplicación nativa React. Debe utilizar el Compositor de experiencias basadas en [formularios](/help/c-experiences/form-experience-composer.md).

## ¿Permite la integración del SDK de Mobile la implementación de la nueva funcionalidad móvil? ¿Puedo activar y desactivar el indicador de función sin nuevas implementaciones de código?

Sí, puede utilizar nuestro SDK móvil para desplegar funciones gradualmente.

## Para una lógica más compleja, ¿debería desarrollarme directamente en la aplicación en lugar de usar el VEC móvil? En caso afirmativo, ¿qué lenguaje de desarrollo debo utilizar?

Actualmente, el VEC admite casos de uso común como cambiar la imagen, el texto, el color, etc. Para casos de uso más avanzados, como la personalización del diseño de la aplicación, debe insertar la [!DNL Target] solicitud/ubicación (mbox) en el código y utilizar el Compositor [de experiencias basadas en](/help/c-experiences/form-experience-composer.md) formularios para diseñar las experiencias y asignar tráfico. Nuestro SDK móvil admite Java, Objective C y Swift. Depende de la preferencia y los recursos de tu equipo para elegir el idioma.

## ¿Qué SDK están disponibles actualmente?

Los SDK de Adobe Experience Platform Mobile admiten actualmente iOS, Android y React. Para obtener más información, consulte la guía SDK de [Adobe Experience Cloud Platform Mobile](https://aep-sdks.gitbook.io/docs/).

## ¿Cuál es la frecuencia de la característica basada en la ubicación, en términos de verificación de la latitud y la longitud?

Consulte la documentación [de](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places para obtener más información.

## ¿Qué clases nativas admiten las "Vistas" móviles? ¿Admite alguna clase derivada de NSObject (o cualquier objeto de Android) o simplemente NSViewController y Actividades?

Para obtener más información, consulte la documentación de Android para obtener información sobre la forma [manual de declarar vistas](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## ¿Necesito at.js para que funcionen los SDK de Adobe Experience Platform Mobile?

No, no necesita at.js para utilizar los SDK móviles. at.js es la biblioteca [!DNL Target] JavaScript para sitios web. Los SDK de Adobe Experience Platform Mobile son para aplicaciones móviles.

## ¿Target Mobile es solo una funcionalidad de SKU de producto de Adobe Target Premium?

Para los clientes de Adobe Target Standard, puede utilizar nuestros SDK móviles solo para las actividades de Prueba A/B y Segmentación de experiencias (XT). Si desea utilizar las funciones de Recomendaciones o las funciones de AI en la aplicación móvil, necesita una licencia de [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## ¿Puedo aprovechar las audiencias de Adobe Audience Manager (AAM) en el VEC para aplicaciones móviles?

Sí, los SDK de Adobe Experience Platform Mobile están creados para [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)y Target. Las audiencias en Audience Manager se comparten con [!DNL Target].

## ¿Existe una integración de aplicaciones móviles entre Adobe Experience Manager (AEM) y las actividades móviles de Target?

Está en nuestra hoja de ruta pero todavía no hay cronología. Actualmente, puede compartir fragmentos [de](/help/c-experiences/c-manage-content/aem-experience-fragments.md) experiencia JSON de AEM a Target y es posible que después los use en una actividad de aplicación móvil.

## ¿Puedo añadir más imágenes mediante el VEC o solo cambiar las imágenes existentes?

Actualmente solo puede cambiar imágenes existentes.

---
description: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles.
keywords: aplicación móvil; preguntas más frecuentes; faq; aplicación móvil de destino
seo-description: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles.
seo-title: Preguntas más frecuentes sobre Adobe Target para aplicaciones móviles
title: Preguntas frecuentes sobre Adobe Target para aplicaciones móviles
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# Target para preguntas más frecuentes sobre aplicaciones móviles

Lista de las preguntas más frecuentes sobre [!DNL Target] aplicaciones móviles.

## ¿Debería utilizar [!DNL Adobe Experience Platform Launch] para implementar el SDK o puedo implementar el SDK sin utilizar [!DNL Launch]?

El SDK está disponible en el git [de Adobe Marketing Cloud](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si no utiliza [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), debe gestionar su propio archivo de configuración y administrarlo en su aplicación.

## ¿Puede utilizar el Compositor de experiencias visuales (VEC) para aplicaciones móviles con compatibilidad con React-Native para el SDK v 5 de Adobe Experience Platform?

[El VEC para aplicaciones móviles nativas](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) actualmente no admite la aplicación nativa React. Debe utilizar el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md).

## ¿Permite la integración del SDK móvil utilizar la nueva funcionalidad móvil? ¿Puedo activar y desactivar el indicador de funciones sin nuevas implementaciones de código?

Sí, puede utilizar nuestro SDK móvil para desplegar funciones gradualmente.

## Para una lógica más compleja,¿debo desarrollar directamente en la aplicación en lugar de utilizar el VEC móvil? Si es así,¿qué lenguaje de desarrollo debo utilizar?

Actualmente, el VEC admite casos de uso comunes como, por ejemplo, cambiar la imagen, el texto, el color, etc. Para casos de uso más avanzados, como personalizar el diseño de la aplicación, debe insertar [!DNL Target] la solicitud/ubicación (mbox) en el código y utilizar el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para diseñar las experiencias y asignar tráfico. Nuestro SDK móvil admite Java, Objective C y Swift. Depende de la preferencia y los recursos de su equipo para elegir el idioma.

## ¿Qué SDK están disponibles hoy?

Los SDK para móviles de Adobe Experience Platform actualmente son compatibles con iOS, Android y React. Para obtener más información, consulte la guía SDK para móviles de la plataforma [Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## ¿Cuál es la frecuencia de la función basada en ubicaciones, en términos de verificación sobre la latitud y la longitud?

Consulte la documentación de [Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) para obtener más información.

## ¿Qué clases nativas admiten la compatibilidad con "Vistas" móviles? ¿Admiten cualquier clase derivada nsobject (o cualquier objeto Android) o simplemente nsviewcontroller y actividades?

Para obtener más información, visite la documentación de Android para obtener la [manera manual de declarar vistas](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## ¿Necesito at. js para que funcionen los SDK Mobile de la Plataforma de Adobe Experience Platform?

No, no necesita at. js para utilizar los SDK móviles. at. js es la [!DNL Target] biblioteca de JavaScript para sitios web. Los SDK para móviles de Adobe Experience Platform son para aplicaciones móviles.

## ¿Es Target Mobile una funcionalidad de SKU de producto de Adobe Target Premium únicamente?

Para los clientes de Adobe Target Standard, puede utilizar nuestros SDK para móviles solo para las actividades Prueba A/B y Segmentación de experiencias (XT). Si desea utilizar las funciones de Recomendaciones o de tecnología AI en la aplicación móvil, necesita una licencia [de Adobe Target Premium](/help/c-intro/intro.md#premium) .

## ¿Puedo aprovechar audiencias de Adobe Audience Manager (AAM) en el VEC para aplicaciones móviles?

Sí, los SDK para móviles de Adobe Experience Platform se crean para [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)y Target. Se comparten las audiencias de Audience Manager [!DNL Target].

## ¿Existe una integración de aplicaciones móviles entre Adobe Experience Manager (AEM) y actividades móviles de Target?

Está en nuestra hoja de ruta pero todavía no hay cronología. Actualmente, puede compartir fragmentos [de experiencia JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM a Target y puede que pueda usarlos en una actividad de aplicación móvil.

## ¿Puedo agregar más imágenes utilizando el VEC o cambiar solo las existentes?

Actualmente solo puede cambiar las imágenes existentes.

---
title: SDK
description: Obtenga información acerca de la arquitectura de SDK en Banderas y las extensiones disponibles de AEP Web SDK y AEP Mobile SDK.
hide: true
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# SDK {#sdks}

Marcas proporciona SDK para integrar marcas de características en sus aplicaciones. Flags se implementa mediante AEP Web SDK y AEP Mobile SDK.

## Arquitectura de SDK {#architecture}

Todos los SDK de marcas comparten la misma arquitectura principal:

* **Inicialización**: SDK se configura durante el inicio y se registra con el servicio Marcas.
* **Recuperación de características**: SDK recupera los datos de indicadores de características y evalúa los indicadores localmente.
* **Almacenamiento en caché**: SDK almacena en caché los datos de indicadores de características y los actualiza en un intervalo de encuesta configurable.
* **Control de errores**: si el servicio no está disponible, SDK continúa ofreciendo evaluaciones de indicadores de características desde la caché local.

## SDK disponibles {#available-sdks}

### AEP Web SDK {#web-sdk}

La extensión Flags para la web se integra con Adobe Experience Platform Web SDK.

>[!NOTE]
>
>La compatibilidad con Web SDK estará disponible próximamente. Póngase en contacto con su representante de Adobe para obtener ayuda sobre el acceso anticipado.

### Extensión de Android {#android-extension}

La extensión Flags para Android se integra con Adobe Experience Platform Mobile SDK.

Consulte la [guía de integración de extensiones de Android](../sdk-releases/android/android-extension-integration-guide.md) para obtener instrucciones de configuración.

### Extensión de iOS {#ios-extension}

La extensión Flags para iOS se integra con Adobe Experience Platform Mobile SDK.

Consulte la [guía de integración de extensiones de iOS](../sdk-releases/ios/ios-extension-integration-guide.md) para obtener instrucciones de configuración.

## Consulte también {#see-also}

* [Guía de integración de Android extension](../sdk-releases/android/android-extension-integration-guide.md)
* [Servicios Web](web-services.md)
* [Pasos de integración](integration-steps.md)

<!-- -->

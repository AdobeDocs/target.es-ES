---
keywords: implementación;biblioteca de javascript;js;atjs;toma de decisiones en el dispositivo;al tomar decisiones en el dispositivo;funciones compatibles
description: Descubra qué funciones se admiten para la toma de decisiones en dispositivos.
title: Qué funciones se admiten en la toma de decisiones en dispositivos
feature: 'at.js '
role: Developer
translation-type: tm+mt
source-git-commit: 5fcc5776e69222e0a232bd92ddfd10cee748e577
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 11%

---

# Funciones compatibles con la toma de decisiones en dispositivos

El SDK de JS [!DNL Adobe Target] ofrece a los clientes la flexibilidad de elegir entre rendimiento y actualización de los datos para tomar decisiones. En otras palabras, si el envío del contenido personalizado más relevante y atractivo a través del aprendizaje automático es lo más importante para usted, se debe realizar una llamada al servidor en directo. Pero cuando el rendimiento es más crítico, se debe tomar una decisión en el dispositivo y en la memoria. Para que funcione la toma de decisiones en el dispositivo, consulte las siguientes secciones que enumeran las funciones compatibles.

## Tipos de actividades compatibles

La tabla siguiente indica qué [tipos de actividad](/help/c-activities/target-activities-guide.md) creados por el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) o el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) son compatibles o no para la toma de decisiones en dispositivos.

| Tipo de actividad | Compatible? |
| --- | --- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Sí |
| [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/assets/premium.png) | No |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | No |
| [](/help/c-activities/t-experience-target/experience-target.md)Segmentación de experiencias (XT) | Sí |
| [Automated ](/help/c-activities/t-automated-personalization/automated-personalization.md) ![PersonalizationPremium](/help/assets/premium.png) | No |
| [Recommendations](/help/c-recommendations/recommendations.md)  ![Premium](/help/assets/premium.png) | No |
| [Actividades que utilizan Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T) | Sí |

## Segmentación de audiencia

La tabla siguiente indica qué reglas de audiencia se admiten o no para la toma de decisiones en el dispositivo.

| Regla de audiencia | Compatible? |
| --- | --- |
| [Ubicación geográfica](/help/c-target/c-audiences/c-target-rules/geo.md) | Sí |
| [Red](/help/c-target/c-audiences/c-target-rules/network.md) | No |
| [Mobile](/help/c-target/c-audiences/c-target-rules/mobile.md) | No |
| [Parámetros personalizados](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | Sí |
| [Sistema operativo](/help/c-target/c-audiences/c-target-rules/operating-system.md) | Sí |
| [Páginas del sitio](/help/c-target/c-audiences/c-target-rules/site-pages.md) | Sí |
| [Navegador](/help/c-target/c-audiences/c-target-rules/browser.md) | Sí |
| [Perfil del visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | No |
| [Fuentes de tráfico](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | No |
| [Periodo de tiempo](/help/c-target/c-audiences/c-target-rules/time-frame.md) | Sí |
| Audiencias de Adobe Experience Cloud<br>(Audiencias de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] y [!DNL Adobe Experience Manager]) | No |

### Segmentación geográfica para la toma de decisiones en el dispositivo

Para mantener una latencia mínima para las actividades de toma de decisiones en dispositivos con audiencias basadas en geografía, Adobe recomienda que proporcione los valores geográficos usted mismo en la llamada a [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md). Establezca el objeto Geografía en el Contexto de la solicitud. Esto significa que desde el explorador, se puede determinar la ubicación de cada visitante. Por ejemplo, puede realizar una búsqueda de IP a información geográfica mediante un servicio que configure. Algunos proveedores de alojamiento, como Google Cloud, proporcionan esta funcionalidad a través de encabezados personalizados en cada `HttpServletRequest`.

(Código por venir)

Sin embargo, si no puede realizar búsquedas de IP a geografía en el servidor, pero aun así desea tomar decisiones en el dispositivo para solicitudes [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) que contienen audiencias basadas en geografía, esto también es compatible. El inconveniente de este enfoque es que utiliza una búsqueda remota de IP a información geográfica, que añade latencia a cada llamada `getOffers`. Esta latencia debe ser inferior a una llamada `getOffers` con decisiones del lado del servidor, ya que se produce en una CDN ubicada cerca del servidor. Proporcione solo el campo &quot;ipAddress&quot; en el objeto Geo del contexto de la solicitud para que el SDK recupere la ubicación geográfica de la dirección IP del visitante. Si se proporciona cualquier otro campo además de &quot;ipAddress&quot;, el SDK [!DNL Target] no recuperará los metadatos de ubicación geográfica para la resolución.

(Código por venir)

### Método de asignación

La siguiente tabla indica qué métodos de asignación se admiten o no para la toma de decisiones en dispositivos.

| Método de asignación | Compatible? |
| --- | --- |
| Manual | Sí |
| [Asignar automáticamente a la mejor experiencia](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Segmentación automática para experiencias personalizadas](/help/c-activities/auto-target/auto-target-to-optimize.md) | No |

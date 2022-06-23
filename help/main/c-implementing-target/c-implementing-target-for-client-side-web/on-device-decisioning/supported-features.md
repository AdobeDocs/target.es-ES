---
keywords: implementación;biblioteca de javascript;js;atjs;toma de decisiones en el dispositivo;al tomar decisiones en el dispositivo;funciones compatibles
description: Descubra qué funciones se admiten para la toma de decisiones en dispositivos.
title: Qué funciones se admiten en la toma de decisiones en dispositivos
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 13%

---

# Funciones compatibles con la toma de decisiones en el dispositivo

La variable [!DNL Adobe Target] El SDK de JS ofrece a los clientes la flexibilidad de elegir entre rendimiento y actualización de los datos para tomar decisiones. En otras palabras, si el envío del contenido personalizado más relevante y atractivo a través del aprendizaje automático es lo más importante para usted, se debe realizar una llamada al servidor en directo. Pero cuando el rendimiento es más crítico, se debe tomar una decisión en el dispositivo y en la memoria. Para que funcione la toma de decisiones en el dispositivo, consulte las siguientes secciones que enumeran las funciones compatibles.

## Tipos de actividades compatibles

La tabla siguiente indica qué [tipos de actividades](/help/main/c-activities/target-activities-guide.md) creado por el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) o [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) son compatibles o no para la toma de decisiones en dispositivos.

| Tipo de actividad | Compatible? |
| --- | --- |
| [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Sí |
| [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![premium](/help/main/assets/premium.png) | No |
| [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | No |
| [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | Sí |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![Premium](/help/main/assets/premium.png) | No |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![premium](/help/main/assets/premium.png) | No |
| [Actividades que utilizan Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Sí |

## Segmentación de audiencia

La tabla siguiente indica qué reglas de audiencia se admiten o no para la toma de decisiones en el dispositivo.

| Regla de audiencia | Compatible? |
| --- | --- |
| [Ubicación geográfica](/help/main/c-target/c-audiences/c-target-rules/geo.md) | Sí |
| [Red](/help/main/c-target/c-audiences/c-target-rules/network.md) | No |
| [Mobile](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | No |
| [Parámetros personalizados](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Sí |
| [Sistema operativo](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | Sí |
| [Páginas del sitio](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | Sí |
| [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) | Sí |
| [Perfil del visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | No |
| [Fuentes de tráfico](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | No |
| [Periodo de tiempo](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Sí |
| Audiencias de Adobe Experience Cloud<br>(Audiencias de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]y [!DNL Adobe Experience Manager] | No |

### Segmentación geográfica para la toma de decisiones en el dispositivo

Para mantener una latencia mínima para las actividades de toma de decisiones en dispositivos con audiencias basadas en geografía, Adobe recomienda que proporcione los valores geográficos en la llamada a [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/). Establezca el objeto Geografía en el Contexto de la solicitud. Esto significa que desde el explorador, se puede determinar la ubicación de cada visitante. Por ejemplo, puede realizar una búsqueda de IP a información geográfica mediante un servicio que configure. Algunos proveedores de alojamiento, como Google Cloud, proporcionan esta funcionalidad a través de encabezados personalizados en cada `HttpServletRequest`.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

Sin embargo, si no puede realizar búsquedas de IP a geografía en su servidor, pero aún desea realizar la toma de decisiones en el dispositivo para [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)También se admiten las solicitudes {target=_blank} que contienen audiencias basadas en geografía. El inconveniente de este enfoque es que utiliza una búsqueda remota de IP a información geográfica, que añade latencia a cada `getOffers` llamada a . Esta latencia debe ser menor que un `getOffers` con la toma de decisiones del lado del servidor, ya que se produce en una CDN ubicada cerca del servidor. Proporcione solo el campo &quot;ipAddress&quot; en el objeto Geo del contexto de la solicitud para que el SDK recupere la ubicación geográfica de la dirección IP del visitante. Si se proporciona cualquier otro campo además de &quot;ipAddress&quot;, la variable [!DNL Target] El SDK no recuperará los metadatos de ubicación geográfica para la resolución.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### Método de asignación

La siguiente tabla indica qué métodos de asignación se admiten o no para la toma de decisiones en dispositivos.

| Método de asignación | Compatible? |
| --- | --- |
| Manual | Sí |
| [Asignar automáticamente a la mejor experiencia](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Segmentación automática para experiencias personalizadas](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | No |

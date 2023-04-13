---
keywords: Real-time Customer Data Platform;rtcdp;personalización;audiencias aep;audiencias de adobe experience platform;atributos de perfil
description: Aprenda a utilizar la integración de  [!DNL Target]/[!DNL Real-time Customer Data Platform]  (RTCDP) para proporcionar datos de clientes más completos y una personalización más impactante.
title: ¿Cómo puedo integrar  [!DNL Target]  con  [!DNL Real-time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: b31fc335c2066f74ec9aebe835a2c47822a49e5a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 8%

---

# Integrar con [!DNL Real-time Customer Data Platform]

Integrado en [!DNL Adobe Experience Platform], [!DNL Real-time Customer Data Platform] (RTCDP) ayuda a las empresas a reunir datos conocidos y anónimos de múltiples fuentes empresariales. RTCDP le permite crear perfiles de cliente que pueden utilizarse para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Para obtener más información sobre RTCDP, consulte [Información general de Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank}.

## Usar audiencias de [!DNL Adobe Experience Platform] {#aep}

Uso [audiencias](/help/main/c-target/c-audiences/audiences.md) creado en [!DNL Adobe Experience Platform] proporcione datos de clientes más completos que conduzcan a una personalización más impactante. La variable [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank} (RTCDP), basado en [!DNL Adobe Experience Platform], ayuda a las empresas a reunir datos conocidos y anónimos de varias fuentes empresariales. Este proceso le permite crear perfiles de cliente que se pueden utilizar para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Conectando [!DNL Target] a [!DNL Real-time Customer Data Platform], los clientes pueden enriquecer su personalización web. Esta integración le permite desbloquear nuevos segmentos a los que anteriormente podría haber estado inaccesible [!DNL Target] para habilitar la personalización en tiempo real en la primera página de la visita web de un cliente. Uso de audiencias y atributos de perfil creados en [!DNL Adobe Experience Platform] permite ampliar los puntos de datos disponibles para una mejor personalización.

Esta integración desbloquea los casos de uso clave con CDP en tiempo real:

* Personalización de la misma página/siguiente visita individual
* Personalización de usuarios nuevos/desconocidos

### Funciones principales

Las funciones clave incluyen:

* Directas [!DNL Target] integración con CDP/[!DNL Adobe Experience Platform] en Edge (eliminando dependencia de [!DNL Audience Core services] - AAM)
* [!UICONTROL Tarjeta de destino perimetral de Target] con gobernanza y aplicación de políticas
* Segmentos CDP en tiempo real y atributos de perfil compartidos

### Casos de uso de personalización

Las secciones siguientes muestran qué tipo de caso de uso de personalización (sesión siguiente o página misma) está disponible cuando se utilizan distintos métodos de implementación:

#### Implementación de at.js

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] AAM) y [!DNL Target]</li><li>[!DNL RTCDP] (Premium o Ultimate) y [!DNL Target]</li><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul> | Personalización de próxima sesión |

#### Implementación de la API del lado del servidor del SDK web de Adobe Experience Platform o del Experience Platform

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><li>Personalización de la misma página mediante Edge</li><li>Gobernanza aplicada al compartir segmentos</li></ul> |
| <ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul><li>Personalización de la misma página mediante Edge</li><ul><li>[!DNL RTCDP] segmentos</li><li>Gobernanza aplicada al compartir segmentos</li></ul> |

#### Mezcla de [!UICONTROL at.js] y [!DNL Platform Web SDK] implementación

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li></ul><li>Personalización de la misma página</li><ul><li>Para todas las páginas con [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul> |

### Tiempo de evaluación de segmentos

La tabla siguiente muestra el tiempo de evaluación de segmentos para eventos que provienen de diferentes escenarios de implementación:

| Situación | Segmento de Edge (evaluación de milisegundos) | Segmento de transmisión (evaluación por minuto) | Evaluación de segmentos por lotes |
| --- | --- | --- | --- |
| Eventos/datos de [!DNL Adobe Experience Platform] SDK | Sí | Sí | N/A |
| Eventos desde [!UICONTROL at.js] | No | Sí | N/A |
| Eventos desde [!DNL Target Mobile] SDK | No | Sí | N/A |
| Eventos desde la carga por lotes | No | No | Sí |
| Eventos de datos sin conexión (flujo) | No | Sí | Sí |

### Vínculos a más información

Para obtener más información, consulte los temas siguientes:

* [Notas de la versión de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} en el *Notas de la versión de Adobe Experience Platform*
* [Configurar destinos de personalización para la personalización de la misma página y de la página siguiente](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} en el *Información general sobre destinos* guía.
* [Conexión personalizada personalizada](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} en el *Información general sobre destinos* guía
* [Conexión Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} en el *Información general sobre destinos* guía
* [Configurar destinos de personalización para los casos de uso de personalización de la misma página y de la página siguiente](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} en el *Información general sobre destinos* guía

## Compartir atributos de perfil CDP en tiempo real con [!DNL Target] {#rtcdp-profile-attributes}

Los atributos de perfil CDP en tiempo real se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limitaciones y consideraciones sobre los atributos de perfil CDP en tiempo real

>[!NOTE]
>
>La función Atributos de perfil CDP en tiempo real está disponible en versión beta para ofertas de HTML y [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Tenga en cuenta lo siguiente:

* Los atributos de una oferta determinada deben proceder del mismo Simulador para pruebas Experience Platform. (En otras palabras, una oferta no puede contener atributos de entornos limitados de Experience Platform diferentes).
* Los atributos dentro de una oferta determinada pueden provenir de diferentes fuentes; es decir, [!DNL Target] y el perfil del Experience Platform. (En otras palabras, puede combinar atributos de los que procedan [!DNL Target] o del perfil del Experience Platform).
* Al definir una oferta, puede asignar valores predeterminados para los atributos de perfil CDP en tiempo real, en caso de que el atributo no tenga un valor explícito. Por ejemplo, si un consentimiento o una política de gobernanza bloquean el atributo que se está utilizando en el servicio de personalización, se puede utilizar el valor predeterminado en su lugar.
* Cuando se comparten, los atributos de perfil CDP en tiempo real se utilizan en los modelos de personalización Inteligencia artificial/Aprendizaje automático para [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] actividades.

### Ejemplo de caso de uso

Como especialista en marketing en línea, desea que AEP/Perfil unificado comparta valores de atributos con [!DNL Target] para proporcionar personalización en tiempo real. Mediante los atributos de perfil CDP en tiempo real, puede mostrar el valor del atributo de Experience Platform en un [!DNL Target] oferta mediante sustitución de tokens. Por ejemplo, puede personalizar según el color favorito de un cliente utilizando `${aep.profile.favoriteColor}`, o su nivel de lealtad y valor de punto de lealtad mediante los tokens `${aep.loyalty.tier}` y `${aep.loyalty.points}`.

Para crear una oferta JSON para compartir atributos de perfil unificado/AEP con [!DNL Target]:

1. While [creación de una oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), en la **[!UICONTROL Seleccionar un origen]** lista, seleccionar **[!UICONTROL Adobe Experience Platform]**.
1. En el **[!UICONTROL Seleccionar un nombre de entorno limitado de perfil]** seleccione el entorno limitado que desee.
1. En el **[!UICONTROL Seleccionar un atributo de perfil]** seleccione los atributos que desee.
1. (Opcional) Desde la **[!UICONTROL Inserción de un valor predeterminado]** seleccione los valores que desee.
1. Haga clic en **[!UICONTROL Agregar]**.

   La siguiente ilustración muestra dos atributos de perfil: `loyalty.tier` y `loyalty.points` se han añadido a la oferta JSON.

   ![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Vídeos y publicaciones en blogs

Los siguientes vídeos y anuncios de blog proporcionan más información sobre la personalización mejorada con Target y RTCDP:

### Vídeo: Personalización de próxima visita con CDP en tiempo real y [!DNL Adobe Target]{#RTCDP}

Obtenga información sobre cómo personalizar en la siguiente visita individual con [!DNL Real-time Customer Data Platform] y [!DNL Adobe Target]. La variable [!DNL Adobe Target] destino en [!DNL Real-time CDP] le permite usar [!DNL Experience Platform] segmentos en [!DNL Adobe Target] para la misma personalización de páginas y la personalización de páginas siguientes con compatibilidad con la administración y la privacidad.

Para obtener más información, consulte [Personalización de próxima visita con CDP en tiempo real y Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} en el *Tutorials de plataforma* guía.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog y video de Adobe Target: Personalización mejorada de la misma página

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] y [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

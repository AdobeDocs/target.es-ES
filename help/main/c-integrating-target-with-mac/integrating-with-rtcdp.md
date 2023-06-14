---
keywords: Real-time Customer Data Platform;rtcdp;personalización;aep audiences;adobe experience platform audiences;atributos de perfil
description: Aprenda a utilizar la integración de  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) para proporcionar datos de clientes más completos y una personalización más impactante.
title: ¿Cómo puedo integrar  [!DNL Target]  con  [!DNL Real-Time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 92990584efd21ab81f6a4cadab2f46529e1bc182
workflow-type: tm+mt
source-wordcount: '1076'
ht-degree: 95%

---

# Integrar con [!DNL Real-Time Customer Data Platform]

Integrado en [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP) ayuda a las empresas a reunir datos conocidos y anónimos de múltiples fuentes empresariales. RTCDP le permite crear perfiles de cliente que pueden utilizarse para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Para obtener más información acerca de RTCDP, consulte [Información general sobre Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank}.

## Características principales

Las funciones clave incluyen las siguientes:

* Integración directa de [!DNL Target] con Real-Time CDP/[!DNL Adobe Experience Platform] en Edge (se elimina la dependencia de [!DNL Audience Core services], AAM)
* [!UICONTROL Tarjeta de destino de Edge de Target] con gobernanza y aplicación de políticas
* Segmentos y atributos de perfil compartidos de Real-Time CDP

## Situaciones de implementación

Las secciones siguientes muestran qué tipo de caso de uso de personalización (sesión siguiente o misma página) está disponible cuando se utilizan distintos métodos de implementación:

### Implementación de at.js

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) y [!DNL Target]</li><li>[!DNL RTCDP] (Premium o Ultimate) y [!DNL Target]</li><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM] y [!DNL Target]</li></ul> | Personalización de próxima sesión |

### Implementación de [!DNL Adobe Experience Platform Web SDK] o [!DNL Experience Platform Server-Side API]

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><li>Personalización de la misma página mediante Edge</li><li>Gobernanza aplicada al compartir segmentos</li></ul> |
| <ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM] y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul><li>Personalización de la misma página mediante Edge</li><ul><li>[!DNL RTCDP] segmentos</li><li>Gobernanza aplicada al compartir segmentos</li></ul> |

### Mezcla de [!UICONTROL at.js] e implementación de [!DNL Platform Web SDK]

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li></ul><li>Personalización de la misma página</li><ul><li>Para todas las páginas con [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM] y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul> |

## Tiempo de evaluación de segmentos

La tabla siguiente muestra el tiempo de evaluación de segmentos para eventos que provienen de diferentes escenarios de implementación:

| Escenario | Segmento de Edge (evaluación de milisegundos) | Segmento de streaming (evaluación por minuto) | Evaluación de segmentos por lotes |
| --- | --- | --- | --- |
| Eventos/datos de SDK de [!DNL Adobe Experience Platform] | Sí | Sí | N/A |
| Eventos de [!UICONTROL at.js] | No | Sí | N/A |
| Eventos de SDK de [!DNL Target Mobile] | No | Sí | N/A |
| Eventos de carga por lotes | No | No | Sí |
| Eventos de datos sin conexión (flujo) | No | Sí | Sí |

## Uso de audiencias de [!DNL Adobe Experience Platform] {#aep}

Usar [audiencias](/help/main/c-target/c-audiences/audiences.md) creadas en [!DNL Adobe Experience Platform] proporciona datos de clientes más completos que conducen a una personalización más impactante. [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank} (RTCDP), integrado en [!DNL Adobe Experience Platform], ayuda a las empresas a reunir datos conocidos y anónimos de varias fuentes empresariales. Este proceso le permite crear perfiles de cliente que se pueden utilizar para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Conectando [!DNL Target] a [!DNL Real-Time Customer Data Platform], los clientes pueden enriquecer su personalización web. Esta integración le permite desbloquear nuevos segmentos que podrían haber sido previamente inaccesibles para [!DNL Target], con el fin de permitir la personalización en milisegundos en tiempo real en la primera página de la visita web de un cliente. Usar audiencias y atributos de perfil creados en [!DNL Adobe Experience Platform] permite ampliar los puntos de datos disponibles para conseguir una mejor personalización.

Esta integración desbloquea los casos de uso clave con Real-Time CDP:

* Personalización de la misma página/siguiente visita individual
* Personalización de usuarios nuevos/desconocidos

## Uso compartido de atributos de perfil de Real-Time CDP con [!DNL Target] {#rtcdp-profile-attributes}

Los atributos de perfil de Real-Time CDP se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y [JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limitaciones y consideraciones de la característica atributos de perfil de Real-Time CDP

>[!NOTE]
>
>La función atributos de perfil de Real-Time CDP está disponible en versión beta para ofertas de HTML y [JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Tenga en cuenta lo siguiente:

* Los atributos de una oferta determinada deben ser de la misma zona protegida de [!UICONTROL Experience Platform]. (En otras palabras, una oferta no puede contener atributos de diferentes zonas protegidas de [!UICONTROL Experience Platform]).
* Los atributos dentro de una oferta determinada pueden provenir de diferentes fuentes; es decir, el perfil de [!DNL Target] y de [!UICONTROL Experience Platform]. (En otras palabras, puede combinar atributos que procedan del perfil de [!DNL Target] o de [!UICONTROL Experience Platform]).
* Al definir una oferta, puede asignar valores predeterminados para [!UICONTROL Atributos de perfil de Real-Time CDP], en caso de que el atributo no tenga un valor explícito. Por ejemplo, si un consentimiento o una política de gobernanza bloquean el atributo que se está utilizando en el servicio de personalización, se puede utilizar el valor predeterminado en su lugar.

### Caso de uso de muestra de JSON

Como experto en marketing en línea, desea que AEP o el perfil unificado compartan valores de atributos con [!DNL Target] para proporcionar personalización en tiempo real. Usando [!UICONTROL Atributos de perfil de Real-Time CDP], puede mostrar el valor del atributo [!UICONTROL Experience Platform] en una oferta de [!DNL Target] mediante reemplazar tókenes. Por ejemplo, puede personalizar según el color favorito de un cliente utilizando `${aep.profile.favoriteColor}`, o su nivel de lealtad y valor de punto de lealtad mediante los tókenes `${aep.loyalty.tier}` y `${aep.loyalty.points}`.

Para crear una oferta JSON para compartir atributos de perfil unificado/AEP con [!DNL Target]:

1. Durante la [creación de una oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), en la lista **[!UICONTROL Seleccionar un origen]**, elija **[!UICONTROL Adobe Experience Platform]**.
1. En la lista **[!UICONTROL Seleccionar un nombre de zona protegida de perfil]**, elija la que desee.
1. En la lista **[!UICONTROL Seleccionar un atributo de perfil]**, elija los atributos que desee.
1. (Opcional) Desde la lista **[!UICONTROL Insertar un valor predeterminado]**, elija los valores que desee.
1. Haga clic en **[!UICONTROL Agregar]**.

La siguiente ilustración muestra dos atributos de perfil: `loyalty.tier` y `loyalty.points` se han añadido a la oferta JSON.

![imagen offer-json-aep-shared-attribute](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Vínculos a más información

Para obtener más información, consulte los temas siguientes:

* [Notas de la versión de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=es#destinations){target=_blank} en las *Notas de la versión de Adobe Experience Platform*
* [Configuración de destinos de personalización para la personalización de la misma página y de la página siguiente](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es){target=_blank} en la guía *Información general sobre destinos*.
* [Conexión de Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=es){target=_blank} en la guía *Información general sobre destinos*
* [Asignación de atributos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=es#map-attributes){target=_blank} en la guía *Información general sobre destinos*.
* [Activación de audiencias en destinos de personalización de Edge](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.htm){target=_blank} en el *Resumen de destinos* guía.
* [Personalización de la misma página y de la página siguiente mediante [!DNL Adobe Target] y destinos de Personalización personalizada](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=en#same-next-page-personalization){target=_blank} en &quot;Preguntas más frecuentes&quot;, en la sección *Resumen de destinos* guía.

## Vídeos y publicaciones en blogs {#videos-blogs}

Los siguientes vídeos y publicaciones de blog proporcionan más información acerca de la personalización mejorada con Target y RTCDP:

### Vídeo: Personalización de próxima visita con Real-Time CDP y [!DNL Adobe Target]{#RTCDP}

Obtenga información sobre cómo personalizar en la siguiente visita con [!DNL Real-Time Customer Data Platform] y [!DNL Adobe Target]. El destino [!DNL Adobe Target] en [!DNL Real-Time CDP] le permite usar segmentos de [!DNL Experience Platform] en [!DNL Adobe Target] para la personalización de la misma página y de página siguiente con compatibilidad con gobernanza y privacidad.

Para obtener más información, consulte [Personalización de próxima visita con Real-Time CDP y Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=es){target=_blank} en la guía *Tutoriales de Platform*.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Vídeo: Configuración de destino de [!DNL Adobe Target] en [!DNL Real-Time Customer Data Platform]

Obtenga información sobre cómo configurar el destino de [!DNL Adobe Target] en [!DNL Real-Time Customer Data Platform] para empezar a enviar segmentos y atributos de perfil desde [!DNL Real-Time CDP] hasta [!DNL Target].

>[!VIDEO](https://video.tv.adobe.com/v/3418799/?learn=on)

### Vídeo: Activar segmentos y atributos de perfil

Obtenga información sobre cómo activar segmentos y atributos de perfil de [!DNL Adobe Real-Time Customer Data Platform] hasta [!DNL Adobe Target] para mostrar contenido personalizado en tiempo real en sus sitios web, aplicaciones móviles y otras propiedades digitales.

>[!VIDEO](https://video.tv.adobe.com/v/3419036/?learn=on)

### Vídeo: Usar segmentos de [!DNL Real-Time CDP] en [!DNL Target]

Aprenda a utilizar segmentos de [!DNL Real-Time Customer Data Platform] en [!DNL Adobe Target] para ofrecer experiencias personalizadas en su sitio web y aplicaciones móviles.

>[!VIDEO](https://video.tv.adobe.com/v/3419149/?learn=on)

### Vídeo: Uso de atributos de perfil de [!DNL Real-Time CDP] en [!DNL Adobe Target]

Aprenda a utilizar los atributos de perfil de [!DNL Adobe Real-Time Customer Data Platform] en [!DNL Adobe Target] para ofrecer experiencias personalizadas en su sitio web y aplicaciones móviles.

>[!VIDEO](https://video.tv.adobe.com/v/3419318/?learn=on)

### Blog y vídeo de [!DNL Adobe Target]: personalización mejorada de la misma página

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] y [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

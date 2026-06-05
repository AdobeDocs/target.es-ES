---
keywords: Real-time Customer Data Platform;rtcdp;personalización;aep audiences;adobe experience platform audiences;atributos de perfil
description: Aprenda a utilizar la integración de  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) para proporcionar datos de clientes más completos y una personalización más impactante.
title: ¿Cómo puedo integrar  [!DNL Target]  con  [!DNL Real-Time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
TQID: https://experienceleague.adobe.com/0Zw98ulFxHFH-PdV8tmocpOXYCKR2ciKtqFKwD44iiM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1173
ht-degree: 71%

---

# Integrar con [!DNL Real-Time Customer Data Platform]

Integrado en [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP) ayuda a las empresas a reunir datos conocidos y anónimos de múltiples fuentes empresariales. RTCDP le permite crear perfiles de cliente que pueden utilizarse para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Para obtener más información sobre RTCDP, consulte [Información general de Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank}.

## Características principales

Las funciones clave incluyen las siguientes:

* Integración directa de [!DNL Target] con Real-Time CDP/[!DNL Adobe Experience Platform] en Edge (se elimina la dependencia de [!DNL Audience Core services], AAM)
* [!UICONTROL Tarjeta de destino de Edge de Target] con control y aplicación de políticas
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

### Combinación de [!UICONTROL at.js] e implementación de [!DNL Platform Web SDK]

| Soluciones | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul> | <ul><li>Personalización de próxima sesión<ul><li>Para todas las páginas con [!UICONTROL at.js]</li></ul></li><li>Personalización de la misma página<ul><li>Para todas las páginas con [!DNL Platform Web SDK]</li></ul></li></ul> |
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

## Uso de públicos de [!DNL Adobe Experience Platform] {#aep}

Usar [públicos](/help/main/c-target/c-audiences/audiences.md) creados en [!DNL Adobe Experience Platform] proporciona datos de clientes más completos que conducen a una personalización más impactante. [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank} (RTCDP), creado en [!DNL Adobe Experience Platform], ayuda a las empresas a reunir datos conocidos y anónimos de varios orígenes empresariales. Este proceso le permite crear perfiles de cliente que se pueden utilizar para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Conectando [!DNL Target] a [!DNL Real-Time Customer Data Platform], los clientes pueden enriquecer su personalización web. Esta integración le permite desbloquear nuevos segmentos que podrían haber sido previamente inaccesibles para [!DNL Target], con el fin de permitir la personalización en milisegundos en tiempo real en la primera página de la visita web de un cliente. Usar públicos y atributos de perfil creados en [!DNL Adobe Experience Platform] permite ampliar los puntos de datos disponibles para conseguir una mejor personalización.

Esta integración desbloquea los casos de uso clave con Real-Time CDP:

* Personalización de la misma página/siguiente visita individual
* Personalización de usuarios nuevos/desconocidos

## Uso compartido de atributos de perfil de Real-Time CDP con [!DNL Target] {#rtcdp-profile-attributes}

Los atributos de perfil de Real-Time CDP se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y [JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limitaciones y consideraciones de la característica atributos de perfil de Real-Time CDP {#limitations}

Tenga en cuenta lo siguiente:

* Los atributos de una oferta determinada deben pertenecer a la misma zona protegida de [!UICONTROL Experience Platform]. (En otras palabras, una oferta no puede contener atributos de diferentes zonas protegidas de [!UICONTROL Experience Platform]).
* Los atributos de una oferta determinada pueden provenir de diferentes fuentes, a saber, el perfil [!DNL Target] y el perfil [!UICONTROL Experience Platform]. (En otras palabras, puede combinar atributos ya provengan de [!DNL Target] o del perfil [!UICONTROL Experience Platform]).
* Al definir una oferta, puede asignar valores predeterminados para [!UICONTROL Atributos de perfil de Real-Time CDP], en caso de que el atributo no tenga un valor explícito. Por ejemplo, si un consentimiento o una política de gobernanza bloquean el atributo que se está utilizando en el servicio de personalización, se puede utilizar el valor predeterminado en su lugar.
* [!DNL Target] solo admite el tipo de datos &quot;string&quot; para los atributos de perfil [!DNL Adobe Experience Platform] que se van a usar en las ofertas. Los atributos de tipo &quot;Mapa&quot; y &quot;Matriz&quot; aún no son compatibles.

### Caso de uso de muestra de JSON

Como experto en marketing en línea, desea que AEP o el perfil unificado compartan valores de atributos con [!DNL Target] para proporcionar personalización en tiempo real. Si usa [!UICONTROL Atributos de perfil de Real-Time CDP], puede mostrar el valor del atributo [!UICONTROL Experience Platform] en una oferta [!DNL Target] mediante el reemplazo de token. Por ejemplo, puede personalizar según el color favorito de un cliente utilizando `${aep.profile.favoriteColor}`, o su nivel de lealtad y valor de punto de lealtad mediante los tókenes `${aep.loyalty.tier}` y `${aep.loyalty.points}`.

Para crear una oferta JSON para compartir atributos de perfil unificado/AEP con [!DNL Target]:

1. Mientras [crea una oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), en la lista **[!UICONTROL Seleccionar un origen]**, seleccione **[!UICONTROL Adobe Experience Platform]**.
1. En la lista **[!UICONTROL Seleccionar un nombre de zona protegida de perfil]**, seleccione la zona protegida que desee.
1. En la lista **[!UICONTROL Seleccionar un atributo de perfil]**, seleccione los atributos que desee.
1. (Opcional) En la lista **[!UICONTROL Insertar un valor predeterminado]**, seleccione los valores que desee.
1. Haga clic en **[!UICONTROL Agregar]**.

La siguiente ilustración muestra dos atributos de perfil: `loyalty.tier` y `loyalty.points` se han añadido a la oferta JSON.

![imagen offer-json-aep-shared-attribute](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Vínculos a más información

Para obtener más información, consulte los temas siguientes:

* [Notas de la versión de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=es#destinations){target=_blank} en las *Notas de la versión de Adobe Experience Platform*
* [Configure destinos de personalización para la personalización de la misma página y de la página siguiente](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es){target=_blank} en la guía de *Información general sobre destinos*.
* [Conexión de Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=es){target=_blank} en la guía de *Información general sobre destinos*
* [Asignar atributos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=es#map-attributes){target=_blank} en la guía de *Información general sobre destinos*.
* [Activar audiencias para destinos de personalización Edge](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html?lang=es){target=_blank} en la guía de *Información general sobre destinos*.
* [Personalización de la misma página y de la página siguiente a través de [!DNL Adobe Target] y destinos personalizados de Personalization](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=es#same-next-page-personalization){target=_blank} en &quot;Preguntas frecuentes&quot; en la guía de *Información general sobre destinos*.

## Vídeos y publicaciones en blogs {#videos-blogs}

Los siguientes vídeos y publicaciones de blog proporcionan más información acerca de la personalización mejorada con Target y RTCDP:

### Vídeo: Personalización de próxima visita con Real-Time CDP y [!DNL Adobe Target]{#RTCDP}

Obtenga información sobre cómo personalizar en la siguiente visita con [!DNL Real-Time Customer Data Platform] y [!DNL Adobe Target]. El destino [!DNL Adobe Target] en [!DNL Real-Time CDP] le permite usar segmentos de [!DNL Experience Platform] en [!DNL Adobe Target] para la personalización de la misma página y de página siguiente con compatibilidad con gobernanza y privacidad.

Para obtener más información, consulte [Personalización de próxima visita con Real-Time CDP y Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=es){target=_blank} en la guía de *Tutoriales de Platform*.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Vídeo: Configuración de destino de [!DNL Adobe Target] en [!DNL Real-Time Customer Data Platform]

Obtenga información sobre cómo configurar el destino de [!DNL Adobe Target] en [!DNL Real-Time Customer Data Platform] para empezar a enviar segmentos y atributos de perfil desde [!DNL Real-Time CDP] hasta [!DNL Target].

>[!VIDEO](https://video.tv.adobe.com/v/3449796/?captions=spa&learn=on)

### Vídeo: Activar segmentos y atributos de perfil

Obtenga información sobre cómo activar segmentos y atributos de perfil de [!DNL Adobe Real-Time Customer Data Platform] hasta [!DNL Adobe Target] para mostrar contenido personalizado en tiempo real en sus sitios web, aplicaciones móviles y otras propiedades digitales.

>[!VIDEO](https://video.tv.adobe.com/v/3447358/?captions=spa&learn=on)

### Vídeo: Usar segmentos de [!DNL Real-Time CDP] en [!DNL Target]

Aprenda a utilizar segmentos de [!DNL Real-Time Customer Data Platform] en [!DNL Adobe Target] para ofrecer experiencias personalizadas en su sitio web y aplicaciones móviles.

>[!VIDEO](https://video.tv.adobe.com/v/3446830/?captions=spa&learn=on)

### Vídeo: Uso de atributos de perfil de [!DNL Real-Time CDP] en [!DNL Adobe Target]

Aprenda a utilizar los atributos de perfil de [!DNL Adobe Real-Time Customer Data Platform] en [!DNL Adobe Target] para ofrecer experiencias personalizadas en su sitio web y aplicaciones móviles.

>[!VIDEO](https://video.tv.adobe.com/v/3451896/?captions=spa&learn=on)

### Blog y vídeo de [!DNL Adobe Target]: personalización mejorada de la misma página

[[!DNL Adobe] anuncia Personalization mejorado en la misma página con [!DNL Adobe Target] y [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

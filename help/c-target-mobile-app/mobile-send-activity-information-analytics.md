---
keywords: mobile;tntVal;analytics;adobe analytics;integración;sdk;sdk móvil;
description: En esta sección se describe cómo enviar la información de actividad de aplicaciones móviles de Adobe Target a Adobe Analytics para la segmentación posterior a Ahoc.
title: Enviar información de Actividad a Adobe Analytics
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 33%

---


# Enviar información de actividad a Adobe Analytics{#send-activity-information-to-adobe-analytics}

En esta sección se describe cómo enviar [!DNL Target] información de actividad de aplicaciones móviles a Adobe [!DNL Analytics] para la segmentación post-hoc.

**Requisitos previos**

* Esta integración requiere que [!DNL Analytics] y [!DNL Target] se implementen mediante el SDK móvil.
* Asegúrese de que el grupo de informes esté habilitado para recibir información de actividad de [!DNL Target].

   Esto generalmente se realiza agregando el código de cliente [!DNL Target] al grupo de informes [!DNL Analytics]. Es posible que ya esté habilitado si utiliza la integración de SiteCatalyst-Test&amp;Target para actividades web. Si tiene preguntas sobre este paso, póngase en contacto con Adobe Client Care.

1. Obtenga la información de la actividad.

   Si incluye una cadena como la siguiente en el contenido de la experiencia, [!DNL Target] devuelve la información de actividad que puede enviar a [!DNL Analytics]:

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Sustituya el texto del código json de la experiencia por algo similar al siguiente ejemplo:

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   En este ejemplo, se agrega un nodo con la variable `tntVal` para obtener la información de actividad. Agregue un código similar para las demás experiencias, con un título y un mensaje adecuados.

   Esta cadena ofrece un número (como 115110:0:0) en la respuesta de [!DNL Target]. Indica el ID de actividad, el ID de experiencia y el tipo de tráfico. A continuación se muestra una respuesta de muestra de [!DNL Target]:

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Busque en el objeto JSON.

   Analice la respuesta que regresó de [!DNL Target] en la llamada de retorno. Puede utilizar `NSJSONSerialization` para analizar esta respuesta y almacenarla en un diccionario o una matriz.

   Para obtener más información, consulte la [documentación de NSJSONSerialización](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error).

1. Envíe los datos a [!DNL Analytics].

   Agregue la información de actividad analizada (como `tntVal` en la respuesta anterior) al objeto de datos de contexto en una llamada de [!DNL Analytics] Esta [!DNL Analytics] llamada que contiene los datos de contexto se puede activar inmediatamente o puede esperar hasta que se active la siguiente llamada [!DNL Analytics].

   Por ejemplo, esta se puede activar en la retrollamada de la llamada de `targetLoadRequest`:

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`es una clave de evento reservada en el SDK móvil. La posclasificación de la variable `tntVal` en [!DNL Analytics] funciona del mismo modo en el SDK móvil que en la web (JavaScript). Después de procesar la información en [!DNL Analytics], debe ver los nombres de actividad y experiencia en la interfaz [!DNL Analytics].


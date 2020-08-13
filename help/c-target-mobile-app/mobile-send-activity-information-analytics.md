---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: En esta sección se describe cómo enviar la información de actividad de aplicaciones móviles de Adobe Target a Adobe Analytics para la segmentación posterior a Ahoc.
title: Enviar información de actividad de Adobe Target a Adobe Analytics
feature: mobile implementation
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 34%

---


# Enviar información de actividad a Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**Requisitos previos**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. Es posible que ya esté habilitado si utiliza la integración de SiteCatalyst-Test&amp;Target para actividades web. Si tiene preguntas sobre este paso, póngase en contacto con Adobe Client Care.

1. Obtenga la información de la actividad.

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Sustituya el texto del código json de la experiencia por algo similar al siguiente ejemplo:

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. Agregue un código similar para las demás experiencias, con un título y un mensaje adecuados.

   Esta cadena ofrece un número (como 115110:0:0) en la respuesta de [!DNL Target]. Indica el ID de actividad, el ID de experiencia y el tipo de tráfico. The following is a sample response from [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Busque en el objeto JSON.

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   Consulte la documentación [de](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialización para obtener más información.

1. Envíe los datos a [!DNL Analytics].

   Agregue la información de actividad analizada (como `tntVal` en la respuesta anterior) al objeto de datos de contexto en una llamada de [!DNL Analytics] This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   Por ejemplo, esta se puede activar en la retrollamada de la llamada de `targetLoadRequest`:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`es una clave de evento reservada en el SDK móvil. The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.


---
description: En esta sección se describe cómo enviar información de actividad de la aplicación móvil de Target a Adobe Analytics para la segmentación postAdHoc.
seo-description: En esta sección se describe cómo enviar información de actividad de la aplicación móvil de Target a Adobe Analytics para la segmentación postAdHoc.
seo-title: Enviar información de actividad a Adobe Analytics
title: Enviar información de actividad a Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Enviar información de actividad a Adobe Analytics{#send-activity-information-to-adobe-analytics}

En esta sección se describe cómo enviar información de actividad de la aplicación móvil de Target a Adobe Analytics para la segmentación postAdHoc.

**Requisitos previos**

* Esta integración requiere que Analytics y Target se implementen mediante el SDK móvil.
* Asegúrese de que el grupo de informes esté habilitado para recibir información de actividad de Target.

   Normalmente, esto se lleva a cabo agregando el código de cliente de Target al grupo de informes de Analytics. Es posible que ya esté habilitado si utiliza la integración de SiteCatalyst-Test&amp;Target para actividades web. Si tiene preguntas sobre este paso, póngase en contacto con Adobe Client Care.

1. Obtenga la información de la actividad.

   Si incluye una cadena como la siguiente en el contenido de su experiencia, Target devuelve la información de la campaña que puede enviar a Analytics:

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

   En este ejemplo, se agrega un nodo con la variable “`tntVal`” a fin de obtener la información de la actividad. Agregue un código similar para las demás experiencias, con un título y un mensaje adecuados.

   Esta cadena ofrece un número (como 115110:0:0) en la respuesta de Target, lo que indica el ID de actividad, el ID de experiencia y el tipo de tráfico. El siguiente es un ejemplo de respuesta de Target:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Busque en el objeto JSON.

   Analice en la respuesta que regresó de Target en la retrollamada. Puede utilizar NSJSONSerialization para analizar esta respuesta y almacenarla en un diccionario o una matriz.

   Consulte la documentación [de](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialización para obtener más información.
1. Envíe los datos a Analytics.

   Agregue la información de actividad analizada (como `tntVal` en la respuesta anterior) al objeto de datos de contexto en una llamada de Analytics. La llamada de Analytics que contiene los datos de contexto se puede activar inmediatamente o puede esperar hasta que se active la siguiente llamada de Analytics.

   Por ejemplo, esta se puede activar en la retrollamada de la llamada de `targetLoadRequest`:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`es una clave de evento reservada en el SDK móvil. La clasificación posterior de la variable de `tntVal` en Analytics funciona del mismo modo en el SDK móvil que en la Web (JavaScript). Una vez que la información se procesa en Analytics, debería ver los nombres de actividad y experiencia en la interfaz de Analytics.


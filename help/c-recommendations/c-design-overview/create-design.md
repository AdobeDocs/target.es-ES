---
keywords: recommendations design;create design;copy design
description: Un diseño define el modo en que las recomendaciones aparecen en una página.
title: Crear un diseño
feature: designs
uuid: 812258e0-8d28-4ef3-b745-45ed694fcabe
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 95%

---


# ![PREMIUM](/help/assets/premium.png) Crear un diseño{#create-a-design}

Un diseño define el modo en que las recomendaciones aparecen en una página.

Puede crear un diseño de [!UICONTROL Recommendations] usando un diseño predeterminado o creando uno personalizado. La pantalla **[!UICONTROL Recommendations > Diseños]** muestra las tarjetas de diseños predeterminados y los diseños que se han creado. Los diseños predeterminados no se pueden editar ni eliminar.

1. En la pantalla **[!UICONTROL Recommendations > Diseños]**, pase el ratón sobre la tarjeta del diseño que quiere crear.

   ![](assets/Card_CopyDesign.png)

1. Para copiar y editar un diseño existente, haga clic en el icono **[!UICONTROL Copiar]**.

   O

   Para crear un diseño personalizado, haga clic en **[!UICONTROL Crear diseño]** en la pantalla **[!UICONTROL Recommendations > Diseños.]**

   ![](assets/createDesign.png)

1. Añada un **[!UICONTROL Nombre de contenido]**.

   Cuando se usa un diseño predeterminado, en el campo **[!UICONTROL Nombre de contenido]** aparecen el nombre del diseño y “Copiar”. Puede editar el nombre. 1. (Opcional) Haga clic para seleccionar una imagen que se mostrará en la tarjeta de diseño.
1. Edite el **[!UICONTROL Código]** de diseño.

   Los diseños de Recommendations utilizan el lenguaje de diseño Velocity de código abierto. Puede encontrar información sobre Velocity en [](https://velocity.apache.org)https://velocity.apache.org.

   Un diseño puede ser HTML o no HTML. De forma predeterminada, los diseños HTML se encapsulan con una <div> etiqueta para permitir el seguimiento de clics en un entorno web. Los diseños que no son HTML son para entornos que no son de web donde los clics no se pueden rastrear.

   >[!NOTE]
   >
   >El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99.

1. Haga clic en **[!UICONTROL Guardar]**.

## Ejemplo de JSON {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

En el siguiente ejemplo se muestra cómo se pueden devolver respuestas JSON al configurar una actividad mediante el editor basado en formularios.

1. Puede crear un diseño desde la biblioteca de diseños o desde el flujo de trabajo basado en formularios. Si intenta hacerlo desde el flujo de trabajo del Compositor de experiencias visuales (VEC), solo podrá crear diseños HTML, que se engloban dentro de   `<div>` para fines de seguimiento de clics.
1. Compruebe que la opción “Diseño HTML” esté desactivada:

   ![](assets/html_design_toggle.png)

1. El código siguiente es un ejemplo de lo que podría pegar en su diseño:

   ```
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. Configure una actividad de recomendaciones basada en formulario que utilice este diseño.

   1. Vaya a la página Actividades.
   1. Haga clic en **[!UICONTROL Crear actividad]**.
   1. Seleccione **[!UICONTROL Recommendations]**.
   1. En **[!UICONTROL Elegir Compositor de experiencias]**, seleccione **[!UICONTROL Formulario]**.

   1. En Ubicación, introduzca el texto: “Sample_Recs_Response”
   1. En **[!UICONTROL Contenido predeterminado]**, haga clic en la flecha hacia abajo y, a continuación, haga clic en **[!UICONTROL Añadir recomendación]**.
   1. Elija un tipo de página. Esto determina el filtrado inicial de la siguiente pantalla.
   1. Seleccione una tarjeta Criterios y, a continuación, haga clic en **[!UICONTROL Siguiente]**.
   1. Seleccione el diseño que ha creado en el paso anterior y, a continuación, haga clic en **[!UICONTROL Guardar]**.
   1. Complete el proceso de configuración.
   1. Haga clic en la flecha derecha situada junto a **[!UICONTROL Inactivo]** y, a continuación, seleccione **[!UICONTROL Activar]**.

1. Una vez configurada y activada la actividad, puede configurar una solicitud de muestra para recuperar la respuesta JSON limpia.

   Desde el momento en que guarda la actividad, Target tendrá que crear un modelo para respaldar la configuración de los criterios seleccionados. En función de una serie de factores, esto puede llevar cierto tiempo. Los resultados aparecen una vez creado el modelo.

   Por ejemplo:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   donde

| Parámetro | Valor |
|--- |--- |
| `[YOUR_CLIENT_CODE]` | Código de cliente de Target (disponible en ../target/products.html#recsSettings > Token de API de Recommendations > Código de cliente). |
| `[YOUR_MBOX_NAME]` | Nombre seleccionado en la sección &quot;ubicaciones&quot; del Recommendations basado en formularios, en este caso Sample_Recs_Response. |
| `[ENTITY_ID`] | El `entity.id` de un artículo del catálogo. |
| `[AT_PROPERTY_TOKEN]` | (Opcional) Añada este parámetro si ha seleccionado una Propiedad (parte de los permisos de empresa) durante la configuración de la actividad. |

Cuando se haya ejecutado el algoritmo y tenga los resultados, su respuesta tendría que parecerse a esta:

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## Trucos y consejos adicionales sobre objetos JSON {#section_C305673C68944749969DB239E3221DC2}

También puede enviar una sencilla lista de elementos delimitada por comas configurando un diseño con la sintaxis siguiente:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Alternativamente, también puede enviar información adicional en la respuesta. El siguiente archivo de código es un ejemplo más complejo que devuelve mucho más que los identificadores de la entidad con sus espacios asociados (solicitud). Este ejemplo de diseño también devuelve detalles de la actividad, detalles del perfil de Target (según corresponda) y otros `entity.attributes` asociados a los elementos devueltos.

```
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

## Training video: Create custom designs in Recommendations (3:20) ![Overview badge](/help/assets/overview.png)

Este vídeo contiene la información siguiente:

* Crear un diseño personalizado
* Cómo hacer referencia a las variables de visualización en los diseños

>[!VIDEO](https://video.tv.adobe.com/v/27687)

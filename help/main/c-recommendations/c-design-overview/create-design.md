---
keywords: diseño de recomendaciones;crear diseño;copiar diseño
description: Aprenda a crear un diseño  [!DNL Target Recommendations] usando un diseño predeterminado o creando uno personalizado para que se ajuste mejor al diseño de la página.
title: ¿Cómo se crea un diseño en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 19%

---

# Crear un diseño

Un diseño define el modo en que las recomendaciones aparecen en una página.

Puede crear un diseño de [!UICONTROL Recommendations] mediante un diseño predeterminado o un diseño personalizado. La pantalla **[!UICONTROL Recommendations > Designs]** muestra tanto las tarjetas de diseño predeterminadas como los diseños que se hayan creado en su cuenta.

Tenga en cuenta la siguiente información cuando trabaje con diseños:

* Puede crear un diseño de Recommendations utilizando un diseño predeterminado o puede crear uno personalizado.
* No se puede editar ni eliminar un diseño predeterminado.
* Puede editar, copiar o eliminar un diseño personalizado.
* Para crear un diseño basado en un diseño predeterminado, primero debe copiar el diseño y, a continuación, editar la copia.

Esta ilustración muestra el diseño predeterminado 1 x 4:

![1 x 4 diseño predeterminado](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

Esta ilustración muestra un diseño personalizado:

![Diseño personalizado](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

Puede crear un diseño durante el proceso de creación de actividades desde el [!UICONTROL Visual Experience Composer] (VEC) o desde la biblioteca de diseño fuera de la creación de actividades. En las secciones siguientes se da por hecho que está creando diseños a partir de la biblioteca, pero los pasos son similares.

## Creación de diseños

Puede crear un diseño basado en un diseño predeterminado o puede crear uno personalizado.

### Crear un diseño basado en un diseño predeterminado

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** para mostrar la biblioteca [!UICONTROL Designs].


1. Haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) del diseño que desea crear y, a continuación, haga clic en **[!UICONTROL Copy]**.

   Se muestra el cuadro de diálogo [!UICONTROL Create Design].

1. Escriba **[!UICONTROL &#x200B; Name]** y una imagen de vista previa opcional para mostrarla en la tarjeta de diseño.

   Cuando se usa un diseño predeterminado, el nombre del diseño y &quot;Copiar&quot; aparecen en el campo **[!UICONTROL Content Name]**. Puede editar el nombre. También puede seleccionar una imagen para mostrarla en la tarjeta de diseño.

1. (Condicional) Edite el diseño **[!UICONTROL Code]** como desee.

   Los diseños de Recommendations utilizan el lenguaje de diseño Velocity de código abierto. Encontrará información sobre Velocity en [https://velocity.apache.org](https://velocity.apache.org) y en [Personalizar un diseño con Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   Un diseño puede ser HTML o no HTML. De manera predeterminada, los diseños de HTML se encapsulan con una etiqueta `<div>` para permitir el rastreo de clics en un entorno web. Los diseños que no son de HTML son para entornos que no son de web donde el rastreo de clics no es posible. Deslice el conmutador [!UICONTROL HTML Design] a la posición &quot;desactivado&quot; para utilizar código que no sea de HTML.

   >[!NOTE]
   >
   >El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99.

1. Haga clic en **[!UICONTROL Create]**.

### Crear un diseño personalizado

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** para mostrar la biblioteca [!UICONTROL Designs].

1. Haga clic en **[!UICONTROL Create Design]**.

   Si desea basar el nuevo diseño personalizado en un diseño existente, haga clic en el icono [!UICONTROL More Actions] ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) del diseño que desea crear y, a continuación, haga clic en [!UICONTROL Copy]. A continuación, puede editar la copia para crear un nuevo diseño personalizado.

1. Agregar **[!UICONTROL Name]** y una imagen de vista previa opcional.

1. (Condicional) Edite el diseño **[!UICONTROL Code]** como desee.

   Consulte la información del paso 4 anterior para obtener más información.

1. Haga clic en **[!UICONTROL Create]**.

## Editar, copiar o eliminar un diseño

Recuerde que no puede editar ni copiar un diseño predeterminado; sólo puede copiar diseños predeterminados.

Haga clic en el icono [!UICONTROL More Actions] ( ![icono de más acciones](/help/main/assets/icons/MoreSmallList.svg) ) del diseño que desee editar o eliminar y, a continuación, haga clic en el icono correspondiente: [!UICONTROL Edit], [!UICONTROL Copy] o [!UICONTROL Delete].

Puede copiar un diseño existente para crear un diseño duplicado que luego pueda modificar. Este proceso permite crear un diseño similar con menos esfuerzo.

Tenga en cuenta que los diseños están disponibles en toda la cuenta. Asegúrese de tener en cuenta el uso en todas las cuentas antes de eliminar un diseño. Los diseños eliminados no se pueden recuperar.

## Ejemplo de JSON {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

El siguiente ejemplo muestra cómo se pueden devolver respuestas JSON al configurar una actividad a través de [editor basado en formularios](/help/main/c-experiences/form-experience-composer.md).

1. Cree un diseño desde [!UICONTROL Design library] o desde el flujo de trabajo basado en formularios. Si intenta crear un diseño dentro del flujo de trabajo [!UICONTROL Visual Experience Composer] (VEC), no podrá crear nada más que un diseño de HTML, que está dentro de un `<div>` para fines de seguimiento de clics.

1. Compruebe que la opción “Diseño HTML” esté desactivada:

   ![imagen html_design_toggle](assets/html_design_toggle.png)

1. El siguiente código es un ejemplo de lo que puede pegar en el diseño:

   ```javascript
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

1. Configure una actividad [!DNL Recommendations] basada en formularios que use este diseño.

   1. Vaya a la página **[!UICONTROL Activities]**.
   1. Haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.
   1. En **[!UICONTROL Choose Experience Composer]**, seleccione **[!UICONTROL Form]** y haga clic en **[!UICONTROL Next]**.
   1. En Ubicación, introduzca el texto: “Sample_Recs_Response”
   1. En **[!UICONTROL Default Content]**, haga clic en la flecha hacia abajo y luego haga clic en **[!UICONTROL Add Recommendation]**.
   1. Elija un tipo de página. Esto determina el filtrado inicial de la siguiente pantalla.
   1. Seleccione una tarjeta Criterios y luego haga clic en **[!UICONTROL Next]**.
   1. Seleccione el diseño que creó en el paso anterior y luego haga clic en **[!UICONTROL Next]**.
   1. Complete el proceso de configuración.
   1. Haga clic en la flecha derecha junto a **[!UICONTROL Inactive]** y luego seleccione **[!UICONTROL Activate]**.

1. Una vez configurada y activada la actividad, puede configurar una solicitud de muestra para recuperar la respuesta JSON limpia.

   Desde el momento en que guarda la actividad, [!DNL Target] necesita generar un modelo para admitir la configuración de criterios seleccionada. Dependiendo de una serie de factores, este proceso podría llevar algún tiempo. Los resultados aparecen una vez creado el modelo.

   Por ejemplo:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   donde

   | Parámetro | Valor |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Código de cliente de Target (disponible en /help/target/products.html#recsSettings > Token de la API de Recommendations > Código de cliente). |
   | `[YOUR_MBOX_NAME]` | El nombre que ha seleccionado en la sección &quot;ubicaciones&quot; de Recommendations basado en formularios, en este caso Sample_Recs_Response. |
   | `[ENTITY_ID` | El `entity.id` de un artículo del catálogo. |
   | `[AT_PROPERTY_TOKEN]` | (Opcional) Añada este parámetro si ha seleccionado una Propiedad (parte de los permisos de empresa) durante la configuración de la actividad. |

Cuando se haya ejecutado el algoritmo y tenga los resultados, su respuesta tendría que parecerse a esta:

![imagen json_recommendation](assets/json_recommendation.png){width="575px"}

## Trucos y consejos adicionales sobre objetos JSON {#section_C305673C68944749969DB239E3221DC2}

También puede enviar una lista de elementos simple delimitada por comas configurando un diseño con la siguiente sintaxis:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Alternativamente, también puede enviar información adicional en la respuesta. El siguiente archivo de código es un ejemplo más complejo que devuelve mucho más que los identificadores de la entidad con sus espacios asociados (solicitud). Este ejemplo de diseño también devuelve detalles de la actividad, [!UICONTROL Target Profile] detalles (según corresponda) y otros `entity.attributes` asociados con los elementos devueltos.

```javascript
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

## Vídeo de formación: Creación de diseños personalizados en Recommendations (3:20) ![Distintivo de información general](/help/main/assets/overview.png)

Este vídeo contiene la información siguiente:

* Crear un diseño personalizado
* Aprenda a hacer referencia a las variables de visualización en sus diseños

>[!VIDEO](https://video.tv.adobe.com/v/35325?captions=spa)

---
keywords: diseño de recomendaciones;crear diseño;copiar diseño
description: Aprenda a crear un diseño de [!DNL Target Recommendations] con un diseño predeterminado o creando uno personalizado para que se ajuste mejor al diseño de una página.
title: Crear un diseño
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
TQID: 'https://experienceleague.adobe.com/GLWcKaQGl6TmL9i7LYUiYepg6SkAjBtL-78-zlaWCTk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 11%
---
# Crear un diseño {#create-design}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear, editar, copiar y eliminar diseños en [!DNL Adobe Target Recommendations], y a devolver recomendaciones como JSON.

>[!ENDSHADEBOX]

Un diseño define el modo en que las recomendaciones aparecen en una página. Un diseño se puede basar en un diseño predeterminado o crearse como un diseño personalizado. La pantalla **[!UICONTROL Recommendations]** > **[!UICONTROL Diseños]** muestra tanto las tarjetas de diseño predeterminadas como los diseños que se han creado en la cuenta.

* Un diseño predeterminado no se puede editar ni eliminar.
* Un diseño personalizado se puede editar, copiar o eliminar.
* Para crear un diseño basado en un diseño predeterminado, copie primero el diseño y, a continuación, edite la copia.

Se puede crear un diseño durante el proceso de creación de actividades desde el **[!UICONTROL Compositor de experiencias visuales]** (VEC), o desde la biblioteca de diseños fuera de la creación de actividades. Los siguientes pasos suponen que el diseño se crea a partir de la biblioteca, pero los pasos son similares.

## Crear un diseño a partir de la biblioteca {#steps}

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Diseños]** para mostrar la biblioteca **[!UICONTROL Diseños]**.

1. Inicie el diseño de una de las siguientes maneras:

   * Para basar el diseño en uno predeterminado o en uno existente, haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) para ese diseño y, a continuación, haga clic en **[!UICONTROL Copiar]**. Se muestra el cuadro de diálogo **[!UICONTROL Crear diseño]**. La copia editada se convierte en un nuevo diseño personalizado.
   * Para crear un diseño personalizado desde cero, haga clic en **[!UICONTROL Crear diseño]**.

     ![Biblioteca de diseños con el botón Crear diseño resaltado](../assets/design_1.png)

1. Escriba un **[!UICONTROL Nombre]** y seleccione una imagen de vista previa opcional para mostrarla en la tarjeta de diseño.

   Cuando se usa un diseño predeterminado, el nombre del diseño seguido de &quot;Copiar&quot; aparece en el campo **[!UICONTROL Nombre del contenido]**. El nombre se puede editar.

1. (Condicional) Edite el diseño **[!UICONTROL Code]** según desee.

   Los diseños de Recommendations utilizan el lenguaje de diseño Velocity de código abierto. Para obtener información acerca de Velocity, consulte [https://velocity.apache.org](https://velocity.apache.org) y [Personalizar un diseño con Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   Un diseño puede ser HTML o no HTML. De manera predeterminada, los diseños de HTML se encapsulan con una etiqueta `<div>` para permitir el seguimiento de clics en un entorno web. Los diseños que no son HTML son para entornos que no son de web donde los clics no se pueden rastrear. Deslice el botón de alternancia **[!UICONTROL HTML Design]** a la posición &quot;desactivado&quot; para utilizar código que no sea de HTML.

   >[!NOTE]
   >
   >El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99.

1. Haga clic en **[!UICONTROL Crear]**.

1. Haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) para que el diseño edite, copie o elimine y, a continuación, haga clic en la opción adecuada: **[!UICONTROL Editar]**, **[!UICONTROL Copiar]** o **[!UICONTROL Eliminar]**.

   ![Biblioteca de diseños con el menú Más acciones abierto, que muestra Editar, Copiar y Eliminar](../assets/design_2.png)

Los diseños están disponibles en toda la cuenta. El uso en todas las cuentas debe tenerse en cuenta antes de eliminar un diseño. Los diseños eliminados no se pueden recuperar.

## Ejemplo de JSON {#json-example}

El siguiente ejemplo muestra cómo se pueden devolver las respuestas JSON cuando se configura una actividad con el [editor basado en formularios](/help/main/c-experiences/form-experience-composer.md).

1. Cree un diseño desde la **[!UICONTROL biblioteca de diseños]** o desde el flujo de trabajo basado en formularios. Un diseño que se crea dentro del flujo de trabajo del **[!UICONTROL Compositor de experiencias visuales]** (VEC) solo puede ser un diseño de HTML, que está dentro de un `<div>` con fines de seguimiento de clics.

1. Asegúrese de que la opción **[!UICONTROL HTML Design]** esté desactivada:

   ![HTML Design cambia a la posición desactivada](/help/main/c-recommendations/c-design-overview/assets/html_design_toggle.png)

1. Pegue un código como el siguiente ejemplo en el diseño:

   +++ Código de diseño de muestra que devuelve una lista de ID de entidad.

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

   +++

1. Configure una actividad [!DNL Recommendations] basada en formularios que use este diseño.

   +++ Obtenga información sobre cómo configurar una actividad [!DNL Recommendations] basada en formularios 

   1. Vaya a la página **[!UICONTROL Actividades]**.
   1. Haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Recommendations]**.
   1. En **[!UICONTROL Elegir Compositor de experiencias]**, seleccione **[!UICONTROL Formulario]** y, a continuación, haga clic en **[!UICONTROL Siguiente]**.
   1. En Ubicación, introduzca el texto &quot;Sample_Recs_Response&quot;.
   1. En **[!UICONTROL Contenido predeterminado]**, haga clic en la flecha hacia abajo y, a continuación, haga clic en **[!UICONTROL Añadir recomendación]**.
   1. Elija un tipo de página. Esto determina el filtrado inicial de la siguiente pantalla.
   1. Seleccione una tarjeta Criterios y, a continuación, haga clic en **[!UICONTROL Siguiente]**.
   1. Seleccione el diseño que se creó en el paso anterior y luego haga clic en **[!UICONTROL Siguiente]**.
   1. Complete el proceso de configuración.
   1. Haga clic en la flecha derecha situada junto a **[!UICONTROL Inactivo]** y, a continuación, seleccione **[!UICONTROL Activar]**.

   +++

1. Una vez configurada y activada la actividad, se puede configurar una solicitud de muestra para recuperar la respuesta JSON limpia.

   Desde el momento en que se guarda la actividad, [!DNL Target] necesita generar un modelo para admitir la configuración de criterios seleccionada. Según varios factores, este proceso puede tardar algún tiempo. Los resultados aparecen una vez que se ha creado el modelo.

   Por ejemplo:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   donde

   | Parámetro | Valor |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | El código de cliente [!DNL Target] (disponible en /help/target/products.html#recsSettings > Token de la API de Recommendations > Código de cliente). |
   | `[YOUR_MBOX_NAME]` | El nombre seleccionado en la sección &quot;ubicaciones&quot; de la actividad de Recommendations basada en formularios, en este caso Sample_Recs_Response. |
   | `[ENTITY_ID]` | `entity.id` de un elemento del catálogo. |
   | `[AT_PROPERTY_TOKEN]` | (Opcional) Se agregó cuando se seleccionó una propiedad (parte de los permisos de Enterprise) durante la configuración de la actividad. |

Una vez que el algoritmo se ha ejecutado y los resultados están disponibles, la respuesta tiene un aspecto similar al siguiente:

![Respuesta JSON con los elementos recomendados](/help/main/c-recommendations/c-design-overview/assets/json_recommendation.png){width="575px"}

## Sugerencias adicionales sobre objetos JSON {#json-tips}

También se puede devolver una lista de elementos simple delimitada por comas configurando un diseño con la siguiente sintaxis:

```
$entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

También se puede enviar información adicional en la respuesta. El siguiente código es un ejemplo más complejo que devuelve mucho más que los ID de entidad con sus espacios asociados (pedidos). Este ejemplo de diseño también devuelve detalles de la actividad, detalles de **[!UICONTROL perfil de Target]** (según corresponda) y otros `entity.attributes` asociados con los elementos devueltos.

+++ Código de diseño de muestra que devuelve detalles de actividad, perfil y entidad.

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

+++


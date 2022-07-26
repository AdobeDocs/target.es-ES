---
keywords: oferta remota;creación de oferta remota
description: Obtenga información sobre cómo crear ofertas JSON en Adobe [!DNL Target] para usar en el Compositor de experiencias basadas en formularios. Las ofertas JSON son útiles para marcos de SPA o integraciones del lado del servidor.
title: ¿Cómo creo ofertas JSON?
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 38%

---

# Creación de ofertas JSON

Cree ofertas JSON en la variable [!UICONTROL Biblioteca de ofertas] en [!DNL Adobe Target] para usar en [!UICONTROL Compositor de experiencias basadas en formularios].

Las ofertas JSON se pueden utilizar en actividades basadas en formularios mediante las cuales se pueden habilitar casos de uso en los que [!DNL Target]La toma de decisiones de es necesaria para enviar una oferta en formato JSON para su consumo en SPA marco de trabajo o integraciones del lado del servidor.

## Consideraciones de JSON

Cuando trabaje con ofertas JSON, tenga en cuenta la información siguiente:

* Actualmente, las ofertas JSON solo están disponibles para [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT).
* Las ofertas JSON se pueden usar en [actividades basadas en formularios](/help/main/c-experiences/form-experience-composer.md) solo.
* La oferta JSON se puede recuperar directamente cuando usa Server Side API, Mobile SDK o NodeJS SDK.
* En el explorador, las ofertas JSON se pueden recuperar SOLAMENTE a través de at.js 1.2.3 (o versiones posteriores) y utilizando   [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} filtrando acciones usando la variable `setJson` acción.
* Las ofertas JSON se proporcionan como objetos JSON nativos en vez de como cadenas. Los consumidores de estos objetos ya no son necesarios para gestionar objetos como cadenas y convertirlos en objetos JSON.
* Las ofertas JSON no se aplican automáticamente, a diferencia de otras ofertas (como la ofertas HTML), porque las ofertas JSON son ofertas no visuales. Los desarrolladores deben escribir código para obtener explícitamente la oferta utilizando   [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank}.

## Creación de una oferta JSON {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Haga clic en **[!UICONTROL Ofertas]** > **[!UICONTROL Ofertas de código]**.

   ![Pestaña Ofertas > Ofertas de código](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta JSON]**.

   ![imagen offer-json](assets/offer-json.png)

1. Escriba el nombre de una oferta.
1. Escriba o pegue su código JSON en el recuadro **[!UICONTROL Código]**.
1. Haga clic en **[!UICONTROL Guardar]**.

## Ejemplo de JSON {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

Las ofertas JSON solo se admiten en actividades creadas con la variable [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). En estos momentos, la única forma de poder utilizar las ofertas JSON es mediante llamadas directas a API.

Vea el siguiente ejemplo:

```json
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

Las acciones pasadas a llamada de retorno de éxito son una matriz de objeto. Si tenemos una sola oferta JSON con este contenido:

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

La matriz de acciones tendrá esta estructura:

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

Para extraer la oferta JSON, debe iterar mediante acciones y encontrar la acción con la variable `setJson` y luego se repite a través de la matriz de contenido.

## Caso de uso {#section_85B07907B51A43239C8E3498EF58B1E5}

Pongamos que la siguiente oferta JSON se entrega a su página web:

```json
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

El código siguiente muestra cómo acceder al atributo “bienvenida”:

```json
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## Ejemplo de oferta JSON utilizando Atributos de perfil CDP en tiempo real

Los atributos de perfil CDP en tiempo real se pueden compartir con Target para su uso en ofertas de HTML y ofertas JSON. (Tenga en cuenta que esta función está en versión beta).

Ejemplo de caso de uso: Como especialista en marketing en línea, Grace quiere que el AEP/Perfil unificado comparta valores de atributo con Target para proporcionar una personalización en tiempo real. Mediante el uso de Atributos de perfil CDP en tiempo real, Grace puede mostrar el valor del atributo AEP en una oferta de Target mediante el reemplazo de tokens. Por ejemplo, puede personalizar según el color favorito de un cliente utilizando `${aep.profile.favoriteColor}`, o su nivel de lealtad y valor de punto de lealtad mediante los tokens `${aep.loyalty.tier}` y `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](assets/offer-json-aep-shared-attribute.png)

En el ejemplo que se muestra arriba, tenga en cuenta que la asignación de valores predeterminados es opcional.

## Filtrado de ofertas por tipo de oferta JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Puede filtrar la variable [!UICONTROL Ofertas] biblioteca por tipo de oferta JSON haciendo clic en el botón **[!UICONTROL Tipo]** lista desplegable y, a continuación, seleccionando la **[!UICONTROL JSON]** casilla de verificación.

![imagen offer-json-filter](assets/offer-json-filter.png)

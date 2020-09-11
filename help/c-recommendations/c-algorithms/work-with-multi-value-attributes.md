---
keywords: multi-value;attributes;recommendations;multi value;multivalue;multi-value
description: Información sobre cómo trabajar con un campo de varios valores en Adobe Target Recommendations mediante operadores especiales de varios valores.
title: Uso de atributos de varios valores en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# Trabajar con atributos de varios valores

A veces puede que desee trabajar con un campo de varios valores. Veamos los siguientes ejemplos:

* Las películas se oferta a los usuarios. Una película determinada tiene múltiples actores.
* Vendes entradas a conciertos. Un usuario determinado tiene varias bandas favoritas.
* Vendes ropa. Hay una camisa disponible en varios tamaños.

Para administrar las recomendaciones en estos escenarios, puede pasar datos de varios valores a operadores especiales de varios valores [!DNL Target Recommendations] y usarlos.

Para permitir [!DNL Recommendations] la identificación de datos de varios valores, debe enviarse como una matriz JSON, como en los ejemplos de código siguientes.

## Transmisión de un parámetro de varios valores en JavaScript

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

Para obtener más información, consulte [Implementación de atributos](/help/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) de varios valores en atributos *de entidad* personalizados.

## Transmisión de un atributo de entidad de varios valores en un archivo CSV

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

Cuando se proporciona un atributo de entidad, un atributo de perfil o un parámetro de mbox como multivalor según el formato anterior, [!DNL Recommendations] se deduce automáticamente que el campo es de varios valores.

Los siguientes operadores están disponibles para su uso con atributos de entidad, perfil y mbox de varios valores:

* [!UICONTROL está contenido en lista]
* [!UICONTROL no está contenido en la lista]

## Uso de atributos de varios valores en las reglas de inclusión

>[!NOTE]
>
>Actualmente, la compatibilidad con la coincidencia dinámica con atributos de varios valores solo está disponible en criterios cuando se usa una regla de coincidencia de atributos de perfil o parámetro (mbox) al comparar un solo valor en el lado izquierdo con un valor múltiple en el lado derecho. Actualmente, los atributos de varios valores no se admiten en promociones, coincidencia de atributos de entidad o en listas en el lado izquierdo de las reglas de inclusión.

### Ejemplo: Excluir elementos vistos recientemente

Supongamos que desea evitar que se recomienden las películas que se encuentran en las diez últimas películas vistas del usuario. En primer lugar, escriba una secuencia de comandos de perfil llamada `user.lastWatchedMovies` para rastrear las últimas diez películas visualizadas como una matriz JSON. A continuación, puede excluir los elementos mediante la siguiente regla de inclusión:

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

Representación de la regla de inclusión de la API JSON:

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": " user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### Ejemplo: Recomendar elementos de los favoritos del usuario

Supongamos que desea recomendar entradas sólo para conciertos si la banda que toca es una de las bandas favoritas del usuario. En primer lugar, asegúrese de tener una variable de perfil llamada `profile.favoriteBands` que contenga las bandas favoritas del usuario. A continuación, asegúrese de que el catálogo incluye un atributo `entity.artistPerforming` que incluye al artista que realiza el concierto. A continuación, puede utilizar la siguiente regla de inclusión:

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

Representación de la regla de inclusión de la API JSON:

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### Ejemplo: Creación de la API de criterios que recomiendan elementos de los favoritos de un usuario

Los criterios que utilizan reglas de filtrado de varios valores, como todos los criterios, se pueden crear a través de las API de E/S de Adobe. A continuación se proporciona una llamada a API de ejemplo para crear un criterio en el que el atributo de entidad `id` esté contenido en la lista del parámetro de mbox `favorites` :

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

Esto se emparejaría con JavaScript en la página para pasar el contenido de favoritos:

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```

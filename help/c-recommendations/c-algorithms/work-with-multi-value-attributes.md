---
keywords: varios valores;atributos;recomendaciones;varios valores;multivalor;varios valores
description: Aprenda a trabajar con un campo de varios valores en Adobe [!DNL Target] Recommendations mediante operadores especiales de varios valores, por ejemplo, al recomendar películas con varios actores.
title: ¿Puedo usar atributos de varios valores en Recommendations?
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 1%

---

# Trabajar con atributos de varios valores

A veces, es posible que desee trabajar con un campo de varios valores. Veamos los siguientes ejemplos:

* Las películas se ofrecen a los usuarios. Una película determinada tiene múltiples actores.
* Vendes entradas a conciertos. Un usuario dado tiene varias bandas favoritas.
* Vendes ropa. Hay una camisa disponible en varios tamaños.

Para gestionar las recomendaciones en estos casos, puede pasar datos de varios valores a [!DNL Target Recommendations] y utilizar operadores especiales de varios valores.

Para permitir que [!DNL Recommendations] identifique los datos de varios valores, debe enviarse como una matriz JSON, como en los ejemplos de código siguientes.

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

Para obtener más información, consulte [Implementación de atributos de varios valores](/help/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) en *Atributos de entidad personalizados*.

## Pasar un atributo de entidad de varios valores en un archivo CSV

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

Cuando se proporciona un atributo de entidad, un atributo de perfil o un parámetro de mbox como multivalor según el formato anterior, [!DNL Recommendations] deduce automáticamente que el campo es de varios valores.

Los siguientes operadores están disponibles para su uso con atributos de entidad, perfil y mbox de varios valores:

* [!UICONTROL está contenido en la lista]
* [!UICONTROL no está contenido en la lista]

## Uso de atributos de varios valores en reglas de inclusión

>[!NOTE]
>
>Actualmente, la compatibilidad con la coincidencia dinámica con atributos de varios valores solo está disponible en criterios cuando se utiliza una regla de coincidencia de atributos de perfil o de parámetro (mbox) al comparar un único valor a la izquierda con un múltiples valores a la derecha. Actualmente, los atributos de varios valores no se admiten en las promociones, la coincidencia de atributos de entidad ni en las listas del lado izquierdo de las reglas de inclusión.

### Ejemplo: Excluir elementos vistos recientemente

Supongamos que desea evitar que se recomienden películas que estén dentro de las diez últimas películas vistas del usuario. En primer lugar, escriba un script de perfil llamado `user.lastWatchedMovies` para rastrear las últimas diez películas vistas como una matriz JSON. A continuación, puede excluir los elementos utilizando la siguiente regla de inclusión:

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

Representación de la API JSON de la regla de inclusión:

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### Ejemplo: Recomendar artículos de los favoritos del usuario

Supongamos que desea recomendar entradas sólo para conciertos si la banda que toca es una de las bandas favoritas del usuario. En primer lugar, asegúrese de que tiene una variable de perfil denominada `profile.favoriteBands` que contiene las bandas favoritas del usuario. A continuación, asegúrese de que su catálogo incluye un atributo `entity.artistPerforming` que incluye al artista que actúa en el concierto. A continuación, puede utilizar la siguiente regla de inclusión:

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

Representación de la API JSON de la regla de inclusión:

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

### Ejemplo: Creación de API de criterios que recomiendan elementos de los favoritos de un usuario

Los criterios que utilizan reglas de filtrado de varios valores, como todos los criterios, se pueden crear mediante las API de Adobe I/O. Aquí se proporciona un ejemplo de llamada de API para crear un criterio en el que el atributo de entidad `id` está contenido en la lista de parámetros de mbox `favorites`:

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

Esto estaría emparejado con JavaScript en la página para pasar el contenido de favoritos:

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```

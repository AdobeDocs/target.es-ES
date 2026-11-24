---
keywords: varios valores;atributos;recomendaciones;varios valores;varios valores;varios valores
description: Aprenda a trabajar con un campo de varios valores en [!DNL Target Recommendations] mediante operadores especiales de varios valores.
title: Trabajo con atributos de varios valores
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 2%
---
# Trabajo con atributos de varios valores {#multi-value-attributes}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información sobre cómo enviar datos de varios valores a [!DNL Adobe Target Recommendations] y cómo usarlos en reglas de inclusión con operadores de varios valores.

>[!ENDSHADEBOX]

Un campo de varios valores contiene varios valores para el mismo artículo o visitante. Por ejemplo:

* Películas ofrecidas a los usuarios: una película determinada tiene varios actores.
* Entradas vendidas para conciertos: un usuario dado tiene múltiples bandas favoritas.
* Ropa vendida: una camisa está disponible en múltiples tallas.

Para controlar las recomendaciones en estos casos, se pueden pasar datos de varios valores a [!DNL Target Recommendations] y utilizarlos con operadores especiales de varios valores.

## Envío de datos de varios valores {#send}

Para permitir que [!DNL Recommendations] identifique datos de varios valores, deben enviarse como una matriz JSON.

Para un parámetro de varios valores en JavaScript (`targetPageParams`), consulte [Implementación de atributos de varios valores](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) en *Atributos de entidad personalizados*.

En un archivo CSV, se envía un atributo de entidad de varios valores como una matriz JSON en la celda del atributo, como en el siguiente ejemplo.

+++ Archivo CSV de ejemplo con un atributo de varios valores

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

+++

Cuando se proporciona un atributo de entidad, un atributo de perfil o un parámetro de mbox como varios valores en este formato, [!DNL Recommendations] infiere automáticamente que el campo es de varios valores.

## Uso de atributos de varios valores en reglas de inclusión {#multi-value-inclusion-rules}

Los siguientes operadores están disponibles para su uso con atributos de entidad, perfil y mbox de varios valores:

* **[!UICONTROL está en la lista]**
* **[!UICONTROL no está en la lista]**

>[!NOTE]
>
>Actualmente, la compatibilidad con la coincidencia dinámica en atributos de varios valores solo está disponible en criterios que utilizan una regla de coincidencia de atributos de perfil o de parámetro (mbox) que compara un solo valor del lado izquierdo con uno de varios valores del lado derecho. Actualmente no se admiten atributos de varios valores en promociones, coincidencia de atributos de entidad o listas en la parte izquierda de reglas de inclusión.

### Ejemplo: Excluir elementos vistos recientemente

Para evitar que se recomienden películas de las últimas diez películas vistas del usuario, escriba primero un script de perfil denominado `user.lastWatchedMovies` que registre las últimas diez películas vistas como una matriz JSON. Los elementos se pueden excluir con la siguiente regla de inclusión:

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
```

Representación de la regla de inclusión en la API JSON:

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

### Ejemplo: Recomendar elementos de los favoritos del usuario

Para recomendar entradas para conciertos únicamente cuando la banda que toca es una de las bandas favoritas del usuario, se requieren dos elementos: una variable de perfil llamada `profile.favoriteBands` que contiene las bandas favoritas del usuario y un atributo `entity.artistPerforming` en el catálogo que contiene la artista que actúa en el concierto. A continuación, se puede utilizar la siguiente regla de inclusión:

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
```

Representación de la regla de inclusión en la API JSON:

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

### Ejemplo: creación de API de criterios que recomiendan elementos de los favoritos de un usuario

Los criterios que utilizan reglas de filtrado de varios valores se pueden crear mediante las API [!DNL Adobe Target], como todos los criterios. La siguiente llamada de API de ejemplo crea un criterio en el que el atributo de entidad `id` está contenido en la lista de parámetros de mbox `favorites`:

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

Esta llamada está emparejada con JavaScript en la página que pasa el contenido de los favoritos:

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```

---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtre dinámicamente en Adobe Target Recommendations comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que el usuario haya interactuado.
title: Filtrar por coincidencia de atributos de entidad en reglas de inclusión dinámica en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---


# ![Coincidencia de atributos de entidad PREMIUM](/help/assets/premium.png)

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual como en el siguiente ejemplo:

Si el mbox de una Página de aterrizaje de marca devuelve `entity.brand=Nike`, solo se devuelven los productos Nike y se muestran en esa página. Del mismo modo, en la Página de aterrizaje de marcas para Adidas, solo se devuelven los productos Adidas. Con este tipo de regla de inclusión dinámica, el usuario solo tiene que especificar una regla de recomendación que devuelva resultados de marca relevantes en todas las páginas de marca en lugar de especificar una colección o un filtro estático para que coincida con cada nombre de marca.

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL La coincidencia] de atributos de entidad permite recomendar solo los elementos que coinciden, por ejemplo:

* Un atributo del elemento que el usuario está viendo actualmente
* El artículo que el usuario vio más recientemente
* El artículo que el usuario compró más recientemente
* El artículo que el usuario vio con más frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### La venta al por mayor a un producto más caro

Supongamos que usted es un comerciante de ropa y desea animar a los usuarios a considerar artículos de mayor precio y, por lo tanto, más rentables. Puede utilizar los operadores &quot;es igual que&quot; y &quot;está entre&quot; para promocionar artículos más caros que procedan de la misma categoría y de la misma marca. Por ejemplo, un vendedor de zapatos puede promocionar zapatos deportivos más caros en un esfuerzo por mejorar la venta de un visitante mirando zapatos deportivos, como en la siguiente muestra de código:

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Promoción de productos con etiquetas privadas

Puede combinar filtros dinámicos y estáticos para promocionar productos de etiquetas privadas. Por ejemplo, una compañía de suministro de oficina puede promocionar cartuchos de tóner de la marca propia de la compañía para llevar a cabo una venta más rentable de un visitante mirando el tóner, y promocionar plumas de la marca propia de la compañía para llevar a cabo una venta más rentable de un visitante mirando plumas, como en la siguiente muestra de código:

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

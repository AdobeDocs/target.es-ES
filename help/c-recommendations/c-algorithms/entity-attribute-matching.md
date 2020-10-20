---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtre dinámicamente en Adobe Target Recommendations comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que el usuario haya interactuado.
title: Filtrar por coincidencia de atributos de entidad en reglas de inclusión dinámica en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 60b71c426b61bb16a23976da9a03926f8e73cf6c
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---


# ![Coincidencia de atributos de entidad PREMIUM](/help/assets/premium.png)

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual como en el ejemplo siguiente:

Si el mbox de una Página de aterrizaje de marca devuelve `entity.brand=brandA`, solo se devuelven y muestran en esa página los productos de marca A. Del mismo modo, en la Página de aterrizaje de la Marca B, solo se devuelven los productos de la Marca B. Con este tipo de regla de inclusión dinámica, el usuario solo tiene que especificar una regla de recomendación que devuelva resultados de marca relevantes en todas las páginas de marca en lugar de especificar una colección o un filtro estático para que coincida con cada nombre de marca.

Tenga en cuenta que debe enviar el `entity.brand` mensaje en el mbox en esas páginas de aterrizaje para que esto funcione.

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL La coincidencia] de atributos de entidad permite recomendar solo los elementos que coinciden, por ejemplo:

* Un atributo del elemento que el usuario está viendo actualmente
* El artículo que el usuario vio más recientemente
* El artículo que el usuario compró más recientemente
* El artículo que el usuario vio con más frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### Recomendar artículos según la marca

Después de crear las reglas de atributos de entidad, filtrarán todas las recomendaciones con atributos que no coincidan con el valor de entidad que se pasa a la página.

El siguiente ejemplo muestra recomendaciones que coinciden con la marca de producto mostrada en la página:

Cuando visita una página que incluye un producto de Marca A, la página establece el valor del `entity.brand` parámetro en &quot;Marca A&quot;.

![Ejemplo de llamada de Destinatario](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

En las recomendaciones de la página, solo verá los productos de marca A.

![Recomendaciones de marca A](/help/c-recommendations/c-algorithms/assets/brandA.png)

Si luego vista una página de producto de Marca B, el valor se restablecerá a &quot;MarcaB&quot; y verá los productos de Marca B recomendados en las páginas de productos de Marca B. `entity.brand`

![Recomendaciones para la marca B](/help/c-recommendations/c-algorithms/assets/brandB.png)

### La venta al por mayor a un producto más caro

Supongamos que usted es un comerciante de ropa y desea animar a los usuarios a considerar artículos de mayor precio y, por lo tanto, más rentables. Puede utilizar los operadores &quot;es igual que&quot; y &quot;está entre&quot; para promocionar artículos más caros que procedan de la misma categoría y de la misma marca. Por ejemplo, un vendedor de zapatos puede promocionar zapatos deportivos más caros en un esfuerzo por vender un visitante mirando zapatos deportivos, como en la siguiente muestra:

![Ventas](/help/c-recommendations/c-algorithms/assets/upsell.png)

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

Puede combinar filtros dinámicos y estáticos para promocionar productos de etiquetas privadas. Por ejemplo, una compañía de suministro de oficina puede promocionar cartuchos de tóner de la marca propia de la compañía para llevar a cabo una venta más rentable de un visitante mirando el tóner, y promocionar plumas de la marca propia de la compañía para llevar a cabo una venta más rentable de un visitante mirando plumas, como en la siguiente muestra:

![Marca de casa](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

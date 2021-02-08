---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de entidad
description: Descubra cómo filtrar dinámicamente en Adobe Target Recommendations comparando un grupo de elementos potenciales con un elemento específico con el que el usuario ha interactuado.
title: ¿Cómo se filtra por coincidencia de atributos de entidad en Actividades de Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# ![Coincidencia de atributos ](/help/assets/premium.png) PREMIUMEntity

Filtre dinámicamente en [!DNL Adobe Target] [!DNL Recommendations] comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que el usuario haya interactuado.

>[!NOTE]
>
>El proceso [para crear y utilizar reglas de inclusión](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los casos de uso y los ejemplos.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual como en el ejemplo siguiente:

Si el mbox de una Página de aterrizaje de marca devuelve `entity.brand=brandA`, solo se devuelven los productos de marca A y se muestran en esa página. Del mismo modo, en la Página de aterrizaje de la Marca B, solo se devuelven los productos de la Marca B. Con este tipo de regla de inclusión dinámica, el usuario solo tiene que especificar una regla de recomendación que devuelva resultados de marca relevantes en todas las páginas de marca en lugar de especificar una colección o un filtro estático para que coincida con cada nombre de marca.

Tenga en cuenta que debe entregar el `entity.brand` en el mbox en esas páginas de aterrizaje para que esto funcione.

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL La ] coincidencia de atributos de entidad permite recomendar solo los elementos que coinciden, por ejemplo:

* Un atributo del elemento que el usuario está viendo actualmente
* El artículo que el usuario vio más recientemente
* El artículo que el usuario compró más recientemente
* El artículo que el usuario vio con más frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### Recomendar artículos según la marca

Después de crear las reglas de atributos de entidad, filtrarán todas las recomendaciones con atributos que no coincidan con el valor de entidad que se pasa a la página.

El siguiente ejemplo muestra recomendaciones que coinciden con la marca de producto mostrada en la página:

Cuando visita una página que incluye un producto de Marca A, la página establece el valor del parámetro `entity.brand` en &quot;Marca A&quot;.

![Ejemplo de llamada de Destinatario](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

En las recomendaciones de la página, solo verá los productos de marca A.

![Recomendaciones de marca A](/help/c-recommendations/c-algorithms/assets/brandA.png)

Si luego vista una página de producto de Marca B, el valor `entity.brand` se restablecerá a &quot;Marca B&quot; y verá los productos de Marca B recomendados en las páginas de productos de Marca B.

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

---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de entidad
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando un grupo de elementos potenciales con un elemento específico con el que el usuario ha interactuado.
title: ¿Cómo filtro por coincidencia de atributos de entidad en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Coincidencia de atributos de entidad

Filtre dinámicamente en [!DNL Adobe Target] [!DNL Recommendations] comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que el usuario haya interactuado.

>[!NOTE]
>
>El [proceso para crear y usar reglas de inclusión](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los ejemplos y casos de uso.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual, como en el siguiente ejemplo:

Si el mbox de una página de aterrizaje de marca devuelve `entity.brand=brandA`, solo se devolverán los productos de la marca A y se mostrarán en esa página. Del mismo modo, en la página de aterrizaje de la marca B, solo se devuelven los productos de la marca B. Con este tipo de regla de inclusión dinámica, el usuario solo debe especificar una regla de recomendación que devuelva los resultados de marca relevantes en todas las páginas de marca, en lugar de especificar una colección o un filtro estático para que coincida con cada nombre de marca.

Tenga en cuenta que debe entregar `entity.brand` en el mbox en esas páginas de aterrizaje para que esto funcione.

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL Entity Attribute Matching] le permite recomendar solamente los elementos que coincidan, por ejemplo:

* Atributo del elemento que el usuario está viendo en este momento
* El artículo que el usuario vio más recientemente
* El artículo que el usuario compró más recientemente
* El artículo que el usuario vio con mayor frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### Recomendación de artículos según la marca

Una vez creadas las reglas de atributos de entidad, filtrarán todas las recomendaciones con atributos que no coincidan con el valor de entidad pasado a la página.

El siguiente ejemplo muestra recomendaciones que coinciden con la marca del producto que se muestra en la página:

Cuando visita una página que incluye un producto de la marca A, la página establece el valor del parámetro `entity.brand` en &quot;MarcaA&quot;.

![Ejemplo de llamada de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

En las recomendaciones de la página, solo verá productos de la marca A.

![Recomendaciones de marca A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Si ve una página de producto de la Marca B, el valor `entity.brand` se restablecerá a &quot;Marca B&quot; y verá los productos de la Marca B recomendados en las páginas de producto de la Marca B.

![Recomendaciones de marca B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Ampliación de ventas a un producto más caro

Supongamos que es un retailer de ropa y desea animar a los usuarios a considerar artículos de mayor precio y, por lo tanto, más rentables. Puede usar los operadores &quot;es igual que&quot; y &quot;está entre&quot; para promocionar artículos más caros que pertenecen a la misma categoría y a la misma marca. Por ejemplo, un retailer de zapatos puede promocionar zapatos de running más caros en un esfuerzo por mejorar la venta de un visitante que mira zapatillas de running, como en el siguiente ejemplo:

![Ampliación de ventas](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

### Promoción de productos de marca privada

Puede combinar filtros dinámicos y estáticos para promocionar productos de etiqueta privada. Por ejemplo, una empresa de suministros de oficina puede promocionar cartuchos de tóner de la marca de la casa de la empresa para impulsar una venta más rentable para un visitante que mira el tóner, y promocionar bolígrafos de la marca de la casa de la empresa para impulsar una venta más rentable para un visitante que mira los bolígrafos, como en el siguiente ejemplo:

![Marca de la casa](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

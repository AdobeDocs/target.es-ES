---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de entidad
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando un grupo de elementos potenciales con un elemento específico con el que el usuario ha interactuado.
title: ¿Cómo Filtro Por Coincidencia De Atributos De Entidad En Actividades De Recommendations?
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Coincidencia de atributos de entidad

Filtre dinámicamente en [!DNL Adobe Target] [!DNL Recommendations] comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que el usuario ha interactuado.

>[!NOTE]
>
>La variable [proceso para crear y usar reglas de inclusión](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los casos de uso y los ejemplos.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual como en el siguiente ejemplo:

Si el mbox de una página de aterrizaje de marca devuelve el valor `entity.brand=brandA`y, a continuación, solo se devuelven los productos de Marca A y se muestran en esa página. Del mismo modo, en la página de aterrizaje de la marca B, solo se devuelven los productos de la marca B. Con este tipo de regla de inclusión dinámica, el usuario solo debe especificar una regla de recomendación que devuelva resultados de marca relevantes en todas las páginas de marca, en lugar de especificar una colección o un filtro estático que coincida con cada nombre de marca.

Tenga en cuenta que debe enviar la variable `entity.brand` en el mbox de esas páginas de aterrizaje para que esto funcione.

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL Coincidencia de atributos de entidad] le permite recomendar solo los elementos que coincidan, por ejemplo:

* Un atributo del elemento que el usuario está viendo en este momento
* El artículo que el usuario vio más recientemente
* El artículo que el usuario compró más recientemente
* El artículo que el usuario vio con mayor frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### Recomendación de artículos según la marca

Una vez creadas las reglas de atributos de entidad, filtrarán todas las recomendaciones con atributos que no coincidan con el valor de entidad pasado en la página.

El siguiente ejemplo muestra recomendaciones que coinciden con la marca de producto mostrada en la página:

Cuando visita una página que incluye un producto de Marca A, la página establece el valor de la variable `entity.brand` como &quot;BrandA&quot;.

![Ejemplo de llamada de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

En las recomendaciones de la página, solo verá los productos de Marca A.

![Recomendaciones de la marca A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Si a continuación ve la página de producto de Marca B, la variable `entity.brand` se restablecerá a &quot;BrandB&quot; y verá los productos de Marca B recomendados en las páginas de producto de Marca B.

![Recomendaciones de la marca B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Ampliar las ventas a un producto más caro

Supongamos que es un vendedor de ropa y desea animar a los usuarios a considerar artículos de mayor precio y, por lo tanto, más rentables. Puede utilizar los operadores &quot;es igual que&quot; y &quot;está entre&quot; para promocionar artículos más caros que pertenecen a la misma categoría y a la misma marca. Por ejemplo, un vendedor de zapatos puede promocionar unas zapatillas más caras con el fin de venderlas a un visitante que esté mirando zapatillas, como en la siguiente muestra:

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

### Promoción de productos con etiquetas privadas

Puede combinar filtros dinámicos y estáticos para promocionar productos de etiquetas privadas. Por ejemplo, una empresa de suministro de oficina puede promocionar cartuchos de tóner de la marca propia de la empresa para obtener una venta más rentable para un visitante que observe el tóner y promocionar plumas de la marca propia de la empresa para obtener una venta más rentable para un visitante que esté mirando plumas, como en el siguiente ejemplo:

![Marca de casa](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

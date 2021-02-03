---
keywords: entidad;atributos de entidad;pasar información a Recommendations;datos de comportamiento;contador de datos;definir URL relativa;mostrar nivel de inventario;definir precio;definir margen de beneficios;atributos personalizados
description: Utilice los atributos de entidad para pasar información de producto o contenido a Adobe Target Recommendations.
title: Atributos de entidad
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 93%

---


# ![PREMIUM](/help/assets/premium.png) Atributos de entidad{#entity-attributes}

Use los atributos de entidad para pasar la información de producto o contenido a [!DNL Adobe Target Recommendations].

[!DNL Recommendations] envía el valor de `productId` o `productPurchasedId` (denominado `entity.id` en el código) que se utiliza en los algoritmos.

>[!NOTE]
>
>* `entity.id` debe coincidir con el valor de `productPurchasedId` enviado a la página de confirmación del pedido y con el `productId` utilizado en los informes de producto de Adobe Analytics.
   >
   >
* Los valores de atributo de entidad proporcionados caducan al cabo de 61 días. Esto significa que debe asegurarse de que el valor más reciente de cada atributo de entidad se pase a Target Recommendations, al menos una vez al mes para cada elemento del catálogo.


La mayoría de los parámetros predefinidos solo aceptan un valor único. Los valores nuevos sobrescriben a los antiguos. El parámetro `categoryId` puede aceptar una lista de valores delimitados por comas para cada categoría que contenga el producto. Los nuevos valores de `categoryId` no sobrescriben los valores existentes, sino que, en cambio, se agregan durante la actualización de entidades (límite de 250 caracteres).

En general, el mbox de información de visualización puede tener el aspecto del siguiente ejemplo si utiliza at.js 1.** xwith  `mboxCreate`.

>[!NOTE]
>
>* Si está utilizando at.js 2.*x*,  `mboxCreate` (como se utiliza en el ejemplo siguiente) ya no es compatible. Para pasar información de productos o contenido a Recommendations mediante at.js 2.*x*, utilice  [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md). Para ver un ejemplo de esto, consulte [Planifique e implemente Recommendations](/help/c-recommendations/plan-implement.md).

>



Todos los atributos de parámetros de entidades hacen distinción entre mayúsculas y minúsculas.

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>Las direcciones URL relativas son preferibles para `pageUrl` y `thumbnailUrl` en lugar de las direcciones URL absolutas, porque las recomendaciones reciben los datos que se han enviado desde todos los entornos del sitio. El uso de direcciones URL relativas evita los vínculos predeterminados de un servidor de ensayo o desarrollo.

Si el mbox está en una página de productos, tiene la opción de incluir el ID del producto y el ID de la categoría. El algoritmo seleccionado determina cuál mostrar. El ID del producto se utiliza para algoritmos de afinidad y el ID de la categoría para algoritmos de categoría.

## Variables disponibles

La siguiente tabla describe las variables disponibles.

### entity.id

Solamente valor único.

Este parámetro obligatorio identifica el producto. Este ID alfanumérico debe ser el mismo en todos los productos de [!DNL Adobe Experience Cloud] que utilice, incluido [!DNL Analytics], a fin de que los distintos productos reconozcan el artículo y compartan los datos sobre él.

Los valores `entity.id` no deben contener barras diagonales, el símbolo &amp;, signos de interrogación, símbolos de porcentaje, comas u otros caracteres de puntuación que requieran codificación URL cuando se pasan en una llamada de API REST. Se permiten guiones y guiones bajos. Incluida puntuación no válida en un valor `entity.id` hace que algunas funciones de [!DNL Recommendations] fallen.

Ejemplo: `'entity.id=67833'`

### entity.name

Solamente valor único.

Nombre del producto que se muestra en el sitio web cuando se recomienda el producto.

Ejemplo: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Admite varios valores (lista separada por comas).

Categoría de la página actual. Puede tratarse de varias categorías, como una subsección de “rebecas” (por ejemplo, mujer, mujer:jerséis, mujer:jerséis:rebecas). Se debe separar varias categorías mediante comas.

`categoryId`está limitada a 250 caracteres.

>[!NOTE]
>
>Para mostrar una recomendación basada en una categoría de una página [!UICONTROL Categoría], solo puede pasarse un `categoryId` al mbox utilizado para mostrar esa recomendación particular. El valor de `categoryId` debe coincidir exactamente con el valor de `entity.categoryId` pasado a la página [!UICONTROL Detalles del producto].

Ejemplos:

* Ejemplo de página Detalles del producto: mujer, mujer:suéters, mujer:suéters:cardigans
* Ejemplo de página de categoría Suéters: mujer:suéters
* Ejemplo de página de categoría Cardigans: mujer:suéters:cardigans

Para las recomendaciones basadas en categorías, se utiliza una coma para separar los valores de categoría. Los valores separados por comas pasan a ser categorías. También puede definir subcategorías con otro separador, como los dos puntos (:), para separar las subcategorías dentro del valor de categoría.

Por ejemplo, en el siguiente código, la categoría Womens (Mujeres) se divide en varias subcategorías:

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

Para la entrega de mbox, se utiliza el nombre de atributo más largo para la clave. Si hay un empate, se utiliza el último atributo. En el ejemplo anterior, la clave de categoría es Womens:Outerwear:Jackets:Caban.

### entity.brand

Solamente valor único.

Muestra la marca de un artículo.

Ejemplo: `'entity.brand=brandxyz'`

### entity.pageUrl

Solamente valor único.

Define la dirección URL relativa de la página donde se puede comprar el artículo.

Ejemplo: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

Solamente valor único.

Define la dirección URL relativa a la imagen en miniatura que se muestra con el artículo.

Ejemplo: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

Solamente valor único.

Un mensaje sobre el producto que se muestra en la recomendación, como “oferta” o “liquidación”. Generalmente el mensaje es más extenso que el nombre del producto. Se utiliza para definir información adicional que se mostrará con el producto en la plantilla..

Ejemplo: `'entity.message=Family&nbsp;special'`

### entity.inventory

Solamente valor único. Requiere un valor “integer” o “long”.

Muestra el nivel de inventario del artículo.

Ejemplo: `'entity.inventory=1'`

**Gestión de atributo de inventario vacío:** si para la entrega dispone de una regla de inclusión, una regla de recopilación o una configuración de criterio con `entity.inventory` > 0 o `entity.inventory` = 0 y no se ha establecido un inventario para el producto, [!DNL Target] lo evalúa como TRUE e incluye productos donde no hay inventario establecido. Este es el comportamiento predeterminado de modo que los productos sin inventario establecido aparezcan en los resultados de la recomendación.

Igualmente, si tiene una regla de exclusión global con `entity.inventory` = 0 y `entity.inventory` no está establecido, [!DNL Target] evalúa esta regla como TRUE y excluye el producto.

**Problema conocido:** la búsqueda de productos no es coherente con la entrega para los atributos sin valor de inventario establecido. Por ejemplo, para una regla con `entity.inventory` = 0, la búsqueda de productos no muestra los productos sin valor de inventario establecido.

### entity.value

Solamente valor único.

Define el precio o el valor del elemento.

Ejemplo: `'entity.value=15.99'`

### entity.margin

Solamente valor único.

Margen de ganancia u otro valor del artículo.

Ejemplo: `'entity.margin=1.00'`

### entity.*custom*

Admite varios valores (matriz JSON).

Define hasta 100 variables personalizadas que proporcionan información adicional sobre el artículo. Puede especificar el nombre de los atributos no utilizados para cada atributo personalizado. Por ejemplo, puede crear un atributo personalizado llamado `entity.genre` para definir un libro o una película. O un vendedor de entradas podría crear atributos del lugar de celebración para un actor secundario, como un equipo visitante en un evento deportivo o un acto de apertura en un concierto.

Restricciones:

* No se pueden usar nombres de atributos de entidad predefinidos para atributos de entidad personalizados.
* El atributo entity.environment se reserva para el sistema y no se puede usar en atributos de entidad personalizados. Se hará caso omiso de los intentos de pasar entity.environment usando targetPageParams, fuentes o API.

Ejemplos:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Los atributos de entidad personalizados admiten varios valores. Consulte [Atributos de entidad personalizados](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) para límites de caracteres y valores.

Ejemplo: `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>Los atributos de entidad personalizados de varios valores requieren matrices JSON válidas. Para obtener información sobre la sintaxis correcta, consulte Atributos de entidad personalizados.

### entity.event.detailsOnly

Solamente valor único.

Se utiliza para impedir que una llamada de mbox incremente los contadores de datos de comportamiento para un algoritmo.

Ejemplo: `'entity.event.detailsOnly=true'`

En los ejemplos siguientes, la primera llamada de mbox actualizará el catálogo y los datos de comportamiento. La segunda llamada de mbox solo actualizará el catálogo.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## Temas relacionados:

* [Atributos de entidad personalizados](/help/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)

---
keywords: entidad;atributos de entidad;pasar información a Recommendations;datos de comportamiento;contador de datos;definir URL relativa;mostrar nivel de inventario;definir precio;definir margen de beneficios;atributos personalizados
description: Aprenda a utilizar los atributos de entidad para pasar información de producto o contenido a  [!DNL Target] Recommendations.
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
title: ¿Cómo se utilizan los atributos de entidad?
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: b6697eee5925cb8fa3b2fa2e107af0c617d30f94
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 48%

---

# Atributos de entidad

Use los atributos de entidad para pasar la información de producto o contenido a [!DNL Adobe Target Recommendations].

Las entidades se refieren a los elementos que desea recomendar. Las entidades pueden incluir productos, contenido (artículos, presentaciones de diapositivas, imágenes, películas y programas de televisión), ofertas de empleo, restaurantes, etc.

[!DNL Recommendations] envía `productId` o `productPurchasedId` (denominados `entity.id` en el código) que se usan en los algoritmos.

Tenga en cuenta lo siguiente:

* `entity.id` debe coincidir con `productPurchasedId` enviado a la página de confirmación de pedido y con `productId` usado en [!DNL Adobe Analytics] informes de producto.
* Los valores de atributo de entidad que pase a [!DNL Recommendations] caducan pasados 61 días. Adobe recomienda pasar el valor más reciente de cada atributo de entidad a [!DNL Recommendations] al menos una vez al mes para cada elemento del catálogo.

La mayoría de los parámetros predefinidos solo aceptan un valor único. Los valores nuevos sobrescriben a los antiguos. El parámetro `categoryId` puede aceptar una lista de valores delimitados por comas para cada categoría que contenga el producto. Los nuevos valores de `categoryId` no sobrescriben los valores existentes, sino que, en cambio, se agregan durante la actualización de entidades (límite de 250 caracteres).

En general, el mbox de información de visualización tiene el siguiente aspecto si utiliza at.js 1.*x* con `mboxCreate`. Todos los atributos de parámetros de entidad distinguen entre mayúsculas y minúsculas.

>[!NOTE]
>
>Si utiliza at.js 2.*x*, `mboxCreate` (como se usa en el ejemplo siguiente) ya no es compatible. Para pasar información de producto o contenido a [!DNL Recommendations] mediante at.js 2.*x*, use [targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html?lang=es){target=_blank}. Para ver un ejemplo, vea [Planificar e implementar Recommendations](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank}.

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

Los valores de `entity.id` deben *no* contener espacios, barras diagonales, el símbolo &amp;, signos de interrogación, símbolos de porcentaje, comas u otros caracteres de puntuación que requieran codificación URL cuando se pasan en una llamada de API REST. Se permiten guiones y guiones bajos. Incluida puntuación no válida en un valor `entity.id` hace que algunas funciones de [!DNL Recommendations] fallen.

Ejemplo: `'entity.id=67833'`

### entity.name

Solamente valor único.

Nombre del producto que se muestra en el sitio web cuando se recomienda el producto.

Ejemplo: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Admite varios valores (lista separada por comas).

Categoría de la página actual. entity.categoryID puede incluir varias categorías, como una subsección de cardigans (por ejemplo, `womens`, `womens:sweaters`, `womens:sweaters:cardigans`). Las categorías múltiples deben separarse con comas.

El valor `categoryId` está limitado a 250 caracteres.

>[!NOTE]
>
>Para mostrar una recomendación basada en una categoría de una página [!UICONTROL Category], solo se puede pasar un(a) `categoryId` al mbox usado para mostrar esa recomendación en particular. El valor de `categoryId` debe coincidir exactamente con el valor de `entity.categoryId` pasado en la página [!UICONTROL Product Detail].

Ejemplos:

* Ejemplo de página Detalles del producto: `womens`, `womens:sweaters`, `womens:sweaters:cardigans`
* Ejemplo de suéters de página de categoría: `womens:sweaters`
* Ejemplo de página de categoría Cardigans: `womens:sweaters:cardigans`

Para las recomendaciones basadas en categorías, una coma separa el valor de categoría. Los valores separados por comas pasan a ser categorías. También puede definir subcategorías con otro separador, como los dos puntos (:), para separar las subcategorías dentro del valor de categoría.

Por ejemplo, en el código siguiente, la categoría Mujer se divide en varias subcategorías:

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...', );
```

Para la entrega de mbox, se utiliza el nombre de atributo más largo para la clave. Si hay un empate, se utiliza el último atributo. En el ejemplo anterior, la clave de categoría es `Womens:Outerwear:Jackets:Caban`.

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

Un mensaje sobre el producto que se muestra en la recomendación, como “oferta” o “liquidación”. Generalmente el mensaje es más extenso que el nombre del producto. Utilice entity.message para definir información adicional que se mostrará con el producto en la plantilla.

Ejemplo: `'entity.message=Family&nbsp;special'`

### entity.inventory

Solamente valor único. Requiere un valor “integer” o “long”.

Muestra el nivel de inventario del artículo.

Ejemplo: `'entity.inventory=1'`

**Gestión de atributos de inventario vacíos:** Para la entrega, si tiene una regla de inclusión, una regla de recopilación o una configuración de criterios con `entity.inventory` > 0 o `entity.inventory` = 0 y el producto no tiene inventario establecido, [!DNL Target] evalúa este valor como TRUE e incluye productos donde no se ha establecido el inventario. Como resultado, los productos con inventario no establecido se muestran en los resultados de la recomendación.

Igualmente, si tiene una regla de exclusión global con `entity.inventory` = 0 y `entity.inventory` no está establecido, [!DNL Target] evalúa esta regla como TRUE y excluye el producto.

**Problema conocido:** La búsqueda de productos no es coherente con la entrega para los atributos de valor de inventario que no están establecidos. Por ejemplo, para una regla con `entity.inventory` = 0 , la búsqueda de productos no muestra los productos sin valor de inventario establecido.

### entity.value

Solamente valor único.

Define el precio o el valor del elemento.

Ejemplo: `'entity.value=15.99'`

entity.value solo admite formato decimal (por ejemplo, 15.99). No se admite el formato de coma (15,99).

### entity.margin

Solamente valor único.

Margen de ganancia u otro valor del artículo.

Ejemplo: `'entity.margin=1.00'`

### entidad.*custom*

Admite varios valores (matriz JSON).

Define hasta 100 variables personalizadas que proporcionan información adicional sobre el artículo. Puede especificar el nombre de los atributos no utilizados para cada atributo personalizado. Por ejemplo, puede crear un atributo personalizado denominado `entity.genre` para definir un libro o una película. Un vendedor de entradas puede crear atributos del lugar de celebración para un actor secundario, como un equipo visitante en un evento deportivo o un acto de apertura en un concierto.

Restricciones:

* No se pueden usar nombres de atributos de entidad predefinidos para atributos de entidad personalizados.
* El atributo entity.environment se reserva para el sistema y no se puede usar en atributos de entidad personalizados. Se omiten los intentos de pasar entity.environment usando targetPageParams, fuentes o API.

Ejemplos:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Los atributos de entidad personalizados admiten varios valores. Consulte [Atributos de entidad personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits) para límites de caracteres y valores.

Ejemplo: `'entity.secondary=["band1",&nbsp;"band2"]'`

Los atributos de entidad personalizados de varios valores requieren matrices JSON válidas. Para obtener información de sintaxis correcta, vea [Atributos de entidad personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly

Solamente valor único.

Se utiliza para impedir que una llamada de mbox incremente los contadores de datos de comportamiento para un algoritmo.

Ejemplo: `'entity.event.detailsOnly=true'`

En los ejemplos siguientes, la primera llamada de mbox actualiza el catálogo y los datos de comportamiento. La segunda llamada de mbox actualiza solo el catálogo.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [Atributos de entidad personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)

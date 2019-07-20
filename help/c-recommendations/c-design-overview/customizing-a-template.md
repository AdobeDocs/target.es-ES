---
description: Utilice el lenguaje de diseño Velocity de código abierto para personalizar los diseños de recomendación.
keywords: diseño personalizado;personalizar diseño;velocity;decimal;coma
seo-description: Utilice el lenguaje de diseño Velocity de código abierto para personalizar los diseños de recomendación.
seo-title: Personalización de un diseño mediante Velocity
solution: Target
title: Personalización de un diseño mediante Velocity
title-outputclass: premium
topic: Premium
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Personalización de un diseño mediante Velocity{#customize-a-design-using-velocity}

Utilice el lenguaje de diseño Velocity de código abierto para personalizar los diseños de recomendación.

## Velocity overview {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Puede encontrar información sobre Velocity en [](https://velocity.apache.org)https://velocity.apache.org.

La sintaxis, la lógica, etc. de Velocity se pueden usar en el diseño de recomendaciones. Esto significa que puede crear bucles *for*, instrucciones *if* y otro código usando Velocity en lugar de JavaScript.

Cualquier variable enviada a [!DNL Recommendations] en el mbox `productPage` o en la carga del CSV se puede mostrar en un diseño. A estos valores se hace referencia con la siguiente sintaxis:

```
$entityN.variable
```

Los nombres de las variables deben cumplir la notación taquigráfica de Velocity, que consta de un carácter *$* inicial seguido de un identificador VTL (Velocity Template Language). El identificador VTL debe comenzar por un carácter alfabético (a-z o A-Z).

Los nombres de las variables de Velocity están restringidos a los siguientes tipos de caracteres:

* Alfabéticos (a-z, A-Z)
* Numéricos (0-9)
* Guion ( - )
* Guion bajo ( _ )

Las siguientes variables están disponibles como matrices de velocidad. Como tales, es posible iterarlas o referenciarlas mediante índice.

* `entities`
* `entityN.categoriesList`

Por ejemplo:

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

O

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

Para obtener más información sobre las variables de Velocity, consulte [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si usa un script de perfil en su diseño, el símbolo $ que precede al nombre del script debe señalarse con una barra (“\”). Por ejemplo, `\${user.script_name}`.

>[!NOTE]
>
>El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99. La longitud del script de la plantilla puede contener hasta 65 000 caracteres.

Por ejemplo, si desea que un diseño muestre algo similar a esto:

![](assets/velocity_example.png)

puede usar el siguiente código:

```
<table style="border:1px solid #CCCCCC;"> 
 
<tr> 
 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
 
</tr> 
 
<tr> 
 
<td style="border-right:1px solid #CCCCCC;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
 
sku: $entity1.prodId<br/> Price: $$entity1.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
 
sku: $entity2.prodId<br/> 
 
Price: $$entity2.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
 
sku: $entity3.prodId<br/> Price: $$entity3.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
</tr> 
 
</table>
```

>[!NOTE] {class="- topic/note "}
>
>Si desea agregar información después del valor de la variable, puede hacerlo usando una anotación formal. Por ejemplo: `${entity1.thumbnailUrl}.gif`.

También puede usar `algorithm.name` y `algorithm.dayCount` como variables en los diseños, de modo que se pueda utilizar un diseño para probar varios criterios y el nombre del criterio se pueda visualizar de forma dinámica en el diseño. Esto indica al visitante que está viendo productos de mayor venta o productos que otras personas han comprado en combinación con otros productos. Incluso puede utilizar dichas variables para visualizar el valor de `dayCount` (número de días de datos utilizados en el criterio), como por ejemplo, “productos más vendidos en los últimos 2 días”, etc.

## Scenario: Display key item with recommended products {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

Puede modificar el diseño para que se muestre su artículo clave junto con otros productos recomendados. Por ejemplo, quizá quiera mostrar el artículo actual junto a las recomendaciones a título de referencia.

Para lograrlo, cree una columna en el diseño que use el atributo `$key` en el que vaya a basar la recomendación en vez del atributo `$entity`. Por ejemplo, el código de la columna clave puede tener el aspecto siguiente:

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

El resultado es un diseño como el siguiente, en el que se muestra el artículo clave en una columna.

![](assets/rec_key.png)

Al crear su actividad de [!DNL Recommendations], si el artículo clave se toma del perfil del visitante (por ejemplo, “último artículo comprado”), [!DNL Target] muestra un producto aleatorio en el [!UICONTROL Compositor de experiencias visuales] (VEC). Se debe a que no hay un perfil disponible mientras diseña la actividad. Cuando los visitantes vean la página, verán el artículo clave previsto.

## Scenario: Replace the decimal point with the comma delimiter in a sales price {#section_01F8C993C79F42978ED00E39956FA8CA}

Puede modificar su diseño para sustituir el delimitador de punto decimal utilizado en Estados Unidos por el delimitador de coma utilizado en Europa y otros países.

El siguiente código muestra una sola línea en un ejemplo condicional de precio de venta:

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

El siguiente código es un ejemplo condicional completo de un precio de venta:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Scenario: Create a 4x2 default Recommendations design with null-checking logic {#default}

Using a Velocity script to control for dynamic sizing of the entity display, the following template accommodates a 1-to-many result to avoid creating empty HTML elements when there aren't enough matching entities returned from [!DNL Recommendations]. This script is best for scenarios when back-up recommendations wouldn't make sense and [!UICONTROL Partial Template Rendering] is enabled.

El siguiente fragmento HTML sustituye la parte HTML existente en el diseño predeterminado de 4 x 2 (la CSS no se incluye aquí, en aras de la brevedad):

* If a fifth entity exists, the script inserts a closing div and opens a new row with `<div class="at-table-row">`.
* With 4x2, the maximum results shown will be eight, but this could be customized for smaller or larger lists by modifying `$count <=8`.
* Tenga en cuenta que la lógica no equilibrará las entidades en varias filas. Por ejemplo, si hay cinco o seis entidades que mostrar, no se convertirán en tres en la parte superior y dos en la parte inferior (o tres en la parte inferior). La fila superior mostrará cuatro elementos antes de iniciar una segunda fila.

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
    </div>
  </div>
```

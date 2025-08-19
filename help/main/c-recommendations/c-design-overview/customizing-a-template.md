---
keywords: diseño personalizado;personalizar diseño;velocity;decimal;coma
description: Aprenda a utilizar el lenguaje de diseño de código abierto  [!DNL Velocity] para personalizar diseños de recomendaciones en [!DNL Target] Recommendations.
title: ¿Cómo puedo personalizar un diseño con Velocity?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
source-git-commit: eba9e0b02ce74fea127d2cb2d08d04dcd2da2d76
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 61%

---

# Personalizar un diseño mediante [!DNL Velocity]

Usar el lenguaje de diseño [!DNL Velocity] de código abierto para personalizar diseños de recomendación en [!DNL Adobe Target Recommendations].

## Información general de [!DNL Velocity] {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Encontrará información sobre [!DNL Velocity] en [https://velocity.apache.org](https://velocity.apache.org).

Se puede usar toda la lógica, sintaxis, etc. de [!DNL Velocity] para un diseño de recomendación. Esto significa que puede crear bucles *for*, instrucciones *if* y otro código mediante [!DNL Velocity] en lugar de JavaScript.

Los atributos de entidad enviados a [!DNL Recommendations] en el mbox `productPage` o la carga CSV se pueden mostrar en un diseño, con la excepción de los atributos &quot;multivalor&quot;. Se puede enviar cualquier tipo de atributo; sin embargo, [!DNL Target] no pasa atributos del tipo &quot;varios valores&quot; como una matriz sobre la que una plantilla puede iterar (por ejemplo, `entityN.categoriesList`).

A estos valores se hace referencia con la siguiente sintaxis:

```
$entityN.variable
```

Los nombres de atributos de entidad deben seguir la notación abreviada [!DNL Velocity], que consta de un carácter *$* inicial, seguido de un identificador de lenguaje de plantilla (VTL) [!DNL Velocity]. El identificador VTL debe comenzar por un carácter alfabético (a-z o A-Z).

Los nombres de atributos de entidad de Velocity están restringidos a los siguientes tipos de caracteres:

* Alfabéticos (a-z, A-Z)
* Numéricos (0-9)
* Guion ( - )
* Guion bajo ( _ )

Los atributos siguientes están disponibles como [!DNL Velocity] matrices. Como tales, es posible iterarlas o referenciarlas mediante índice.

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

Para obtener más información acerca de las variables (atributos) de [!DNL Velocity], vea [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si usa un script de perfil en su diseño, el símbolo $ que precede al nombre del script debe señalarse con un `\` (barra invertida). Por ejemplo:

`\${user.script_name}`

>[!NOTE]
>
>El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99. La longitud del script de la plantilla puede contener hasta 65 000 caracteres.

Por ejemplo, si desea que un diseño muestre algo similar a esto:

![imagen velocity_example](assets/velocity_example.png)

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

>[!NOTE]
>
>Si desea agregar texto después del valor de un atributo antes de una etiqueta que indique que el nombre del atributo ha finalizado, puede hacerlo usando una anotación formal para incluir el nombre del atributo. Por ejemplo: `${entity1.thumbnailUrl}.gif`.

También puede usar `algorithm.name` y `algorithm.dayCount` como atributos de entidad en los diseños, de modo que se pueda usar un diseño para probar varios criterios y el nombre del criterio se pueda mostrar dinámicamente en el diseño. Esto indica al visitante que está viendo productos de mayor venta o productos que otras personas han comprado en combinación con otros productos. Incluso puede utilizar estos atributos para mostrar `dayCount` (número de días de datos utilizados en el criterio), como &quot;productos más vendidos en los últimos 2 días&quot;, etc.

## Trabajar con números en [!DNL Velocity] plantillas

De manera predeterminada, las plantillas [!DNL Velocity] tratan todos los atributos de entidad como valores de cadena. Puede que desee tratar un atributo de entidad como un valor numérico para realizar una operación matemática o compararlo con otro valor numérico. Para tratar un atributo de entidad como un valor numérico, siga estos pasos:

1. Declare una variable ficticia e inicialícela con un valor doble o entero arbitrario.
1. Asegúrese de que el atributo de entidad que desea utilizar no esté en blanco (requerido para que el analizador de plantillas de [!DNL Target Recommendations] valide y guarde la plantilla).
1. Pase el atributo de entidad al método `parseInt` o `parseDouble` en la variable ficticia que ha creado en el paso 1 para convertir la cadena en un valor entero o doble.
1. Realice la operación o comparación matemática con el nuevo valor numérico.

### Ejemplo: Cálculo de un precio de descuento

Supongamos que desea reducir el precio mostrado de un artículo en 0,99 € para aplicar un descuento. Puede utilizar el siguiente método para lograr este resultado:

```
#set( $double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### Ejemplo: Selección del número de estrellas que se mostrarán según la clasificación de un elemento

Supongamos que desea mostrar un número adecuado de estrellas en función de la clasificación de cliente media numérica de un artículo. Puede utilizar el siguiente método para lograr este resultado:

```
#set( $double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### Ejemplo: Cálculo del tiempo en horas y minutos en función de la longitud de un elemento en minutos

Supongamos que almacena la duración de una película en minutos, pero desea mostrar la duración en horas y minutos. Puede utilizar el siguiente método para lograr este resultado:

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Visualización de un elemento clave con productos recomendados {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

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

![imagen rec_key](assets/rec_key.png)

Al crear su actividad [!DNL Recommendations], si el elemento clave se toma del perfil del visitante como, por ejemplo, &quot;último elemento comprado&quot;, [!DNL Target] muestra un producto aleatorio en [!UICONTROL Visual Experience Composer] (VEC). Se debe a que no hay un perfil disponible mientras diseña la actividad. Cuando los visitantes vean la página, verán el artículo clave previsto.

## Realización de reemplazos en un valor de cadena {#section_01F8C993C79F42978ED00E39956FA8CA}

Puede modificar el diseño para reemplazar valores dentro de una cadena. Por ejemplo, sustituir el delimitador de punto decimal utilizado en Estados Unidos por el delimitador de coma utilizado en Europa y otros países.

El siguiente código muestra una sola línea en un ejemplo condicional de precio de venta:

```
<span class="price">$entity1.value.replace(".", ",") &euro;</span><br>
```

El siguiente código es un ejemplo condicional completo de un precio de venta:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") &euro;</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") &euro;<br> #else 
    <span class="price">$entity1.value.replace(".", ",") &euro;</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Personalización del tamaño de la plantilla y comprobación de valores en blanco {#default}

Utilizando un script [!DNL Velocity] para controlar el tamaño dinámico de la visualización de la entidad, la siguiente plantilla admite un resultado de &quot;1 a muchos&quot; para evitar la creación de elementos HTML vacíos cuando no hay suficientes entidades coincidentes devueltas de [!DNL Recommendations]. Este script es mejor para los casos en los que la copia de seguridad de recomendaciones no tendría sentido y en los que [!UICONTROL Partial Template Rendering] está habilitado.

El siguiente fragmento HTML sustituye la parte HTML existente en el diseño predeterminado de 4 x 2 (la CSS no se incluye aquí, en aras de la brevedad):

* Si existe una quinta entidad, la secuencia de comandos inserta un div de cierre y abre una nueva fila con `<div class="at-table-row">`.
* Con 4 x 2, los resultados máximos mostrados serán ocho, pero esto puede personalizarse para listas más pequeñas o grandes si modifica `$count <=8`.
* Tenga en cuenta que la lógica no equilibrará las entidades en varias filas. Por ejemplo, si hay cinco o seis entidades que mostrar, no se convertirán en tres en la parte superior y dos en la parte inferior (o dos en la parte superior y tres en la parte inferior). La fila superior mostrará cuatro elementos antes de iniciar una segunda fila.

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

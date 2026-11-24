---
keywords: diseño personalizado;personalizar diseño;velocity;decimal;coma
description: Aprenda a utilizar el lenguaje de diseño de código abierto [!DNL Velocity] para personalizar diseños de recomendación en [!DNL Target] Recommendations.
title: Personalización de un diseño mediante Velocity
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
TQID: 'https://experienceleague.adobe.com/cccBRfwqqn-eL2hraSDAoJHPYSCkcA9tVne3OWDXxEU'
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
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 21%
---
# Personalizar un diseño mediante [!DNL Velocity] {#customize-design}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a utilizar el lenguaje de diseño de código abierto [!DNL Velocity] para personalizar diseños de recomendación en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

## Información general de [!DNL Velocity] {#velocity-overview}

Encontrará información sobre [!DNL Velocity] en [https://velocity.apache.org](https://velocity.apache.org).

Se puede usar toda la lógica, sintaxis, etc. de [!DNL Velocity] para un diseño de recomendación. Esto significa que los bucles *for*, las instrucciones *if* y otros códigos se pueden crear con [!DNL Velocity] en lugar de con JavaScript.

Los atributos de entidad enviados a [!DNL Recommendations] en el mbox `productPage` o la carga CSV se pueden mostrar en un diseño, con la excepción de los atributos &quot;multivalor&quot;. Se puede enviar cualquier tipo de atributo; sin embargo, [!DNL Target] no pasa atributos del tipo &quot;varios valores&quot; como una matriz sobre la que un diseño puede iterar (por ejemplo, `entityN.categoriesList`).

A estos valores se hace referencia con la siguiente sintaxis:

```
$entityN.variable
```

Los nombres de atributos de entidad deben seguir la notación abreviada [!DNL Velocity], que consta de un carácter *$* inicial, seguido de un identificador de lenguaje de plantilla (VTL) [!DNL Velocity]. El identificador VTL debe comenzar por un carácter alfabético (a-z o A-Z).

[!DNL Velocity] nombres de atributos de entidad están restringidos a los siguientes tipos de caracteres:

* Alfabéticos (a-z, A-Z)
* Numéricos (0-9)
* Guion ( - )
* Guion bajo ( _ )

Los atributos siguientes están disponibles como [!DNL Velocity] matrices. Como tal, se pueden repetir o hacer referencia a ellas a través de un índice.

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

Para obtener más información acerca de [!DNL Velocity] variables (atributos), consulte [Documentación de Velocity](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si se usa un script de perfil en un diseño, el símbolo $ que precede al nombre del script debe señalarse con un `\` (barra invertida). Por ejemplo:

`\${user.script_name}`

>[!NOTE]
>
>El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99. El script de diseño puede contener hasta 65 000 caracteres.

Diseño que muestra algo similar a la siguiente ilustración:

![Ejemplo de un diseño de 4 x 1 titulado &quot;Otras actividades divertidas&quot;, con cuatro artículos que muestran una foto, un nombre, un precio, una calificación y una distancia](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

puede utilizar el siguiente código:

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
>Para agregar texto después del valor de un atributo, antes de una etiqueta que indique que el nombre del atributo ha finalizado, utilice una anotación formal para incluir el nombre del atributo. Por ejemplo: `${entity1.thumbnailUrl}.gif`.

`algorithm.name` y `algorithm.dayCount` también se pueden usar como atributos de entidad en los diseños, por lo que se puede usar un diseño para probar varios criterios y el nombre de los criterios se puede mostrar dinámicamente en el diseño. Esto indica al visitante que el visitante está viendo productos de mayor venta o productos que otras personas han comprado en combinación con otros productos. También se puede mostrar `dayCount` (el número de días de datos utilizados en los criterios; por ejemplo, &quot;principales vendedores en los últimos 2 días&quot;).

## Trabajar con números en [!DNL Velocity] diseños {#numbers}

De manera predeterminada, [!DNL Velocity] diseños tratan todos los atributos de entidad como valores de cadena. Es posible que un atributo de entidad deba tratarse como un valor numérico para realizar una operación matemática o compararlo con otro valor numérico. Para tratar un atributo de entidad como un valor numérico, siga estos pasos:

1. Declare una variable ficticia e inicialícela con un valor doble o entero arbitrario.
1. Asegúrese de que el atributo de entidad que se va a utilizar no esté vacío (requerido para que el analizador de diseño de [!DNL Target Recommendations] valide y guarde el diseño).
1. Pase el atributo de entidad al método `parseInt` o `parseDouble` en la variable ficticia creada en el paso 1 para convertir la cadena en un valor entero o doble.
1. Realice la operación o comparación matemática con el nuevo valor numérico.

### Ejemplo: Cálculo de un precio de descuento

Para reducir el precio mostrado de un artículo en 0,99 € y aplicar un descuento, se puede utilizar el siguiente método:

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

Para mostrar un número adecuado de estrellas en función de la clasificación de cliente media numérica de un artículo, se puede utilizar el siguiente método:

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

Para mostrar la duración de una película en horas y minutos cuando se almacena en minutos, se puede utilizar el siguiente método:

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Visualización de un elemento clave con productos recomendados {#key-item}

Un diseño puede mostrar el artículo clave junto con otros productos recomendados. Por ejemplo, el elemento actual se puede mostrar como referencia junto a las recomendaciones.

Para ello, cree una columna en el diseño que use el atributo `$key` en el que se basa la recomendación, en lugar del atributo `$entity`. Por ejemplo, el código de la columna clave podría tener este aspecto:

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

![Diseño con cuatro columnas, donde la primera columna muestra el elemento clave marcado como producto actual](/help/main/c-recommendations/c-design-overview/assets/rec_key.png)

Cuando se crea una actividad [!DNL Recommendations], si el elemento clave se toma del perfil del visitante (por ejemplo, &quot;último elemento comprado&quot;), [!DNL Target] muestra un producto aleatorio en **[!UICONTROL Compositor de experiencias visuales]** (VEC). Esto se debe a que un perfil no está disponible mientras se diseña la actividad. Cuando los visitantes ven la página, ven el elemento clave esperado.

## Realización de reemplazos en un valor de cadena {#replacements}

Un diseño puede reemplazar valores dentro de una cadena. Por ejemplo, el delimitador de punto decimal utilizado en Estados Unidos se puede reemplazar por el delimitador de coma utilizado en Europa y otros países.

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
</div>
```

## Personalización del tamaño del diseño y comprobación de valores en blanco {#default}

Un script [!DNL Velocity] puede controlar el tamaño dinámico de la visualización de la entidad. El siguiente diseño admite un resultado de uno a varios para evitar la creación de elementos HTML vacíos cuando no se devuelven suficientes entidades coincidentes de [!DNL Recommendations]. Este script es ideal para situaciones en las que las recomendaciones de copia de seguridad no tendrían sentido y en las que **[!UICONTROL Representación parcial del diseño]** esté habilitada.

El siguiente fragmento HTML sustituye la parte HTML existente en el diseño predeterminado de 4 x 2 (la CSS no se incluye aquí, en aras de la brevedad):

* Si existe una quinta entidad, la secuencia de comandos inserta un div de cierre y abre una nueva fila con `<div class="at-table-row">`.
* Con 4 x 2, el número máximo de resultados mostrados es de ocho, pero esto se puede personalizar para listas más pequeñas o grandes modificando `$count <=8`.
* La lógica no equilibra las entidades en varias filas. Por ejemplo, si hay cinco o seis entidades que mostrar, no se convierten dinámicamente en tres en la parte superior y dos en la parte inferior (o tres en la parte superior y tres en la parte inferior). La fila superior muestra cuatro elementos antes de iniciar una segunda fila.

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

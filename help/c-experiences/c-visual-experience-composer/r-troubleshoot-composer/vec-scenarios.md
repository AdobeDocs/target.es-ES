---
description: Los escenarios de este tema muestran cómo afectan los cambios realizados en la página a la capacidad de Target para mostrar una experiencia.
keywords: Recommendations
seo-description: Los escenarios de este tema muestran cómo afectan los cambios realizados en la página a la capacidad de Target para mostrar una experiencia.
seo-title: Escenarios de modificación de página
solution: Target
title: Escenarios de modificación de página
topic: Premium
uuid: bb868f55-7e77-49c4-81b5-3aff5b63b827
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Escenarios de modificación de página {#page-modification-scenarios}

Los escenarios de este tema muestran cómo afectan los cambios realizados en la página a la capacidad de Target para mostrar una experiencia.

El selector de Target determina dónde mostrar una experiencia. Si se modifica una página fuera de Target, los cambios podrían afectar a la capacidad de Target de mostrar la experiencia.

Cuando se usa el selector, la clase única no equivale al ID. El selector siempre funciona con una clase única. Si no se asigna ninguna clase al elemento, el selector calcula el número de elementos del mismo nivel anteriores que tienen el mismo nombre de etiqueta.

>[!NOTE]
>
>Aunque en estos escenarios se usan como ejemplos elementos de la lista, los conceptos se aplican a cualquier elemento.

## Escenario: Insertar un elemento con distintos nombres de clase antes del elemento seleccionado.{#section_298F661F72384F6AB957D5885A99D822}

En este ejemplo, se inserta un nuevo elemento como elemento del mismo nivel en el selector de Target.

Hay una posibilidad de que JavaScript agregue la primera clase presente en el elemento. En ese caso, no se realiza la publicación y la acción no se aplica.

**Elemento insertado:**

```
<li class="kids-section">Kids</li>
```

**Seleccionado:**

`<li class="women-section">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

El selector funciona según lo esperado porque `li.women-section:eq(0)` no se ve afectado.

Antes de registrar los valores de:

```
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

Después:

```
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## Escenario: Insertar un elemento con el mismo nombre de clase que el elemento seleccionado.{#section_0969B88C2F154E648D9969C8C85EF55A}

En este escenario, se intenta insertar una lista cuando hay seleccionado un elemento de una lista.

**Elemento insertado:**

```
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**Seleccionado**

`<li class="women-section">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

El selector no funciona porque `ul.nav:eq(0)` proporciona un elemento añadido dinámicamente. El elemento no estará disponible y la acción no se aplicará. Cuando, después de crear una actividad, se añade un elemento de lista similar con la misma clase de manera dinámica o manual, se crea un nuevo elemento en la primera posición. Esto interrumpe el selector.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

Después (intentado):

```
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## Escenario: Insertar un elemento después del elemento seleccionado {#section_15B07B84BEE94ED39D85BBBE0733E170}

En este escenario, se inserta un elemento de lista después del elemento seleccionado.

**Elemento insertado:**

```
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**Seleccionado:**

`<li class="women-section">Women Shoes</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

En este caso, insertar una lista después del final de la lista con el elemento de lista seleccionado funciona según lo esperado. El nuevo elemento se añade en la misma posición que el elemento seleccionado, con respecto al elemento principal.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

Después:

```
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Escenario: Quitar el elemento que hay justo antes de otro elemento {#section_F193674F04F84AA593EAA1137C880EBA}

En este escenario, se quita el elemento de lista situado justo antes del elemento seleccionado.

**Elemento quitado:**

```
<li class="men-section"> Men </li>
```

**Seleccionado:**

`<li class="women-section">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

El elemento se quita correctamente porque la clase del elemento seleccionado no se altera.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Después:

```
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Escenario: Quitar el elemento que hay justo después de otro elemento {#section_F83B51BE54924FB58679D512DAF1EBB2}

En este escenario, se quita el elemento de lista situado justo después del elemento seleccionado.

**Elemento quitado:**

```
<li class="kids-section">Kids</li>
```

**Seleccionado:**

`<li class="women-section">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

El elemento se quita correctamente porque la clase del elemento seleccionado no se altera. El elemento quitado incluye una clase única dentro del subárbol principal.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

Después:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Escenario: Quitar el elemento seleccionado {#section_1989CF1E2C344CC5963084ED83C18F9C}

En este escenario, se elimina el elemento de lista seleccionado.

**Elemento quitado:**

```
<li class="women-shoes">Women</li>
```

**Seleccionado:**

`<li class="women-shoes">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

El elemento se quita correctamente.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

Después

```
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Escenario: Cambiar el nombre de la clase del elemento seleccionado   {#section_79D244C588BA452DB8E433D82B7F63EA}

En este escenario, se cambia la clase del elemento de lista seleccionado.

**Elemento cambiado:**

```
<li class="women-section">Women</li>
```

**Seleccionado:**

`<li class="women-section">Women</li>`

Selector: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

No se puede cambiar el nombre de la clase del elemento porque no se encuentra la `class`.

Antes de registrar los valores de:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Después (intentado):

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

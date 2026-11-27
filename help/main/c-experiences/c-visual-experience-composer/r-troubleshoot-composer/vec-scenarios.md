---
keywords: Recommendations
description: Explore escenarios comunes que muestran cómo los cambios realizados en la página en el Compositor de experiencias visuales (VEC) afectan a la capacidad de Adobe Target para mostrar una experiencia.
title: ¿Cuáles Son Algunos Escenarios Comunes De Modificación De Página?
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# Escenarios de modificación de página {#vec-scenarios}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo los cambios realizados en una página fuera de [!DNL Target] afectan la capacidad de [!DNL Target] para mostrar una experiencia, a través de siete escenarios con ejemplos.

>[!ENDSHADEBOX]

El selector [!DNL Target] determina dónde se muestra una experiencia. Cuando se modifica una página fuera de [!DNL Target], los cambios podrían afectar la capacidad de [!DNL Target] para encontrar esa ubicación y mostrar la experiencia.

El selector siempre funciona con una clase única, lo que no equivale a un ID. Cuando no se asigna ninguna clase al elemento, el selector cuenta los elementos del mismo nivel anteriores que tienen el mismo nombre de etiqueta.

>[!NOTE]
>
>Los escenarios utilizan elementos de lista como ejemplos, pero los conceptos se aplican a cualquier elemento.

La siguiente tabla resume los escenarios. En cada escenario, el selector es `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`.

| Escenario | Acción aplicada | Motivo |
|---|---|---|
| Insertar un elemento con un nombre de clase diferente antes del elemento seleccionado | Sí | `li.women-section:eq(0)` no se ve afectado |
| Insertar un elemento con el mismo nombre de clase que el elemento seleccionado | No | Un nuevo elemento toma la primera posición, lo que rompe el selector |
| Insertar un elemento después del elemento seleccionado | Sí | El nuevo elemento se agrega en la misma posición relativa al elemento principal |
| Quitar el elemento inmediatamente anterior al elemento seleccionado | Sí | La clase del elemento seleccionado no se modifica |
| Quitar el elemento que hay justo después del elemento seleccionado | Sí | La clase del elemento seleccionado no se modifica |
| Quitar el elemento seleccionado | Sí | El elemento se ha eliminado correctamente |
| Cambiar nombre de clase del elemento seleccionado | No | `class` no se encuentra |

## Insertar un elemento con un nombre de clase diferente antes del elemento seleccionado

Un nuevo elemento se inserta como elemento secundario del elemento en el selector [!DNL Target]. Si JavaScript agregó la primera clase al elemento, la entrega falla y la acción no se aplica.

**Elemento insertado:**

```html
<li class="kids-section">Kids</li>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** El selector funciona según lo esperado porque `li.women-section:eq(0)` no se ve afectado.

**Antes:**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**Después:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## Insertar un elemento con el mismo nombre de clase que el elemento seleccionado

Se inserta una lista mientras se selecciona un elemento de la lista.

**Elemento insertado:**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** El selector no funciona. `ul.nav:eq(0)` ahora apunta a un elemento agregado dinámicamente, que no está disponible, por lo que la acción no se aplica. Añadir un elemento de lista similar con la misma clase, de forma dinámica o manual, después de crear la actividad coloca un nuevo elemento en la primera posición, lo que rompe el selector.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**Después (intentado):**

```html
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

## Insertar un elemento después del elemento seleccionado

Después del elemento de lista seleccionado se inserta una lista.

**Elemento insertado:**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**Elemento seleccionado:**

`<li class="women-section">Women Shoes</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** La inserción de una lista después de la lista que termina con el elemento seleccionado funciona según lo esperado. El nuevo elemento se agrega en la misma posición que el elemento seleccionado en relación con el elemento principal.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**Después:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Quitar el elemento inmediatamente anterior al elemento seleccionado

Elemento de la lista antes de eliminar el elemento seleccionado.

**Elemento quitado:**

```html
<li class="men-section"> Men </li>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** El elemento se quitó correctamente porque la clase del elemento seleccionado no se modifica.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Después:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Quitar el elemento que hay justo después del elemento seleccionado

El elemento de la lista después de eliminar el elemento seleccionado.

**Elemento quitado:**

```html
<li class="kids-section">Kids</li>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** El elemento se quitó correctamente porque la clase del elemento seleccionado no se modifica y el elemento quitado tiene una clase única dentro de su subárbol principal.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**Después:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Quitar el elemento seleccionado

Se elimina el elemento de lista seleccionado.

**Elemento quitado:**

```html
<li class="women-section">Women</li>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** El elemento se quitó correctamente.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Después:**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Cambiar nombre de clase del elemento seleccionado

La clase del elemento de lista seleccionado cambia.

**Elemento cambiado:**

```html
<li class="women-section">Women</li>
```

**Elemento seleccionado:**

`<li class="women-section">Women</li>`

**Selector:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** No se puede cambiar el nombre de la clase porque no se encuentra `class`.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Después (intentado):**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```

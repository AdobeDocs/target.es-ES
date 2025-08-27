---
keywords: Segmentación de experiencias;prueba de página de destino
description: Un selector de elementos es una expresión CSS que puede identificar uno o más elementos. Aprenda a utilizar selectores de elementos en el  [!DNL Target] Compositor de experiencias visuales (VEC) de Adobe.
title: ¿Puedo utilizar selectores de elementos en el Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 31%

---

# Selectores de elementos utilizados en el Compositor de experiencias visuales

Un selector de elementos es una expresión CSS que puede identificar uno o más elementos.

Puede encontrar información básica sobre selectores CSS en el documento [Selectores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) en *[!DNL Mozilla Developer Network]* (MDN).

Puede determinar si desea usar ID de elementos o clases de elementos en las preferencias de la cuenta. Haga clic en **[!UICONTROL Administration > Visual Experience Composer]** y luego elija los selectores CSS que prefiera.

* **Usar ID de elemento**: deshabilite esta opción si el mismo ID se usa para varios elementos o si los ID de elemento pueden cambiar durante la carga de la página.
* **Usar clases de elementos**: Deshabilite esta opción si las clases de elementos de una página pueden cambiar.
* **Use selectores preferidos**: actívelo si desea usar selectores únicos en el VEC para identificar áreas clave del sitio web.

>[!NOTE]
>
>Las clases de elementos están disponibles como selectores en las actividades [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] y [!UICONTROL  Multivariate Test].

Para obtener información sobre cuándo utilizar selectores CSS y cuándo utilizar Ids. únicos, consulte [Prácticas recomendadas y limitaciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6).

## Cómo [!DNL Target] genera un selector para un elemento {#section_D89D954BCBFB486CA081BE183776A475}

[!DNL Target] utiliza un algoritmo simple para crear un selector. Aquí hay una explicación muy breve de la lógica de generación:

1. Si un elemento tiene un identificador, por ejemplo `id="container"`, el selector para el elemento es `#container`.

   Por ejemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. Si un elemento contiene un atributo class, [!DNL Target] intenta aprovechar la primera clase de cualquier clase presente en el elemento.

   [!DNL Target] intenta analizar el elemento principal hasta encontrar el elemento `<HTML>` o un elemento con un ID. Siempre que un elemento contenga un ID y el selector se calcule en su hijo descendiente, el ID de este elemento contribuye al selector.

   Por ejemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   En este ejemplo:

   Selector: `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (“ > ” indica el elemento secundario inmediato).

   `eq` indica al índice que existe un elemento que tiene &quot;tagName=UL&quot; y la primera clase es `navigation`. Por lo tanto, `index` es 0. Consulte el artículo [Selectores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) de MDN para obtener más información.

1. Si un elemento no contiene una clase, [!DNL Target] usa `tagName` para el elemento y atraviesa el elemento principal hasta encontrar el elemento `<HTML>` o un elemento con un identificador.

   Por ejemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   Selector: `#container` > `ul.navigation(0)` > `li:nth-of-type(4)`

En el proceso anterior:

* Puede usar cualquier selector CSS siempre y cuando identifique de manera unívoca a un elemento en DOM.
* El enfoque anterior es el que usa [!DNL Target]. [!DNL Target] no le exige que utilice este método. Puede agregar cualquier selector siempre que el punto 1 sea verdadero.
* Puede usar cualquier atributo en el selector. Este documento sólo utiliza un nombre de clase como ejemplo.

---
keywords: Segmentación de experiencias;prueba de página de destino
description: Un selector de elementos es una expresión CSS que puede identificar uno o más elementos. Aprenda a utilizar selectores de elementos en el Compositor de experiencias visuales (VEC) de Adobe [!DNL Target].
title: ¿Puedo utilizar selectores de elementos en el Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# Selectores de elementos utilizados en [!UICONTROL Compositor de experiencias visuales] {#vec-selectors}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda cómo funcionan los selectores de elementos en el [!UICONTROL Compositor de experiencias visuales] (VEC), cómo elegir qué selectores se utilizan y cómo [!DNL Target] genera un selector para un elemento.

>[!ENDSHADEBOX]

Un selector de elementos es una expresión CSS que puede identificar uno o más elementos. La información básica sobre los selectores CSS está disponible en el documento [Selectores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) del *[!DNL Mozilla Developer Network]* (MDN).

El uso de clases de elementos o ID de elementos se establece en las preferencias de cuenta. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, elija los selectores CSS preferidos:

* **[!UICONTROL Usar ID de elemento]**: deshabilite esta opción si se usa el mismo ID para varios elementos o si los ID de elemento podrían cambiar al cargar la página.
* **[!UICONTROL Usar clases de elementos]**: Deshabilite esta opción si las clases de elementos de una página pueden cambiar.
* **[!UICONTROL Usar selectores preferidos]**: habilítelo para usar selectores únicos en el VEC para identificar áreas clave del sitio web.

>[!NOTE]
>
>Las clases de elementos están disponibles como selectores en las actividades **[!UICONTROL Prueba A/B]**, **[!UICONTROL Automated Personalization]** y **[!UICONTROL Prueba multivariable]**.

Para obtener información sobre cuándo usar selectores CSS y cuándo usar ID únicos, consulte [Prácticas recomendadas y limitaciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices).

## Cómo [!DNL Target] genera un selector para un elemento {#generate-selector}

[!DNL Target] utiliza un algoritmo simple para crear un selector. La lógica de generación es la siguiente:

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

1. Si un elemento contiene un atributo class, [!DNL Target] intenta utilizar la primera clase de las clases presentes en el elemento.

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

   En este ejemplo, el selector es `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (&quot; > &quot; indica el elemento secundario inmediato).

   `eq` proporciona el índice del elemento que tiene &quot;tagName=UL&quot; y la primera clase `navigation`. Por lo tanto, `index` es 0. Consulte el artículo [Selectores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) de MDN para obtener más información.

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

   El selector es `#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`.

En este proceso:

* Se puede utilizar cualquier selector de CSS, siempre que identifique de forma exclusiva un elemento en el DOM.
* El enfoque anterior es el que usa [!DNL Target]. [!DNL Target] no exige este enfoque. Se puede añadir cualquier selector, siempre que identifique el elemento de forma exclusiva.
* En el selector se puede utilizar cualquier atributo. Este artículo utiliza solo un nombre de clase como ejemplo.

---
keywords: recomendaciones;preguntas más frecuentes;FAQ
description: Preguntas más frecuentes (FAQ) y sus respuestas acerca de  [!DNL Target Recommendations] diseños.
title: ¿Dónde puedo obtener respuestas a las preguntas de diseño de  [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: eba9e0b02ce74fea127d2cb2d08d04dcd2da2d76
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 81%

---

# Preguntas más frecuentes sobre diseño

Lista de preguntas frecuentes (FAQ) acerca de diseños de [!DNL Adobe Target] [!DNL Recommendations].

## El precio del elemento recomendado no muestra ambos valores a la derecha del punto decimal. ¿Cómo puedo mostrarlos?

De forma predeterminada, los valores numéricos (como `entity.value`) que se devuelven en plantillas de diseño no mostrarán ceros finales tras la coma decimal. Por ejemplo, si un elemento es de 35 $, `entity.value` es igual a 35 y solo se muestra 35 en la página, no 35 $.

Hay dos opciones disponibles para resolver este problema:

* Puede utilizar Secuencias de comandos de Velocity o Javascript para aplicar formato al valor devuelto.

* Puede pasar el precio del artículo en dos atributos de entidad independientes. La primera, `entity.value`, se puede utilizar para realizar comparaciones numéricas (como reglas de comparación de precios). La segunda debe ser un atributo personalizado, como `entity.displayValue`, que almacene el valor de la entidad como una cadena para permitir un procesamiento adecuado.

  Por ejemplo,

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## ¿Por qué la categoría no se muestra en el diseño? Estoy utilizando `$entity1.categoryId`. {#section_073309B8051049C7953D396A93EA0713}

El ID de categoría no se puede mostrar en el diseño. Dado que es posible almacenar varias categorías, el sistema no sabe qué categoría mostrar.

## ¿Cómo debo cambiar un diseño para obtener una actualización instantánea?   {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La alteración del diseño que se está usando actualmente tarda unos minutos en actualizarse. Para cambiar el diseño de forma instantánea, cree un nuevo diseño, selecciónelo en la actividad y guarde la recomendación.

## ¿Cómo se puede capturar información esencial para mostrarla en el diseño? Ejemplo: si queremos visualizar la categoría del producto principal, ¿se codifica el valor en el diseño Velocity?   {#section_F08043B14BA24BC8815FEF25F4F84C39}

El parámetro `$key. *`valor`*` captura la mayor parte de la información principal del producto para mostrarla dentro del diseño. Por ejemplo, si desea mostrar la miniatura del producto clave, utilice `$key.thumbnailURL`.

## ¿Qué versión de Velocity se utiliza? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

La versión 1.7, sin herramientas ni bibliotecas adicionales agregadas. La funcionalidad básica de Velocity se encuentra disponible.

## ¿Cómo puedo sustituir un valor de entidad existente por un espacio en blanco? Por ejemplo, un elemento `entity.message` debe borrarse cuando finaliza una promoción. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Parece ser que se consigue enviando un espacio de no separación de JavaScript. Haga que los programadores envíen `\u00A0` como el valor. Ejemplo: `entity.message=\u00A0`. Puede considerar la posibilidad de que este sea el valor predeterminado cuando no haya ningún valor presente, en lugar de un cero.

## ¿Puedo usar un script de perfil en un diseño de [!DNL Recommendations]? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Sí. Para utilizar un script de perfil en un diseño de [!DNL Recommendations], ajuste el nombre en `\${...}`. Por ejemplo, si el script de perfil se llama `user.basket`, menciónelo como `\${user.basket}` en el diseño. Tenga en cuenta que la barra invertida implica que Velocity no procesa el script de perfil. Por lo tanto, no se puede realizar ninguna operación en el script de perfil de una plantilla de Velocity. El valor se imprimirá directamente en la página.

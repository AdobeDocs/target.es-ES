---
keywords: recomendaciones;preguntas más frecuentes;FAQ
description: Revise una lista de las preguntas más frecuentes (FAQ) y sus respuestas sobre los diseños de Adobe [!DNL Target] Recommendations.
title: ¿Dónde puedo responder a preguntas de diseño para [!DNL Target] Recommendations?
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: c7d5c8eb50b28ee3f7651e510d005e3f37912f62
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 70%

---

# ![PREMIUM](/help/assets/premium.png) FAQ de diseño

Lista de las preguntas más frecuentes (FAQ) sobre [!DNL Adobe Target] [!DNL Recommendations] diseños.

## El precio del elemento recomendado no muestra ambos valores a la derecha del punto decimal. ¿Cómo puedo mostrarlos?

De forma predeterminada, los valores numéricos (como `entity.value`) que se devuelven en plantillas de diseño no mostrarán ceros finales tras la coma decimal. Por ejemplo, si un elemento es de 35 $, `entity.value` es igual a 35 y solo se muestra 35 en la página, no 35 $.

Hay dos opciones disponibles para resolver este problema:

* Puede utilizar Secuencias de comandos de Velocity o Javascript para aplicar formato al valor devuelto.

* Puede pasar el precio del artículo en dos atributos de entidad independientes. La primera, `entity.value`, se puede utilizar para realizar comparaciones numéricas (como reglas de comparación de precios). La segunda debe ser un atributo personalizado, como `entity.displayValue`, que almacene el valor de la entidad como una cadena para permitir un procesamiento adecuado.

   Por ejemplo,

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## ¿Por qué la categoría no se muestra en el diseño? Estoy utilizando `$entity1.categoryId`. {#section_073309B8051049C7953D396A93EA0713}

El ID de categoría no se puede mostrar en el diseño. Dado que es posible almacenar varias categorías, el sistema no sabría determinar cuál mostrar.

## ¿Cómo debo cambiar un diseño para obtener una actualización instantánea?   {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La alteración del diseño que se está usando actualmente tarda unos minutos en actualizarse. Para cambiar el diseño instantáneamente, cree un nuevo diseño, selecciónelo en la actividad y guarde la recomendación.

## ¿Cómo se puede capturar información esencial para mostrarla en el diseño? Ejemplo: si queremos visualizar la categoría del producto principal, ¿se codifica el valor en el diseño Velocity?   {#section_F08043B14BA24BC8815FEF25F4F84C39}

El parámetro `$key. *`valor`*` captura la mayor parte de la información principal del producto para mostrarla dentro del diseño. Ejemplo: para visualizar la miniatura del producto clave, debe utilizar `$key.thumbnailURL`.

## ¿Qué versión de Velocity se utiliza? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

La versión 1.7, sin herramientas ni bibliotecas adicionales agregadas. La funcionalidad básica de Velocity se encuentra disponible.

## ¿Cómo puedo sustituir un valor de entidad existente por un espacio en blanco? Por ejemplo, un entity.message de artículo debe borrarse cuando finaliza la promoción. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Al enviar un espacio de no separación de JavaScript, esto parece hacerse. Haga que los programadores envíen `\u00A0` como el valor. Ejemplo: `entity.message=\u00A0`. Puede considerar la posibilidad de que este sea el valor predeterminado cuando no haya ningún valor presente, en lugar de un cero.

## ¿Puedo usar un script de perfil en un diseño [!DNL Recommendations]? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Sí. Para utilizar un script de perfil en un diseño [!DNL Recommendations], ajuste el nombre en `\${...}`. Por ejemplo, si el script de perfil se llama `user.basket`, menciónelo como `\${user.basket}` en el diseño. Tenga en cuenta que la barra invertida implica que Velocity no procesa el script de perfil. Por lo tanto, no se puede realizar ninguna operación en el script de perfil de una plantilla de Velocity. El valor se imprime directamente en la página.

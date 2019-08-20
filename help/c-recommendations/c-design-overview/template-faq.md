---
description: Lista de las preguntas más frecuentes (FAQ) sobre diseños de recomendaciones.
keywords: recomendaciones;preguntas más frecuentes;FAQ
seo-description: Lista de las preguntas más frecuentes (FAQ) sobre diseños de recomendaciones.
seo-title: Preguntas más frecuentes sobre diseño
solution: Target
title: Preguntas más frecuentes sobre diseño
title-outputclass: premium
topic: Premium
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
badge: premium
translation-type: tm+mt
source-git-commit: 279b6bef59e0b486a9aad7f3b6117edbbe377688

---


# ![PREMIUM](/help/assets/premium.png) FAQ de diseño{#design-faq}

Lista de las preguntas más frecuentes (FAQ) sobre diseños de recomendaciones.

## El precio del elemento recomendado no muestra ambos valores a la derecha del punto decimal. ¿Cómo puedo mostrarlos?

De forma predeterminada, los valores numéricos (como `entity.value`) que se devuelven en plantillas de diseño no mostrarán ceros finales tras la coma decimal. Por ejemplo, si un elemento es de 35,00 $, `entity.value` es igual a 35 y solo se muestra 35 en la página, no 35,00 $.

Hay dos opciones disponibles para resolver este problema.

* Puede utilizar Secuencias de comandos de Velocity o Javascript para aplicar formato al valor devuelto.

* Puede pasar el precio del elemento en dos atributos de entidad independientes. La primera, `entity.value`se puede utilizar para comparaciones numéricas (como reglas de comparación de precios). La segunda debe ser un atributo personalizado, como `entity.displayValue` almacenar el valor de la entidad como una cadena para permitir un procesamiento adecuado.

   Por ejemplo,

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## ¿Por qué la categoría no se muestra en el diseño? Estoy utilizando $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

El ID de categoría no se puede mostrar en el diseño. Dado que es posible almacenar varias categorías, el sistema no sabría determinar cuál mostrar.

## ¿Cómo debo cambiar un diseño para obtener una actualización instantánea?  {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La alteración del diseño que se está usando actualmente tarda unos minutos en actualizarse. Para cambiar el diseño de forma instantánea, cree un nuevo diseño, selecciónelo en la campaña y guarde la recomendación.

## ¿Cómo se puede capturar información esencial para mostrarla en el diseño? Ejemplo: si queremos visualizar la categoría del producto principal, ¿se codifica el valor en el diseño Velocity?  {#section_F08043B14BA24BC8815FEF25F4F84C39}

El parámetro `$key. *`valor`*` captura la mayor parte de la información principal del producto para mostrarla dentro del diseño. Ejemplo: para visualizar la miniatura del producto clave, debe utilizar `$key.thumbnailURL`.

## ¿Qué versión de Velocity se utiliza?{#section_28F00E15A4A54A768782A3F5BB0CDB21}

La versión 1.7, sin herramientas ni bibliotecas adicionales agregadas. La funcionalidad básica de Velocity se encuentra disponible.

## ¿Cómo puedo sustituir un valor de entidad existente por un espacio en blanco? Por ejemplo, un entity.message de artículo debe borrarse cuando finaliza la promoción. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Parece ser que se consigue enviando un espacio de no separación de JavaScript. Haga que los programadores envíen `\u00A0` como el valor. Ejemplo: `entity.message=\u00A0`. Puede considerar la posibilidad de que este sea el valor predeterminado cuando no haya ningún valor presente, en lugar de un cero.

## ¿Puedo usar un script de perfil en un diseño de Recommendations?{#section_6BD55203984A4D80A0C6F241AD7806DF}

Sí. Sin embargo, debe agregar una barra inclinada (\) antes del símbolo $ en el nombre del script de perfil.

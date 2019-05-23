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
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# ![PREMIUM](/help/assets/premium.png) FAQ de diseño{#design-faq}

Lista de las preguntas más frecuentes (FAQ) sobre diseños de recomendaciones.

## ¿Por qué la categoría no se muestra en el diseño? Estoy utilizando $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

El ID de categoría no se puede mostrar en el diseño. Dado que es posible almacenar varias categorías, el sistema no sabría determinar cuál mostrar. 

## ¿Cómo debo cambiar un diseño para obtener una actualización instantánea?   {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La alteración del diseño que se está usando actualmente tarda unos minutos en actualizarse. Para cambiar el diseño de forma instantánea, cree un nuevo diseño, selecciónelo en la campaña y guarde la recomendación.

## ¿Cómo se puede capturar información esencial para mostrarla en el diseño? Ejemplo: si queremos visualizar la categoría del producto principal, ¿se codifica el valor en el diseño Velocity?   {#section_F08043B14BA24BC8815FEF25F4F84C39}

El parámetro `$key. *`valor`*` captura la mayor parte de la información principal del producto para mostrarla dentro del diseño. Ejemplo: para visualizar la miniatura del producto clave, debe utilizar `$key.thumbnailURL`.

## ¿Qué versión de Velocity se utiliza?{#section_28F00E15A4A54A768782A3F5BB0CDB21}

La versión 1.7, sin herramientas ni bibliotecas adicionales agregadas. La funcionalidad básica de Velocity se encuentra disponible.

## ¿Cómo puedo sustituir un valor de entidad existente por un espacio en blanco? Por ejemplo, un entity.message de artículo debe borrarse cuando finaliza la promoción. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Parece ser que se consigue enviando un espacio de no separación de JavaScript. Haga que los programadores envíen `\u00A0` como el valor. Ejemplo: `entity.message=\u00A0`. Puede considerar la posibilidad de que este sea el valor predeterminado cuando no haya ningún valor presente, en lugar de un cero.

## ¿Puedo usar un script de perfil en un diseño de Recommendations?{#section_6BD55203984A4D80A0C6F241AD7806DF}

Sí. Sin embargo, debe agregar una barra inclinada (\) antes del símbolo $ en el nombre del script de perfil.

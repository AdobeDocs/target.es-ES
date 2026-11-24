---
keywords: recomendaciones;preguntas más frecuentes;FAQ
description: Preguntas más frecuentes (FAQ) y sus respuestas acerca de [!DNL Target Recommendations] diseños.
title: Preguntas más frecuentes sobre diseño
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
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
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 19%
---
# Preguntas más frecuentes sobre diseño {#design-faq}

>[!BEGINSHADEBOX]

**En esta página:** Encuentre respuestas a preguntas frecuentes acerca de [!DNL Adobe Target] diseños de [!DNL Recommendations].

>[!ENDSHADEBOX]

+++ ¿Cómo puede el precio de un artículo recomendado mostrar ambos dígitos a la derecha del punto decimal?

De manera predeterminada, los valores numéricos (como `entity.value`) que se devuelven en los diseños no muestran ceros finales después de la coma decimal. Por ejemplo, si un elemento cuesta 35 $, `entity.value` es igual a 35 y solo se muestra 35 en la página, no 35 $.

Hay dos opciones disponibles para resolver este problema:

* Secuencias de comandos de Velocity o JavaScript pueden aplicar formato al valor devuelto.

* El precio del artículo se puede pasar a dos atributos de entidad independientes. La primera, `entity.value`, se puede utilizar para realizar comparaciones numéricas (como reglas de comparación de precios). El segundo debe ser un atributo personalizado, como `entity.displayValue`, que almacene el valor de la entidad como una cadena para permitir un procesamiento adecuado.

  Por ejemplo,

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ ¿Por qué la categoría no se muestra en el diseño cuando se utiliza $entity1.categoryId?

El ID de categoría no se puede mostrar en un diseño. Se pueden almacenar varias categorías, por lo que el sistema no sabe qué categoría mostrar.

+++

+++ ¿Cómo se puede cambiar un diseño para obtener una actualización instantánea?

La alteración del diseño que se está usando actualmente tarda unos minutos en actualizarse. Para cambiar el diseño de forma instantánea, cree un nuevo diseño, selecciónelo en la actividad y guarde la recomendación.

+++

+++ ¿Cómo se puede mostrar la información clave, como la categoría del producto clave, en un diseño?

Los parámetros `$key` capturan la mayor parte de la información del producto clave para mostrarla dentro del diseño. Por ejemplo, para mostrar la miniatura del producto clave, use `$key.thumbnailURL`.

+++

+++ ¿Qué versión de Velocity se utiliza?

Versión 1.7, sin herramientas ni bibliotecas adicionales añadidas. La funcionalidad básica de Velocity se encuentra disponible.

+++

+++ ¿Cómo se puede reemplazar un valor de entidad existente por un en blanco, por ejemplo, cuando el entity.message de un elemento debe borrarse al final de una promoción?

Parece ser que se consigue enviando un espacio de no separación de JavaScript. Los desarrolladores envían `\u00A0` como valor, por ejemplo `entity.message=\u00A0`. También se puede considerar el uso de ese valor como predeterminado cuando no hay ningún valor presente, en lugar de un cero.

+++

+++ ¿Se puede usar un script de perfil en un diseño de [!DNL Recommendations]?

Sí. Para utilizar un script de perfil en un diseño de [!DNL Recommendations], ajuste el nombre en `\${...}`. Por ejemplo, si el script de perfil se llama `user.basket`, en el diseño haga referencia a él como `\${user.basket}`. La barra invertida implica que Velocity no procesa el script de perfil, por lo que no se pueden realizar operaciones en el script de perfil de una plantilla de Velocity. El valor se imprime directamente en la página.

+++

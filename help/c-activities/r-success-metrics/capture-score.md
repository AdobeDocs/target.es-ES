---
keywords: puntuación de captación;puntuación
description: La métrica de participación Puntuación de captación calcula una puntuación acumulada basada en el valor asignado a páginas visitadas del sitio, desde el punto en el que el visitante ve por primera vez el primer mbox de visualización de la campaña.
title: Puntuación de captación
subtopic: Primeros pasos
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Puntuación de captación{#capture-score}

La métrica de participación Puntuación de captación calcula una puntuación acumulada basada en el valor asignado a páginas visitadas del sitio, desde el punto en el que el visitante ve por primera vez el primer mbox de visualización de la campaña.

En el siguiente ejemplo se muestra cómo se calcula la participación de puntuación en una campaña que prueba dos experiencias: una con la imagen de un gato y otra con la imagen de un perro.

![](assets/example_score.png)

En este ejemplo, el visitante experimenta en primer lugar la experiencia del gato. Dé por supuesto que un mbox global transcurre en una puntuación de página basada en el valor de la página. Si el especialista en marketing ha capturado una participación de recuento de páginas en una métrica de éxito asociada con `**any mbox**`, la puntuación de visitas se acumula para cualquier petición de mbox que se visualice después del mbox de visualización alrededor de la imagen del gato.

La primera página añade 1 a la puntuación, la segunda página 0,25, la tercera 0,10 y la cuarta 0,10 para un total de 1,45. Esto puede interpretarse como puntos o moneda. En una visita independiente, un visitante experimenta la experiencia Dog (Perro) y, aunque el visitante ve menos páginas, la puntuación es 2,10, mayor que la de la otra visita; esto se debe a que el visitante ha visualizado páginas con más valor.

Puede tener en cuenta los costos de adquisición de la cuenta y los ingresos de vínculos afiliados pasando AdBoxes y redirectores, tal como se muestra en el flujo de páginas siguiente. Observe que, en este ejemplo, ambos mboxes de la página de artículos alcanzan una puntuación, lo que posiblemente representa un CPM conocido.

![](assets/example_score2.png)

**Asignación de una puntuación de página**

Puede asignar un valor a cualquier página de su sitio en función de la importancia que dicha página tenga para usted. Por ejemplo, un sitio de cocina puede vender anuncios por más dinero en la característica de artículos de características que en la sección de experiencia. Debido a ello, los artículos de características son más valiosos que la sección de experiencia. La puntuación de página permite desarrollar un “value” (valor) global de una visita, por lo que la persona que lee más artículos de características obtiene más puntos que alguien que solo navega a través de las experiencias.

Existen dos métodos para asignar una puntuación a una página:

* En el código del mbox, cree un parámetro de mbox denominado `mboxPageValue`.

   Ejemplo: `('global_mbox', 'mboxPageValue=10');`

   El valor especificado se añade a la puntuación cada vez que se visualiza la página con dicho mbox. Si varios mboxes de la página incluyen valores de puntuación, la puntuación de la página es el total de todos los valores de mboxes. `mboxPageValue` es un parámetro reservado usado para pasar valores en un mbox a fin de capturar una puntuación de participación. Se pueden pasar valores positivos y negativos. La suma se calcula al final de la visita de cada visitante para obtener la puntuación total de la visita.

* Transmita el parámetro `?mboxPageValue=n` en la dirección URL de la página.

   Ejemplo: `https://www.mydomain.com?mboxPageValue=5`

   Al utilizar este método, el valor especificado se añade a la puntuación para cada mbox de la página. Por ejemplo, si transfiere el parámetro `?mboxPageValue=10` y la página contiene tres mboxes, la puntuación de la página es 30.

>[!NOTE] {class="- topic/note "}
>
>Los mboxes ubicados por encima del primer mbox de visualización de la campaña no se incluirán en la puntuación.

Una práctica recomendada es asignar valores al código del mbox. Esto permite precisar los valores que mide en función del contenido de cada mbox.

>[!NOTE] {class="- topic/note "}
>
>Para facilitar el mantenimiento puede configurar cada asignación de valor de puntuación de página del sitio en el archivo [!DNL at.js] o [!DNL mbox.js] con alguna lógica JavaScript condicional. De este modo se elimina la necesidad de añadir más código a las páginas. Póngase en contacto con su consultor de cuentas para solicitar asistencia.

Puede combinar ambos métodos, pero esto dará como resultado una puntuación mayor de la esperada. Por ejemplo, si asigna un valor de 10 a cada uno de los tres mboxes y no asigna ninguna puntuación a un cuarto mbox, al pasar el parámetro de dirección URL `?mboxPageValue=5`, la puntuación de la página será de 50: 30 por los tres mboxes con valores asignados y 5 por cada uno de los cuatro mboxes de la página.

El contador se inicia con el primer mbox de visualización, no con el mbox de entrada. Por ejemplo, si accede a la campaña desde la página principal, que no tiene ningún mbox de visualización, entonces vincúlese a una página de catálogo que contenga un mbox de visualización; el contador se pone en marcha al desplazarse a la página de catálogo.

También puede pasar valores negativos en determinadas páginas que le cuesten dinero o que no sean adecuadas para que las vea un visitante. Los valores negativos también afectan a la puntuación global. Esta técnica se puede usar en una página a la que los visitantes accedan desde un anuncio, para que pueda conocer cuánto era el CPC. O bien, por ejemplo, los puede usar para una página de asistencia o de contacto, donde sabe que los visitantes pueden llamar o solicitar asistencia desde esta página.

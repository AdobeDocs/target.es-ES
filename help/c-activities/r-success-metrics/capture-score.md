---
keywords: capture score;score
description: La métrica de participación Puntuación de captura de Adobe Target calcula una puntuación agregada en función del valor asignado a las páginas visitadas en el sitio, desde el punto en que el visitante ve por primera vez la primera solicitud de Destinatario de visualización de la campaña.
title: Puntuación de captación
feature: Success Metrics
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 50%

---


# Puntuación de captación

La métrica de compromiso Puntuación de captura de [!DNL Adobe Target] calcula una puntuación agregada en función del valor asignado a las páginas visitadas en el sitio, desde el punto en que el visitante ve por primera vez la primera solicitud de visualización de [!DNL Target] de la campaña.

En el siguiente ejemplo se muestra cómo se calcula la participación de puntuación en una campaña que prueba dos experiencias: una con la imagen de un gato y otra con la imagen de un perro.

![](assets/example_score.png)

En este ejemplo, el visitante experimenta en primer lugar la experiencia del gato. Supongamos que una solicitud [!DNL Target] global pasa en un puntaje de página basado en el valor de la página. Si el especialista en mercadotecnia ha capturado un compromiso de recuento de páginas en una métrica de éxito asociada con `**any Target request**`, el puntaje de visitas se acumula para cualquier solicitud vista después de la solicitud de visualización alrededor de la imagen del gato.

La primera página añade 1 a la puntuación, la segunda página 0,25, la tercera 0,10 y la cuarta 0,10 para un total de 1,45. Esto puede interpretarse como puntos o moneda. En una visita independiente, un visitante experimenta la experiencia Dog (Perro) y, aunque el visitante ve menos páginas, la puntuación es 2,10, mayor que la de la otra visita; esto se debe a que el visitante ha visualizado páginas con más valor.

Puede tener en cuenta los costos de adquisición de la cuenta y los ingresos de vínculos afiliados pasando AdBoxes y redirectores, tal como se muestra en el flujo de páginas siguiente. Observe que, en este ejemplo, ambas solicitudes [!DNL Target] de la página del artículo pasan una puntuación, posiblemente representando un CPM conocido.

![](assets/example_score2.png)

## Asignación de una puntuación de página

Puede asignar un valor a cualquier página de su sitio en función de la importancia que dicha página tenga para usted. Por ejemplo, un sitio de cocina puede vender anuncios por más dinero en la característica de artículos de características que en la sección de experiencia. Debido a ello, los artículos de características son más valiosos que la sección de experiencia. La puntuación de página permite desarrollar un “value” (valor) global de una visita, por lo que la persona que lee más artículos de características obtiene más puntos que alguien que solo navega a través de las experiencias.

Existen dos métodos para asignar una puntuación a una página:

* En la solicitud [!DNL Target], cree un parámetro denominado `mboxPageValue`.

   Ejemplo: `('global_mbox', 'mboxPageValue=10');`

   El valor especificado se agrega a la puntuación cada vez que se ve la página con esa solicitud [!DNL Target]. Si varias solicitudes de la página incluyen valores de puntuación, la puntuación de la página es el total de todos los valores de solicitud. `mboxPageValue` es un parámetro reservado que se utiliza para pasar valores en una solicitud de Destinatario para capturar una puntuación de participación. Se pueden pasar valores positivos y negativos. La suma se calcula al final de la visita de cada visitante para obtener la puntuación total de la visita.

* Transmita el parámetro `?mboxPageValue=n` en la dirección URL de la página.

   Ejemplo: `https://www.mydomain.com?mboxPageValue=5`

   Con este método, el valor especificado se agrega a la puntuación para cada solicitud [!DNL Target] de la página. Por ejemplo, si pasa el parámetro `?mboxPageValue=10`y hay tres [!DNL Target] solicitudes en la página, la puntuación de la página es 30.

>[!NOTE]
>
>Las solicitudes de destinatario ubicadas por encima de la primera solicitud de visualización [!DNL Target] de la actividad no se incluirán en la puntuación.

Lo mejor es asignar valores en la solicitud [!DNL Target]. Esto le permite precisar los valores que mide en función del contenido de cada solicitud.

>[!NOTE]
>
>Para facilitar el mantenimiento puede configurar cada asignación de valor de puntuación de página del sitio en el archivo [!DNL at.js] o [!DNL mbox.js] con alguna lógica JavaScript condicional. De este modo se elimina la necesidad de añadir más código a las páginas. Póngase en contacto con su consultor de cuentas para solicitar asistencia.

Puede combinar ambos métodos, pero esto dará como resultado una puntuación mayor de la esperada. Por ejemplo: si asigna un valor de 10 a cada una de las tres solicitudes [!DNL Target] y no asigna ninguna puntuación a una cuarta solicitud, entonces pase el parámetro de URL `?mboxPageValue=5`, la puntuación de página será de 50, 30 para las tres solicitudes con valores asignados y 5 para cada una de las cuatro solicitudes de la página.

El contador inicio con la primera solicitud de visualización, no con la solicitud de entrada. Por ejemplo, si introduce la actividad en la página principal que no tiene una solicitud de visualización y, a continuación, vincula a la página de catálogo que contiene una solicitud de visualización, el contador comenzará cuando se desplace a la página de catálogo.

También puede pasar valores negativos en determinadas páginas que le cuesten dinero o que no sean adecuadas para que las vea un visitante. Los valores negativos también afectan a la puntuación global. Esta técnica se puede usar en una página a la que los visitantes accedan desde un anuncio, para que pueda conocer cuánto era el CPC. O bien, por ejemplo, los puede usar para una página de asistencia o de contacto, donde sabe que los visitantes pueden llamar o solicitar asistencia desde esta página.

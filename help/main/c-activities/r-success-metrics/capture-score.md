---
keywords: puntuación de captación;puntuación
description: Obtenga información acerca de la métrica de participación Puntuación de captación en Adobes [!DNL Target] que calcula una puntuación acumulada en función del valor asignado a páginas visitadas del sitio.
title: ¿Qué es la métrica Puntuación de captación?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 48%

---

# Puntuación de captación

La métrica de participación Puntuación de captación en [!DNL Adobe Target] calcula una puntuación acumulada en función del valor asignado a páginas visitadas del sitio, desde el momento en que el visitante ve por primera vez la primera visualización de la campaña [!DNL Target] solicitud.

En el siguiente ejemplo se muestra cómo se calcula la participación de puntuación en una campaña que prueba dos experiencias: una con la imagen de un gato y otra con la imagen de un perro.

![imagen example_score](assets/example_score.png)

En este ejemplo, el visitante experimenta en primer lugar la experiencia del gato. Supongamos que un [!DNL Target] La solicitud pasa una puntuación de página basada en el valor de la página. Si el especialista en marketing ha capturado una participación de recuento de páginas en una métrica de éxito asociada con `**any Target request**`, la puntuación de visitas se acumula para cualquier solicitud que se visualice después de la solicitud de visualización alrededor de la imagen del gato.

La primera página añade 1 a la puntuación, la segunda página 0,25, la tercera 0,10 y la cuarta 0,10 para un total de 1,45. Esto puede interpretarse como puntos o moneda. En una visita independiente, un visitante experimenta la experiencia Dog (Perro) y, aunque el visitante ve menos páginas, la puntuación es 2,10, mayor que la de la otra visita; esto se debe a que el visitante ha visualizado páginas con más valor.

Puede tener en cuenta los costos de adquisición de la cuenta y los ingresos de vínculos afiliados pasando AdBoxes y redirectores, tal como se muestra en el flujo de páginas siguiente. Observe que, en este ejemplo, tanto [!DNL Target] Las solicitudes de en la página del artículo pasan una puntuación, que posiblemente represente a un CPM conocido.

![imagen example_score2](assets/example_score2.png)

## Asignación de una puntuación de página

Puede asignar un valor a cualquier página de su sitio en función de la importancia que dicha página tenga para usted. Por ejemplo, un sitio de cocina puede vender anuncios por más dinero en la característica de artículos de características que en la sección de experiencia. Debido a ello, los artículos de características son más valiosos que la sección de experiencia. La puntuación de página permite desarrollar un “value” (valor) global de una visita, por lo que la persona que lee más artículos de características obtiene más puntos que alguien que solo navega a través de las experiencias.

Existen dos métodos para asignar una puntuación a una página:

* En el [!DNL Target] solicitud, cree un parámetro llamado `mboxPageValue`.

   Ejemplo: `('global_mbox', 'mboxPageValue=10');`

   El valor especificado se agrega a la puntuación cada vez que la página con ese valor [!DNL Target] se visualiza la solicitud. Si varias solicitudes de la página incluyen valores de puntuación, la puntuación de la página es el total de todos los valores de solicitud. `mboxPageValue` es un parámetro reservado utilizado para pasar valores en una solicitud de Target para capturar una puntuación de participación. Se pueden pasar valores positivos y negativos. La suma se calcula al final de la visita de cada visitante para obtener la puntuación total de la visita.

* Transmita el parámetro `?mboxPageValue=n` en la dirección URL de la página.

   Ejemplo: `https://www.mydomain.com?mboxPageValue=5`

   Con este método, el valor especificado se agrega a la puntuación de cada [!DNL Target] en la página. Por ejemplo, si pasa el parámetro `?mboxPageValue=10`y hay tres [!DNL Target] solicitudes en la página, la puntuación de la página es 30.

>[!NOTE]
>
>Solicitudes de Target ubicadas encima de la primera visualización de la actividad [!DNL Target] la solicitud no se incluirá en la puntuación.

Una práctica recomendada es asignar valores en la variable [!DNL Target] solicitud. Esto le permite ser preciso en los valores que mide, según el contenido de cada solicitud.

>[!NOTE]
>
>Para facilitar el mantenimiento, puede configurar las asignaciones de valor de puntuación de página del sitio en la [!DNL at.js] con alguna lógica JavaScript condicional. De este modo se elimina la necesidad de añadir más código a las páginas. Póngase en contacto con su consultor de cuentas para solicitar asistencia.

Puede combinar ambos métodos, pero esto dará como resultado una puntuación mayor de la esperada. Por ejemplo, si asigna un valor de 10 a cada uno de tres [!DNL Target] y ninguna puntuación a una cuarta solicitud, y pase el parámetro de URL `?mboxPageValue=5`, la puntuación de la página será 50, 30 para las tres solicitudes con valores asignados y, a continuación, 5 para cada una de las cuatro solicitudes de la página.

El contador comienza con la primera solicitud de visualización, no con la solicitud de entrada. Por ejemplo, si introduce la actividad en la página de inicio que no tiene una solicitud de visualización y, a continuación, vincula a la página de catálogo que contiene una solicitud de visualización, el contador comienza cuando se desplaza a la página de catálogo.

También puede pasar valores negativos en determinadas páginas que le cuesten dinero o que no sean adecuadas para que las vea un visitante. Los valores negativos también afectan a la puntuación global. Esta técnica se puede usar en una página a la que los visitantes accedan desde un anuncio, para que pueda conocer cuánto era el CPC. O bien, por ejemplo, los puede usar para una página de asistencia o de contacto, donde sabe que los visitantes pueden llamar o solicitar asistencia desde esta página.

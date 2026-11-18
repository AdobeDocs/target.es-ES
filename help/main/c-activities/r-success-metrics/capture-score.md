---
keywords: puntuación de captación;puntuación
description: Obtenga información acerca de la métrica de participación Puntuación de captación en Adobe [!DNL Target] que calcula una puntuación acumulada basada en el valor asignado a páginas visitadas del sitio.
title: ¿Qué es la métrica Puntuación de captación?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
TQID: 'https://experienceleague.adobe.com/iqCPEY9x7Lg9TlAhxn8e-B1XOnUfNgUWFdOf8Bw2F3w'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: eb2bfbe8-b0f3-4cc3-ae8d-af79179585eb
    internal-label: Success metrics
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 13%
---
# Puntuación de captación {#capture-score}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo la métrica de participación Puntuación de captación calcula la puntuación de una visita y cómo asignar una puntuación a una página.

>[!ENDSHADEBOX]

La métrica de participación Puntuación de captación de [!DNL Adobe Target] calcula una puntuación acumulada basada en el valor asignado a las páginas que ve un visitante en el sitio. La puntuación comienza en el punto en el que el visitante ve por primera vez la primera solicitud [!DNL Target] de visualización de la actividad.

El siguiente ejemplo muestra cómo se calcula la puntuación en una actividad que prueba dos experiencias, una con una imagen de gato y otra con una imagen de perro.

![Flujo de página de la visita de la experiencia cat, con una puntuación por cada página](assets/example_score.png)

En este ejemplo, el primer visitante ve la experiencia del gato. Supongamos que una solicitud [!DNL Target] global pasa una puntuación de página basada en el valor de la página. Si el especialista en marketing ha capturado una participación de recuento de páginas en una métrica de éxito asociada con **cualquier solicitud de Target**, la puntuación de visitas se acumula para cualquier solicitud vista después de la solicitud de visualización alrededor de la imagen del gato.

La primera página agrega 1 a la puntuación, la segunda página 0,25, la tercera 0,10 y la cuarta 0,10, con un total de 1,45. Este total puede interpretarse como moneda o como puntos. En una visita separada, un visitante ve la experiencia del perro. Aunque este visitante ve menos páginas, la puntuación es de 2,10, lo que es mayor que en la otra visita, ya que vio páginas más valiosas.

Puede tener en cuenta los costos de adquisición de la cuenta y los ingresos de vínculos afiliados pasando AdBoxes y redirectores, tal como se muestra en el flujo de páginas siguiente. En este ejemplo, ambas [!DNL Target] solicitudes de la página de artículos superan una puntuación, y posiblemente representen un CPM conocido.

![Flujo de página con costos de adquisición e ingresos de vínculos de afiliados pasados como puntuaciones](assets/example_score2.png)

## Asignación de una puntuación de página

Puede asignar un valor a cualquier página de su sitio en función de la importancia que dicha página tenga para usted. Por ejemplo, un sitio de cocina podría vender anuncios por más dinero en las páginas de artículos de funciones que en la sección de experiencias. Los artículos de funciones son más valiosos que la sección de experiencia. La puntuación de página permite desarrollar un &quot;valor&quot; general de una visita, de modo que una persona que lee más artículos de características obtiene más puntos que alguien que solo navega por las experiencias.

Existen dos métodos para asignar una puntuación a una página:

* En la solicitud [!DNL Target], cree un parámetro denominado `mboxPageValue`.

  Ejemplo: `('global_mbox', 'mboxPageValue=10');`

  El valor especificado se agrega a la puntuación cada vez que se visualiza la página con esa solicitud [!DNL Target]. Si varias solicitudes de la página incluyen valores de puntuación, la puntuación de la página es el total de todos los valores de solicitud. `mboxPageValue` es un parámetro reservado usado para pasar valores en una solicitud [!DNL Target] con el fin de capturar una puntuación de participación. Se pueden pasar valores positivos y negativos. La suma se calcula al final de cada visita para determinar la puntuación total de la visita.

* Pase el parámetro `?mboxPageValue=n` en la dirección URL de la página.

  Ejemplo: `https://www.mydomain.com?mboxPageValue=5`

  El valor especificado se agrega a la puntuación para cada solicitud [!DNL Target] de la página. Por ejemplo, si pasa el parámetro `?mboxPageValue=10` y hay tres solicitudes [!DNL Target] en la página, la puntuación de la página es 30.

>[!NOTE]
>
>El contador comienza con la primera solicitud de visualización de la actividad, no con la solicitud de entrada, y [!DNL Target] solicitudes ubicadas encima de esa solicitud no se incluyen en la puntuación. Por ejemplo, si introduce la actividad en la página principal, que no tiene una solicitud de visualización, y luego vincula a una página de catálogo que contiene una solicitud de visualización, el contador comienza cuando se desplaza a la página de catálogo.

Se recomienda asignar valores en la solicitud [!DNL Target]. Este método permite ser preciso en cuanto a los valores que se miden, en función del contenido de cada solicitud.

>[!NOTE]
>
>Para facilitar el mantenimiento, puede configurar las asignaciones de valor de puntuación de página del sitio en el archivo [!DNL at.js] con alguna lógica de JavaScript condicional. Este método elimina la necesidad de agregar más código a las páginas. Póngase en contacto con su consultor de cuentas para solicitar asistencia.

Puede combinar ambos métodos, pero esto dará como resultado una puntuación mayor de la esperada. Por ejemplo, asigne un valor de 10 a cada una de las tres solicitudes [!DNL Target] y ninguna puntuación a una cuarta solicitud. A continuación, pase el parámetro de dirección URL `?mboxPageValue=5`. La puntuación de página es 50: 30 para las tres solicitudes con valores asignados, más 20 para el parámetro de URL (5 para cada una de las cuatro solicitudes de la página).

También puede pasar valores negativos en determinadas páginas que le cuesten dinero o que no sean adecuadas para que las vea un visitante. Los valores negativos también afectan a la puntuación general. Esta técnica se puede utilizar en una página a la que los visitantes llegan desde un anuncio para saber cuánto fue el CPC. También se puede utilizar en una página de soporte o de contacto, donde los visitantes pueden llamar o solicitar ayuda.

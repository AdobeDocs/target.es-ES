---
keywords: mvt;prueba multivariable;prácticas recomendadas de pruebas multivariable;prácticas recomendadas de mvt;combinaciones de mvt;informes de mvt
description: Obtenga información sobre cómo mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar [!UICONTROL Prueba multivariable] actividades en [!DNL Adobe Target].
title: Prácticas recomendadas para un [!UICONTROL Prueba multivariable] actividad?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 70%

---

# [!UICONTROL Prácticas recomendadas de pruebas multivariable]

Sugerencias para mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades de [!UICONTROL pruebas multivariadas] (MVT) en [!DNL Adobe Target].

## Planificar  {#section_4D4A1F6226F042379BF48DB753608579}

* Tenga en cuenta las ubicaciones de la página que tienen probabilidad de generar resultados relevantes.

  Por ejemplo, un banner o una imagen a pantalla completa (hero) tienen más posibilidades de generar conversiones que un cambio en el pie de página. Si incluye ubicaciones con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar las ubicaciones más destacadas de la página.
* Prepare con antelación las variaciones de la página.

  Tenga en cuenta las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba MVT.

## Crear  {#section_C59C722CA82E48ABA58A4A7FA758F193}

* No incluya en la prueba más combinaciones de las necesarias.

  Cada combinación que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene tres ubicaciones con tres ofertas cada una, hay 27 combinaciones posibles (3x3x3). Tres ubicaciones, de los cuales dos contienen tres ofertas posibles y una tiene dos ofertas, generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada ubicación y oferta que se añaden.

* Asigne un nombre a las ubicaciones y las ofertas.

  Puede cambiar el nombre de cada ubicación y oferta en la prueba por uno que sea más descriptivo. El número de ofertas de cada ubicación se muestra en el encabezado de la ubicación. Los nombres útiles le ayudan a identificar sus ofertas al examinar los informes.

* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas.

  Revise todas las experiencias generadas por la prueba antes de publicarlas. Asegúrese de que no haya combinaciones con afirmaciones contradictorias (por ejemplo, 20% de descuento y 19 $ de descuento en la misma experiencia) o diseños incompatibles, como tener un fondo y una fuente del mismo color.

* Utilice el [Estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página.

  Asegúrese de que el Estimador de tráfico dé luz verde a la configuración de la prueba para que pueda obtener los resultados que desea.

* Las alternativas de cada elemento deben ser significativamente diferentes entre sí.

## Analizar  {#section_9A2118CF1039451681C13D9AE79A58AB}

* Utilice con frecuencia el [Informe Contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) para monitorizar el rendimiento de cada ubicación y oferta.
* En el [informe Rendimiento de experiencia](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) tome decisiones según los datos que se muestran con los filtros Los 5 mejores y Los 5 peores.

  Si usa el filtro [!UICONTROL Todos], será más difícil extraer la información que desea y, además, no todas las experiencias pueden mostrarse en el gráfico. Utilice el filtro [!UICONTROL Todos] si desea observar una experiencia concreta que no se encuentra entre las cinco mejores o las cinco peores.

## Realizar el seguimiento  {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Aunque [!DNL Target] le permite editar una actividad activa, si edita una actividad que está en curso, podría restablecer la prueba. Es posible que los informes no reconozcan algunos de los cambios. Es seguro realizar cambios en las ofertas HTML solo en la biblioteca de ofertas.

  Las acciones específicas que restablecen los nombres y los informes de las experiencias incluyen:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente
   * Editar ofertas de texto enriquecido
   * Editar ofertas de color de fondo

* Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

  Después de elegir qué ubicaciones y qué contenido le resultan más útiles para lograr sus objetivos, puede realizar una prueba A/B para refinar aún más los resultados. Por ejemplo, cuando sepa qué ubicaciones son las más importantes, pruebe dos imágenes específicas entre sí o compare las palabras o los colores de una llamada a la acción.

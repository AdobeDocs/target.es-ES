---
keywords: mvt;multivariate test;multivariate test best practices;mvt best practices;mvt combinations;mvt reports
description: Sugerencias para mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades de prueba multivariable en Adobe Target.
title: Prácticas recomendadas de pruebas multivariadas con Adobe Target
feature: mvt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 100%

---


# Prácticas recomendadas de pruebas multivariable{#multivariate-test-best-practices}

Sugerencias para mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades de pruebas multivariadas (MVT) en [!DNL Adobe Target].

## Planificar  {#section_4D4A1F6226F042379BF48DB753608579}

* Tenga en cuenta las ubicaciones de la página que tienen probabilidad de generar resultados relevantes.

   Por ejemplo, un banner o una imagen a pantalla completa (hero) tienen más posibilidades de generar conversiones que un cambio en el pie de página. Si incluye ubicaciones con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar las ubicaciones más destacadas de la página.
* Prepare con antelación las variaciones de la página.

   Tenga en cuenta las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba MVT.

## Crear  {#section_C59C722CA82E48ABA58A4A7FA758F193}

* No incluya en la prueba más combinaciones de las necesarias.

   Cada combinación que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene tres ubicaciones con tres ofertas cada una, hay 27 combinaciones posibles (3x3x3). Tres ubicaciones, de los cuales dos contienen tres ofertas posibles y una tiene dos ofertas, generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada ubicación y oferta que se añaden.

* Asigne un nombre a las ubicaciones y las ofertas.

   Puede cambiar el nombre de cada ubicación y oferta en la prueba por uno que sea más descriptivo. El número de ofertas de cada ubicación se muestra en el encabezado de la ubicación. Los nombres descriptivos le ayudarán a identificar las ofertas cuando examine los informes.

* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas.

   Revise todas las experiencias generadas por la prueba antes de publicarlas. Asegúrese de que no haya combinaciones con reclamos contradictorios (por ejemplo, 20 % de descuento y 19 dólares de descuento en la misma experiencia) o diseños incompatibles, como un fondo y una fuente del mismo color.

* Utilice el [Estimador de tráfico](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página.

   Asegúrese de que el Estimador de tráfico aprueba la configuración de la prueba, para que pueda obtener los resultados que desea.
* Es recomendable que las alternativas de cada elemento sean bastante diferentes entre sí.

## Analizar  {#section_9A2118CF1039451681C13D9AE79A58AB}

* Utilice con frecuencia el [informe Contribución de ubicación](/help/c-reports/location-contribution-report.md) para supervisar el rendimiento de cada ubicación y cada oferta.
* En el [informe Rendimiento de experiencia](/help/c-reports/experience-performance-report.md) tome decisiones según los datos que se muestran con los filtros Los 5 mejores y Los 5 peores.

   Si usa el filtro [!UICONTROL Todos], será más difícil extraer la información que desea y, además, no todas las experiencias pueden mostrarse en el gráfico. Utilice el filtro [!UICONTROL Todos] si desea observar una experiencia concreta que no se encuentra entre las cinco mejores o las cinco peores.

## Realizar el seguimiento  {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Aunque [!DNL Target] le permite modificar una actividad que se esté publicando, tenga en cuenta que, si lo hace, podría provocar que se restablezca la prueba. Por lo tanto, es posible que los informes no reconozcan algunos de los cambios. Es seguro realizar cambios en las ofertas HTML solo en la biblioteca de ofertas.

   Estas son algunas acciones específicas que restablecen los nombres de experiencia y los informes:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente
   * Editar ofertas de texto enriquecido
   * Editar ofertas de color de fondo

* Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

   Después de elegir qué ubicaciones y qué contenido le resultan más útiles para lograr sus objetivos, puede realizar una prueba A/B para refinar aún más los resultados. Por ejemplo, cuando sabe qué ubicaciones son más importantes, pruebe dos imágenes específicas comparándolas entre sí o compare el texto o los colores de una llamada a la acción.


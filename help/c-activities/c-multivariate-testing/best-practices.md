---
description: Sugerencias para mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades multivariable de prueba en Adobe Target.
keywords: mvt;prueba multivariable;prácticas recomendadas de pruebas multivariable;prácticas recomendadas de mvt;combinaciones de mvt;informes de mvt
seo-description: Sugerencias para mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades multivariable de prueba en Adobe Target.
seo-title: Prácticas recomendadas de prueba multivariable con Adobe Target
solution: Target
title: Prácticas recomendadas de pruebas multivariable
topic: Standard
uuid: 4468a2eb-3fc1-4bc5-85ac-90cc02db4fbb
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Prácticas recomendadas de pruebas multivariable{#multivariate-test-best-practices}

Tips to help you improve performance, avoid issues, and correct known issues that might occur when creating and running Multivariate Test (MVT) activities in [!DNL Adobe Target].

## Planificar  {#section_4D4A1F6226F042379BF48DB753608579}

* Tenga en cuenta las ubicaciones de la página que tienen probabilidad de generar resultados relevantes.

   Por ejemplo, una pancarta o una imagen primordial probablemente vayan generando más conversiones que un cambio en el pie de página. Si incluye ubicaciones con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar las ubicaciones más destacadas de la página.
* Prepare con antelación las variaciones de la página.

   Tenga en cuenta las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba MVT.

## Crear  {#section_C59C722CA82E48ABA58A4A7FA758F193}

* No incluya en la prueba más combinaciones de las necesarias.

   Cada combinación que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene tres ubicaciones con tres ofertas cada una, hay 27 combinaciones posibles (3 x 3 x 3). Tres ubicaciones, donde dos ubicaciones contienen tres ofertas posibles y una ubicación tiene dos ofertas, proporciona 18 opciones (3 x 3 x 2). Los números aumentan considerablemente con cada ubicación y oferta que se añaden.

* Asigne un nombre a las ubicaciones y las ofertas.

   Puede cambiar el nombre de cada ubicación y oferta en la prueba por uno que sea más descriptivo. El número de ofertas de cada ubicación se muestra en el encabezado de la ubicación. Los nombres descriptivos le ayudarán a identificar las ofertas cuando examine los informes.

* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas.

   Revise todas las experiencias generadas por la prueba antes de publicarlas. Asegúrese de que no haya combinaciones con reclamos contradictorios (por ejemplo, 20 % de descuento y 19 dólares de descuento en la misma experiencia) o diseños incompatibles, como un fondo y una fuente del mismo color.

* Use the [Traffic Estimator](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) to make sure that your test is designed for the amount of traffic your page receives.

   Asegúrese de que el Estimador de tráfico aprueba la configuración de la prueba, para que pueda obtener los resultados que desea.
* Es recomendable que las alternativas de cada elemento sean bastante diferentes entre sí.

## Analizar  {#section_9A2118CF1039451681C13D9AE79A58AB}

* Make frequent use of the [Location Contribution report](/help/c-reports/location-contribution-report.md) to monitor the performance of each location and each offer.
* In the [Experience Performance report](/help/c-reports/experience-performance-report.md), base your decisions on the data shown using the Best 5 and Worst 5 filters.

   [!UICONTROL El] filtro Todos hace que sea difícil extraer la información que desee y no todas las experiencias se pueden mostrar en el gráfico. Use the [!UICONTROL All] filter if you want to look at a specific experience that is not in the best or worst five.

## Realizar el seguimiento  {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Although [!DNL Target] allows you to edit a live activity, be aware that editing an activity that is in progress could reset the test. Por lo tanto, es posible que los informes no reconozcan algunos de los cambios. Es seguro realizar cambios en las ofertas HTML solo en la biblioteca de ofertas.

   Estas son algunas acciones específicas que restablecen los nombres de experiencia y los informes:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente
   * Editar ofertas de texto enriquecido
   * Editar ofertas de color de fondo

* Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

   Después de elegir qué ubicaciones y qué contenido le resultan más útiles para lograr sus objetivos, puede realizar una prueba A/B para refinar aún más los resultados. Por ejemplo, cuando sabe qué ubicaciones son más importantes, pruebe dos imágenes específicas comparándolas entre sí o compare el texto o los colores de una llamada a la acción.


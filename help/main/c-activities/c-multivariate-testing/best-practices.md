---
keywords: mvt;prueba multivariable;prácticas recomendadas de pruebas multivariable;prácticas recomendadas de mvt;combinaciones de mvt;informes de mvt
description: Obtenga información sobre cómo mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades de [!UICONTROL Prueba multivariada] en [!DNL Adobe Target].
title: ¿Cuáles son las prácticas recomendadas para una actividad de [!UICONTROL prueba multivariable]?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
TQID: 'https://experienceleague.adobe.com/nQEf5GZ8-zVZakygPtMAYWk-xoJPdcycFbzCNKTqJ-k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 30%
---
# Prácticas recomendadas de [!UICONTROL Prueba multivariable] {#mvt-best-practices}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a planificar, crear, analizar y realizar el seguimiento de una actividad de **[!UICONTROL Prueba multivariable]** para obtener resultados confiables.

>[!ENDSHADEBOX]

Las siguientes sugerencias le ayudarán a mejorar el rendimiento, evitar problemas y corregir problemas conocidos que podrían producirse al crear y ejecutar actividades de **[!UICONTROL Prueba multivariable]** (MVT) en [!DNL Adobe Target].

## Planificar {#plan}

* **Use al menos tres elementos en la prueba.**

  Si tiene menos, ejecute una serie de pruebas A/B. Para obtener más información, consulte [Cuándo usar la prueba multivariable frente a A/B](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#when-to-use-mvt).

* **Tenga en cuenta la cantidad de tráfico que recibe normalmente, incluido el número de impresiones y conversiones.**

  La prueba multivariable requiere tráfico suficiente para generar resultados útiles y esta información ayuda a reducir la probabilidad de diseñar una prueba con requisitos que superen el tráfico del sitio.

* **Tenga en cuenta las ubicaciones de la página que tienen probabilidad de generar resultados significativos.**

  Un titular o una imagen a pantalla completa (hero) probablemente generará más conversiones que un cambio en el pie de página. Si incluye ubicaciones con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar las ubicaciones más destacadas de la página.

* **Mantenga los elementos independientes entre sí.**

  Por ejemplo, no realice una prueba del diseño y del contenido a la vez.

* **Examine el código HTML de las páginas que desea probar.**

  Asegúrese de que los elementos de HTML del sitio no tengan ID de DOM duplicados. Los ID duplicados pueden ocasionar que el mismo fragmento de contenido se publique en más de una ubicación.

* **Prepare sus variaciones de página con antelación.**

  Tenga en cuenta las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba MVT.

* **Planificar tiempo adicional para control de calidad.**

  El número de experiencias aumenta, por lo que el control de calidad tarda más.

## Crear {#create}

* **No incluya más combinaciones de las necesarias para la prueba.**

  Cada combinación que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene tres ubicaciones con tres ofertas cada una, hay 27 combinaciones posibles (3x3x3). Tres ubicaciones, de los cuales dos contienen tres ofertas posibles y una tiene dos ofertas, generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada ubicación y oferta que se añaden.

* **Nombrar ubicaciones y ofertas.**

  Puede cambiar el nombre de cada ubicación y oferta en la prueba por uno que sea más descriptivo. El número de ofertas de cada ubicación se muestra en el encabezado de la ubicación. Los nombres útiles le ayudan a identificar sus ofertas al examinar los informes.

* **Aproveche las características de vista previa para evitar combinaciones no deseadas de contenido.**

  Revise todas las experiencias generadas por la prueba antes de publicarlas. Asegúrese de que no haya combinaciones con afirmaciones contradictorias (por ejemplo, 20% de descuento y 19 $ de descuento en la misma experiencia) o diseños incompatibles, como un fondo y una fuente del mismo color.

* **Use el [Estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator) para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página.**

  Asegúrese de que el **[!UICONTROL Estimador de tráfico]** le dé luz verde a la configuración de la prueba para que pueda obtener los resultados que desea.

* **Hacer que las alternativas de cada elemento sean significativamente diferentes entre sí.**

  Aunque no es obligatorio, es recomendable que cada elemento tenga el mismo número de alternativas.

## Analizar {#analyze}

* **Use con frecuencia el [informe de contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)** para supervisar el rendimiento de cada ubicación y oferta.

* **En el [informe Rendimiento de experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), tome decisiones según los datos mostrados usando los filtros [!UICONTROL Mejores 5] y [!UICONTROL Peores 5].**

  El filtro **[!UICONTROL Todos]** dificulta la extracción de la información deseada y no todas las experiencias se pueden mostrar en el gráfico. Use el filtro **[!UICONTROL Todos]** si quiere ver una experiencia específica que no se encuentra entre las cinco mejores o las cinco peores.

## Seguimiento {#follow-up}

* Aunque [!DNL Target] le permite editar una actividad activa, **editar una actividad que esté en curso podría restablecer la prueba.** Es posible que los informes no reconozcan algunos de los cambios. Es seguro realizar cambios en las ofertas de HTML solo en la biblioteca de ofertas.

  Las acciones específicas que restablecen los nombres y los informes de las experiencias incluyen:

  * Añadir una nueva ubicación
  * Eliminar una ubicación
  * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente
  * Editar ofertas de texto enriquecido
  * Editar ofertas de color de fondo

* **Si el grupo de informes no se carga cuando edita una actividad que usa métricas basadas en [!DNL Analytics] (se muestra un control de número),** cambia las métricas a [!DNL Target] métricas y, a continuación, cambia de nuevo a las métricas basadas en [!DNL Analytics]. Ahora el grupo de informes debería cargarse.

* **Siga una prueba MVT con una o más pruebas A/B** para determinar el mejor contenido posible para los resultados que desea. Después de elegir qué ubicaciones y qué contenido le resultan más útiles para lograr sus objetivos, puede realizar una prueba A/B para refinar aún más los resultados. Por ejemplo, cuando sepa qué ubicaciones son las más importantes, pruebe dos imágenes específicas entre sí o compare las palabras o los colores de un call to action.

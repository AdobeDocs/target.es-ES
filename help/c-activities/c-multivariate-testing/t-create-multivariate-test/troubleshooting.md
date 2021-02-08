---
keywords: Pruebas multivariable;solución de problemas;solución de problemas;mvt
description: Explore los desafíos potenciales que podría enfrentar al usar actividades de prueba multivariada (MVT) en Adobe Target, junto con las soluciones sugeridas.
title: ¿Cómo se solucionan las pruebas multivariable?
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---


# Resolución de problemas de pruebas multivariada

Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una prueba [!UICONTROL multivariada] (MVT) en [!DNL Adobe Target].

* Al editar una actividad, si ha utilizado métricas basadas en [!DNL Analytics] y el grupo de informes no se carga (se muestra el control de giro), cambie las métricas a métricas [!DNL Target] y luego vuelva a cambiar a una métrica basada en [!DNL Analytics]. Ahora el grupo de informes debería cargarse.
* Si realiza cambios en una prueba que ya se está ejecutando, puede restablecer la prueba y sus datos.

   [!DNL Target] permite editar una actividad en directo. Tenga en cuenta que si modifica una actividad que se está publicando, podría restablecer la prueba y es posible que los informes no reconozcan algunos cambios.

   Puede realizar pequeños cambios con total seguridad, como por ejemplo, modificar ofertas de texto o de html.

   Estas son las acciones específicas que restablecen los informes y los nombres de experiencias:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente


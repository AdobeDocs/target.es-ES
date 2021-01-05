---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una prueba MVT en Adobe Target.
title: Resolución de problemas de pruebas multivariada
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 45%

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


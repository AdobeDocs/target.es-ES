---
keywords: Pruebas multivariable;solucionar problemas;solución de problemas;mvt
description: Explore los posibles desafíos a los que podría enfrentarse al usar actividades de [!UICONTROL Multivariate Test] (MVT) en  [!DNL Adobe Target], junto con las soluciones sugeridas.
title: ¿Cómo puedo solucionar problemas de [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# Solucionar problemas de actividades [!UICONTROL Multivariate Test]

Este artículo contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una [!UICONTROL Multivariate Test] (MVT) en [!DNL Adobe Target].

* Al editar una actividad, si ha utilizado métricas basadas en [!DNL Analytics] y el grupo de informes no se carga (se muestra el control de número), cambie las métricas a [!DNL Target] métricas y, a continuación, vuelva a cambiar a la métrica basada en [!DNL Analytics]. Ahora el grupo de informes debería cargarse.
* Si realiza cambios en una prueba que ya se está ejecutando, puede restablecer la prueba y sus datos.

  [!DNL Target] le permite editar una actividad en vivo. Si edita una actividad en curso, se podría restablecer la prueba, por lo que los informes podrían no reconocer algunos de los cambios.

  Puede realizar pequeños cambios con total seguridad, como por ejemplo, modificar ofertas de texto o de html.

  Las acciones específicas que restablecen los nombres y los informes de las experiencias incluyen:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente

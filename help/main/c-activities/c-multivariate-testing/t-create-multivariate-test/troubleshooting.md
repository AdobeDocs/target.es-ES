---
keywords: Pruebas multivariable;solución de problemas;solución de problemas;mvt
description: Explore los posibles desafíos que podría enfrentar al usar actividades de pruebas multivariable (MVT) en Adobe Target, junto con las soluciones sugeridas.
title: ¿Cómo puedo solucionar problemas de las pruebas multivariable?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# Resolución de problemas de pruebas multivariada

Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar un [!UICONTROL Multivariable] Prueba (MVT) en [!DNL Adobe Target].

* Al editar una actividad, si ha utilizado [!DNL Analytics]Las métricas basadas en y el grupo de informes no se carga (se muestra un control de número), cambie las métricas a [!DNL Target] métricas y luego cambiar de nuevo a [!DNL Analytics]Métrica basada en Ahora el grupo de informes debería cargarse.
* Si realiza cambios en una prueba que ya se está ejecutando, podría restablecer la prueba y sus datos.

   [!DNL Target] permite editar una actividad activa. Tenga en cuenta que si modifica una actividad que se está publicando, podría restablecer la prueba y es posible que los informes no reconozcan algunos cambios.

   Puede realizar pequeños cambios con total seguridad, como por ejemplo, modificar ofertas de texto o de html.

   Estas son las acciones específicas que restablecen los informes y los nombres de experiencias:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente

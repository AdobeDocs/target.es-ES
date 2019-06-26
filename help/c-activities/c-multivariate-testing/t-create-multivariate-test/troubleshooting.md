---
description: Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una prueba MVT.
keywords: Editor de experiencia de web móvil
seo-description: Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una prueba MVT.
seo-title: Resolución de problemas de pruebas multivariada
solution: Target
subtopic: Ventanillas móviles
title: Resolución de problemas de pruebas multivariada
topic: Standard
uuid: 4de03e03-cbbd-4e8f-a1b9-19ba8b2e6951
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Resolución de problemas de pruebas multivariada{#troubleshoot-multivariate-tests}

Este tema contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una prueba MVT.

* Cuando modifica una actividad, si utilizó métricas basadas en Analytics y no se carga el grupo de informes (se muestra un control de número), cambie las métricas por las métricas de Target y después vuelva a cambiar a la métrica basada en Analytics. Ahora el grupo de informes debería cargarse.
* Si realiza cambios en una prueba que ya se está ejecutando, es posible que se restablezca la prueba y sus datos.

   Target permite modificar una actividad que se está publicando. Tenga en cuenta que si modifica una actividad que se está publicando, podría restablecer la prueba y es posible que los informes no reconozcan algunos cambios.

   Puede realizar pequeños cambios con total seguridad, como por ejemplo, modificar ofertas de texto o de html.

   Estas son las acciones específicas que restablecen los informes y los nombres de experiencias:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente


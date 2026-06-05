---
keywords: Pruebas multivariable;solucionar problemas;solución de problemas;mvt
description: Explore los posibles desafíos a los que podría enfrentarse al usar las actividades de [!UICONTROL Prueba multivariable] (MVT) en [!DNL Adobe Target], junto con las soluciones sugeridas.
title: ¿Cómo puedo solucionar problemas de una [!UICONTROL prueba multivariable]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
TQID: https://experienceleague.adobe.com/O9lmC1PmICPCOxcMDYVcSdpRoM-bqwKR-79deFIG2mg
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 21%

---

# Solucionar problemas de [!UICONTROL pruebas multivariable] actividades

Este artículo contiene sugerencias para resolver algunos problemas que podrían producirse al diseñar una [!UICONTROL Prueba multivariada] (MVT) en [!DNL Adobe Target].

* Al editar una actividad, si ha utilizado métricas basadas en [!DNL Analytics] y el grupo de informes no se carga (se muestra el control de número), cambie las métricas a [!DNL Target] métricas y, a continuación, vuelva a cambiar a la métrica basada en [!DNL Analytics]. Ahora el grupo de informes debería cargarse.
* Si realiza cambios en una prueba que ya se está ejecutando, puede restablecer la prueba y sus datos.

  [!DNL Target] le permite editar una actividad en vivo. Si edita una actividad en curso, se podría restablecer la prueba, por lo que los informes podrían no reconocer algunos de los cambios.

  Puede realizar pequeños cambios con total seguridad, como por ejemplo, modificar ofertas de texto o de html.

  Las acciones específicas que restablecen los nombres y los informes de las experiencias incluyen:

   * Añadir una nueva ubicación
   * Eliminar una ubicación
   * Añadir nuevas ofertas o eliminar ofertas de una ubicación existente

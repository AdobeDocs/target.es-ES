---
title: ¿Qué es un indicador de funcionalidad?
description: Descubra cuáles son los indicadores de características y cómo le permiten activar o desactivar las características de la aplicación durante la ejecución sin tener que volver a implementarlas.
badge: label="Beta" type="Informative"
hide: true
exl-id: c4ed4ab5-0d73-4697-b05c-476d6e4010ce
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%
---
# ¿Qué es un indicador de funcionalidad? {#what-is-a-feature-flag}

Un indicador de características es un mecanismo que permite activar o desactivar las características de la aplicación durante la ejecución, sin volver a implementar el código.

Los indicadores de características desvinculan la **implementación de código** de la **disponibilidad de características**. Puede enviar código nuevo a producción con la función oculta tras un indicador y, a continuación, activarla cuando esté listo, para todos los usuarios o para un subconjunto de destino.

Esta separación reduce significativamente el riesgo. Los desarrolladores pueden crear y enviar contenido de forma continua con una interrupción mínima, mientras que los equipos de productos conservan el control total sobre cuándo y a quién se vuelve visible una función.

>[!NOTE]
>
>En Marcas, una marca de característica es la unidad atómica más importante de control de características. Se puede usar solo para segmentar una sola característica o combinado con otras marcas en un [grupo de características](feature-groups-to-control-multiple-features.md).

<!-- -->

---
title: Reglas de audiencia complejas
description: Aprenda a trabajar con conjuntos de reglas de audiencia grandes o complejos en Banderas, incluidos los límites de valor masivo y cómo dividir reglas en varias condiciones.
badge: label="Beta" type="Informative"
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 3%
---
# Reglas de audiencia complejas {#complex-rules}

## Uso de lógica anidada para reglas complejas {#nested-logic}

La lógica anidada permite combinar varias condiciones de audiencia con un control AND/OR preciso. Para habilitarlo:

1. Añada las condiciones de audiencia que necesite.
2. Habilite **Lógica anidada** en la sección de reglas de audiencia.
3. Cada condición tiene asignado un número. Introduzca una expresión lógica que haga referencia a estos números, por ejemplo:
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## Consulte también {#see-also}

* [Audiencia en indicadores y grupos de características](audience-in-feature-flags-and-feature-groups.md)

<!-- -->

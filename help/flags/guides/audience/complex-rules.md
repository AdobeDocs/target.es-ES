---
title: Reglas de audiencia complejas
description: Aprenda a trabajar con conjuntos de reglas de audiencia grandes o complejos en Banderas, incluidos los límites de valor masivo y cómo dividir reglas en varias condiciones.
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 2%

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

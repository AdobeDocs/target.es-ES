---
title: Uso del contexto en las reglas de audiencia
description: Obtenga información sobre cómo utilizar atributos de contexto en reglas de audiencia para indicadores de características y grupos de características en Marcas.
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# Uso del contexto en las reglas de audiencia {#context-in-audience-rules}

Los atributos de contexto son valores proporcionados por la aplicación cliente durante la ejecución. Permiten segmentar usuarios en función de información dinámica a nivel de sesión, como el idioma activo del usuario, el tipo de dispositivo o el estado de la aplicación.

Los atributos de contexto son relevantes para los clientes web y móviles.

## Funcionamiento de los atributos de contexto {#how-context-attributes-work}

La aplicación pasa los atributos de contexto a Marcas al evaluar una marca de característica. En la consola se definen reglas que comprueban estos valores, y la plataforma los utiliza en el momento de la evaluación para determinar si el usuario cumple los requisitos.

## Añadir un atributo de contexto {#adding-context-attribute}

Para añadir un atributo de contexto a una regla de audiencia:

1. Abra la marca de características o el grupo de características en la consola.
2. Vaya a la ficha **Audiencia**.
3. En **Contexto**, agregue una nueva condición.
4. Seleccione el atributo de contexto, el operador y el valor.

Si el atributo de contexto que necesita no aparece en la lista, puede crear uno nuevo. Consulte [Creación de atributos de contexto](creating-your-context-attributes.md).

## Consulte también {#see-also}

* [Audiencia en indicadores y grupos de características](audience-in-feature-flags-and-feature-groups.md)

<!-- -->

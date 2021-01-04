---
keywords: automated traffic allocation;targeting;auto-allocate;auto allocate
description: La actividad Asignación automática de Adobe Target identifica un ganador entre dos o más experiencias y automáticamente reasigna más tráfico al ganador para aumentar las conversiones mientras la prueba continúa ejecutándose y aprendiendo.
title: La asignación automática puede proporcionar resultados de prueba más rápidos y mayores ingresos que una prueba manual
feature: Auto-Allocate
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---


# La asignación automática puede proporcionar resultados de prueba más rápidos y mayores ingresos que una prueba manual

Con una actividad A/B manual, es posible que esté perdiendo conversiones, ya que no podrá entregar la experiencia ganadora a toda la audiencia hasta que se complete la actividad. La distribución del tráfico se mantiene fija incluso después de reconocer que algunas experiencias tienen un rendimiento superior al de otras, y la actividad debe ejecutar todo el curso antes de poder actuar con un ganador.

## Asignación automática del tráfico

Si desea una opción para ofrecer la experiencia ganadora más a menudo y antes en la actividad mientras elimina o reduce simultáneamente el costo de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos, [!UICONTROL Asignación automática] es la mejor opción.

## ¿Cómo funciona la asignación automática?

[!UICONTROL La asignación automática ] utiliza el principio del método multi-armed bandit. Si el término no es familiar, un bandido con un solo arma es un término coloquial para una máquina tragaperras (piensen: Las Vegas). Visualice la asignación automática del tráfico como si tuviera varias máquinas tragaperras, en este caso, pruebe las variaciones y, al principio, extraiga todos los controladores de forma equitativa. Con el tiempo, una o más máquinas, o variaciones de prueba, podrían tener un rendimiento mayor que otras. Cuando esto sucede, un jugador naturalmente inicio sacar las cartas de las que ganan con más frecuencia. En términos de asignación de tráfico, [!DNL Adobe Target] proporcionará a más visitantes la experiencia o experiencias que están ganando más.

Considere la siguiente ilustración de una actividad A/B de dos semanas. Con [!UICONTROL Asignación automática], a medida que surge una experiencia ganadora, [!UICONTROL Destinatario] desvía más tráfico hacia esa ganadora al principio de la prueba.

![Ilustración de asignación automática](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿Cómo me da la asignación automática resultados más rápidos?

El aspecto positivo es bastante claro: más visitantes ven las variaciones que funcionan mejor. Y a medida que una única variación avanza, aún más visitantes se desvían a esa experiencia ganadora, mientras la prueba seguía en marcha. Esto resulta especialmente útil si la actividad A/B que se está ejecutando tiene lugar durante un momento comercial central, como un día festivo, un lanzamiento de producto o un evento de noticias del mundo.

## ¿Cómo puede la asignación automática obtener mayores ingresos?

[!UICONTROL La asignación automática ] encuentra el ganador más rápido que una división A/B manual, y también le permite explotar ese ganador capturando inmediatamente los ingresos al alza que se habrían perdido con un enfoque tradicional o manual. Dado que [!UICONTROL Asignación automática] dirige más tráfico a la experiencia con la mayor tasa de conversión, puede aumentar los ingresos mientras la actividad se ejecuta y aprende.

En el siguiente ejemplo, [!UICONTROL Asignación automática] obtuvo más ingresos durante la prueba al impulsar más tráfico (40%) a la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo seguir con la asignación manual del tráfico?

Cuando necesite clasificar el orden de cada experiencia en relación con las demás, la prueba A/B manual es más aplicable. [!UICONTROL La asignación automática ] busca y explota los mejores resultados, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Debe utilizar la asignación manual del tráfico para controlar completamente la cantidad de tráfico de visitante que ve cada variante de prueba y para personalizar los umbrales estadísticos relevantes para su negocio.

## Introducción

¿Está listo para iniciar la primera actividad [!UICONTROL de asignación automática]? [Aprende cómo aquí](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).


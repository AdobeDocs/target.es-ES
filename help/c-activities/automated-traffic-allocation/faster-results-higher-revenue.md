---
keywords: asignación de tráfico automática;segmentación;asignación automática;asignación automática
description: Descubra cómo una actividad de asignación automática en Adobe [!DNL Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico al ganador.
title: ¿Pueden las actividades de asignación automática obtener resultados más rápidos e ingresos más altos?
feature: Asignación automática
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# La asignación automática puede proporcionar resultados de prueba más rápidos e ingresos más altos que una prueba manual

Con una actividad A/B manual, es posible que esté perdiendo conversiones porque no puede ofrecer la experiencia ganadora a toda la audiencia hasta que la actividad se complete. La distribución del tráfico permanece fija incluso después de reconocer que algunas experiencias se comportan mejor que otras, y la actividad debe ejecutar todo el curso antes de poder actuar como ganador.

## Asignación automática del tráfico

Si desea una opción para ofrecer la experiencia ganadora con mayor frecuencia y antes en la actividad, eliminando o reduciendo simultáneamente el coste de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos, [!UICONTROL Asignación automática] es su mejor opción.

## ¿Cómo funciona la asignación automática?

[!UICONTROL La ] asignación automática utiliza el principio del método multi-armed bandit. Si el término no es familiar, un bandido con un solo arma es un término coloquial para una máquina tragaperras (piensen: Las Vegas). Visualice la asignación automática del tráfico como si tuviera varias máquinas tragaperras, en este caso, variaciones de prueba y, al principio, obteniendo todas las manipulaciones de forma equitativa. Con el tiempo, una o más máquinas, o variaciones de las pruebas, podrían resultar más rentables que otras. Cuando esto sucede, un jugador naturalmente comenzaría a sacar las riendas de los que ganan con más frecuencia. En términos de asignación de tráfico, [!DNL Adobe Target] ofrecerá a más visitantes la experiencia o experiencias que están ganando más.

Veamos la siguiente ilustración de una actividad A/B de dos semanas. Con [!UICONTROL Asignación automática], a medida que surge una experiencia ganadora, [!UICONTROL Target] desvía más tráfico hacia ese ganador al principio de la prueba.

![Ilustración de asignación automática](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿De qué manera la asignación automática me da resultados más rápidos?

El aspecto positivo es bastante claro: más visitantes ven las variaciones que funcionan mejor. Y a medida que una sola variación avanza, aún más visitantes se desvían a esa experiencia ganadora, mientras la prueba seguía en ejecución. Esto resulta especialmente útil si la actividad A/B que se está ejecutando se está produciendo durante un momento comercial central, como un día festivo, un lanzamiento del producto o un evento de noticias mundiales.

## ¿Cómo puede la asignación automática obtener mayores ingresos?

[!UICONTROL La ] asignación automática encuentra el ganador más rápido que una división A/B manual y también le permite aprovechar ese ganador para capturar inmediatamente los ingresos al alza que se habrían perdido con un enfoque tradicional o manual. Como [!UICONTROL Asignación automática] dirige más tráfico a la experiencia con la tasa de conversión más alta, puede aumentar sus ingresos mientras la actividad se ejecuta y aprende.

En el siguiente ejemplo, [!UICONTROL Asignación automática] obtuvo más ingresos durante la prueba al impulsar más tráfico (40%) a la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo seguir con la asignación manual del tráfico?

Cuando necesite ordenar el rendimiento de cada experiencia en relación con las demás, es más aplicable una prueba A/B manual. [!UICONTROL La ] asignación automática encuentra y explota los mejores resultados, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Debe utilizar la asignación de tráfico manual para un control completo de cuánto tráfico de visitantes ve cada variante de prueba y para la personalización de los umbrales estadísticos relevantes para su negocio.

## Introducción

¿Está listo para iniciar su primera actividad [!UICONTROL Asignación automática]? [Aprenda cómo hacerlo aquí](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

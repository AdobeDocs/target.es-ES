---
keywords: asignación de tráfico automatizada;segmentación;asignación automática;asignación automática
description: Descubra cómo una actividad de [!UICONTROL Auto Allocate] en  [!DNL Adobe Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico.
title: ¿Pueden las actividades de [!UICONTROL Auto-Allocate] obtener resultados más rápidos e ingresos más altos?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate] le proporciona resultados de prueba más rápidos así como mayores ingresos que una prueba manual

Con una actividad A/B manual, es posible que pierda conversiones porque no puede ofrecer la experiencia ganadora a toda la audiencia hasta que se complete la actividad. La distribución del tráfico permanece fija incluso después de reconocer que algunas experiencias se comportan mejor que otras y de que la actividad debe ejecutar su curso completo antes de poder actuar sobre un ganador.

## Asignación automática del tráfico

Si desea que una opción presente la experiencia ganadora con más frecuencia y en una fase anterior de la actividad, al mismo tiempo que elimina o reduce el costo de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos, [!UICONTROL Auto-Allocate] es la mejor opción.

## ¿Cómo funciona [!UICONTROL Auto-Allocate]?

[!UICONTROL Auto-Allocate] usa el principio de multi-armed bandit. Si el término no es familiar, un bandido de un solo brazo es un término coloquial para una máquina tragaperras (piense: Las Vegas). Visualice la asignación automática del tráfico como si tuviera varias máquinas tragaperras, en este caso, pruebe las variaciones y, al principio, extraiga todos los controladores de la misma manera. Con el tiempo, una o más máquinas, o las variaciones de las pruebas, podrían pagar más que otras. Cuando esta situación sucede, un jugador naturalmente empezaría a tirar de las manos de los que ganan más a menudo. En términos de asignación de tráfico, [!DNL Target] proporciona a más visitantes la experiencia o experiencias que están ganando más.

Consideremos la siguiente ilustración de una actividad A/B de dos semanas. Con [!UICONTROL Auto-Allocate], a medida que surge una experiencia ganadora, [!UICONTROL Target] desvía más tráfico hacia ese ganador en las primeras etapas de la prueba.

![Ilustración de asignación automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿Cómo proporciona [!UICONTROL Auto-Allocate] resultados más rápidos?

El lado positivo es claro: cada vez más visitantes ven las variaciones que funcionan mejor. Y a medida que una sola variación avanza, aún más visitantes se desvían a esa experiencia ganadora, mientras la prueba seguía ejecutándose. Este método es especialmente útil si la actividad A/B que se está ejecutando se produce durante un momento empresarial clave, como un día festivo, el lanzamiento de un producto o un evento de noticias internacionales.

## ¿Cómo puede [!UICONTROL Auto-Allocate] proporcionar mayores ingresos?

[!UICONTROL Auto-Allocate] encuentra el ganador más rápido que una división A/B manual, y también le permite aprovecharlo de inmediato para capturar ingresos al alza que se habrían perdido según un enfoque tradicional o manual. Dado que [!UICONTROL Auto-Allocate] dirige más tráfico a la experiencia con la tasa de conversión más alta, puede aumentar los ingresos mientras la actividad se ejecuta y aprende.

En el ejemplo siguiente, [!UICONTROL Auto-Allocate] obtuvo más ingresos durante la prueba al insertar más tráfico (40 %) en la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo atenerme a la asignación manual del tráfico?

Cuando debe ordenar por orden de clasificación el rendimiento de cada experiencia en relación con las demás, lo más aplicable es una prueba A/B manual. [!UICONTROL Auto-Allocate] encuentra y explota a los ejecutantes de mayor rendimiento, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Utilice la asignación de tráfico manual para controlar por completo qué parte del tráfico de visitantes ve cada variante de prueba y para personalizar los umbrales estadísticos que son relevantes para su negocio.

## Introducción

¿Está listo para iniciar su primera actividad [!UICONTROL Auto-Allocate]? [Aprenda a hacerlo aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

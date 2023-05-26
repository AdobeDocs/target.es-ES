---
keywords: asignación de tráfico automatizada;segmentación;asignación automática;asignación automática
description: Descubra cómo funciona una actividad de asignación automática en Adobe [!DNL Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico.
title: ¿Pueden las actividades de asignación automática obtener resultados más rápidos e ingresos más altos?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 2%

---

# La asignación automática puede proporcionar resultados de prueba con mayor rapidez, así como mayores ingresos que las pruebas manuales

Con una actividad A/B manual, es posible que esté perdiendo conversiones porque no puede ofrecer la experiencia ganadora a toda la audiencia hasta que se complete la actividad. La distribución del tráfico permanece fija incluso después de reconocer que algunas experiencias se comportan mejor que otras y de que la actividad debe ejecutar su curso completo antes de poder actuar sobre un ganador.

## Asignación automática del tráfico

Si desea una opción para ofrecer la experiencia ganadora con mayor frecuencia y de forma más temprana en la actividad, eliminando o reduciendo simultáneamente el coste de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos, [!UICONTROL Asignación automática] es tu mejor opción.

## ¿Cómo funciona la asignación automática?

[!UICONTROL Asignación automática] utiliza el principio del bandido multiarmado. Si el término no es familiar, un bandido de un solo brazo es un término coloquial para una máquina tragaperras (piense: Las Vegas). Visualice la asignación automática del tráfico como si tuviera varias máquinas tragaperras, en este caso, pruebe las variaciones y, al principio, extraiga todos los controladores de la misma manera. Con el tiempo, una o más máquinas, o las variaciones de las pruebas, podrían pagar más que otras. Cuando esto sucede, un jugador naturalmente empezaría a tirar de las manijas de los que ganan más a menudo. En términos de asignación de tráfico, [!DNL Adobe Target] proporcionará a más visitantes la experiencia o experiencias que están ganando más.

Consideremos la siguiente ilustración de una actividad A/B de dos semanas. Con [!UICONTROL Asignación automática], a medida que surge una experiencia ganadora, [!UICONTROL Target] desvía más tráfico a ese ganador al principio de la prueba.

![Ilustración de asignación automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿Cómo me permite la asignación automática obtener resultados más rápidos?

El lado positivo es bastante claro: más visitantes ven las variaciones que funcionan mejor. Y a medida que una sola variación avanza, aún más visitantes se desvían a esa experiencia ganadora, mientras la prueba seguía ejecutándose. Esto resulta especialmente útil si la actividad A/B que se está ejecutando se produce durante un momento empresarial clave, como un día festivo, el lanzamiento de un producto o un evento de noticias internacionales.

## ¿Cómo podría la asignación automática darme mayores ingresos?

[!UICONTROL Asignación automática] encuentra el ganador más rápido que una división A/B manual, y también le permite aprovecharlo inmediatamente para capturar ingresos al alza que se habrían perdido con un enfoque tradicional o manual. Porque [!UICONTROL Asignación automática] dirige más tráfico a la experiencia con la tasa de conversión más alta, puede aumentar los ingresos mientras la actividad se ejecuta y aprende.

En el ejemplo siguiente, [!UICONTROL Asignación automática] obtuvo más ingresos durante la prueba al transferir más tráfico (40 %) a la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo atenerme a la asignación manual del tráfico?

Cuando necesite ordenar por orden de clasificación el rendimiento de cada experiencia en relación con las demás, lo más adecuado es una prueba A/B manual. [!UICONTROL Asignación automática] encuentra y explota a los mejores ejecutantes, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Debe utilizar la asignación de tráfico manual para controlar por completo qué parte del tráfico de visitantes ve cada variante de prueba y para personalizar los umbrales estadísticos que son relevantes para su negocio.

## Introducción

Listo para lanzar su primer [!UICONTROL Asignación automática] actividad? [Descubra cómo aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

---
keywords: asignación de tráfico automatizada;segmentación;asignación automática;asignación automática
description: Descubra cómo una actividad de [!UICONTROL Asignación automática] en [!DNL Adobe Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico.
title: ¿Pueden las actividades de [!UICONTROL Asignación automática] obtener resultados más rápidos e ingresos más altos?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 0%

---

# [!UICONTROL Asignación automática] le proporciona resultados de prueba más rápidos y mayores ingresos que una prueba manual

Con una actividad A/B manual, es posible que pierda conversiones porque no puede ofrecer la experiencia ganadora a toda la audiencia hasta que se complete la actividad. La distribución del tráfico permanece fija incluso después de reconocer que algunas experiencias se comportan mejor que otras y de que la actividad debe ejecutar su curso completo antes de poder actuar sobre un ganador.

## Asignación automática del tráfico

Si desea una opción que ofrezca la experiencia ganadora con más frecuencia y en etapas anteriores de la actividad, al mismo tiempo que elimina o reduce el costo de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos, [!UICONTROL Asignación automática] es la mejor opción.

## ¿Cómo funciona [!UICONTROL Asignación automática]?

[!UICONTROL Asignación automática] usa el principio del bandido multibrazo. Si el término no es familiar, un bandido de un solo brazo es un término coloquial para una máquina tragaperras (piense: Las Vegas). Visualice la asignación automática del tráfico como si tuviera varias máquinas tragaperras, en este caso, pruebe las variaciones y, al principio, extraiga todos los controladores de la misma manera. Con el tiempo, una o más máquinas, o las variaciones de las pruebas, podrían pagar más que otras. Cuando esta situación sucede, un jugador naturalmente empezaría a tirar de las manos de los que ganan más a menudo. En términos de asignación de tráfico, [!DNL Target] proporciona a más visitantes la experiencia o experiencias que están ganando más.

Consideremos la siguiente ilustración de una actividad A/B de dos semanas. Con la asignación automática [!UICONTROL Auto-Allocate], a medida que surge una experiencia ganadora, [!UICONTROL Target] desvía más tráfico hacia ese ganador al principio de la prueba.

![Ilustración de asignación automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿Cómo proporciona [!UICONTROL Asignación automática] resultados más rápidos?

El lado positivo es claro: cada vez más visitantes ven las variaciones que funcionan mejor. Y a medida que una sola variación avanza, aún más visitantes se desvían a esa experiencia ganadora, mientras la prueba seguía ejecutándose. Este método es especialmente útil si la actividad A/B que se está ejecutando se produce durante un momento empresarial clave, como un día festivo, el lanzamiento de un producto o un evento de noticias internacionales.

## ¿Cómo puede [!UICONTROL Asignación automática] proporcionar mayores ingresos?

[!UICONTROL Asignación automática] encuentra el ganador más rápido que una división A/B manual, y también le permite aprovecharlo de inmediato para capturar ingresos al alza que se habrían perdido en un enfoque tradicional o manual. Dado que [!UICONTROL Asignación automática] dirige más tráfico a la experiencia con la tasa de conversión más alta, puede aumentar los ingresos mientras la actividad se ejecuta y aprende.

En el ejemplo siguiente, [!UICONTROL Asignación automática] obtuvo más ingresos durante la prueba al transferir más tráfico (40 %) a la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo atenerme a la asignación manual del tráfico?

Cuando debe ordenar por orden de clasificación el rendimiento de cada experiencia en relación con las demás, lo más aplicable es una prueba A/B manual. [!UICONTROL Asignación automática] busca y explota a los ejecutantes de mayor rendimiento, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Utilice la asignación de tráfico manual para controlar por completo qué parte del tráfico de visitantes ve cada variante de prueba y para personalizar los umbrales estadísticos que son relevantes para su negocio.

## Introducción

¿Listo para lanzar tu primera actividad [!UICONTROL Asignación automática]? [Aprenda a hacerlo aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

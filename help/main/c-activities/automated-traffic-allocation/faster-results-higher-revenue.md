---
keywords: asignación de tráfico automatizada;segmentación;asignación automática;asignación automática
description: Descubra cómo una actividad [!UICONTROL Asignación automática] en [!DNL Adobe Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico.
title: ¿Pueden las actividades de [!UICONTROL Asignación automática] obtener resultados más rápidos e ingresos más altos?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: 'https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%
---
# Cómo [!UICONTROL Asignación automática] supera una prueba manual {#faster-results-higher-revenue}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda por qué una actividad de **[!UICONTROL Asignación automática]** puede ofrecer resultados más rápidos e ingresos más altos que una prueba A/B manual, cómo funciona y cuándo la asignación de tráfico manual sigue siendo la mejor opción.

>[!ENDSHADEBOX]

Con una actividad A/B manual, es posible que esté perdiendo conversiones porque no puede ofrecer la experiencia ganadora a toda la audiencia hasta que se complete la actividad. La distribución del tráfico permanece fija incluso después de reconocer que algunas experiencias se comportan mejor que otras y de que la actividad debe ejecutar su curso completo antes de poder actuar sobre un ganador.

## Asignación automática del tráfico {#auto-allocating-traffic}

**[!UICONTROL Asignación automática]** es la mejor opción si desea ofrecer la experiencia ganadora con más frecuencia y en etapas anteriores de la actividad, al mismo tiempo que elimina o reduce el costo de configuración y cálculo de la selección de tamaños de muestra, niveles de confianza y otros conceptos estadísticos.

## ¿Cómo funciona [!UICONTROL Asignación automática]? {#how-it-works}

**[!UICONTROL Asignación automática]** usa el principio del bandido multibrazo. Un bandido de un solo brazo es un término coloquial para una máquina tragaperras. Piense en la asignación automática del tráfico como un conjunto de máquinas tragamonedas, en este caso variaciones de prueba, cuyos controladores se tiran por igual al principio. Con el tiempo, una o más máquinas, o las variaciones de las pruebas, podrían pagar más que otras. Cuando esto sucede, un jugador comienza a tirar de las manijas de las máquinas que ganan con más frecuencia. En términos de asignación de tráfico, [!DNL Target] proporciona a más visitantes la experiencia o experiencias que están ganando más.

La siguiente ilustración muestra una actividad A/B de dos semanas. Con la asignación automática **[!UICONTROL Auto-Allocate]**, a medida que surge una experiencia ganadora, [!DNL Target] desvía más tráfico hacia ese ganador al principio de la prueba.

![Ilustración de asignación automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## ¿Cómo proporciona [!UICONTROL Asignación automática] resultados más rápidos? {#faster-results}

Más visitantes ven las variaciones que funcionan mejor. A medida que una sola variación avanza, aún más visitantes se desvían a esa experiencia ganadora mientras la prueba sigue ejecutándose. Este método es especialmente útil si la actividad A/B se ejecuta durante un momento empresarial clave, como un día festivo, un lanzamiento de producto o un evento de noticias internacionales.

## ¿Cómo puede [!UICONTROL Asignación automática] proporcionar mayores ingresos? {#higher-revenue}

**[!UICONTROL Asignación automática]** encuentra el ganador más rápido que una división A/B manual y le permite aprovecharlo inmediatamente, capturando ingresos al alza que se habrían perdido en un enfoque tradicional o manual. **[!UICONTROL Asignación automática]** dirige más tráfico a la experiencia con la tasa de conversión más alta, de modo que puede aumentar los ingresos mientras la actividad se ejecuta y aprende.

En el ejemplo siguiente, **[!UICONTROL Asignación automática]** obtuvo más ingresos durante la prueba al transferir más tráfico (40 %) a la Experiencia D, que tenía la tasa de conversión más alta.

![La asignación automática proporciona una ilustración de ingresos más alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## ¿En qué casos debo atenerme a la asignación manual del tráfico? {#manual-allocation}

Una prueba A/B manual es la opción más adecuada cuando se debe ordenar por orden de clasificación el rendimiento de cada experiencia en relación con las demás. **[!UICONTROL Asignación automática]** busca y explota a los ejecutantes de mayor rendimiento, pero no garantiza la diferenciación entre las experiencias de menor rendimiento. Utilice la asignación de tráfico manual para controlar por completo qué parte del tráfico de visitantes ve cada variante de prueba y para personalizar los umbrales estadísticos que son relevantes para su negocio.

## Introducción {#get-started}

¿Listo para lanzar tu primera actividad **[!UICONTROL Asignación automática]**? Consulte [Crear una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y la [descripción general de asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
